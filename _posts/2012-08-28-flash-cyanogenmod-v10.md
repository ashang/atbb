--- layout: post title: Flash CyanogenMod v10 date: 2012-08-28 09:14:00.000000000 +08:00 type: post published: true status: publish categories: \[\] tags: \[\] meta: blogger\_blog: www.ashang.org blogger\_author: Aaron Shang blogger\_d06f7f5bcdfeb296283c00dcf750b675\_permalink: '1979071403484919067' \_oembed\_f9949ee02f6b89bf9bf2c8a9593ac44f: "{{unknown}}" \_oembed\_6a1cd8bb571bb832c6b4cc27afb8abe2: "{{unknown}}" \_oembed\_effd740fbb6d29d58b1eedcde2a75b37: "{{unknown}}" \_oembed\_a99e8fc843bc5299fb31c3d258f57bc1: "{{unknown}}" \_oembed\_ba3606658b8c755b86ffce0fb970aa8d: "{{unknown}}" \_oembed\_05e0c941d4f4b847c3a6dcc8493e67eb: "{{unknown}}" author: login: aaronshang email: aaronshang@gmail.com display\_name: Aaron first\_name: '' last\_name: '' ---

Find your device image here:

<http://www.cyanogenmod.com/devices>

Here is for Sony Ericsson Xperia Play, etc.

<http://www.cyanogenmod.com/devices/sony-ericsson-xperia-play-gsm>

If you see boot-device\_code.img for your prototype, also download it to use for the boot.img.

Push the image zip file to your phone storage.

Your device should be unlockable and unlocked, check here for Sony Ericsson Arc, etc

<http://unlockbootloader.sonymobile.com/>

At least you should get fastboot and android driver to your PC.

If you work on a Linux system, it's OK to just get a Linux version fastboot.

Steps:

Power on your device, while press the unlock button.

Some unlock button according to different devices.

<span style="font-family:Symbol;">·<span style="font-family:'Times New Roman';font-size:7pt;">         </span></span>Menu button (for Xperia™ arc, Xperia™ arc S, Xperia™ neo, Xperia™ neo V, Xperia™ pro).

<span style="font-family:Symbol;">·<span style="font-family:'Times New Roman';font-size:7pt;">         </span></span>Search button (for Xperia™ PLAY).

<span style="font-family:Symbol;">·<span style="font-family:'Times New Roman';font-size:7pt;">         </span></span>Volume up button (for Xperia™ mini, Xperia™ mini pro, Xperia™ ray, Xperia™ active, Live with Walkman™, Xperia™ S).

Check if fastboot can work on the device, version 0.3 means you can continue.

**fastboot -i 0x0fce getvar version**

*version: 0.3*

*finished. total time: 0.000s*

Then flash the boot image.

**fastboot flash boot boot.img**

*sending 'boot' (5290 KB)...*

*(bootloader) USB download speed was 9707kB/s*

*OKAY \[  0.562s\]*

*writing 'boot'...*

*(bootloader) Download buffer format: boot IMG*

*(bootloader) Flash of partition 'boot' requested*

*(bootloader) S1 partID 0x0000000C, block 0x00000280-0x00000BeC*

*(bootloader) Erase operation complete, 0 bad blocks encountered*

*(bootloader) Flashing...*

*(bootloader) Flash operation complete*

*OKAY \[  1.109s\]*

*finished. total time: 1.672s*

Reboot your device, press volume done button many times during booting. (\* indeed, once is OK just after the front keypad is lighten.)

Using the menu with volume up/down and back to navigate, and Home (on some devices it is Power) button to select, wipe your user data, wipe your cache, and then install update zip file. Wait for the update is finished, then back to upper menu and select to restart the device.

Now you have <span class="il" style="background-color:#ffffcc;">Jelly</span> <span class="il" style="background-color:#ffffcc;">Bean</span>, which is now Android 4.1.1.
