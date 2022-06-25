---
cover: /static/wireguard.png
date: 2022-03-12
datetime: 2022-03-12 00:00:00+00:00
description: Virtual Private Networks are a big deal, and this shouldn Wireguard is
  an awesome peer-to-peer VPN tunnel that makes it really easy for me to get into
  my home n
edit_link: https://github.com/edit/main/pages/blog/wireguard.md
jinja: false
long_description: Virtual Private Networks are a big deal, and this shouldn Wireguard
  is an awesome peer-to-peer VPN tunnel that makes it really easy for me to get into
  my home network when I Wireguard can be configured as a  I use  The reason I like
  it is that I have
now: 2022-06-25 12:28:31.767872
path: pages/blog/wireguard.md
slug: wireguard
status: published
tags:
- meta
- homelab
templateKey: blog-post
title: Wireguard
today: 2022-06-25
year: 2022
---

## VPN

Virtual Private Networks are a big deal, and this shouldn't be considered anything even close to a guide on using them.
Here are just my notes and some setup for how I use [wireguard](https://www.wireguard.com/) at home.

## Wireguard

Wireguard is an awesome peer-to-peer VPN tunnel that makes it really easy for me to get into my home network when I'm out and about.
My main reasons for this are 1. I don't trust public wi-fi and 2. I want to use pi-hole for ad blocking when I'm not at home

Wireguard can be configured as a "peer-to-site" VPN tunnel as well.
My vpn setup let's me jump to various machines on my network from anywhere!

I use [pivpn](https://pivpn.io/) in a VM that's already running `pi-hole` to host my wireguard server.
It's super easy to setup just by following the instructions on the pivpn site.

The reason I like it is that I have a nice `cli` for managing wireguard configs.

```bash
dumbledore@pihole-vpn:~$ pivpn
::: Control all PiVPN specific functions!
:::
::: Usage: pivpn <command> [option]
:::
::: Commands:
:::    -a, add              Create a client conf profile
:::    -c, clients          List any connected clients to the server
:::    -d, debug            Start a debugging session if having trouble
:::    -l, list             List all clients
:::   -qr, qrcode           Show the qrcode of a client for use with the mobile app
:::    -r, remove           Remove a client
:::  -off, off              Disable a user
:::   -on, on               Enable a user
:::    -h, help             Show this help dialog
:::    -u, uninstall        Uninstall pivpn from your system!
:::   -up, update           Updates PiVPN Scripts
:::   -bk, backup           Backup VPN configs and user profiles
```


When I'm ready to add a new client to my `wg` network, it's as easy as `pivpn add` and follow the instructions.
The easiest part here is that you'll be given a QR code in the terminal that you can just scan with the client (like a smart phone) and you'll have your wireguard config handled by the app (oh right, download the wireguard app) in no time!