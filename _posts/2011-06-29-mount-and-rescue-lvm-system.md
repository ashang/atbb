--- layout: post title: mount and rescue lvm system date: 2011-06-29 12:39:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: ashang.blogspot.com blogger\_author: Aaron Shang blogger\_8a1e6a99d0c87917b8bd0714e7958b89\_permalink: '3651811989648237493' reddit: a:2:{s:5:"count";i:0;s:4:"time";i:1405497215;} author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

**mount boot partition**

sudo mount /dev/sda1 /opt

sudo vi /opt/grub/grub.cfg

menuentry

search --no-floppy --fs-uuid --set $UUID\_OF\_BOOT\_PARTITION
linux /vmlinuz root=/dev/mapper/vg-root

**mount root partition on lvm**

sudo apt-get install lvm2

sudo lvdisplay

sudo lvchange -ay /dev/vg-label

sudo mount /dev/mapper/vg-root /mnt

sudo vi /mnt/etc/fstab

UUID=$UUID\_OF\_BOOT\_PARTITION /boot ext2 defaults 0 2
/dev/mapper/vg-root / ext4 defaults 0 2
/dev/mapper/vg-home /home ext4 defaults 0 2

<img src="%7B%7B%20site.baseurl%20%7D%7D/assets/" width="1" height="1" />
