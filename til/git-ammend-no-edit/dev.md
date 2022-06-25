---
canonical_url: https://pype.dev/til/git-ammend-no-edit/
cover_image: /static/images/til/git-ammend-no-edit.png
description: After carefully staging only lines related to a specific change and comitting
  I suddenly realized I missed one... darn, what do I do? Old me would have soft res
published: true
tags:
- git
title: Git ammend to a commit
---

After carefully staging only lines related to a specific change and comitting I suddenly realized I missed one... darn, what do I do?

Old me would have soft reset my branch to the previous commit and redone all my careful staging... what a PIA...

New me (credit: ThePrimeagen)...

```bash
# stage other changes I missed
git commit --amend --no-edit
```