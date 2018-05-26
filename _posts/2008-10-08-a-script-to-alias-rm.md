--- layout: post title: a script to alias rm date: 2008-10-08 13:57:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_8a1e6a99d0c87917b8bd0714e7958b89\_permalink: '4512448830940257951' blogger\_author: Aaron Shang blogger\_blog: ashang.blogspot.com author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---
    # This is used as a shell script for alias as 'rm', say, 
    # name it del.sh, then alias rm='del.sh'
    # Aaron is gradually improving it, in the process of learning bash.
    # suggestions welcomed to aaronshang@gmail
     #
    # usage: 
    # create a dir for backup: MYSAV=/$HOME/.local/share/Trash/
    # remove: $ rm files
    # restore: $ rm -r files
    # use \rm to call original rm.
    #
    # I had tried to use (dirname $myfile) to replace (pwd) to save two cd,
     # but dirname is relative to current working dir, not absolute dir.

    # mv -f $(basename $myfile) ${MYSAV}/$(find $(pwd) -maxdepth 1 -name $(basename $myfile)  |tr "/" "=")==`date +%Y-%m-%d-% H-%M-%S`
     
    ## then must be on next line of if

    MYSAV=/$HOME/.local/share/Trash/

    ##(($#==0)) && { echo "No parameters!";exit 1; }
    ## ??
    ##  1==0: not found

    case "$1" in
    -r)
     
    cd $MYSAV
    for i in $(echo $*|awk '{$1="";print}')
    do
      myfile=$(\ls |grep "

lt;"$i"
```
```

gt;"|tail -1)
file=$(echo ${myfile%%==\*}|tr "=" "/" |tr "^" " ")
mv $myfile "${file%/\*}/${file\#\#\*/}"
done
;;
\*)
\#for myfile in "$\*"
for myfile in $\*
do
if test -e "$myfile"
then
cd $(dirname "$myfile")
mv -f "$(basename "$myfile")" ${MYSAV}/$(echo $(pwd)/$(basename "$myfile") \\
|tr "/" "=" |tr " " "^")==$(date +%Y-%m-%d-%H-%M-%S)
cd -
else
echo "$myfile:No such file or directory!"
fi
done
;;
esac
\#exit 0
\# ==== Bug records
\#Bug: Failed if files not exist
\#Bug: Failed if filename contains space
\#Fixed: for myfile in "$\*", and add "" for all myfile instances and change spaces to ^
\#Bug: Failed for multi files if add "$\*",
\#Fix: just because "" in for myfile in "$\*" above, get rid of
\#Fix: I have to remove spaces before using this script:
\# alias rmspace='rename '
```
```

\#039;'y/\\ /\_/'
```
```

\#039;' '
\# script rename is from perl
\# Bug: error if the restored is a dir
\# rm -r xxx
\#2==0: not found
\#mv: rename =home=xxx-...11-04-17 to /home/xxx/intro\_files: No such file or directory

<img src="%7B%7B%20site.baseurl%20%7D%7D/assets/" width="1" height="1" />
