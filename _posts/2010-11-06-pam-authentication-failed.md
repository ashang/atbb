--- layout: post title: PAM authentication failed date: 2010-11-06 17:13:18.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: reddit: a:2:{s:5:"count";i:0;s:4:"time";i:1412780817;} author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

Error for userdel/user/add/groupadd/groupdel:
=============================================

PAM authentication failed
=========================

    Solution: Add pam file.

    e.g. for userdel:

    add a file /etc/pam.d/userdel

auth sufficient pam\_rootok.so
auth required pam\_unix.so

account required pam\_unix.so

session required pam\_unix.so

password required pam\_permit.so
