---
layout: default
title: NetBeans Integration with RVM
permalink: /integration/netbeans/
---

# NetBeans Integration with RVM

There is a great writeup on how to properly use RVM inside netbeans by
[Alan Skorkin](http://www.skorks.com/2010/01/using-multiple-rubies-seamlessly-on-the-one-machine-with-rvm/comment-page-1/#comment-3422)

If you use netbeans you should really read Alan's writeup.

Additionally, thanks to our friendly mr-interweb on IRC a hint on gems with netbeans

> 13:46 mr-interweb: Netbeans was detecting the wrong gem root


> 13:48 mr-interweb: Just a FYI in case other people have problems with
Netbeans, Netbeans does not allow you to type in a path. You must browse to the
path, but it will not show you hidden folders. So, you must create symbolic
links like "ln -s ~/.gem ~/gem"
