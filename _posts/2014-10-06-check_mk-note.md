---
layout: post
title: "check_mk note"
description: ""
category: TECO
tags: [check_mk monitor]
---
{% include JB/setup %}

### Check_MK Packages

Check_MK Packages 简单来说就是check_mk的打包,可以建立,安装,升级,移除你的扩展通过包的方式

* 建立包

通过`cmk -P find`命令可以收集没打包的文件

`cmk -P create xxx`打包

`cmk -vP list`查看打包

另外可以在`~/var/check_mk/packages/xxx`看到描述文件,根据需要修改

最后通过`cmk -vP pack xxx`打包完成

其它的一些可以通过命令查看或者看[官方文档](http://mathias-kettner.com/checkmk_packaging.html)
