--- layout: post title: debian setting locale failed date: 2010-10-08 18:10:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_8a1e6a99d0c87917b8bd0714e7958b89\_permalink: '1722728571835279329' blogger\_author: Aaron Shang blogger\_blog: ashang.blogspot.com author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

perl: warning: Setting locale failed.
perl: warning: Please check that your locale settings:
LANGUAGE = (unset),
LC\_ALL = (unset),
LANG = "zh\_CN.UTF-8"
are supported and installed on your system.
perl: warning: Falling back to the standard locale ("C").
locale: Cannot set LC\_CTYPE to default locale: No such file or directory
locale: Cannot set LC\_MESSAGES to default locale: No such file or directory
locale: Cannot set LC\_ALL to default locale: No such file or directory

to fix this:
\# dpkg-reconfigure locales

<img src="%7B%7B%20site.baseurl%20%7D%7D/assets/" width="1" height="1" />
