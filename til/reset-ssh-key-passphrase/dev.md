---
canonical_url: https://pype.dev/til/reset-ssh-key-passphrase/
cover_image: /static/images/til/reset-ssh-key-passphrase.png
description: I got into a pickle where I encrypted the ssh keys I use for my SSH connections
  on LAN, but then I couldn ssh-keygen -p But I needed to remove the passphrase to
published: true
tags:
- homelab
- cli
title: Reset SSH key passphrase
---

I got into a pickle where I encrypted the ssh keys I use for my SSH connections on LAN, but then I couldn't run my ansible playbook on my server! ssh-keygen -p and leave the new passphrase blank saved my day (although password protected key files are safer!)

# TL;DR - just reset it to nothing

`ssh-keygen -p` will let you reset the passphrase on your ssh keys (good for you! yay security!)

But I needed to remove the passphrase to quickly deploy an ansible playbook 🤓