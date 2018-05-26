--- layout: post title: read process status date: 2010-10-29 10:55:24.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: - process - status meta: \_edit\_last: '1' \_wp\_old\_slug: '' reddit: a:2:{s:5:"count";i:0;s:4:"time";i:1404686775;} author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

read process status

read:
/proc/pid/stat

See:
psmisc/prtstat.c

210 static void print\_stat(const int pid, const opt\_type options)
211 {
212 char \*pathname;
213 char buf\[BUFSIZ\];
214 char \*bptr;
215 FILE \*fp;
216
217 struct proc\_info \*pr;
218 pr = malloc(sizeof(struct proc\_info));
219
220 if ( (asprintf(&pathname, "/proc/%d/stat",(int)pid)) &lt; 0) {
221 perror(\_("asprintf in print\_stat failed.\\n"));
222 exit(1);
223 }
