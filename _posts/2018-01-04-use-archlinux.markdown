---
layout: post
title:  "使用Archlinux"
date:   2018-01-04 22:22:18 +0800
categories: jekyll update
---

下载安装镜像文件：
```
wget http://mirrors.163.com/archlinux/iso/2018.01.01/archlinux-2018.01.01-x86_64.iso
```

也可以下载antergos，这是archlinux的一个比较容易入门的发行版。

https://antergos.com/download/antergos-live-iso/

```
wget http://mirrors.antergos.com/iso/release/antergos-17.12-x86_64.iso
```
下载后用dd命令制作U盘安装器
```
dd bs=4M if=/path/to/antergos-x86_64.iso of=/dev/sdX status=progress && 
sync
```

首先要安装字体
```
pacman -Sy wqy-zenhei
```
然后安装输入法
```
sudo pacman -S fcitx fcitx-table-extra 
fcitx-configtool fcitx-gtk2 fcitx-gtk3 fcitx-qt4 fcitx-qt5 
fcitx-googlepinyin
```
打开输入法进行配置即可
```
fcitx-configtool 
```

配置开机启动

```
nano ~/.xprofile
```
```
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx
```
