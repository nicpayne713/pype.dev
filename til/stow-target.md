---
cover: /static/stow-target.png
date: 2022-03-04
datetime: 2022-03-04 00:00:00+00:00
description: Check out  What if I want to stow a package somewhere else? Maybe I don
edit_link: https://github.com/edit/main/pages/til/stow-target.md
jinja: false
long_description: Check out  What if I want to stow a package somewhere else? Maybe
  I don
now: 2022-06-25 12:28:31.768041
path: pages/til/stow-target.md
slug: til/stow-target
status: published
tags:
- bash
- linux
templateKey: til
title: Stow-Target
today: 2022-06-25
year: 2022
---

Check out [stow](/stow) for a brief introduction to `stow`

What if I want to stow a package somewhere else?
Boom, that's where `-t` comes in...

Maybe I don't like having my `dotfiles` repo at `$HOME` and instead I want it in `~/git` or `~/personal` just to stay organized...
Well then I could have the same workflow except the `stow` command looks like this:

```bash
stow zsh -t ~/
#or
stow zsh -t $HOME
```