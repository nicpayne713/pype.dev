---
canonical_url: https://pype.dev/til/stow-target/
cover_image: /static/images/til/stow-target.png
description: Check out  What if I want to stow a package somewhere else? Maybe I don
published: true
tags:
- bash
- linux
title: Stow-Target
---

Check out [stow](/stow) for a brief introduction to `stow`

What if I want to stow a package somewhere else? Boom, that's where `-t` comes in...

Maybe I don't like having my `dotfiles` repo at `$HOME` and instead I want it in `~/git` or `~/personal` just to stay organized... Well then I could have the same workflow except the `stow` command looks like this:

```bash
stow zsh -t ~/
#or
stow zsh -t $HOME
```