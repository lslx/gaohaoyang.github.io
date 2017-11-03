---
layout: post
title:  "blog写作环境搭建"
categories: meta
tags:  markdown
author: lslx
---


* content
{:toc}
安装本地测试环境：

```
sudo apt install ruby-full
sudo apt install rubygems

# this cmd will show error dont warry
sudo gem update --system
sudo gem install jekyll
```
克隆blog到本地
```
mkdir blog
cd blog
git clone git@github.com:lslx/lslx.github.io.git
```
下载markdown编辑器[remarkable](http://remarkableapp.github.io/linux/download.html)
安装：
```
sudo dpkg -i remarkable_1.87_all.deb 
# 上一个命令因依赖问题出错，则用此命令修复
sudo apt -f install
```
remarkable 打开并编辑
```
cd lslx.github.io/_posts
remarkable  2017-11-01-xxx.md
```
保存后启动服务器
```
cd ~/blog/lslx.github.io
jekyll s
```
本地测试：
```
google-chrome http://localhost:4000/
```
提交到github
```
cd ~/blog/lslx.github.io
git status
git commit -am "come comment"
git push origin master
```
公网测试
```
google-chrome https//lslx.github.io
```



























