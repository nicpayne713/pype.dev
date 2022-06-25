---
cover: /static/jellyfin-media-players.png
date: 2022-04-17
datetime: 2022-04-17 00:00:00+00:00
description: I use Jellyfin at home for serving up most of our media - movies and
  shows etc. My dream is to have a GPU capable of transcoding any and all of our media
  for sm
edit_link: https://github.com/edit/main/pages/blog/jellyfin-media-players.md
jinja: false
long_description: I use Jellyfin at home for serving up most of our media - movies
  and shows etc. My dream is to have a GPU capable of transcoding any and all of our
  media for smooth playback on any device... What can I do to still use Jellyfin but
  get smooth playback
now: 2022-06-25 12:28:31.767893
path: pages/blog/jellyfin-media-players.md
slug: jellyfin-media-players
status: published
tags:
- homelab
templateKey: blog-post
title: Jellyfin-Media-Players
today: 2022-06-25
year: 2022
---

I use Jellyfin at home for serving up most of our media - movies and shows etc.

My dream is to have a GPU capable of transcoding any and all of our media for smooth playback on any device...
Now, I thought I'd have that by now with my Nvidia Quadro P400 however I have issues left and right with 4k content.

What can I do to still use Jellyfin but get smooth playback?

THe first answer is figure out why I suck with GPUs, but pausing that there's shorter solutions -> namely, use a media player that's compatabile with the encoded content!

## VLC

I'll keep this one short - VLC is great and if you don't need a netflix like experience, I'd recommend just using it to browse your network drives and play whatever you have

## Jellyfin Web Player

This is the reason I'm writing this post... the web player is great but not everything is supported on all devices

## Jellyfin MPV Shim

This cross-platform cast client is my answer now.
You can find the project [here](https://github.com/jellyfin/jellyfin-mpv-shim/blob/master/README.md#linux-installation)

The installation instrauctions are super straightforward for Windows, Mac OS, or Linux.

I'm on Linux and so my install went like this:

```bash

sudo apt update
sudo apt install mpv 

pipx install jellyfin-mpv-shim
pipx inject jellyfin-mpv-shim pystray

#profit

```

I used `pipx` to install the player as I prefer it for stand alone utilities over pip installing anything globally.

Afer that I just start the player at the terminal with `jellyfin-mpv-shim`
Then in the web browser I can cast my content to the player and bypass the web player (and thus solve much of my transcoding issues) trivially!