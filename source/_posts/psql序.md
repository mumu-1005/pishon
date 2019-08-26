---
title: PSQL序
categories:
  - SQL
  - Postgre SQL
tags:
  - tools
comments: false
date: 2019-08-26 23:53:18
updated: 2019-08-26 23:53:18
img:
---

### 切换到postgres用户进入数据库控制台
{% codeblock %}
sudo -u postgres psql
{% endcodeblock %}

### 创建imsdb这个数据库
{% codeblock %}
create database imsdb [owner user]
{% endcodeblock %}

### 赋予用户所有权限
{% codeblock %}
grant all privileges on database imsdb to user
{% endcodeblock %}

### 更改数据库owner
{% codeblock %}
alter database imsdb owner to user
{% endcodeblock %}

### 查看所有数据库列表 
{% codeblock %}
\l
{% endcodeblock %}

### 连接数据库
{% codeblock %}
\c imsdb 
{% endcodeblock %}

### 显示所有的schema
{% codeblock %}
\dn
{% endcodeblock %}

### 显示所有的用户
{% codeblock %}
\du
{% endcodeblock %}

### 显示表的权限分配情况
{% codeblock %}
\dp
{% endcodeblock %}

### 显示当前的模式
{% codeblock %}
show search_path
{% endcodeblock %}

### 更改模式
{% codeblock %}
set search_path to myschema
{% endcodeblock %}

### 已列的形式展示或取消
{% codeblock %}
\x 
{% endcodeblock %}

### 查看所有表
{% codeblock %}
\dt
{% endcodeblock %}

### 显示执行时间
{% codeblock %}
\timing on     
{% endcodeblock %} 

### 关闭显示执行时间
{% codeblock %}
\timing off
{% endcodeblock %}

### 禁用全表扫描
{% codeblock %}
alter role xyh set enable_seqscan =off;
set enable_seqscan =off;
{% endcodeblock %}