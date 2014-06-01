---
layout: post
title: Mirror the Raspberry Pi X server
---

Steps to mirror the Raspberry Pi X server on your machine:

Install [Xephyr](http://en.wikipedia.org/wiki/Xephyr "Xephyr on wikipedia") on your linux machine
{% highlight sh %}$ sudo pacman -S xorg-server-xephyr{% endhighlight %}

Launch Xephyr Server in Gnome. Open a terminal and type:
{% highlight sh %}$ Xephyr -ac -br -noreset -screen 1366x768 :1{% endhighlight %}

Connect to RPI via ssh
  {% highlight sh %}$ ssh pi@rpi-ip{% endhighlight %}

Export RPI Display
{% highlight sh %}$ export DISPLAY=pc-ip:1{% endhighlight %}

Test Midory buy running "midori" in ssh terminal

In ssh terminal run your graphical environment (for instance LXDE)
{% highlight sh %}$ startlxde{% endhighlight %}
