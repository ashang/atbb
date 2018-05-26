--- layout: post title: awk printf align date: 2010-10-09 06:29:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: aaronshang.blogspot.com blogger\_author: ashang blogger\_5bb2c9d46ab12c7e5ecee20eaa8bbd68\_permalink: '8412224416410450361' author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

arp -n | awk '{printf("%-20s %-20s %-20s\\n",$1, $3, $5)}'
