---
layout: post
title: "ansible学习笔记"
description: ""
category: TECO
tags: [ansible]
---
{% include JB/setup %}

### ansile-playbook

* 在task中的任务里加上`ingore_erros: True`可以跳过错误,继续往下执行

```yaml
cat check_mk_agent.yml 
---
- hosts: tmp
  sudo: yes
  tasks:
    - name: check_mk_agent_install
      command: rpm -ivh http://10.16.21.17/download/check_mk-agent-1.2.4p5-1.noarch.rpm 
      ignore_errors: True

    - name: check_mk_agent_copy
      copy: src=/opt/tools/files/check_mk_agent.linux dest=/usr/bin/check_mk_agent
```
