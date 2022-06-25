---
cover: ''
date: 2022-06-13
datetime: 2022-06-13 00:00:00+00:00
description: I got into a pickle where I encrypted the ssh keys I use for my SSH connections
  on LAN, but then I couldn ssh-keygen -p But I needed to remove the passphrase to
edit_link: https://github.com/edit/main/pages/til/reset-ssh-key-passphrase.md
jinja: false
long_description: "I got into a pickle where I encrypted the ssh keys I use for my
  SSH connections on LAN, but then I couldn ssh-keygen -p But I needed to remove the
  passphrase to quickly deploy an ansible playbook \U0001F913"
now: 2022-06-25 12:28:31.768200
path: pages/til/reset-ssh-key-passphrase.md
slug: til/reset-ssh-key-passphrase
status: published
tags:
- homelab
- cli
templateKey: til
title: Reset SSH key passphrase
today: 2022-06-25
year: 2022
---

I got into a pickle where I encrypted the ssh keys I use for my SSH connections on LAN, but then I couldn't run my ansible playbook on my server! ssh-keygen -p and leave the new passphrase blank saved my day (although password protected key files are safer!)

# TL;DR - just reset it to nothing

`ssh-keygen -p` will let you reset the passphrase on your ssh keys (good for you! yay security!)

But I needed to remove the passphrase to quickly deploy an ansible playbook 🤓