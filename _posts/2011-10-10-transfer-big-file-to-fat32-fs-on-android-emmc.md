--- layout: post title: Transfer big file to FAT32 fs on android eMMC date: 2011-10-10 13:54:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: www.ashang.org blogger\_author: Aaron Shang blogger\_d06f7f5bcdfeb296283c00dcf750b675\_permalink: '7002939651166392271' \_oembed\_17f715b9663946be39a43c87d34f7101: "{{unknown}}" author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---
<span style="color:#1f497d;"></span>

<span style="color:#1f497d;">Summary: </span>

<span style="color:#1f497d;"> - Fat32 doesn’t support file size more than 4GiB; </span>

<span style="color:#1f497d;"> - No crashes during transferring big files to eMMC storage, 4.5GiB+ outsize; 2.5GiB+ OK in my test, using “cp” and “adb push”);</span>

<span style="color:#1f497d;"> - I had NO idea for MTP mode in Linux. (Any hints?)</span>

<span style="color:#1f497d;">$ dd if=/dev/zero of=test-file-4.5g bs=1024 count=4500000</span>

<span style="color:#1f497d;">-rw-r--r--   1 root root 4608000000 2011-09-29 12:43 test-file-4.5g</span>

<span style="color:#1f497d;">/dev/sdb              11915392       960  11914432   1% /media/8780-09E2</span>

<span style="color:#1f497d;">$ time cp test-file-4.5g /media/8780-09E2/</span>

<span style="color:#1f497d;">cp: writing \`/media/8780-09E2/test-file-4.5g': File too large</span>

<span style="color:#1f497d;">real    33m55.000s</span>

<span style="color:#1f497d;">user    0m0.050s</span>

<span style="color:#1f497d;">sys     0m12.500s</span>

<span style="color:#1f497d;">-rw-r--r-- 1 root root 4294967295 2011-10-08 16:29 /media/8780-09E2/test-file-4.5g</span>

<span style="color:#1f497d;">$ /bin/rm -fr /media/8780-09E2/test-file-4.5g </span>

<span style="color:#1f497d;">$ time adb push /test-file-4.5g /mnt/sdcard/</span>

<span style="color:#1f497d;">failed to copy 'test-file-4.5g' to '/mnt/sdcard//test-file-4.5g': File too large</span>

<span style="color:#1f497d;">real    14m24.386s</span>

<span style="color:#1f497d;">user    0m0.150s</span>

<span style="color:#1f497d;">sys     0m10.370s</span>

<span style="color:#1f497d;">$ time dd if=/dev/zero of=test-file-2.5g bs=1024 count=2500000</span>

<span style="color:#1f497d;">2500000+0 records in</span>

<span style="color:#1f497d;">2500000+0 records out</span>

<span style="color:#1f497d;">2560000000 bytes (2.6 GB) copied, 63.4219 s, 40.4 MB/s</span>

<span style="color:#1f497d;">real    1m3.554s</span>

<span style="color:#1f497d;">user    0m0.260s</span>

<span style="color:#1f497d;">sys     0m7.420s</span>

<span style="color:#1f497d;">$ cp test-file-2.5g /media/8780-09E2/test1</span>

<span style="color:#1f497d;">Disconnect phone memory card;</span>

<span style="color:#1f497d;">$ adb push test-file-2.5g /mnt/sdcard/test2</span>

<span style="color:#1f497d;">Mount phone memory card; </span>

<span style="color:#1f497d;">-rw-r--r-- 1 root root 2560000000 2011-10-09 13:01 test1</span>

<span style="color:#1f497d;">-rw-r--r-- 1 root root 2560000000 2011-10-09 04:00 test2</span>

<span style="color:#1f497d;">$ mount|\\grep /dev/sdb</span>

<span style="color:#1f497d;">/dev/sdb on /media/8780-09E2 type vfat (rw,nosuid,nodev,uhelper=udisks,uid=0,gid=0,shortname=mixed,dmask=0077,utf8=1,showexec,flush)</span>

Ref:

<span style="color:#1f497d;"><http://en.wikipedia.org/wiki/Fat32></span>

<span style="color:#1f497d;">Limits Max file size\[1\]      4 GB minus 1 byte</span>
