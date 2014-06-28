---
layout: post
title: 4.4.3/4.4.4 upgrade of rooted and Xposed Nexus 5
---

Uninstall Xposed (from the Xposed app itself, not from the setting/apps menu)

Download Nexus 5 [factory image](https://dl.google.com/dl/android/aosp/hammerhead-ktu84p-factory-35ea0277.tgz)

In case of OTA 4.4.3 uncompress the following files
*bootloader-hammerhead-hhz11k.img
*radio-hammerhead-m8974a-2.0.50.1.13.img
*boot.img
*system.img

Download latest [SuperSu UPDATE-SuperSU-v2.00.zip](http://download.chainfire.eu/supersu) and save it on the handset via MTP or adb command
{% highlight sh %}$ adb push UPDATE-SuperSU-v2.00.zip /sdcard/{% endhighlight %}

Download latest [TWRP recovery image](http://techerrata.com/browse/twrp2/hammerhead)

Shutdown the Nexus5, press vol- and vol+ and power buttons together until the N5 enter in fastboot mode

Then flash the images in the sequence below:
{% highlight sh %}
$ fastboot flash bootloader bootloader-hammerhead-hhz11k.img
$ fastboot reboot-bootloader
$ sleep 5 # safer to add in case of bash scripting
$ fastboot flash radio radio-hammerhead-m8974a-2.0.50.1.13.img
$ fastboot reboot-bootloader
$ sleep 5 # safer to add in case of bash scripting

$ fastboot flash boot boot.img
$ fastboot flash system system.img
$ fastboot erase cache
$ fastboot format cache
$ fastboot flash recovery openrecovery-twrp-2.7.0.0-hammerhead.img
{% endhighlight %}
