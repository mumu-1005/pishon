---
title: PSQL序
categories:
  - SQL
tags:
  - tools
  - Postgre SQL
comments: false
date: 2019-08-26 23:53:18
updated: 2019-08-26 23:53:18
img:
---
<div hidden="true">psql常用命令</div>
<!-- more -->


### 切换到postgres用户进入数据库控制台
{% codeblock lang:shell hightlight:true %}
sudo -u postgres psql
{% endcodeblock %}

### 创建新数据库
{% codeblock  lang:sql hightlight:true %}
create database newdbname [owner username]
{% endcodeblock %}

### 赋予用户数据库所有权限
{% codeblock  lang:sql hightlight:true %}
grant all privileges on database dbname to username
{% endcodeblock %}

### 更改数据库owner
{% codeblock  lang:sql hightlight:true %}
alter database dbname owner to username
{% endcodeblock %}

### 查看所有数据库列表 
{% codeblock  lang:sql hightlight:true %}
\l
{% endcodeblock %}

### 连接数据库
{% codeblock  lang:sql hightlight:true %}
\c dbname 
{% endcodeblock %}

### 显示所有的schema
{% codeblock  lang:sql hightlight:true %}
\dn
{% endcodeblock %}

### 显示所有的用户
{% codeblock  lang:sql hightlight:true %}
\du
{% endcodeblock %}

### 显示表的权限分配情况
{% codeblock  lang:sql hightlight:true %}
\dp
{% endcodeblock %}

### 显示当前的模式
{% codeblock  lang:sql hightlight:true %}
show search_path
{% endcodeblock %}

### 更改模式
{% codeblock  lang:sql hightlight:true %}
set search_path to myschema
{% endcodeblock %}

### 已列的形式展示或取消
{% codeblock  lang:sql hightlight:true %}
\x 
{% endcodeblock %}

### 查看所有表
{% codeblock  lang:sql hightlight:true %}
\dt
{% endcodeblock %}

### 显示执行时间
{% codeblock  lang:sql hightlight:true %}
\timing on     
{% endcodeblock %} 

### 关闭显示执行时间
{% codeblock  lang:sql hightlight:true %}
\timing off
{% endcodeblock %}

### 禁用全表扫描
{% codeblock  lang:sql hightlight:true %}
alter role rolename set enable_seqscan = off;
set enable_seqscan = off;
{% endcodeblock %}