---
cover: /static/skimpy.png
date: 2022-03-23
datetime: 2022-03-23 00:00:00+00:00
description: I work with data a lot, but the nature of my job isn When I However,
  Visidata is a terminal based application and I First thing to do is  This is super
  nice for
edit_link: https://github.com/edit/main/pages/til/skimpy.md
jinja: false
long_description: I work with data a lot, but the nature of my job isn When I However,
  Visidata is a terminal based application and I First thing to do is  This is super
  nice for seeing missing values in particular as well as the distribution shape of
  the data. But wa
now: 2022-06-25 12:28:31.768151
path: pages/til/skimpy.md
slug: til/skimpy
status: published
tags:
- python
templateKey: til
title: Skimpy
today: 2022-06-25
year: 2022
---

## EDA

I work with data a lot, but the nature of my job isn't to dive super deep into a small amount of datasets,
I'm often jumping between several projects every day and need to just get a super quick glance at some tables to get a high level view.

When I'm doing more interactive exploration I've graduated from Jupyter cells with `df_N.head()` to using an amazing tool called [visidata](https://www.visidata.org/)

However, Visidata is a terminal based application and I'm often in an iPython console... so is there a way to move even faster for my super quick summary views?

__yes!__ 

## Skimpy

First thing to do is `pip install skimpy` and then it's as easy to get some summary stats with `skimpy <data>`

![Alt Text](/images/skimpy-zsh.png "skimpy-zsh")

This is super nice for seeing missing values in particular as well as the distribution shape of the data.

## iPython

But wait... I just said I'm normally in an iPython session but that was called from zsh.. If I'm hoping back into zsh I might as well use visidata to have more powerful exploration at my fingertips.
So... can I see this table quickly without breaking my iPython workflow?

__Of course you can with magic!__


![Alt Text](/images/skimpy-ipython.png "skimpy-ipython")


The above assumes you're looking at a file, like you would in the terminal. 
`skimpy` works even better in iPython with `from skimpy import skim` then pass any DataFrame to `skim`!

![Alt Text](/images/skimpy-ipython2.png "skimpy-ipython2")