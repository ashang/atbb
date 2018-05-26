--- layout: post title: busybox modprobe ip\_tables date: 2010-10-09 09:31:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: aaronshang.blogspot.com blogger\_author: ashang blogger\_5bb2c9d46ab12c7e5ecee20eaa8bbd68\_permalink: '2599688433241380425' author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

no matter whether the modules exist or not, busybox will put module info into this file:
/lib/modules/\`uname -r\`/[modules.dep.bb](http://modules.dep.bb)

the file will not be made empty even the modules removed:
\# modprobe -v -r ip\_tables

\# more [modules.dep.bb](http://modules.dep.bb)
kernel/net/ipv4/netfilter/ip\_tables.ko symbol:ipt\_unregister\_table symbol:ipt\_register\_table symbol:ipt\_do\_table symbol:ipt\_do\_table symbol:ipt\_unregister\_table symbol:ipt\_register\_table

kernel/net/ipv4/netfilter/iptable\_filter.ko
ip\_tables

The modules should be put into the right place, such as:
/lib/modules/\`uname -r\`/kernel/net/ipv4/netfilter

    iptables tries to load ip_tables even though it is statically compiled in the kernel


