---
title: nginx配置首页默认跳转路径
categories:
  - Nginx
tags:
  - Nginx
comments: false
date: 2016-09-09 11:23:58
updated: 2016-09-09 11:23:58
---
https指定路径跳转
```
rewrite ^/index.html(.*)$ 指定的跳转路径 permanent;
```

http跳转到https
```
server {
 listen 80;
 server_name localhost; 
 rewrite ^(.*)$ https://$host$1 permanent;
 location / {
index index.html index.htm;
}
```