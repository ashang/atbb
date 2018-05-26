--- layout: post title: case insensitive tab-completion or wild expansion date: 2012-09-09 10:15:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: www.ashang.org blogger\_author: Aaron Shang blogger\_d06f7f5bcdfeb296283c00dcf750b675\_permalink: '9036074437535999451' \_oembed\_6a708c1947bd126c7878ca9df57da583: "{{unknown}}" \_oembed\_afe298aef7106699a8db417388327e3c: "{{unknown}}" \_oembed\_8bbefa846626081682724d55cd3a2ba7: "{{unknown}}" \_oembed\_b5f7c06d305361b0557ee195a64393d1: "{{unknown}}" author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

To let wildcard expansion case insensitive, enable this in bashrc

shopt -s nocaseglob

To let tab-completion case insensitive, you can bind the completion-ignore-case option for bash:

bind \`echo set completion-ignore-case on\`

This will be effective immediately.

Or add this in inputrc for readline;

$ echo 'set completion-ignore-case On' &gt;&gt; ~/.inputrc

Include the system inputrc file:

include /etc/inputrc

To show all binds:

bind -p

To let bash recognizes spelling mistakes, add this in ~/.bashrc:

shopt -s cdspell

For tcsh / zsh users:

set complete enhance

Reference:
<http://www.caliban.org/bash/index.shtml#completion>
<https://wiki.ubuntu.com/Spec/EnhancedBash>


