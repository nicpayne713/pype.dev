---
cover: /static/python-f-string-align.png
date: 2022-03-08
datetime: 2022-03-08 00:00:00+00:00
description: 'I am personally trying to use  This little python script shows how options
  in the '
edit_link: https://github.com/edit/main/pages/til/python-f-string-align.md
jinja: false
long_description: 'I am personally trying to use  This little python script shows
  how options in the '
now: 2022-06-25 12:28:31.768173
path: pages/til/python-f-string-align.md
slug: til/python-f-string-align
status: published
tags:
- python
templateKey: til
title: Python-F-String-Align
today: 2022-06-25
year: 2022
---

I am personally trying to use `logger` instead of `print` in all of my code, 
however I learned from [@Python-Hub] that you can align printouts using `print` with `f`-strings!.

This little python script shows how options in the `f`-string can format the printout.

```python

import random

variables = "Foo Bar Baz Bing".split()
scores = random.sample(range(1, 11), len(variables))

print("*" * 30)
print("\n")
print("With 'varable' left aligned")
for varable, score in zip(variables, scores):
    print(f"{varable:<10} | {score}")

print("*" * 30)
print("\n")
print("With 'varable' right aligned")
for varable, score in zip(variables, scores):
    print(f"{varable:>15} | {score}")

print("*" * 30)
print("\n")
print("With 'varable' center aligned")
for varable, score in zip(variables, scores):
    print(f"{varable:^5} | {score}")

```




![Alt text](/images/py-print-align.png "python print")