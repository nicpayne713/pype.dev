---
cover: /static/stow.png
date: 2022-03-04
datetime: 2022-03-04 00:00:00+00:00
description: 'Stow is a great tool for managing dotfiles. My usage looks like cloning
  my dotfiles to my home directory, setting some environment variables via a script,
  then '
edit_link: https://github.com/edit/main/pages/til/stow.md
jinja: false
long_description: Stow is a great tool for managing dotfiles. My usage looks like
  cloning my dotfiles to my home directory, setting some environment variables via
  a script, then stowing relevant packages and boom my config is good to go... By
  default stow will stow pa
now: 2022-06-25 12:28:31.767976
path: pages/til/stow.md
slug: til/stow
status: published
tags:
- bash
- linux
templateKey: til
title: Stow
today: 2022-06-25
year: 2022
---

Stow is a great tool for managing dotfiles. My usage looks like cloning my dotfiles to my home directory, setting some environment variables via a script, then stowing relevant packages and boom my config is good to go...

```bash
cd ~
git clone <my dotfiles repo>
cd dotfiles
# env variable stuff ignored here
stow zsh  # This will symlink my .zshrc file which is in ~/dotfiles/zsh to ~/.zshrc
```
By default stow will stow packages up one directory from the root directory. 
In this example the root directory is `~/dotfiles` and the package is `zsh`.
So the files in the `zsh` package will symlinked into `~/`.

`stow` makes it easy to share dotfiles across machines, or safely experiment with config changes while always being protected by `git` since your dotfiles are in a git repo!
...They are in a git repo... right?