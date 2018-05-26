--- layout: post title: use proxy for apt date: 2011-06-18 10:46:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: ashang.blogspot.com blogger\_author: Aaron Shang blogger\_8a1e6a99d0c87917b8bd0714e7958b89\_permalink: '5974307861553183122' reddit: a:2:{s:5:"count";i:0;s:4:"time";i:1412810174;} \_oembed\_ea1c17f6d1f9c10d3aa9d509d53fe4d6: "{{unknown}}" author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

add proxy server to
/etc/apt/apt.conf.d/80proxy
Acquire::http::Proxy "<http://proxy.server.hostname:8080/>";
Acquire::http::Proxy::proxy.server.hostname DIRECT;

<img src="%7B%7B%20site.baseurl%20%7D%7D/assets/4041220-5974307861553183122?l=ashang.blogspot.com" width="1" height="1" />
