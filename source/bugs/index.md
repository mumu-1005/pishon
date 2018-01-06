---
title: bugs
date: 2019-07-06 16:10:01
---

## 2016-03-16

### ISSUE
端口占用无法启动Apache
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
E/AndroidRuntime(439): Caused by: java.lang.ClassCastException: android.app
 

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

