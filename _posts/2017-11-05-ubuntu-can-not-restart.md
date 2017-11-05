---
layout: post
title:  "ubuntu 不能重启（死机）"
categories: meta
tags:  markdown
author: lslx
---

# ubuntu 16.04 死机问题
dell xps上安装了ubuntu16.04后，时常死机，当注销，重启，关机，任一操作执行时发生，不论通过gui操作还是命令行。经查，原因为nvidia驱动导致。解决办法：
```
sudo apt-get upgrade
sudo apt-get dist-upgrade
sudo ubuntu-drivers devices
sudo apt-get install nvidia-384
```

更新驱动期间提示需关闭UEFI Secure Boot
```
Your system has UEFI Secure Boot enabled. UEFI Secure Boot is not compatible with the use of third-party drivers. The system will assist you in toggling UEFI Secure Boot. To ensure that this change is being made by you as an authorized user, and not by an attacker, you must choose a password now and then use the same password after reboot to confirm the change. If you choose to proceed but do not confirm the password upon reboot, Ubuntu will still be able to boot on your system but the Secure Boot state will not be changed. If Secure Boot remains enabled on your system, your system may still boot but any hardware that requires third-party drivers to work correctly may not be usable.  
```

结果不关闭也解决了死机问题。但是不关闭会在安装其他软件的时候出现问题，条件是此软件含有内核驱动部分，建议还是关掉。比如安装vbox时
```
invoke-rc.d: initscript virtualbox, action "restart" failed.
● virtualbox.service - LSB: VirtualBox Linux kernel module
   Loaded: loaded (/etc/init.d/virtualbox; bad; vendor preset: enabled)
   Active: failed (Result: exit-code) since 日 2017-11-05 19:04:49 CST; 7ms ago
     Docs: man:systemd-sysv-generator(8)
  Process: 23151 ExecStart=/etc/init.d/virtualbox start (code=exited, status=1/FAILURE)

11月 05 19:04:49 fhc-XPS-15-9560 systemd[1]: Starting LSB: VirtualBox Linux kernel module...
11月 05 19:04:49 fhc-XPS-15-9560 virtualbox[23151]:  * Loading VirtualBox kernel modules...
11月 05 19:04:49 fhc-XPS-15-9560 virtualbox[23151]:  * No suitable module for running kernel found
11月 05 19:04:49 fhc-XPS-15-9560 virtualbox[23151]:    ...fail!
11月 05 19:04:49 fhc-XPS-15-9560 systemd[1]: virtualbox.service: Control process exited, code=exit...s=1
11月 05 19:04:49 fhc-XPS-15-9560 systemd[1]: Failed to start LSB: VirtualBox Linux kernel module.
11月 05 19:04:49 fhc-XPS-15-9560 systemd[1]: virtualbox.service: Unit entered failed state.
11月 05 19:04:49 fhc-XPS-15-9560 systemd[1]: virtualbox.service: Failed with result 'exit-code'.
Hint: Some lines were ellipsized, use -l to show in full.
正在设置 virtualbox-qt (5.0.40-dfsg-0ubuntu1.16.04.1) ...
正在处理用于 libc-bin (2.23-0ubuntu9) 的触发器 ...
/sbin/ldconfig.real: /usr/lib/nvidia-384/libEGL.so.1 is not a symbolic link

/sbin/ldconfig.real: /usr/lib32/nvidia-384/libEGL.so.1 is not a symbolic link

正在处理用于 systemd (229-4ubuntu21) 的触发器 ...
正在处理用于 ureadahead (0.100.0-19) 的触发器 ...

```

























