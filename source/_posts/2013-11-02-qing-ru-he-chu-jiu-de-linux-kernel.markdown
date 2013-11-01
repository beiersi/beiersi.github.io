---
layout: post
title: "如何清除旧的linux kernel"
date: 2013-11-02 00:13
comments: true
categories: 
---
前几天用aptitude upgrade升级，总是提示无法安装成功新的linux kernel，看到报错信息里面有以后bzip没有空间什么的（过了好几天，原文提示记不住了），df看了一下boot分区90%多了，网上搜索了一下，大概的解决办法应该删除之前旧的linux核心，可参考 [这里](http://askubuntu.com/questions/2793/how-do-i-remove-or-hide-old-kernel-versions-to-clean-up-the-boot-menu),执行命令：

dpkg -l 'linux-*' | sed '/^ii/!d;/'"$(uname -r | sed "s/\(.*\)-\([^0-9]\+\)/\1/")"'/d;s/^[^ ]* [^ ]* \([^ ]*\).*/\1/;/[0-9]/!d' | xargs sudo apt-get -y purge

。然后boot分区就有空间了。继续执行apt-get upgrade，成功升级。

