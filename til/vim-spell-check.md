---
cover: /static/vim-spell-check.png
date: 2022-04-01
datetime: 2022-04-01 00:00:00+00:00
description: 'set: spell spelllang=en_us Sometimes there Common example: package names
  plotly You can easily add these to your vim config by hitting '
edit_link: https://github.com/edit/main/pages/til/vim-spell-check.md
jinja: false
long_description: 'set: spell spelllang=en_us Sometimes there Common example: package
  names plotly You can easily add these to your vim config by hitting '
now: 2022-06-25 12:28:31.768054
path: pages/til/vim-spell-check.md
slug: til/vim-spell-check
status: published
tags:
- vim
templateKey: til
title: Vim-Spell-Check
today: 2022-06-25
year: 2022
---

__Did you know you can spell check in Vim?!__


<!DOCTYPE html>
<html>
   <head>
      <title>Vim Spell check</title>
   </head>

   <body>
      <h3>Without...</h3>
      <p>Here is a missspelled word.</p>

      <h3>With!</h3>
      <p>Here is a <u>missspelled</u> word.</p>

   </body>
</html>

## What is this magic???

`set: spell spelllang=en_us`


## Custom words?

Sometimes there's things that are words to you but not the default spell checker...

Common example: package names!

`plotly`, `streamlit`, `psutil`, etc etc...


You can easily add these to your vim config by hitting `zw` ontop of the word!