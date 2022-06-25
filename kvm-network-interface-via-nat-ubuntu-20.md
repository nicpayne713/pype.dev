---
cover: ''
date: 2022-06-25
datetime: 2022-06-25 00:00:00+00:00
description: 'I have started using VMs more and more in my development workflow and
  it First thing There was a  These commands got me up and running without even turning
  the '
edit_link: https://github.com/edit/main/pages/blog/kvm-network-interface-via-nat-ubuntu-20.md
jinja: false
long_description: I have started using VMs more and more in my development workflow
  and it First thing There was a  These commands got me up and running without even
  turning the VM off I went full on  I was unsure what the ip range should be so I
  just stuck with the o
now: 2022-06-25 12:28:31.767900
path: pages/blog/kvm-network-interface-via-nat-ubuntu-20.md
slug: kvm-network-interface-via-nat-ubuntu-20
status: published
tags:
- homelab
- linux
templateKey: blog-post
title: kvm-network-interface-via-nat-ubuntu-20
today: 2022-06-25
year: 2022
---

I have started using VMs more and more in my development workflow and it's
impossible to work in a VM without an internet connection for me most of the
time. Setting up the KVM networking is kind of confusing to me and I've done it
two different ways. Here is how I set it up on my home desktop using NAT.

# Credit

First thing's first: [credit to this post](https://computingforgeeks.com/managing-kvm-network-interfaces-in-linux/)

# Commands

There was a `default` network already made by virt-manager but my VM couldn't connect over it at all...

These commands got me up and running without even turning the VM off

> I went full on `sudo -i` for this just to make it easier - be careful

## Dump an existint network config

```bash
# as root

virsh net-dumpxml default > br1.xml

vim br1.xml

```

## Edit it

I was unsure what the ip range should be so I just stuck with the original blog. 
The `default` network had the CIDR block defined as `192.168.122.0/24` which is different from my home network so I guess it's fine?

```xml
<network>
  <name>br1</name>
  <forward mode='nat'>
    <nat>
      <port start='1024' end='65535'/>
    </nat>
  </forward>
  <bridge name='br1' stp='on' delay='0'/>
  <ip address='192.168.10.1' netmask='255.255.255.0'>
    <dhcp>
      <range start='192.168.10.10' end='192.168.10.100'/>
    </dhcp>
  </ip>
</network>
```

## Define a network

```bash
virsh net-define br1.xml
virsh net-autostart br1
```

Then to check...

```bash
virsh net-list --all

 Name      State    Autostart   Persistent
--------------------------------------------
 br1       active   yes         yes
 default   active   yes         yes
```

## UUID

`virsh net-uuid br1`


## Magic

`virsh attach-interface --domain <NAME OF VM> --type bridge --source br1 --model virtio --config --live`

My VM, `ubuntu20.04` was running and immediately connected to the newly attached device!


# Credit again

Visit the original post for more details - this serves more as as a quicker set of notes for future me