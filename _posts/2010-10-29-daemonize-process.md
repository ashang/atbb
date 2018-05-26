--- layout: post title: daemonize process date: 2010-10-29 10:26:42.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: - daemon meta: \_edit\_last: '1' \_wp\_old\_slug: '' author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

Description: turns other processes into daemons
There are many tasks that need to be performed to correctly set up a
daemon process. This can be tedious. Daemon performs these tasks for
other processes. This is useful for writing daemons in languages other
than C, C++ or Perl (e.g. /bin/sh, Java).
.
If you want to write daemons in languages that can link against C functions
(e.g. C, C++), see libslack which contains the core functionality of daemon.
.
Upstream URL: http://www.libslack.org/daemon/
