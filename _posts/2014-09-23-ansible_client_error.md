---
layout: post
title: ansible受控节点报错
category: TECO
tags: ansible
keywords: ansible
description:
---

# ansible

### 受控节点(被管理的服务器)
1. python 2.4版本 会报错"msg": "Error: ansible requires a json module, none found!
需要安装 `python-simplejson`

        for i in `cat ip.list`;do echo $i;ssh -oUserKnownHostsFile=/dev/null -oStrictHostKeyChecking=no root@$i "yum install python-simplejson.x86_64 -y";done

<!-- create time: 2014-09-18 10:00:43  -->

