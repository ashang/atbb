--- layout: post title: ARM VFP detection date: 2011-11-24 15:44:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: www.ashang.org blogger\_author: Aaron Shang blogger\_d06f7f5bcdfeb296283c00dcf750b675\_permalink: '6076711596799301801' \_oembed\_fbff903a34b4ab4cb3bb2467da9eb459: "{{unknown}}" author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

<span class="Apple-style-span" style="background-color:white;font-family:Arial, sans-serif;font-size:13px;line-height:18px;">
ARM VFP detection</span>

<span class="Apple-style-span" style="background-color:white;font-family:Arial, sans-serif;font-size:13px;line-height:18px;">A CPU has VFPv3 hardware if the FPSID\[19:16\] bits are 2 or more.</span>
<span class="Apple-style-span" style="background-color:white;font-family:Arial, sans-serif;font-size:13px;line-height:18px;">Currently Linux was only checking for 3 or more.</span>
<span class="Apple-style-span" style="background-color:white;font-family:Arial, sans-serif;font-size:13px;line-height:18px;">arch/arm/vfp/vfpmodule.c</span>

<a href="http://goo.gl/75bzu" class="uri" class="ot-anchor">http://goo.gl/75bzu</a>

 \#ifdef CONFIG\_VFPv3

-               if (VFP\_arch &gt;= 3) {

+               if (VFP\_arch &gt;= 2) {

                        elf\_hwcap |= HWCAP\_VFPv3;

The subarchitecture field in the fpsid register is 7 bits wide.

The topmost bit is used to designate that the subarchitecture designer is not ARM.

This change has the side effect of causing VFP implementations other than ARM to be reported as VFPv3 with common VFP subarch v3.
Before this change it would be reported as VFPv1 with an implementation defined subarchitecture.

<span class="Apple-style-span" style="background-color:white;font-family:Arial, sans-serif;font-size:13px;line-height:18px;">The VFP version is stored in ARM FPSID register of SUBARCH\[22:16\], and the reset value is 0b100\_0000.</span>

But in vfp\_init() of vfpmodule.c, the SUBARCH is treated as SUBARCH \[19:16\], so it is judged as normal VFP. 

The V8 javascript engine looks for vfpv3 in /proc/cpuinfo when deciding how to generate code. 

If it only report support for vfp, slower code will be generated.

$ adb shell cat /proc/cpuinfo

Processor       : ARMv7 Processor rev 8 (v7l)

processor       : 0

BogoMIPS        : 31.25

Features        : swp half thumb fastmult vfp edsp neon vfpv3

CPU implementer : 0x15

CPU architecture: 7

CPU variant     : 0x0

CPU part        : 0x02d

CPU revision    : 8

Hardware        : foobar

Revision        : 0000

Serial          : 0000000000000000
