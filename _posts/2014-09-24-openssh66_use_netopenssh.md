---
layout: post
title: "使用Net::OpenSSH不读取 SSH的默认配置文件的方法"
description: ""
category: 
tags: []
---



我的一台服务器由于要做ansible的管理机,为了性能的提升,将openssh升级到6.6,并做了私有的配置,但是之前用的Perl的一个Net::OpenSSH模块不能使用了,报如下错误

        unable to establish master SSH connection: bad ssh master at /root/.libnet-openssh-perl/root-10.28.70.21-13814-629135, socket owned by pid 13872 (pid 13846 expected)

google了下解决方法:


```perl

my $ssh = Net::OpenSSH->new(
    $host,
    master_opts      => [ -F => '/dev/null' ],
    default_ssh_opts => [ -F => '/dev/null' ],
);

```

