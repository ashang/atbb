--- layout: post title: ELF file data encoding not little-endian date: 2009-02-25 16:20:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_author: Aaron Shang blogger\_8a1e6a99d0c87917b8bd0714e7958b89\_permalink: '669285334796713500' blogger\_blog: ashang.blogspot.com author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

ELF file data encoding not little-endian
<span style="font-family:arial narrow,sans-serif;">$ man tar</span>
<span style="font-family:arial narrow,sans-serif;">/usr/bin/gtbl: error while loading shared libraries: /lib/libstdc++.so.6: ELF file data encoding not little-endian</span>
<span style="font-family:arial narrow,sans-serif;">$ file /usr/bin/gtbl </span>
<span style="font-family:arial narrow,sans-serif;">/usr/bin/gtbl: symbolic link to \`tbl'</span>
<span style="font-family:arial narrow,sans-serif;">$ ldd /usr/bin/gtbl</span>
<span style="font-family:arial narrow,sans-serif;">    linux-gate.so.1 =&gt;  (0xb8095000)</span>
<span style="color:rgb(51,51,255);font-family:arial narrow,sans-serif;">    libstdc++.so.6 =&gt; /usr/lib/libstdc++.so.6 (0xb7fa4000)</span>
<span style="font-family:arial narrow,sans-serif;">    libm.so.6 =&gt; /lib/tls/i686/cmov/libm.so.6 (0xb7f7e000)</span>
<span style="font-family:arial narrow,sans-serif;">    libgcc\_s.so.1 =&gt; /lib/libgcc\_s.so.1 (0xb7f6e000)</span>
<span style="font-family:arial narrow,sans-serif;">    libc.so.6 =&gt; /lib/tls/i686/cmov/libc.so.6 (0xb7e0b000)</span>
<span style="font-family:arial narrow,sans-serif;">    /lib/ld-linux.so.2 (0xb8096000)</span>
<span style="font-family:arial narrow,sans-serif;">$ file /usr/bin/tbl </span>
<span style="font-family:arial narrow,sans-serif;"> /usr/bin/tbl: ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked (uses shared libs), for GNU/Linux 2.6.9, stripped</span>
<span style="font-family:arial narrow,sans-serif;">$ ls -l /lib/libstdc++.so\*</span>
<span style="font-family:arial narrow,sans-serif;">lrwxrwxrwx 1 root root     18 2009-02-25 10:37 /lib/libstdc++.so -&gt; libstdc++.so.6.0.4</span>
<span style="font-family:arial narrow,sans-serif;"> lrwxrwxrwx 1 root root     18 2009-02-25 10:37 /lib/libstdc++.so.6 -&gt; libstdc++.so.6.0.4</span>
<span style="font-family:arial narrow,sans-serif;">-rwxr-xr-x 1 root root 935932 2009-02-25 10:37 /lib/libstdc++.so.6.0.4</span>
<span style="font-family:arial narrow,sans-serif;">$ file /lib/libstdc++.so\*</span>
<span style="font-family:arial narrow,sans-serif;">/lib/libstdc++.so:       symbolic link to \`libstdc++.so.6.0.4'</span>
<span style="font-family:arial narrow,sans-serif;"> /lib/libstdc++.so.6:     symbolic link to \`libstdc++.so.6.0.4'</span>
<span style="font-family:arial narrow,sans-serif;">/lib/libstdc++.so.6.0.4: ELF 32-bit MSB shared object, </span><span style="color:rgb(51,51,255);font-family:arial narrow,sans-serif;">PowerPC</span><span style="font-family:arial narrow,sans-serif;"> or cisco 4500, version 1 (SYSV), stripped</span>
<span style="font-family:arial narrow,sans-serif;">$ readelf -h /lib/libstdc++.so.6.0.4 </span>
<span style="font-family:arial narrow,sans-serif;">ELF Header:</span>
<span style="font-family:arial narrow,sans-serif;">  Magic:   7f 45 4c 46 01 02 01 00 00 00 00 00 00 00 00 00 </span>
<span style="font-family:arial narrow,sans-serif;">  Class:                             ELF32</span>
<span style="color:rgb(51,51,255);font-family:arial narrow,sans-serif;">  Data:                              2's complement, big endian</span>
<span style="color:rgb(51,51,255);font-family:arial narrow,sans-serif;">  Version:                           1 (current)</span>
<span style="color:rgb(51,51,255);font-family:arial narrow,sans-serif;">  OS/ABI:                            UNIX - System V</span>
<span style="color:rgb(51,51,255);font-family:arial narrow,sans-serif;">  ABI Version:                       0</span>
<span style="color:rgb(51,51,255);font-family:arial narrow,sans-serif;">  Type:                              DYN (Shared object file)</span>
<span style="color:rgb(51,51,255);font-family:arial narrow,sans-serif;">  Machine:                           PowerPC</span>
<span style="font-family:arial narrow,sans-serif;">  Version:                           0x1</span>
<span style="font-family:arial narrow,sans-serif;">  Entry point address:               0x3f0fc</span>
<span style="font-family:arial narrow,sans-serif;">  Start of program headers:          52 (bytes into file)</span>
<span style="font-family:arial narrow,sans-serif;">  Start of section headers:          934732 (bytes into file)</span>
<span style="font-family:arial narrow,sans-serif;">  Flags:                             0x0</span>
<span style="font-family:arial narrow,sans-serif;">  Size of this header:               52 (bytes)</span>
<span style="font-family:arial narrow,sans-serif;">  Size of program headers:           32 (bytes)</span>
<span style="font-family:arial narrow,sans-serif;">  Number of program headers:         5</span>
<span style="font-family:arial narrow,sans-serif;">  Size of section headers:           40 (bytes)</span>
<span style="font-family:arial narrow,sans-serif;">  Number of section headers:         30</span>
<span style="font-family:arial narrow,sans-serif;">  Section header string table index: 29</span>
<span style="color:rgb(51,51,255);font-family:arial narrow,sans-serif;">
<span style="color:rgb(51,0,51);">$ readelf -h /usr/lib/libstdc++.so.6.0.10 </span>
<span style="color:rgb(51,0,51);">ELF Header:</span>
<span style="color:rgb(51,0,51);">  Magic:   7f 45 4c<span style="color:rgb(51,51,255);"> 46 01 01 01</span> 00 00 00 00 00 00 00 00 00 </span>
<span style="color:rgb(51,0,51);">  Class:                             ELF32</span>
<span style="color:rgb(51,51,255);">  Data:                              2's complement, little endian</span>
<span style="color:rgb(51,0,51);">  Version:                           1 (current)</span>
<span style="color:rgb(51,0,51);">  OS/ABI:                            UNIX - System V</span>
<span style="color:rgb(51,0,51);">  ABI Version:                       0</span>
<span style="color:rgb(51,0,51);">  Type:                              DYN (Shared object file)</span>
<span style="color:rgb(51,51,255);">  Machine:                           Intel 80386</span>
<span style="color:rgb(51,0,51);">  Version:                           0x1</span>
<span style="color:rgb(51,0,51);">  Entry point address:               0x44230</span>
<span style="color:rgb(51,0,51);">  Start of program headers:          52 (bytes into file)</span>
<span style="color:rgb(51,0,51);">  Start of section headers:          949224 (bytes into file)</span>
<span style="color:rgb(51,0,51);">  Flags:                             0x0</span>
<span style="color:rgb(51,0,51);">  Size of this header:               52 (bytes)</span>
<span style="color:rgb(51,0,51);">  Size of program headers:           32 (bytes)</span>
<span style="color:rgb(51,0,51);">  Number of program headers:         7</span>
<span style="color:rgb(51,0,51);">  Size of section headers:           40 (bytes)</span>
<span style="color:rgb(51,0,51);">  Number of section headers:         30</span>
<span style="color:rgb(51,0,51);">  Section header string table index: 29</span>
</span>

<img src="%7B%7B%20site.baseurl%20%7D%7D/assets/" width="1" height="1" />
