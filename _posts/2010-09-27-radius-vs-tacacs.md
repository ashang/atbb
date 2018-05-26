--- layout: post title: radius vs tacacs+ date: 2010-09-27 08:09:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: aaronshang.blogspot.com blogger\_author: ashang blogger\_5bb2c9d46ab12c7e5ecee20eaa8bbd68\_permalink: '8121983696337048102' author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

radius is UDP, so need re-transmit attempts, time-outs to compensate for best-effort transport,

tacacs+ is TCP,

- ACK within network round-trip time, i.e., RTT, regardless how loaded and slow the backend auth mechanism might be
- immediate indication of crashed, or not running, server by a reset RST;
    UDP cannot tell the diff between a server that is down, slow, or non-existent
- TCP keepalive, server crashes can be detected out-of-band with actual requests; can maintain multiple server connections simultaneously.

Pakcet encryption

radius only encrypts pass in the access-request packet, from client to server,

tacacs+ has header field to indicate whether the body is encrypted or not

radius combines authentication and authorization,

tacacs+ separates AAA. can use kerberos to do authentication,

permission granted upon particular com,and

TODO: diameter
