---
cover: ''
date: 2022-05-19
datetime: 2022-05-19 00:00:00+00:00
description: As the nextcloud docs say... if you want to write to an external volume
  that You want to self-host your own cloud and use a smart file system for convenience...
edit_link: https://github.com/edit/main/pages/til/nextcloud-permissions-with-zfs-and-ansible-nas.md
jinja: false
long_description: As the nextcloud docs say... if you want to write to an external
  volume that You want to self-host your own cloud and use a smart file system for
  convenience... My home NAS is built on ZFS and among other things I have a  I want
  to use nextcloud main
now: 2022-06-25 12:28:31.768158
path: pages/til/nextcloud-permissions-with-zfs-and-ansible-nas.md
slug: til/nextcloud-permissions-with-zfs-and-ansible-nas
status: published
tags:
- homelab
- zfs
templateKey: til
title: Nextcloud permissions with ZFS and Ansible-NAS
today: 2022-06-25
year: 2022
---

# TL;DR

As the nextcloud docs say... if you want to write to an external volume that
location has to be writeable by the user/group `www-data` on the host system...
so if that makes sense to you then this TIL probably isn't a ton of value.. if
not however, read on :)



# Case Study

You want to self-host your own cloud and use a smart file system for convenience...
Nextcloud and ZFS are pretty common goto answers for each of those problems.

My home NAS is built on ZFS and among other things I have a `zpool` named
`tank` and nested in there is a `tank/nas` dataset with several child zfs
datasets under that.

I want to use nextcloud mainly for auto-uploading photos from my wife's and my phones for automatic backups.
The issue is that the nextcloud application (I run in Docker) is fixed as the
`www-data` user and so any volume/folder that you want nextcloud to write to
needs to be permissioned such that `www-data` owns it... but I don't want
`www-data` to own everything in my NAS... so what's a girl to do?

# Solution

Well, one way to go is to just utilize docker volumes, write the data in the
container to `/var/www/html` and let that be the place your data backsup to.

I still wanted nextcloud to automatically write right to my NAS so I created a
`nextcloud-upload` directory inside of `tank/nas/media/photos` (photos cause
that's all that gets automatically uploaded)

Then I `chown -R www-data:www-data /tank/nas/media/photos/nextcloud-upload` so
that just that sub-folder is owned by `www-data`. Now everyone's happy!