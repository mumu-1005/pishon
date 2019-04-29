---
title: mysql允许远程访问操作
categories:
  - server
tags:
  - MySQL
  - 服务器配置
comments: false
date: 2016-11-05 14:35:51
updated: 2016-11-05 14:35:51
img:
---
### 终端操作

- ##### 1、先在服务器中通过命令行方式登录mysql： mysql -uroot -p密码 

- ##### 2、执行use mysql; 

- ##### 3、执行grant all privileges on *.* to root@'%' identified by '密码'; 

- ##### 4、执行flush privileges; 
<br>

### 数据库管理中心操作
##### 在user表中将相应用户对应的host改为“%”​