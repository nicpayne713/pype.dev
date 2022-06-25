---
cover: /static/abstract-base-class.png
date: 2022-03-09
datetime: 2022-03-09 00:00:00+00:00
description: I don If you are creating a library with classes that you expect your
  users to extend, but you want to ensure that any extension has explicit methods
  defined th
edit_link: https://github.com/edit/main/pages/til/abstract-base-class.md
jinja: false
long_description: I don If you are creating a library with classes that you expect
  your users to extend, but you want to ensure that any extension has explicit methods
  defined then this is for you If I try to instantiate  In order for me to extend  Now
  everything work
now: 2022-06-25 12:28:31.768214
path: pages/til/abstract-base-class.md
slug: til/abstract-base-class
status: published
tags:
- python
templateKey: til
title: Abstract-Base-Class
today: 2022-06-25
year: 2022
---

## ABCMeta

I don't do a lot of OOP currently, but I have been on a few heavy OOP projects and this `ABCMeta` and `abstractmethod` from `abc` would've been super nice to know about!

If you are creating a library with classes that you expect your users to extend, but you want to ensure that any extension has explicit methods defined then this is for you!.

```python
from abc import ABCMeta, abstractmethod
class Family(metaclass=ABCMeta):
    @abstractmethod
    def get_dad(self):
        """Any extension of the Family class must implement a `get_dad` method"""

class MyFamily(Family):
    pass

```

If I try to instantiate `MyFamily` I will not be allowed:
```python

❯ my_fam = MyFamily()
╭─────────────────────────────── Traceback (most recent call last) ────────────────────────────────╮
│ <ipython-input-8-ecb8e21ce815>:1 in <module>                                                     │
╰──────────────────────────────────────────────────────────────────────────────────────────────────╯
TypeError: Can't instantiate abstract class MyFamily with abstract methods get_dad

```

![Alt text](/images/py-abc-meta.png "abcmeta")

In order for me to extend `Family` I have to implement the method `get_dad`

```python
class MyFamily(Family):
    def get_dad(self):
        return "Me"
```

Now everything works as expected and I can sleep well knowing no one can extend my base class without creating methods I know they need.


```python

my_fam = MyFamily()

my_fam.get_dad()
'Me'

```