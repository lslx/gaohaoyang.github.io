---
layout: post
title:  "安装ubuntu16.04最新内核"
categories: meta
tags:  system
author: lslx
---

# 安装ubuntu最新内核

手动下载内核地址[下载内核4.13.11](http://kernel.ubuntu.com/~kernel-ppa/mainline/v4.13.11/)
或者命令下载并安装：
```
mkdir kernel4.13.11
cd kernel4.13.11/
wget http://kernel.ubuntu.com/~kernel-ppa/mainline/v4.13.11/linux-headers-4.13.11-041311-generic_4.13.11-041311.201711020532_amd64.deb
wget http://kernel.ubuntu.com/~kernel-ppa/mainline/v4.13.11/linux-headers-4.13.11-041311_4.13.11-041311.201711020532_all.deb
wget http://kernel.ubuntu.com/~kernel-ppa/mainline/v4.13.11/linux-image-4.13.11-041311-generic_4.13.11-041311.201711020532_amd64.deb
sudo dpkg -i *deb

```

重启后查看新内核版本
```
uname -r
```
显示
```
4.13.11-041311-generic
```
























