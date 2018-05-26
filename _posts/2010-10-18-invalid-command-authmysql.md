--- layout: post title: Invalid command 'AuthMYSQL' date: 2010-10-18 05:29:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: aaronshang.blogspot.com blogger\_author: ashang blogger\_5bb2c9d46ab12c7e5ecee20eaa8bbd68\_permalink: '6321000185421551005' author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

$ sudo /etc/init.d/apache2 restart
Syntax error on line 16 of /etc/apache2/conf.d/awstats.conf:
Invalid command 'AuthMYSQL', perhaps misspelled or defined by a module not included in the server configuration
Action 'configtest' failed.
The Apache error log may have more information.
   ...fail!

$ sudo apt-get install libapache2-mod-auth-mysql

$ sudo a2enmod auth\_mysql
Enabling module auth\_mysql.
Run '/etc/init.d/apache2 restart' to activate new configuration!

$ sudo /etc/init.d/apache2 restart
 \* Restarting web server apache2                                                                                                                        \[ OK \]


