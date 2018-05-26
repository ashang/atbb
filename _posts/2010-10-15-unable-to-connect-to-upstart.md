--- layout: post title: unable to connect to upstart date: 2010-10-15 20:32:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: ashang.blogspot.com blogger\_author: Aaron Shang blogger\_8a1e6a99d0c87917b8bd0714e7958b89\_permalink: '7767561988834387070' \_oembed\_46aeb1e79a52671ccfdcb6694e050268: "{{unknown}}" \_oembed\_b947e4560b041e78188d5579a29181c8: "{{unknown}}" author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

Upstart jobs cannot be run in a chroot
--------------------------------------

<span id="line-206" class="anchor"></span><span id="line-207" class="anchor"></span>Upstart jobs cannot be started in a chroot because upstart acts as a service supervisor, and processes within the chroot are unable to communicate with the upstart running outside of the chroot (<a href="https://bugs.launchpad.net/bugs/430224" class="interwiki" title="Bug">430224</a>). This will cause some packages that have been converted to use upstart jobs instead of init scripts to fail to upgrade within a chroot. Users are advised to configure their chroots with /sbin/initctl pointing to /bin/true

<https://bugs.launchpad.net/ubuntu/+source/upstart/+bug/430224>

Replacing /sbin/initctl with a symlink to /bin/true is a fairly standard
way to disable services in a chroot

100 root@odysseus ~ \# apt-get install procps
Reading package lists... Done
Building dependency tree      
Reading state information... Done
procps is already the newest version.
0 upgraded, 0 newly installed, 0 to remove and 157 not upgraded.
1 not fully installed or removed.
After this operation, 0 B of additional disk space will be used.
Do you want to continue \[Y/n\]?
Setting up procps (1:3.2.8-9ubuntu3) ...
start: Unable to connect to Upstart: Failed to connect to socket /com/ubuntu/upstart: Connection refused
dpkg: error processing procps (--configure):
 subprocess installed post-installation script returned error exit status 1
configured to not write apport reports
                                      Errors were encountered while processing:
 procps
E: Sub-process /usr/bin/dpkg returned an error code (1)

100 root@odysseus ~ \# dpkg-divert --local --rename --add /sbin/initctl
Adding 'local diversion of /sbin/initctl to /sbin/initctl.distrib'

root@odysseus ~ \# ln -s /bin/true /sbin/initctl

root@odysseus ~ \# apt-get install procps
Reading package lists... Done
Building dependency tree      
Reading state information... Done
procps is already the newest version.
0 upgraded, 0 newly installed, 0 to remove and 157 not upgraded.
1 not fully installed or removed.
After this operation, 0 B of additional disk space will be used.
Do you want to continue \[Y/n\]?
Setting up procps (1:3.2.8-9ubuntu3) ...
Processing triggers for menu ...
Processing triggers for libc-bin ...
ldconfig deferred processing now taking place
apt-get install procps  5.42s user 0.62s system 57% cpu 10.574 total

<img src="%7B%7B%20site.baseurl%20%7D%7D/assets/4041220-7767561988834387070?l=ashang.blogspot.com" width="1" height="1" />
