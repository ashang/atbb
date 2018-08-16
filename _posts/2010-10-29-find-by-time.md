--- layout: post title: find by time date: 2010-10-29 09:30:24.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: - find - shell - time meta: \_edit\_last: '1' \_wp\_old\_slug: '' author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' excerpt: find time ---

`$ ll total 16 -rw-r--r-- 1 ashang root 2790 2007-07-04 21:59 qjackctlrc -rw-r--r-- 1 ashang root 1765 2005-07-25 05:22 qt_designerrc -rw-r--r-- 1 ashang root 1942 2007-06-26 02:47 qt_plugins_3.3rc -rw-r--r-- 1 ashang root  102 2006-01-09 09:57 qtrc`

$ find -mtime +1500
./qtrc
./qt\_designerrc

$ find -mtime -1500
.
./qt\_plugins\_3.3rc
./qjackctlrc

$ find -atime -1500
.

$ stat qtrc
File: \`qtrc'
Size: 102 Blocks: 8 IO Block: 4096 regular file
Device: 803h/2051d Inode: 4981208 Links: 1
Access: (0644/-rw-r--r--) Uid: ( 1000/ ashang) Gid: ( 0/ root)
Access: 2010-10-29 12:24:52.000000000 +0800
Modify: 2006-01-09 09:57:39.000000000 +0800
Change: 2010-10-29 17:06:23.244057998 +0800

Let's see the 3 times.

> Modify: 2006-01-09 09:57:39.000000000 +0800

This was the time it's contents was last modified.

> Access: 2010-10-29 12:24:52.000000000 +0800

This was the time I made a copy here.

> Change: 2010-10-29 17:06:23.244057998 +0800

This was the time I chmod it.
