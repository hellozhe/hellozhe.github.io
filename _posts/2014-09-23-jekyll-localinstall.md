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

    ruby环境2.1.2
    - 安装ruby

            curl -L get.rvm.io | bash -s stable
            rvm install ruby-2.1.2

* jekky
    1.  更换gem source

            gem sources -l
            gem sources --remove https://rubygems.org/
            gem sources -a http://ruby.taobao.org/

    2. 安装jekyll

            gem install jekyll

    3. 安装rdiscount(默认的解析markdown中文有点问题)
            
            gem install rdiscount

    4. 运行jekyll环境

        到代码目录运行,加上-w参数监测文件变化,自动重新编译

            jekyll server -w


---

### tips
- 设置字符的全局变量 

        LC_ALL=en_US.UTF-8

- Error: invalid byte sequence in US-ASCII #2379 解决方法
    1. 找到jekyll.rb文件并编辑

             find / -name  "jekyll.rb"
    2. 找到`clean_path.gsub!(/\A\w\:\//, '/')` ,替换为`clean_path.force_encoding('UTF-8').gsub!(/\A\w\:\//, '/')`
