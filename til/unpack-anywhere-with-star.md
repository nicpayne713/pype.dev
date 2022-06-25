---
cover: /static/unpack-anywhere-with-star.png
date: 2022-04-24
datetime: 2022-04-24 00:00:00+00:00
description: Unpacking iterables in python with  But  I
edit_link: https://github.com/edit/main/pages/til/unpack-anywhere-with-star.md
jinja: false
long_description: Unpacking iterables in python with  But  I
now: 2022-06-25 12:28:31.767955
path: pages/til/unpack-anywhere-with-star.md
slug: til/unpack-anywhere-with-star
status: published
tags:
- python
templateKey: til
title: Unpack-Anywhere-With-Star
today: 2022-06-25
year: 2022
---

Unpacking iterables in python with `*` is a pretty handy trick for writing code that is just a tiny bit more pythonic than not.

```python
arr: Tuple[Union[int, str]] = (1, 2, 3, 'a', 'b', 'c')


print(arr)
>>> (1, 2, 3, 'a', 'b', 'c')

# the * unpacks the tuple into the individual elements
print(*arr)
>>> 1, 2, 3, 'a', 'b', 'c'

x, y, z, *alphas = arr

# x = 1, y = 2, z = 3
# alphas = [ 'a', 'b', 'c' ]

```

But [@Ned Batchelder](https://twitter.com/nedbat) showed me via Twitter than you can arbitrarily unpack arguments based on position - it doesn't have to be done at the beginning or the end!

```python
x, y, *mixed, alpha = arr

# x = 1, y = 2
# mixed = [3, 'a', 'b']
# alpha = 'c'
```

I'm not entirely sure when I'll need this but it definitley shows me another example of how flexible python is!