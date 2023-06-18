+++
title = "IDE性能监测"
date = 2023-06-17T19:06:58+08:00
description = ""
isCJKLanguage = true
draft = false
+++
# IDE performance monitor﻿

https://www.jetbrains.com/help/go/activity-monitor.html

Last modified: 01 July 2021

> Activity Monitor is an experimental feature in GoLand.

In case of performance issues, you can use Activity Monitor to track the percentage of CPU consumed by various subsystems and plugins.

1. From the main menu, select Help | Diagnostic Tools | Activity Monitor.
2. The Activity Monitor window lists all subsystems and plugins that are consuming CPU at the moment and arranges them by how much %CPU they are using:

If you notice increased CPU consumption, and no indexing or background processes are running at this moment, we recommend that you [contact](https://intellij-support.jetbrains.com/hc/en-us/?intellij-idea) our technical support for assistance. Background processes are always displayed in the status bar at the bottom of the IDE window.