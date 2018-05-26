--- layout: post title: jaunty and sid sources.list date: 2009-02-25 16:31:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: aaronshang.blogspot.com blogger\_author: Aaron Shang blogger\_5bb2c9d46ab12c7e5ecee20eaa8bbd68\_permalink: '6947093192473237637' \_oembed\_f4ae20f4f6894223a6cfa3a24e516867: "{{unknown}}" \_oembed\_1784bdb2fca181eb1251fba2d88f06d3: "{{unknown}}" \_oembed\_fd8e917abb7d94ffea19bdec49dbde82: "{{unknown}}" \_oembed\_adfdc6b07cea86777a84114ca74c33fd: "{{unknown}}" \_oembed\_b38b1fc4dec8c5aa78381a0c2170b69d: "{{unknown}}" \_oembed\_4c2a25a31316cb60fbb38d418a8e58b3: "{{unknown}}" \_oembed\_d3a3a3f7b32dbea3bb6162b9366b91fa: "{{unknown}}" \_oembed\_e564ef72d17c957a623c6c58700580f3: "{{unknown}}" \_oembed\_d297d4118335f06191418758370d2848: "{{unknown}}" \_oembed\_db3b9272d4fcfd74e1afb97f27c30257: "{{unknown}}" \_oembed\_af18b0d9c7d577b0844fbc4f12e28df6: "{{unknown}}" \_oembed\_7671dd2421e3b759dd5c45572d6f567a: "{{unknown}}" \_oembed\_b61561e7d00c00a0020a732070ba8a1b: "{{unknown}}" \_oembed\_1099de624625b7eeb11fec170a7ca505: "{{unknown}}" \_oembed\_cf9b7f0714a30e67fe491dd67853bac6: "{{unknown}}" \_oembed\_1cefb066fcc907702d01e5ce8914d392: "{{unknown}}" \_oembed\_1b194c3f107476c9938db05d8778f5d7: "{{unknown}}" \_oembed\_c048890bc2da48a89e4afb6c3295f0b6: "{{unknown}}" \_oembed\_82bac94d2f5f6a14328c38d97415be54: "{{unknown}}" \_oembed\_73cee73d56197db40e0c454a506f52b2: "{{unknown}}" \_oembed\_6b10c2996977ca91ca82e746e37380a0: "{{unknown}}" \_oembed\_b12ec287728d0ece827a0a2b12b3b7c1: "{{unknown}}" \_oembed\_d2d56d735c4c01ab45e7cbe900e68a1e: "{{unknown}}" \_oembed\_cc8db6b87e770944ff5fb185f3cae0fb: "{{unknown}}" \_oembed\_748da9de84008cedc54013082aa66cb5: "{{unknown}}" \_oembed\_a9bc5d8959399a42b43f249a15e914e7: "{{unknown}}" \_oembed\_2b3241ae0ea52d67888fa437312b4305: "{{unknown}}" \_oembed\_197cce54082d5a2a008def45ba4c9b40: "{{unknown}}" \_oembed\_a9f10c3ee08329187dceb107a4302026: "{{unknown}}" \_oembed\_856061e5633bd7cba8fa3126750abec1: "{{unknown}}" \_oembed\_56e8e912cf67ac292a216742151e8ac6: "{{unknown}}" \_oembed\_f825065ae47e7dbddafb267ead6f22cf: "{{unknown}}" \_oembed\_ecf450ab4e62f370e949b63732df803b: "{{unknown}}" \_oembed\_8d9b7b73a86476391b48a7430510da37: "{{unknown}}" \_oembed\_935fe86dce899cd3bdd243af3baa5291: "{{unknown}}" \_oembed\_7c01fd717e4e664d5067e07e416fe01d: "{{unknown}}" \_oembed\_3862cbb44f1969ca7e2583b7f1101314: "{{unknown}}" \_oembed\_fb7d1cef31202c74954acb2fc090ecb7: "{{unknown}}" \_oembed\_e24d49eebdc88e192d7e67e4f3f30733: "{{unknown}}" \_oembed\_3d465644ed5ead50eb5d00d09009cd32: "{{unknown}}" \_oembed\_4c185af80c83efe3d6ec6a57bb88c4d5: "{{unknown}}" \_oembed\_3789148b67a83767380d6826b1da4ca6: "{{unknown}}" \_oembed\_56549f60a98ee5effab2b75aa176d669: "{{unknown}}" \_oembed\_3e9e9bd9430fda201dfe59acee9ad696: "{{unknown}}" \_oembed\_4e302af6e38aa7fdd16952d44ea98014: "{{unknown}}" \_oembed\_2445e9750c1046708d31ae2feb1ccd81: "{{unknown}}" \_oembed\_e0320b3182eea19b9cbc65d1b855de96: "{{unknown}}" \_oembed\_9bdbbf20f38650625b5dd7d7e3c70a75: "{{unknown}}" \_oembed\_5c02923521b00df1e128283a1c40d951: "{{unknown}}" \_oembed\_278f5d1751ae73f45e1a569f71176f28: "{{unknown}}" \_oembed\_2d7ca1493ebaf148c523d8785adf9b79: "{{unknown}}" \_oembed\_e1a02e773d2e2ddbfc6dadebde3e5536: "{{unknown}}" \_oembed\_d0b96d831dcef653025d427a2b32677b: "{{unknown}}" \_oembed\_1a6918f8b26c26064115280256ad0fd4: "{{unknown}}" \_oembed\_268072d9cb6cd8c6760a934972f6a7e2: "{{unknown}}" \_oembed\_fcbf03208cb1df29eeed4cfcb0e284e8: "{{unknown}}" author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

    #$ cat /etc/apt/sources.list
    # sudo apt-key add key.gpg
    # wget URL –quiet -O - | sudo apt-key add -

    # gpg –keyserver subkeys.pgp.net –recv KEY
    # gpg –export –armor KEY | sudo apt-key add -
     
    # Canonical's 'partner' repository
    deb http://archive.canonical.com/ jaunty partner 

    deb http://ftp.sjtu.edu.cn/ubuntu jaunty main universe multiverse restricted
     deb http://ftp.sjtu.edu.cn/ubuntu/ jaunty-proposed main multiverse restricted universe
    deb http://ftp.sjtu.edu.cn/ubuntu/ jaunty-security main multiverse restricted universe
     deb http://ftp.sjtu.edu.cn/ubuntu/ jaunty-updates main multiverse restricted universe

    deb-src http://ftp.sjtu.edu.cn/ubuntu/ jaunty main multiverse restricted universe
     deb-src http://ftp.sjtu.edu.cn/ubuntu/ jaunty-proposed main multiverse restricted universe
    deb-src http://ftp.sjtu.edu.cn/ubuntu/ jaunty-security main multiverse restricted universe
     deb-src http://ftp.sjtu.edu.cn/ubuntu/ jaunty-updates main multiverse restricted universe

    deb http://mirror.lupaworld.com/ubuntu/ jaunty main multiverse restricted universe
     deb http://mirror.lupaworld.com/ubuntu/ jaunty-proposed main multiverse restricted universe
    deb http://mirror.lupaworld.com/ubuntu/ jaunty-security main multiverse restricted universe
     deb http://mirror.lupaworld.com/ubuntu/ jaunty-updates main multiverse restricted universe

    # deb http://mirror.lupaworld.com/ubuntu/ubuntu-cn/ jaunty main multiverse restricted universe
     # deb http://mirror.lupaworld.com/ubuntu/ubuntu-cn/ jaunty-proposed main multiverse restricted universe
    # deb http://mirror.lupaworld.com/ubuntu/ubuntu-cn/ jaunty-security main multiverse restricted universe
     # deb http://mirror.lupaworld.com/ubuntu/ubuntu-cn/ jaunty-updates main multiverse restricted universe

    # deb http://archive.ubuntu.org.cn/ubuntu-cn/ jaunty main multiverse restricted universe
     # deb http://archive.ubuntu.org.cn/ubuntu-cn/ jaunty-proposed main multiverse restricted universe
    # deb http://archive.ubuntu.org.cn/ubuntu-cn/ jaunty-security main multiverse restricted universe
     # deb http://archive.ubuntu.org.cn/ubuntu-cn/ jaunty-updates main multiverse restricted universe

    deb http://archive.ubuntu.com/ubuntu/ jaunty main multiverse restricted universe
     deb http://archive.ubuntu.com/ubuntu/ jaunty-proposed main multiverse restricted universe
    deb http://archive.ubuntu.com/ubuntu/ jaunty-security main multiverse restricted universe
     deb http://archive.ubuntu.com/ubuntu/ jaunty-updates main multiverse restricted universe

    #deb http://mirror.rootguide.org/ubuntu/ jaunty main restricted multiverse
     #deb http://mirror.rootguide.org/ubuntu/ jaunty-updates main restricted universe multiverse
    #deb http://mirror.rootguide.org/ubuntu/ jaunty-security main restricted universe multiverse
     #deb http://mirror.rootguide.org/ubuntu/ jaunty-proposed main multiverse restricted universe

    #deb http://mirrors.163.com/ubuntu/ jaunty main restricted universe multiverse
     #deb http://mirrors.163.com/ubuntu/ jaunty-updates main restricted universe multiverse
    #deb http://mirrors.163.com/ubuntu/ jaunty-proposed main restricted universe multiverse
     #deb http://mirrors.163.com/ubuntu/ jaunty-security main restricted universe multiverse
    #deb-src http://mirrors.163.com/ubuntu/ jaunty main restricted universe multiverse
     #deb-src http://mirrors.163.com/ubuntu/ jaunty-updates main restricted universe multiverse
    #deb-src http://mirrors.163.com/ubuntu/ jaunty-proposed main restricted universe multiverse
     #deb-src http://mirrors.163.com/ubuntu/ jaunty-security main restricted universe multiverse

    deb http://mirrors.shlug.org/ubuntu/  jaunty main restricted universe multiverse
     deb http://mirrors.shlug.org/ubuntu/  jaunty-security main restricted universe multiverse
    deb http://mirrors.shlug.org/ubuntu/  jaunty-updates main restricted universe multiverse
     deb http://mirrors.shlug.org/ubuntu/  jaunty-proposed main restricted universe multiverse
    #deb-src http://mirrors.shlug.org/ubuntu/  jaunty main restricted universe multiverse
     #deb-src http://mirrors.shlug.org/ubuntu/  jaunty-security main restricted universe multiverse
    #deb-src http://mirrors.shlug.org/ubuntu/  jaunty-updates main restricted universe multiverse
     #deb-src http://mirrors.shlug.org/ubuntu/  jaunty-proposed main restricted universe multiverse

    # deb http://ubuntu.cn99.com/ubuntu/ jaunty main restricted universe multiverse
     # deb http://ubuntu.cn99.com/ubuntu/ jaunty-security main restricted universe multiverse
    # deb http://ubuntu.cn99.com/ubuntu/ jaunty-updates main restricted universe multiverse
     # deb http://ubuntu.cn99.com/ubuntu/ jaunty-proposed main restricted universe multiverse

    #deb http://ubuntu.dormforce.net/ubuntu/ jaunty main multiverse restricted universe
     #deb http://ubuntu.dormforce.net/ubuntu/ jaunty-proposed main multiverse restricted universe
    #deb http://ubuntu.dormforce.net/ubuntu/ jaunty-security main multiverse restricted universe
     #deb http://ubuntu.dormforce.net/ubuntu/ jaunty-updates main multiverse restricted universe

    deb http://debian.ustc.edu.cn/ubuntu/ jaunty main restricted universe multiverse
     deb http://debian.ustc.edu.cn/ubuntu/ jaunty-updates main restricted universe multiverse
    deb http://debian.ustc.edu.cn/ubuntu/ jaunty-security main restricted universe multiverse  
     deb http://debian.ustc.edu.cn/ubuntu/ jaunty-proposed main multiverse restricted universe
    #deb-src http://debian.ustc.edu.cn/ubuntu/ jaunty main multiverse restricted universe
     #deb-src http://debian.ustc.edu.cn/ubuntu/ jaunty-proposed main multiverse restricted universe
    #deb-src http://debian.ustc.edu.cn/ubuntu/ jaunty-security main multiverse restricted universe
     #deb-src http://debian.ustc.edu.cn/ubuntu/ jaunty-updates main multiverse restricted universe

    #deb http://mirror.rootguide.org/ubuntu/ jaunty main restricted universe multiverse
     #deb http://mirror.rootguide.org/ubuntu/ jaunty-updates main restricted universe multiverse
    #deb http://mirror.rootguide.org/ubuntu/ jaunty-security main restricted universe multiverse
     #deb http://mirror.rootguide.org/ubuntu/ jaunty-proposed main multiverse restricted universe

    # Medibuntu
    # Please report any bug on https://bugs.launchpad.net/medibuntu/
     # wget http://packages.medibuntu.org/medibuntu-key.gpg -O- | sudo apt-key add - 
    deb http://packages.medibuntu.org/ jaunty non-free free
     deb http://packages.medibuntu.org/ jaunty-staging non-free free

    #deb http://repository.debuntu.org/ jaunty multiverse
    # wget http://repository.debuntu.org/GPG-Key-chantra.txt -O- | sudo apt-key add - 
     
    #deb http://ftp.sjtu.edu.cn/debian sid main contrib non-free
    #deb http://ftp.sjtu.edu.cn/debian proposed-updates main contrib non-free
     #
    #deb http://anheng.com.cn/debian sid main contrib non-free
    #deb http://anheng.com.cn/debian proposed-updates main contrib non-free
     #deb-src http://anheng.com.cn/debian sid main contrib non-free
    #
    #deb http://ftp.debian.org/debian sid main contrib non-free
    #deb http://ftp.debian.org/debian proposed-updates main contrib non-free
     #deb http://security.debian.org/ sid/updates main contrib non-free
    #
    #deb http://http.us.debian.org/debian sid main contrib non-free
     #deb http://http.us.debian.org/debian proposed-updates main contrib non-free
    #
    #deb http://debian.ustc.edu.cn/debian sid main contrib non-free
     #deb http://debian.ustc.edu.cn/debian-security sid/updates main contrib non-free
    #deb http://debian.ustc.edu.cn/debian proposed-updates main contrib non-free
     
    #deb ftp://debian.ustc.edu.cn/debian-uo sid marillat ustc misc 
    #deb http://debian.ustc.edu.cn/debian-uo sid marillat ustc misc 
     #
    #deb-src http://debian.ustc.edu.cn/debian sid main contrib non-free
    #deb-src http://debian.ustc.edu.cn/debian-security sid/updates main contrib non-free
     #deb-src http://debian.ustc.edu.cn/debian proposed-updates main contrib non-free
    #
    #deb http://mirrors.geekbone.org/debian/ sid main contrib non-free
     #deb http://mirrors.geekbone.org/debian-security sid/updates main contrib non-free
    #deb http://mirrors.geekbone.org/debian/ proposed-updates main contrib non-free
     

<img src="%7B%7B%20site.baseurl%20%7D%7D/assets/8843138513749523318-6947093192473237637?l=aaronshang.blogspot.com" width="1" height="1" />
