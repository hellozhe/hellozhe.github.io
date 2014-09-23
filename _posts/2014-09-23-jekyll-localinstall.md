---
layout: post
title: jekyll本地环境的安装
category: TECO
tags: jekyll
keywords: jekyll
description: MAC Jekyll本地环境安装
---

## MAC下安装jekyll 本地环境

* ruby
ruby环境1.9.3
* 安装jekky
    1.  更换gem source

            gem sources -l
            gem sources --remove https://rubygems.org/
            gem sources -a http://ruby.taobao.org/

    2. 安装jekyll

            gem install jekyll


    3. 运行jekyll环境

        到代码目录运行

            jekyll server

* key
