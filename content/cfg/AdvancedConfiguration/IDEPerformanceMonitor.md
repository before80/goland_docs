+++
title = "IDE性能监测"
date = 2023-06-17T19:06:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# IDE performance monitor﻿ - IDE性能监视器

https://www.jetbrains.com/help/go/activity-monitor.html

Last modified: 01 July 2021

最后修改日期：2021年7月1日

> Activity Monitor is an experimental feature in GoLand.
>
> 活动监视器是GoLand的一个实验性功能。

In case of performance issues, you can use Activity Monitor to track the percentage of CPU consumed by various subsystems and plugins.

​	在出现性能问题时，您可以使用活动监视器来跟踪各个子系统和插件消耗的CPU百分比。 

1. From the main menu, select Help | Diagnostic Tools | Activity Monitor.
2. The Activity Monitor window lists all subsystems and plugins that are consuming CPU at the moment and arranges them by how much %CPU they are using:
3. 从主菜单中选择 Help | Diagnostic Tools | Activity Monitor。
4. 活动监视器窗口列出了当前消耗CPU的所有子系统和插件，并按它们使用的%CPU大小进行排列：

If you notice increased CPU consumption, and no indexing or background processes are running at this moment, we recommend that you [contact](https://intellij-support.jetbrains.com/hc/en-us/?intellij-idea) our technical support for assistance. Background processes are always displayed in the status bar at the bottom of the IDE window.

​	如果您注意到增加的CPU消耗，并且此时没有进行索引或后台进程，请建议您联系我们的技术支持以获取帮助。后台进程始终显示在IDE窗口底部的状态栏中。