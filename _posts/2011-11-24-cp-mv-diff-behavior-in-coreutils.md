--- layout: post title: cp-mv-diff-behavior-in-coreutils date: 2011-11-24 15:49:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: www.ashang.org blogger\_author: Aaron Shang blogger\_d06f7f5bcdfeb296283c00dcf750b675\_permalink: '8537366323461565446' author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---
If you aliased mv and cp, and would use "-f" with them, the behavior for them are different.

$ alias mv

alias mv='mv -i'

$ alias cp

alias cp='cp -i -R -P --preserve=all'

GNU coreutils 8.5

$ man cp

       -f, --force              if an existing destination file cannot be opened, remove it and try again (redundant if the -n option is used)

        -i, --interactive              prompt before overwrite (overrides a previous -n option)

        -n, --no-clobber              do not overwrite an existing file (overrides a previous -i option)

$ man mv

       -f, --force              do not prompt before overwriting

       -i, --interactive              prompt before overwrite

       -n, --no-clobber              do not overwrite an existing file

       If you specify more than one of -i, -f, -n, only the final one takes effect.

 

 
