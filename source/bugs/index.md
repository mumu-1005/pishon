---
title: bug集
date: 2019-07-05 20:10:19
---

## 2014-04-24 

### E/AndroidRuntime(439): Caused by: java.lang.ClassCastException: android.app

#### 原因：应用的程序名称没指定具体的Application的类

#### solution
①、在AndroidManifest.xml中的Application标签中添加名字
②、Progject->clean
③、重新运行

<hr>