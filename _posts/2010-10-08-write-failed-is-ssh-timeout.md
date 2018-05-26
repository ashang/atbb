--- layout: post title: Write failed is SSH Timeout date: 2010-10-08 08:06:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: aaronshang.blogspot.com blogger\_author: ashang blogger\_5bb2c9d46ab12c7e5ecee20eaa8bbd68\_permalink: '9088039048678827909' author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

****<span> </span>**SSH session Timeout and break with this:
Write failed: Broken pipe?**

to make it better, try tune client side option ServerAliveInterval to a small value.

~/.ssh/ssh\_config:
ServerAliveInterval 30
