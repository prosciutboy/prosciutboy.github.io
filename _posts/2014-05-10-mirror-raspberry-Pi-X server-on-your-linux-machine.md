---
layout: post
title: Mirror the Raspberry Pi X server
---

Steps to mirror the Raspberry Pi X server on your machine:

1. Install [Xephyr](http://en.wikipedia.org/wiki/Xephyr "Xephyr on wikipedia") on your linux machine
{% highlight sh %}pacman -S xorg-server-xephyr{% endhighlight %}
2. Launch Xephyr Server in Gnome. Open a terminal and type:
{% highlight sh %}Xephyr -ac -br -noreset -screen 1366x768 :1{% endhighlight %}
3. Connect to RPI via ssh
  {% highlight sh %}ssh pi@rpi-ip{% endhighlight %}
4. Export RPI Display
{% highlight sh %}export DISPLAY=pc-ip:1{% endhighlight %}
5. Test Midory buy running "midori" in ssh terminal
6. In ssh terminal run your graphical environment (for instance LXDE)
{% highlight sh %}$ startlxde{% endhighlight %}
