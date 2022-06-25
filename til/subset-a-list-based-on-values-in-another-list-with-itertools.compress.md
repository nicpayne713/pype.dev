---
cover: ''
date: 2022-05-19
datetime: 2022-05-19 00:00:00+00:00
description: 'I have list '
edit_link: https://github.com/edit/main/pages/til/subset-a-list-based-on-values-in-another-list-with-itertools.compress.md
jinja: false
long_description: 'I have list '
now: 2022-06-25 12:28:31.768075
path: pages/til/subset-a-list-based-on-values-in-another-list-with-itertools.compress.md
slug: til/subset-a-list-based-on-values-in-another-list-with-itertools.compress
status: published
tags:
- python
- python
templateKey: til
title: Subset a list based on values in another list with itertools.compress
today: 2022-06-25
year: 2022
---

I have list [True, False, False, True] and another list [1, 2, 3, 4] and a use case where I want to filter list 2 based on list 1 to remove values that line up with the element False in list 1.... so the outcome will be [1, 4]. list(compress(list2, list1)) will do it. As long as you can create a mask for the filter than itertool.compress will be your friend!