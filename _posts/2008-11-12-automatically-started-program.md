--- layout: post title: automatically started program date: 2008-11-12 17:52:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_author: Aaron Shang blogger\_8a1e6a99d0c87917b8bd0714e7958b89\_permalink: '6786020135553106793' blogger\_blog: ashang.blogspot.com author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

Another program would be moved out from my automatically started list

I put my often used programs into $HOME/.xinitrc, to make them
automatically started by DM at booting, here is the end of this
.xinitrc：

export IME=scim
export GTK\_IM\_MODULE=$IME
export XMODIFIERS=@im=$IME
export QT\_IM\_MODULE=$IME
exec scim -d &
exec stardict &
exec VirtualBox &
exec firefox &

export TERM=xfce4-terminal
exec $TERM &

\# finally start the window manager
unset WINDOW\_MANAGER STARTUP

exec skype &
export WINDOWMANAGER=xfce4-session

exec $WINDOWMANAGER
exec qterm &

\# call failsafe
exit 0

One of my often used programs that had been moved out of this list is
thunderbird (mutt before this), because I had been used to Gmail as my
mail reader.

For important or useful emails, I would tidy them up and archive them
in time, both stored in local and remote storage.

Another program that had been moved out is stardict. One reason is
that I have to install it in different distros I work with, and copy
those dics to $HOME/.stardict/dic. Another reason is the alternates I
had found.

One alternate is the web version of this dict, which have enough dics
can be self customized:
<http://www.stardict.org/>

Another alternate is Google's dict, with powerful functions such as
translating, look-up, and searching for words:
<http://www.google.com/dictionary>
This is my default page for native language:
<http://www.google.com/dictionary?aq=f&langpair=en%7Czh-CN>
in short, it is:
<http://www.google.cn/dictionary>

Which is the next? scim, i think.
But I have to choose one alternate, will try and decide one.

Then what next? skype, but not until gmail chat can do voice and video.

<img src="%7B%7B%20site.baseurl%20%7D%7D/assets/4041220-6786020135553106793?l=ashang.blogspot.com" width="1" height="1" />
