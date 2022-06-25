---
cover: /static/vim-auto-space.png
date: 2022-03-04
datetime: 2022-03-04 00:00:00+00:00
description: 'I ran into an issue where I had some copy-pasta markdown tables in a
  docstring but the generator I used to make the table gave me tabs instead of spaces
  in odd '
edit_link: https://github.com/edit/main/pages/til/vim-auto-space.md
jinja: false
long_description: 'I ran into an issue where I had some copy-pasta markdown tables
  in a docstring but the generator I used to make the table gave me tabs instead of
  spaces in odd places which caused '
now: 2022-06-25 12:28:31.767990
path: pages/til/vim-auto-space.md
slug: til/vim-auto-space
status: published
tags:
- vim
templateKey: til
title: Vim-Auto-Space
today: 2022-06-25
year: 2022
---

I ran into an issue where I had some copy-pasta markdown tables in a docstring but the generator I used to make the table gave me tabs instead of spaces in odd places which caused `black` to throw a fit.
Instead of manually changing all tabs to spaes, or trying some goofy `:%s/<magic tab character>/<%20 maybe?>/g` I learned that Vim has my back...

```
:retab
```