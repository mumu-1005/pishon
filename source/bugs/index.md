---
title: bugs
date: 2019-07-06 16:10:01
---

## 2019-01-12

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

## 2018-11-23

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

## 2017-08-06

### ISSUE-refusing to merge unrelated histories
```
fatal: refusing to merge unrelated histories   
        ```
### SOLUTION
```
git pull origin master --allow-unrelated-histories
```
<hr>

## 2016-03-16

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

## 2014-04-24 

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

