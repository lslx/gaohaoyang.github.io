---
layout: post
title:  "工作环境设置"
categories: meta
tags:  env
author: lslx
---
# 工作环境
## 1. 需求

- 编译android主流版本4.x, 5.x, 6.x, 7.x, 8.x
- 多开虚拟机，模拟器
## 2.硬件环境
 **最低硬件环境**
- 至少16g ram
- 至少1t硬盘

## 3.软件环境（任选其一）
- ubuntu 14.04
- ubuntu 16.04
- ubuntu 17.04

## 4.不能使用的环境和原因
**1. 为什么不用windows**
- 官方不支持用windows编译android
- windows原生脚本环境很差，新的powershell在完成常规任务时太繁琐，并且适用范围局限于平台
- 闭源不适合作为逆向工作平台，而仅应该作为逆向目标。

**2. 为什么不用mac**
- 虽然是可编译android的，但坑很多，支持不完整，模拟器不能编译运行，此情况在未来也不会有所改善。
- 有很多相关工具根本没有mac版本，或者支持很差，具体就不列举了。
- 作为逆向工程平台mac并不友好，很多逆向工具对mac支持较差。
- 闭源不适合作为逆向工作平台，而仅应该作为逆向目标。

**3. 为什么不用非ubuntu环境**
- 因为ubuntu为官方指定编译环境。
- 非ubuntu环境也可能编译成功，但需要付出不必要的精力。

## 5.实际使用的软硬件环境
-  硬件：32g ram，2t 固态硬盘
- 操作系统： ubuntu16.04
##  6.系统安装
原系统xps15-9560，内存增至32G，硬盘增至2T固态（双固态都是1T容量），原为windows10 正版，现增加ubuntu16.04成为双系统。
原windows装于sandy固态，现将ubuntu16.04安装于另一个固态steam。分区方案：

- 根（/）：100G
- swap：10G
- home：其余空间（大概900G）
## 7.其他软件
###系统类
- qemu
- vmware
- vbox
###沟通类
-  邮件客户端
- qq（需要安装在虚拟机中）否则坑大:[Ubuntu 16.04 安装QQ解决方案](http://blog.csdn.net/fuchaosz/article/details/51919607)
- 微信

### 逆向工具类
 - as： 可调framework和用户dex，用户态so
- gdb：可调用户态execute，so
- jdb：可调framework和用户dex
- strace：可追踪无自调试保护的进程或进程组的系统调用
- ftrace：可追踪进程或进程组的系统调用，无论有没有自调试
- kprobes：可追踪几乎任何内核态函数，无论是否为系统调用。（用来跟踪工具，探查原理）
- uprobes: 可追踪用户态函数调用。
- kdump：  可用于dump系统内核。
- crash-utility：用于查看系统dump，或者运行中的内核，包括用户态进程。
- gdb-kgdb: 用于实时调试整个系统，包括用户态进程。（用来绕过几乎所有的反调试，包括自调试保护）
- ida:     用于静态分析，或动态调试 （更适合静态分析）
- 010editor: 分析变异的二进制
- beyondcompare: 对比文件或文件夹
- panda：基于qemu的逆向平台





















