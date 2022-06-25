---
cover: /static/file-length.png
date: 2022-04-04
datetime: 2022-04-04 00:00:00+00:00
description: 'I have a specific need for counting the number of lines in a file quickly.
  To get that list I run an internal tool like this: This simply parses our internal
  li'
edit_link: https://github.com/edit/main/pages/til/file-length.md
jinja: false
long_description: 'I have a specific need for counting the number of lines in a file
  quickly. To get that list I run an internal tool like this: This simply parses our
  internal linter for the lines releated to my s3 linter utility and pipes those lines
  to a file. To ge'
now: 2022-06-25 12:28:31.768096
path: pages/til/file-length.md
slug: til/file-length
status: published
tags:
- linux
templateKey: til
title: File-Length
today: 2022-06-25
year: 2022
---

I have a specific need for counting the number of lines in a file quickly.
At work we use S3 for data storage during our Kedro pipeline development, and in the development process we may end up orphaning several datasets.
In order to keep our workspace clean I have a short utility that compares the datasets in a Kedro DataCatalog with the files in the relevant S3 location.

To get that list I run an internal tool like this:

```bash
kedro our-liter | grep s3 >> orphaned_datasets.txt
```

This simply parses our internal linter for the lines releated to my s3 linter utility and pipes those lines to a file.

To get a quick idea of how out of wack a pipeline is I could open the text file in vim, git it with the `G` and see what line number I'm on but I'm way too lazy for that...

## AWK

`awk 'END {print NR}' orphaned_datasets.txt` gives me the number of lines and I can alias this to whatever feels appropriate in my `zshrc`!

__built-ins for the win!__