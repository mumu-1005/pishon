---
title: bugs
date: 2019-07-06 16:10:01
---
## 2014-04-24 

### E/AndroidRuntime(439): Caused by: java.lang.ClassCastException: android.app

#### 原因：应用的程序名称没指定具体的Application的类

#### solution
①、在AndroidManifest.xml中的Application标签中添加名字

{% asset_img 001.png  %}

②、Progject->clean
③、重新运行

<hr>