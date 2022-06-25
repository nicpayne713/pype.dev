---
cover: /static/ubuntu-static-ip.png
date: 2022-03-03
datetime: 2022-03-03 00:00:00+00:00
description: 'Sometimes I need to manually set a static IP of a Linux machine. I generally
  run the latest version of Ubuntu server in my VMs at home. In Ubuntu 20 I gateway4 '
edit_link: https://github.com/edit/main/pages/til/ubuntu-static-ip.md
jinja: false
long_description: 'Sometimes I need to manually set a static IP of a Linux machine.
  I generally run the latest version of Ubuntu server in my VMs at home. In Ubuntu
  20 I gateway4 Hit it with the '
now: 2022-06-25 12:28:31.768048
path: pages/til/ubuntu-static-ip.md
slug: til/ubuntu-static-ip
status: published
tags:
- linux
templateKey: til
title: Ubuntu-Static-Ip
today: 2022-06-25
year: 2022
---

Sometimes I need to manually set a static IP of a Linux machine. I generally run the latest version of Ubuntu server in my VMs at home.

In Ubuntu 20 I'm able to change up `/etc/netplan/<something>.yml`

```yaml
network:
  version: 2
  ethernets:
    enp0s4:
      addresses: [192.168.1.{Static IP}/24]
      gateway4: 192.168.1.1
      nameservers:
        addresses: [192.168.1.1, 1.1.1.1]
```

`gateway4` is your router address
`nameservers` is a list of desired DNS servers for that machine to use. I  usually use my router which is configured to use my pi-hole as my primary DNS, then set  `1.1.1.1` (CloudFlare) as a backup

Hit it with the `sudo netplan apply` and you should be good to go!