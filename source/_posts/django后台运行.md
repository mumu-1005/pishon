---
title: django后台运行
categories:
  - 'Python'
tags:
  - 'Python'
  - 'Django'
comments: false
date: 2018-10-21 16:21:25
updated: 2018-10-21 16:21:25
---
## 生效命令
``` sh
nohup python manage.py runserver &  #后台运行django server

exit  #退出控制台

tail -f nohup.out #监控运行过程中的输出
```
<hr>

## 命令解释
``` sh
nohup  # (no hang up) 不挂断地运行命令

&   # 在后台运行命令

nohup.out  # 会自动在当前目录创建该文件，记录原控制台输出内容
```

