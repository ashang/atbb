--- layout: post title: grep utf-8 contents date: 2010-10-29 10:24:06.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: - grep - utf-8 meta: \_edit\_last: '1' \_wp\_old\_slug: '' author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' excerpt: grep utf-8 contents ---

grep utf-8 contents

If your locale is some utf-8, then just grep.

If not utf-8 locale, then make a change:

> $ iconv -f utf-8 -t your\_current\_locale &lt; your\_utf-8\_target\_file -o new\_file\_as\_your\_locale
