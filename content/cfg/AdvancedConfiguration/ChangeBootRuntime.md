+++
title = "更改IDE的启动Java运行时"
weight = 20
date = 2023-06-17T19:06:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Change the boot Java runtime of the IDE﻿ - 更改IDE的启动Java运行时

https://www.jetbrains.com/help/go/switching-boot-jdk.html



Last modified: 10 March 2023

最后修改日期：2023年3月10日

​	作为一个Java应用程序，GoLand需要一个Java运行时环境（JRE）。默认情况下，GoLand使用[JetBrains Runtime](https://github.com/JetBrains/JetBrainsRuntime)（一个基于[OpenJDK](https://github.com/openjdk/jdk)的分支），该运行时环境已包含在IDE中。JetBrains Runtime修复了各种已知的OpenJDK和Oracle JDK的错误，并提供更好的性能和稳定性。然而，在某些情况下，您可能需要使用其他Java运行时或特定版本的JetBrains Runtime。

> ​	更改启动Java运行时可能会导致意外问题。除非经[JetBrains支持团队](https://www.jetbrains.com/support/)特别要求，否则不要更改它。

> ​	GoLand的运行时与您的应用程序所使用的运行时不同。为每个项目定义一个 SDK，其中包括所需的开发和运行时环境。

### 切换用于运行GoLand的Java运行时

1. 从主菜单中选择 Help | Find Action 或按下 Ctrl+Shift+A。

5. 查找并选择 Choose Boot Java Runtime for the IDE 操作。

6. 选择新的期望运行时并点击 OK。

   如果需要，您可以更改GoLand将下载所选运行时的位置。

7. 等待GoLand以新的运行时重新启动。

​	首次打开Choose Boot Runtime for the IDE对话框时，从服务器加载JetBrains Runtime构建列表可能需要一些时间。

![Choose Boot Runtime for the IDE](ChangeBootRuntime_img/choose-boot-java-runtime-for-ide.png)

​	要使用计算机上可用的其他Java运行时，select Add Custom Runtime… under Advanced in the New field。GoLand会列出所有它能够检测到的JDK和JRE。选择一个或者点击 Add JDK指定所需Java主目录的位置。

​	要重置回IDE最初使用的默认运行时，请点击 Use Default Runtime。

> ​	在为GoLand使用非默认的Java运行时时，它将不会与IDE一起更新，也可能与新版本不兼容。在更新GoLand时，重置回默认运行时以获取最新兼容的JetBrains Runtime版本。

​	所选运行时的路径存储在GoLand的[配置目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory)中的 **goland.jdk** 或 **goland64.jdk** 文件中。如果选择的运行时出现问题，您可以删除此文件以恢复默认运行时。

​	您还可以通过添加 `GOLAND_JDK` 环境变量并设置为所需JDK主目录的路径来覆盖GoLand使用的运行时。