---
title: 攒点BUG
date: 2019-07-06 16:10:01
comments: false
---
<div style="display: inline-block;"><li><a href="#2019-04-20">2019-04-20</a></li></div>
<div style="display: inline-block; margin-left: 20px;"><li><a href="#2019-03-11">2019-03-11</a></li></div>
<div style="display: inline-block; margin-left: 20px;"><li><a href="#2019-01-12">2019-01-12</a></li></div>
<div style="display: inline-block; margin-left: 20px;"><li><a href="#2018-12-28">2018-12-28</a></li></div>
<div style="display: inline-block; margin-left: 20px;"><li><a href="#2018-11-23">2018-11-23</a></li></div>
<br>
<div style="display: inline-block;"><li><a href="#2018-07-17">2018-07-17</a></li></div>
<div style="display: inline-block; margin-left: 20px;"><li><a href="#2018-05-12">2018-05-12</a></li></div>
<div style="display: inline-block; margin-left: 20px;"><li><a href="#2018-04-28">2018-04-28</a></li></div>
<div style="display: inline-block; margin-left: 20px;"><li><a href="#2018-04-24">2018-04-24</a></li></div>
<div style="display: inline-block; margin-left: 20px;"><li><a href="#2018-02-22">2018-02-22</a></li></div>
<br>
<div style="display: inline-block;"><li><a href="#2018-01-23">2018-01-23</a></li></div>
<div style="display: inline-block; margin-left: 20px;"><li><a href="#2017-12-30">2017-12-30</a></li></div>
<div style="display: inline-block; margin-left: 20px;"><li><a href="#2017-08-06">2017-08-06</a></li></div>
<div style="display: inline-block; margin-left: 20px;"><li><a href="#2016-03-16">2016-03-16</a></li></div>
<div style="display: inline-block; margin-left: 20px;"><li><a href="#2014-04-24">2014-04-24</a></li></div>
<br>

<h2 id="2019-04-20">2019-04-20</h2> 

### ISSUE
{% codeblock %}
ERROR: more than one row returned by a subquery used as an expression
{% endcodeblock %}
### SOLUTION
{% codeblock lang:sql %}
SELECT
    field1,field2,
    (select ARRAY_AGG(field3) from b where exp) 
FROM
    a 
WHERE
     exp
ORDER  BY
    field1;
{% endcodeblock %}
<hr>

<h2 id="2019-03-11">2019-03-11</h2>

### ISSUE

{% codeblock lang:python %}
# 连接中断，返回的相应大小被限制在127.86kb
SIGPIPE: writing to a closed pipe/socket/fd (probably the client disconnected) on request /project/api/ !!!
uwsgi_response_write_body_do(): Broken pipe [core/writer.c line 341] during GET /project/api/ 
IOError: write error
{% endcodeblock%}

### SOLUTION

{% codeblock lang:shell %}
# 打开Nginx配置文件 调整默认的限制缓存大小 根据实际业务调整
uwsgi_buffers 8 512k;   默认为8 4k  8为数量
{% endcodeblock %}

<hr>

<h2 id="2019-01-12">2019-01-12</h2>

### ISSUE
```
Crypto/PublicKey/RSA.py", line 375, in decrypt
    raise NotImplementedError("Use module Crypto.Cipher.PKCS1_OAEP instead")
NotImplementedError: Use module Crypto.Cipher.PKCS1_OAEP instead    
        ```
### SOLUTION
```
pip uninstall pycryptodome
pip uninstall pycrypto
pip install pycrypto
```
<hr>

<h2 id="2018-12-28"> 2018-12-28</h2>

### ISSUE-dpkg删除/安装未完全安装的软件包
```
installed python-lockfile package post-installation script subprocess returned error exit status 127
        ```
### SOLUTION
```
sudo apt-get install -f --reinstall coreutils init-system-helpers
```
<hr>

<h2 id="2018-11-23"> 2018-11-23</h2>

### ISSUE-强制关闭Redis快照导致不能持久化
```
MISCONF Redis is configured to save RDB snapshots, but is currently not able to 
persist on disk. Commands that may modify the data set are disabled. Please 
check Redis logs for details about the error.    
        ```
### SOLUTION
```
127.0.0.1:6379> config set stop-writes-on-bgsave-error no
```
<hr>

<h2 id="2018-07-17">2018-04-24</h2> 

### ISSUE
{% codeblock %}
ValueError: Expecting property name enclosed in double quotes: line 1 column 2 (char 1)
{% endcodeblock %}
### SOLUTION
{% codeblock %}
# 将json中的单引号改成双引号
{% endcodeblock %}
<hr>

<h2 id="2018-05-12">2018-04-24</h2> 

### ISSUE
{% codeblock %}
selenium.common.exceptions.InvalidSelectorException: Message: Compound class names not permitted
{% endcodeblock %}
### SOLUTION
{% codeblock %}
在selenium元素定位中复合class，取一个class名即可
{% endcodeblock %}
<hr>

<h2 id="2018-04-28">2018-04-28</h2> 

### ISSUE
{% codeblock %}
Your password does not satisfy the current policy requirements
{% endcodeblock %}
### SOLUTION
{% codeblock %}
SHOW VARIABLES LIKE 'validate_password%';
set global validate_password_policy=LOW; 
ALTER USER 'root'@'localhost' IDENTIFIED BY '123456'; 
{% endcodeblock %}
<hr>

<h2 id="2018-04-24">2018-04-24</h2> 

### ISSUE
{% codeblock %}
NameError: name '__main__' is not defined
{% endcodeblock %}
### SOLUTION
{% codeblock %}
if __name__ == '__main__':
{% endcodeblock %}
<hr>

<h2 id="2018-02-22">2018-02-22</h2> 

### ISSUE
{% codeblock %}
>>> eval(a)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "<string>", line 1, in <module>
NameError: name 'null' is not defined
{% endcodeblock %}
### SOLUTION
{% codeblock %}
>>> json.loads(a)
{% endcodeblock %}
<hr>

<h2 id="2018-01-23">2018-01-23</h2> 

### ISSUE
{% codeblock %}
SyntaxError: Non-ASCII character '\xe4' in file
{% endcodeblock %}
### SOLUTION
{% codeblock %}
# Python将ASCII作为默认的标准编码，要定义源代码编码，必须在源文件中第一行放置一个魔术注释
# -*- coding: utf-8 -*-
{% endcodeblock %}
<hr>

<h2 id="2017-12-30">2017-12-30</h2> 

### ISSUE
{% codeblock %}
Ubuntu安装包时报错 E:Unable to locate package xxx
{% endcodeblock %}
### SOLUTION
{% codeblock %}
apt-get update
{% endcodeblock %}
<hr>

<h2 id="2017-08-06">2017-08-06</h2>

### ISSUE-refusing to merge unrelated histories
```
fatal: refusing to merge unrelated histories   
        ```
### SOLUTION
```
git pull origin master --allow-unrelated-histories
```
<hr>

<h2 id="2016-03-16">2016-03-16</h2>

### ISSUE-端口占用无法启动Apache
		```
XAMPP: Starting Apache...fail.
XAMPP:  Another web server is already running.    
        ```
### SOLUTION
```
in bash：
// killed Apache server that was pre-installed on MAC OS X.
sudo apachectl stop
```
<hr>

<h2 id="2014-04-24">2014-04-24</h2>

### ISSUE
```
E/AndroidRuntime(439): Caused by: java.lang.ClassCastException: 
android.app
```

### SOLUTION
- 原因：应用的程序名称没指定具体的Application的类
- 步骤
  - 在AndroidManifest.xml中的Application标签中添加名字
  `
  <application
  	android:name="com.shelling.ans.AnsApplication"
  `
  - Progject->clean
  - 重新运行

<hr>

