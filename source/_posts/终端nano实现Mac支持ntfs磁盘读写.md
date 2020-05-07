---
title: 终端nano实现Mac支持ntfs磁盘读写
categories:
  - TOOLS
tags:
  - tools
  - macOS
  - NTFS
comments: false
date: 2019-01-28 15:05:26
updated: 2019-01-28 15:05:26
---
<div hidden="true">无需安装第三方软件（如：Paragon NTFS、Mounty）实现Mac支持ntfs磁盘读写</div>
<!-- more -->

无需安装第三方软件（如：Paragon NTFS、Mounty）实现Mac支持ntfs磁盘读写

之前已经实现了cc盘的可读写挂载，现在进行另外三个盘的修改

## 先获取三个磁盘的UUID

### 关于本机
![image](https://uploader.shimo.im/f/rRCbnOsb7NlLxOt5.png!thumbnail)

### 选取 系统报告
![image](https://uploader.shimo.im/f/391t3hxDKb0soP0Q.png!thumbnail)

### 记下磁盘对应的UUID
![image](https://uploader.shimo.im/f/dDeR60P1dpbUDTRH.png!thumbnail)

## 在nano中添加设置

### 在终端输入sudo nano /etc/fstab 进入编辑界面

![image](https://uploader.shimo.im/f/zgUD21EhXkdk7ibI.png!thumbnail)

### 现在你看到了一个编辑界面
![image](https://uploader.shimo.im/f/64BCAKyfFEWPY03j.png!thumbnail)

### 分别输入三个磁盘的设置

- UUID=硬盘对应的UUID号码 none ntfs rw,auto,nobrowse
- 换行回车

![image](https://uploader.shimo.im/f/R2fQY06KxPkOgFmw.png!thumbnail)
### Ctrl+X保存
![image](https://uploader.shimo.im/f/Uzuw4RCHaMohtKLD.png!thumbnail)
### 确认保存操作 敲击Y
![image](https://uploader.shimo.im/f/YCJi5Cef0XDZdVGF.png!thumbnail)
### 回车 退出当前编辑窗口

![image](https://uploader.shimo.im/f/T7phDg1zjnbIk8gi.png!thumbnail)

## 设置成功 查看磁盘读写效果
### 推出磁盘，
![image](https://uploader.shimo.im/f/o8JlDT4FwcN3fE17.png!thumbnail)
### 重新插入，发现Finder中没有显示这几个盘

#### Finder左上角工具栏中选择 前往 -> 前往文件夹

#### 输入/Volumes/
![image](https://uploader.shimo.im/f/mXygxR4jU3bBgfEu.png!thumbnail)

#### 出现所有的磁盘信息

![image](https://uploader.shimo.im/f/syKzkIVMVhbjTnWU.png!thumbnail)
#### 将磁盘拉到左边边栏列表中 设置磁盘快捷访问
![image](https://uploader.shimo.im/f/MGudgYu6pxJ1ml3K.png!thumbnail)
![image](https://uploader.shimo.im/f/WQyqTOT3W9IjMHiT.png!thumbnail)
#### 查看效果 已经可以进行写操作了
![image](https://uploader.shimo.im/f/p1RKGPWTfJKnPKZ7.png!thumbnail)
