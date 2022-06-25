---
canonical_url: https://pype.dev/til/vim-auto-space/
cover_image: /static/images/til/vim-auto-space.png
description: 'I ran into an issue where I had some copy-pasta markdown tables in a
  docstring but the generator I used to make the table gave me tabs instead of spaces
  in odd '
published: true
tags:
- vim
title: Vim-Auto-Space
---

I ran into an issue where I had some copy-pasta markdown tables in a docstring but the generator I used to make the table gave me tabs instead of spaces in odd places which caused `black` to throw a fit. Instead of manually changing all tabs to spaes, or trying some goofy `:%s/<magic tab character>/<%20 maybe?>/g` I learned that Vim has my back...

```
:retab
```