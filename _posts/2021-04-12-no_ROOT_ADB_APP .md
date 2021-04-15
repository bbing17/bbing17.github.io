---
layout: mypost
title: 无需ROOT 使用ADB禁用系统APP
categories: [玩机]
---
## 准备工作
1. 下载*ADB*工具，解压，不需要加系统环境变量啥的（网上都有找一找就可以了）
2. 手机打开*开发者模式*，点开*USB调试*
3. 打开*CMD*，进入*adb路径*

（完成以上三步就可以开始操作了）
<!--more-->

## 手机连接电脑

命令`adb devices`，先看看手机有没有正确链接

命令`adb shell pm list packages`，列出手机上安装的所有应用的包名

命令`adb shell pm disable-user xx包名`，禁用某个APP

命令`adb shell pm enable xx包名`，启用某个APP

命令`adb shell pm uninstall --user 0 包名`，卸载某个APP（想保留APP数据在包名前面加参数 -k）

命令`adb install -r 包名`，安装某个APP
