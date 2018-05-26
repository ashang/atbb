--- layout: post title: awk printf align date: 2010-10-09 14:29:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: www.ashang.org blogger\_author: Aaron Shang blogger\_d06f7f5bcdfeb296283c00dcf750b675\_permalink: '1947869694924932265' author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

arp -n | awk '{printf("%-20s %-20s %-20s\\n",$1, $3, $5)}'
