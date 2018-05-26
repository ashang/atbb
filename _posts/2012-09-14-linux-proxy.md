--- layout: post title: Linux proxy date: 2012-09-14 17:29:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: www.ashang.org blogger\_author: Aaron Shang blogger\_d06f7f5bcdfeb296283c00dcf750b675\_permalink: '1886323217547802793' \_oembed\_efc7d090d0aed6d4a466a636f95e9c70: "{{unknown}}" \_oembed\_073961bb68813ab59477923e8419f313: "{{unknown}}" author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

**<span style="font-size:medium;">== proxy for apt ==</span>**

edit
<span style="font-family:courier new, monospace;">/etc/apt/apt.conf</span>

or
<span style="font-family:courier new, monospace;">$ sudo vi /etc/apt/apt.conf.d/60proxy</span>
<span style="font-family:courier new, monospace;">Acquire::http::Proxy "http://x.x.x.x:port";</span>

<span style="font-family:courier new, monospace;">Don't miss the trailing ";". </span>

The proxy can be in pac form:
"http://x.x.x.x:port/accelerated.pac"

URL:
<http://en.wikipedia.org/wiki/Proxy_auto-config>

**<span style="font-size:medium;">== proxy for wget ==</span>**

    wget -e http_proxy=http://x.x.x.x:port -c -m -np -k URL 

     
