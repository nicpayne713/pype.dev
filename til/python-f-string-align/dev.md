---
canonical_url: https://pype.dev/til/python-f-string-align/
cover_image: /static/images/til/python-f-string-align.png
description: 'I am personally trying to use  This little python script shows how options
  in the '
published: true
tags:
- python
title: Python-F-String-Align
---

I am personally trying to use `logger` instead of `print` in all of my code,  however I learned from [@Python-Hub] that you can align printouts using `print` with `f`-strings!.

This little python script shows how options in the `f`-string can format the printout.

```python

import random

variables = "Foo Bar Baz Bing".split() scores = random.sample(range(1, 11), len(variables))

print("*" * 30) print("\n") print("With 'varable' left aligned") for varable, score in zip(variables, scores):
    print(f"{varable:<10} | {score}")

print("*" * 30) print("\n") print("With 'varable' right aligned") for varable, score in zip(variables, scores):
    print(f"{varable:>15} | {score}")

print("*" * 30) print("\n") print("With 'varable' center aligned") for varable, score in zip(variables, scores):
    print(f"{varable:^5} | {score}")

```




![Alt text](/images/py-print-align.png "python print")