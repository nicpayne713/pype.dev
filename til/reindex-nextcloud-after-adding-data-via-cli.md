---
cover: ''
date: 2022-05-29
datetime: 2022-05-29 00:00:00+00:00
description: 'I wrote  Because I had a ton of photos on the NAS anyways that I wanted
  moved over to As www-data I needed to '
edit_link: https://github.com/edit/main/pages/til/reindex-nextcloud-after-adding-data-via-cli.md
jinja: false
long_description: 'I wrote  Because I had a ton of photos on the NAS anyways that
  I wanted moved over to As www-data I needed to '
now: 2022-06-25 12:28:31.767942
path: pages/til/reindex-nextcloud-after-adding-data-via-cli.md
slug: til/reindex-nextcloud-after-adding-data-via-cli
status: published
tags:
- homelab
- linux
templateKey: til
title: Reindex Nextcloud After Adding Data via CLI
today: 2022-06-25
year: 2022
---

# My Nextcloud woes

I wrote [here]("nextcloud-permissions-with-zfs-and-ansible-nas") about setting
up `www-data` as the owner of any directories you want nextcloud to manage.
However, I regularly struggle wtih permissions issues on my NAS because of the
external storage app anyways so I've decided to just put our photos in the spot
Nextcloud would otherwise put them, and use this as healthy pressure on our
family to organize our photos and put the ones we care about with the rest of
our family media.

# Migration

Because I had a ton of photos on the NAS anyways that I wanted moved over to
Nextcloud I just rsync'd the photos directory on my NAS to the user's photos
directory in nextcloud but they weren't showing up in the web UI!

# The Fix?

As www-data I needed to `php /var/www/nextcloud/occ files:scan --all` inside my
nextcloud docker container AFTER moving a bunch of photos off my "NAS" into the
folder mounted to the nextcloud container as its data folder! Before I did this
they weren't showing up in the web UI/