---
cover: /static/git-ammend-no-edit.png
date: 2022-03-04
datetime: 2022-03-04 00:00:00+00:00
description: After carefully staging only lines related to a specific change and comitting
  I suddenly realized I missed one... darn, what do I do? Old me would have soft res
edit_link: https://github.com/edit/main/pages/til/git-ammend-no-edit.md
jinja: false
long_description: After carefully staging only lines related to a specific change
  and comitting I suddenly realized I missed one... darn, what do I do? Old me would
  have soft reset my branch to the previous commit and redone all my careful staging...
  what a PIA... New
now: 2022-06-25 12:28:31.768138
path: pages/til/git-ammend-no-edit.md
slug: til/git-ammend-no-edit
status: published
tags:
- git
templateKey: til
title: Git ammend to a commit
today: 2022-06-25
year: 2022
---

After carefully staging only lines related to a specific change and comitting I suddenly realized I missed one... darn, what do I do?

Old me would have soft reset my branch to the previous commit and redone all my careful staging... what a PIA...

New me (credit: ThePrimeagen)...

```bash
# stage other changes I missed
git commit --amend --no-edit
```