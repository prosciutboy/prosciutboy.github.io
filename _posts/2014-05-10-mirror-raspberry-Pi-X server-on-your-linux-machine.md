---
layout: post
title: mirror the Raspberry Pi X server
---

Steps to mirror the Raspberry Pi X server on your machine:
1. Install [Xephyr](http://en.wikipedia.org/wiki/Xephyr "Xephyr on wikipedia") on your linux machine
```Shell
pacman -S xorg-server-xephyr
```

2. Launch Xephyr Server in Gnome. Open a terminal and type:
```Shell
Xephyr -ac -br -noreset -screen 1366x768 :1
```

3. Connect to RPI via ssh
```Shell
ssh pi@rpi-ip
```

4. Export RPI Display
```Shell
export DISPLAY=pc-ip:1
```

5. Test Midory buy running "midori" in ssh terminal

6. In ssh terminal run your graphical environment (for instance LXDE)
```Shell
$ startlxde
```
