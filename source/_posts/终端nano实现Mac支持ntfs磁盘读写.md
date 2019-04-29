---
title: 终端nano实现Mac支持ntfs磁盘读写
categories:
  - tools
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
{% asset_img local-1555860278719.png 关于本机 %}

### 选取 系统报告
{% asset_img local-1555860306877.png 选取系统报告 %}

### 记下磁盘对应的UUID
{% asset_img local-1555860356722.png 记下磁盘对应的UUID %}

## 在nano中添加设置

### 在终端输入sudo nano /etc/fstab 进入编辑界面

{% asset_img local-1555860081256.png 进入nano编辑界面 %}

### 现在你看到了一个编辑界面
{% asset_img local-1555860117975.png %}

### 分别输入三个磁盘的设置

- UUID=硬盘对应的UUID号码 none ntfs rw,auto,nobrowse
- 换行回车

{% asset_img local-1555860614792.png %}
### Ctrl+X保存
{% asset_img 02fa7fd6-cbc7-4880-a1c4-7010ff5c57cb.png %}
### 确认保存操作 敲击Y
{% asset_img 63c8e4fa-27eb-4197-812d-41ff57a5f96c.png %}
### 回车 退出当前编辑窗口

{% asset_img 4d24c25d-393d-4d9a-985d-5cf95932bbba.png %}

## 设置成功 查看磁盘读写效果
### 推出磁盘，
{% asset_img 0ec971da-e074-4682-91ac-3f8c0b7a3d51.png %}
### 重新插入，发现Finder中没有显示这几个盘

#### Finder左上角工具栏中选择 前往 -> 前往文件夹

#### 输入/Volumes/
{% asset_img 9b5ddcde-a262-4f18-a1ef-e3c5c7fc8e78.png %}

#### 出现所有的磁盘信息

{% asset_img 48d6bfd5-a5aa-41f7-8201-47b953517491.png %}
#### 将磁盘拉到左边边栏列表中 设置磁盘快捷访问
{% asset_img local-1555861146798.png %}
{% asset_img local-1555861184116.png %}
#### 查看效果 已经可以进行写操作了
{% asset_img 092eee2b-8405-40ce-a4ec-931f5bf99682.png %}
