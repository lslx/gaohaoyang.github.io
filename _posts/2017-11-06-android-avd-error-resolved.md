---
layout: post
title:  "android 模拟器启动错误"
categories: daliy
tags:  avd
author: lslx
---

# android 模拟器启动错误的解决

环境：ubuntu 16.04 64位安装 android studio 3.0
创建模拟器后，启动模拟器，报错：
```
emulator process finished with exit code 1
```
原因：模拟器加载库不正确

解决办法有三种，推荐第三种
1. 使用命令行
```
~/Android/Sdk/tools/emulator -use-system-libs -avd YOUR_AVD_NAME
```
2. 创建符号链接，[参考](https://stackoverflow.com/questions/42872128/android-emulator-does-not-work-on-ubuntu-16-10)
```
mv ~/Android/Sdk/emulator/lib64/libstdc++/libstdc++.so.6{,.bak}
mv ~/Android/Sdk/emulator/lib64/libstdc++/libstdc++.so.6.0.18 {,.bak}
ln -s /usr/lib/libstdc++.so  ~/Android/Sdk/emulator/lib64/libstdc++/
```
3. 安装缺少的32位库，[参考](https://developer.android.com/studio/install.html?hl=zh-cn)
```
sudo apt-get install lib32z1 lib32ncurses5 lib32stdc++6
```























