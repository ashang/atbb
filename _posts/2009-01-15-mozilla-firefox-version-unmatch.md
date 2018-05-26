--- layout: post title: mozilla firefox version unmatch date: 2009-01-15 13:55:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: aaronshang.blogspot.com blogger\_author: ashang blogger\_5bb2c9d46ab12c7e5ecee20eaa8bbd68\_permalink: '3039202999252387680' author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

errors when launching firefox:

$ firefox
Error: Platform version '1.9' is not compatible with
minVersion &gt;= 1.9.0.1
maxVersion &lt;= 1.9.0.\*

$ sudo vi /usr/lib/firefox-3.0.4/application.ini

find these lines:
\[Gecko\]
MinVersion=1.9.0.1
MaxVersion=1.9.0.\*

modify the version range, then It works with this dirty trick.
