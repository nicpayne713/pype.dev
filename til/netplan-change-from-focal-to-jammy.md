---
cover: ''
date: 2022-05-22
datetime: 2022-05-22 00:00:00+00:00
description: I am revamping my home server and bumped myself early up to Jammy Jellyfish...
  Turns out Netplan got a little change in how to express the  Old Ubuntu 20.04 way
edit_link: https://github.com/edit/main/pages/til/netplan-change-from-focal-to-jammy.md
jinja: false
long_description: I am revamping my home server and bumped myself early up to Jammy
  Jellyfish... Turns out Netplan got a little change in how to express the  Old Ubuntu
  20.04 way New jammin way for Jammy Jellyfish (
now: 2022-06-25 12:28:31.768018
path: pages/til/netplan-change-from-focal-to-jammy.md
slug: til/netplan-change-from-focal-to-jammy
status: published
tags:
- homelab
- linux
templateKey: til
title: Netplan change from Focal to Jammy
today: 2022-06-25
year: 2022
---

I am revamping my home server and bumped myself early up to Jammy Jellyfish...
however to my peril I reused my netplan config and after hitting my server with
the 'ol `netplan apply` I lost connection...
DNS still seemed to kinda work externally, but internally nothing was up... 

Turns out Netplan got a little change in how to express the `gateway` key in the netplan config!

Old Ubuntu 20.04 way

```yaml
network:
  version: 2
  ethernets:
    enp0s4:
      addresses: [192.168.1.{Static IP}/24]
      gateway4: 192.168.1.1  # <-- This changes!
      nameservers:
        addresses: [192.168.1.1, 1.1.1.1]
```

New jammin way for Jammy Jellyfish (__at least that worked for me__)
```yaml
network:
  version: 2
  ethernets:
    enp0s4:
      addresses: [192.168.1.{Static IP}/24]
      routes:
        - to: default
          via: 192.168.1.1 
      nameservers:
        addresses: [192.168.1.1, 1.1.1.1]
```