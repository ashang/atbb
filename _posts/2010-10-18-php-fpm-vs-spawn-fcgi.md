--- layout: post title: php-fpm vs spawn-fcgi date: 2010-10-18 07:48:03.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: - php-fpm meta: \_oembed\_c03e3c501b0e45213ce67fbb986bf51a: "{{unknown}}" \_edit\_last: '1' \_oembed\_124458a3caded4a6abd15753b62769ba: "{{unknown}}" \_wp\_old\_slug: hello-world \_oembed\_882f3d094a791acb8bfc5ca82eefa443: "{{unknown}}" \_oembed\_5dfe87ce40b2b12e73f256b2fdcf9bb4: "{{unknown}}" \_oembed\_65ca2f2547bf141ee12409fd64615bfb: "{{unknown}}" \_oembed\_10680701532b0c670da38bcbe39e18ce: "{{unknown}}" \_oembed\_3a6e2be1c6f4f09dc4d92ba9606458e5: "{{unknown}}" \_oembed\_f4e956048012157a2073b948bbcc184d: "{{unknown}}" \_oembed\_1c99c56e7a45e74ac6a7ea417102b682: "{{unknown}}" \_oembed\_7c1309bedfa47543a6d99333daa16138: "{{unknown}}" \_oembed\_9dc91b2d001ee1aac892f1271873e33a: "{{unknown}}" \_oembed\_40017a0d206b8647a996752161c9e49b: "{{unknown}}" \_oembed\_e47d0de285d6d605e6d5304368cc865a: "{{unknown}}" \_oembed\_b0c2e7958ac32892e4ce50d17569e5ed: "{{unknown}}" \_oembed\_e3d35302773778f2c043b05b62a127fd: "{{unknown}}" \_oembed\_2b670a506272623e23e550b89de138da: "{{unknown}}" \_oembed\_fc2df37bf15ac01dcbc18c78a6e10a66: "{{unknown}}" \_oembed\_e7d13d2cc003acf5c5b0ffd9875a4a22: "{{unknown}}" \_oembed\_aae6053079de6b7a92fe80c3087ede68: "{{unknown}}" \_oembed\_f45b6a4b97500368601cb8b1c9a84b0a: "{{unknown}}" \_oembed\_ae0c4715d69166c75d53c1630c26ffe9: "{{unknown}}" \_oembed\_fd8d20568440e9c71f87724141e63e2f: "{{unknown}}" \_oembed\_05a9d335eaa58801d39e6d094d80a150: "{{unknown}}" \_oembed\_78f2172ed7842efc0a0163dc17b53956: "{{unknown}}" \_oembed\_dc8f86b3a87cf4b965521463a5871c91: "{{unknown}}" \_oembed\_ac0768f7d28dae031a5511d274efbe94: "{{unknown}}" \_oembed\_96759fa7fb321e2d4550666a63b09d35: "{{unknown}}" \_oembed\_ccedbeadfee2d0b39dd7c74a2fd06de0: "{{unknown}}" \_oembed\_ecf0291600e6f54ada27e2a0484eb139: "{{unknown}}" \_oembed\_ee4fff93583c0940f639ef36ef747c58: "{{unknown}}" \_oembed\_b640b185bd3e3ad16b13f024dd6e1008: "{{unknown}}" \_oembed\_78be07e67111471c3588acdb5e78a17d: "{{unknown}}" \_oembed\_97770a8cf2e962c660c5862c26760aec: "{{unknown}}" \_oembed\_cc00732c3477cf3691f5e7e306e8244b: "{{unknown}}" \_oembed\_e75c3d5c808fbe36390255731ce9f382: "{{unknown}}" \_oembed\_b08c05983042ff0b7f2cc8e1dee692a0: "{{unknown}}" \_oembed\_02498f30ab4fc0ea8e5041a9ca884876: "{{unknown}}" \_oembed\_54b94ec4bf3a64da25a5a56d16af1c82: "{{unknown}}" \_oembed\_040d1b2a69d49e8c943afdb5d4d807b3: "{{unknown}}" author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

Basic features:

http://php-fpm.org/

What is PHP-FPM?
PHP-FPM (FastCGI Process Manager) is an alternative PHP FastCGI implementation with some additional features useful for sites of any size, especially busier sites.

These features include:

\* Adaptive process spawning (NEW!)
\* Basic statistics (ala Apache's mod\_status) (NEW!)
\* Advanced process management with graceful stop/start
\* Ability to start workers with different uid/gid/chroot/environment and different php.ini (replaces safe\_mode)
\* Stdout & stderr logging
\* Emergency restart in case of accidental opcode cache destruction
\* Accelerated upload support
\* Support for a "slowlog"
\* Enhancements to FastCGI, such as fastcgi\_finish\_request() - a special function to finish request & flush all data while continuing to do something time-consuming (video converting, stats processing, etc.)

... and much more.

It was not designed with virtual hosting in mind (large amounts of pools) however it can be adapted for any usage model.

Comparison:

http://php-fpm.org/about/

Uncomplete nginx practice:
http://wiki.nginx.org/NinX%2BPHP%2BFPM%2Bremote
