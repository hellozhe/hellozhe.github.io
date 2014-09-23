---
layout: post
title: "check_mk_multisite_pnp4nagios"
description: ""
category: TECO
tags: check_mk
---

### check_mk multisite pnp4nagios

check_mk多机房监控，中控机如何取得远程监控机的pnp4naigos图

* 修改check_mk下的sites.mk,主要改GZ_MM远程机的选项,其中url_prefix的值要和远程监控机的入口目录一样

    ```
    cat sites.mk 
# Written by WATO
# encoding: utf-8

    sites = \
    {'GZ_MM': {'alias': u'GZ_MM',
               'disabled': False,
               'insecure': False,
               'multisiteurl': 'http://10.20.102.163/mm/check_mk/',
               'nagios_cgi_url': '/gz/nagios/cgi-bin',
               'nagios_url': '/gz/nagios/',
               'persist': False,
               'pnp_url': '/gz/pnp4nagios',
               'repl_priority': 0,
               'socket': 'tcp:10.20.102.163:6557',
               'timeout': 10,
               'url_prefix': '/gz/'},
     'MASTER': {'alias': u'BJ_ZW_MASTER',
                'disabled': False,
                'insecure': False,
                'multisiteurl': '',
                'persist': False,
                'repl_priority': 0,
                'timeout': 10}}
    ```
* 修改apache proxy 重定向到远程监控机的pnp4nagios

    ```
    cat /etc/httpd/conf.d/multisite_proxy.conf
    <Location /gz/>
    RewriteEngine On
    RewriteRule ^/.+/gz/(.*) http://10.20.102.163/gz/$1 [P]
    </Location>
    ```
* 重启apache && omd
