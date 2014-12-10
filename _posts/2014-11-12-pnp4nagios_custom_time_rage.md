---
layout: post
title: "pnp4nagios_custom_time_rage"
description: ""
category:  TECO
tags: [omd]
---

今天用用omd自带的pnp4naios查看自定义时间的状态图报错,具体现象和[这个](https://github.com/lingej/pnp4nagios/issues/82)一样.
解决方法如下:
找到`/opt/omd/versions/1.20/share/pnp4nagios/htdocs/application/controllers/system.php`


```php
    - $this->start = pnp::clean($this->input->get('start',FALSE));
    - $this->end = pnp::clean($this->input->get('end',FALSE));
    + $this->start = $this->input->get('start',FALSE);
    + $this->end = $this->input->get('end',FALSE);
```


{% include JB/setup %}
