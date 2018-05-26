--- layout: post title: WordPress init date: 2010-11-01 10:47:17.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: \_edit\_last: '17109838' \_wp\_old\_slug: '' geo\_latitude: '0.000000' geo\_longitude: '0.000000' geo\_accuracy: '0' geo\_public: '1' reddit: a:2:{s:5:"count";i:0;s:4:"time";i:1412780097;} \_oembed\_bcfffbee4189bb6d83876190014b68fd: "{{unknown}}" \_oembed\_c2120edc62be2177393a679d46175907: "{{unknown}}" \_oembed\_de25ef9ce801c48c76ed965e69573865: "{{unknown}}" \_oembed\_d49eadde14fb4fdf09aea7358568b482: "{{unknown}}" author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

Notes on starting WordPress

-   Get WordPress from: <http://wordpress.org/latest.tar.gz> and explode it to **your\_target\_install\_path**

<!-- -->

-   Create database in MySQL:

<!-- -->

-   $ mysql -u root -p
-   mysql&gt; create database database\_name;
-   mysql&gt; grant all on database\_name.\* to database\_user@localhost identified by 'password\_for\_this\_user';
-   mysql&gt; flush privileges;
-   mysql&gt; exit

<!-- -->

-   $ $EDITOR wp-config.php according to above MySQL operations.

<!-- -->

-   Add to apache conf

<!-- -->

-   Done. Access URL: <http://your.domain/weblog>

