---
layout: mypost
title: PIXEL 2XL 刷机指南
categories: [玩机]
---

# PIXEL 2XL 刷机 root 指南

> 前提是你的 *PIXEL 2XL (bootloader已解锁)*

## 刷机

待补充

## 安装永久TWRP进RECOVERY

1. 手机里打开usb调试

2. 在计算机上，打开命令提示（在窗口上）或终端（在Linux或macOS）窗口，并键入：
`adb reboot bootloader`
您也可以通过键组合引导进入快速启动模式：
设备关闭后，按住`电源键 和 音量键下`

3. 设备重启模式后进入fastboot模式，通过键入来验证您的 PC 找到它：`fastboot devices`

4. 然后使用fastboot将临时TWRP刷入`fastboot boot twrp-3.x.x-x-taimen.img`

5. 进入install，刷入twrp-pixel2-installer-taimen-3.x.x-x，重启时不要安装TWRP app，选择上面的重启或进入rec。

## 安装Magisk给设备root

1. 手机进入bootloader模式，音量键下按两下看到*RECOVERY MODE*，按开机键进入**TWRP**。

2. 选*install*，安装Magisk 20.x，重启系统（**再说一遍不要安装TWRP的app**），看到桌面有Magisk Manager的面具说明root成功。

## 所需文件下载
- [TWRP 蓝奏云下载](https://bbing.lanzous.com/b010brccj)
- [magisk 蓝奏云下载](https://bbing.lanzous.com/b010brbmd)
密码:bbing.cc
