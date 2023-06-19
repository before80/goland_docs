+++
title = "更改IDE的启动Java运行时"
weight = 20
date = 2023-06-17T19:06:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Change the boot Java runtime of the IDE﻿ 更改IDE的启动Java运行时

https://www.jetbrains.com/help/go/switching-boot-jdk.html



Last modified: 10 March 2023

最后修改日期：2023年3月10日

As a Java application, GoLand requires a Java runtime environment (JRE). By default, GoLand uses [JetBrains Runtime](https://github.com/JetBrains/JetBrainsRuntime) (a fork of [OpenJDK](https://github.com/openjdk/jdk)), which is included with the IDE. JetBrains Runtime fixes various known OpenJDK and Oracle JDK bugs, and provides better performance and stability. However, in some cases you may be required to use another Java runtime or a specific version of JetBrains Runtime.

​	作为一个Java应用程序，GoLand需要一个Java运行时环境（JRE）。默认情况下，GoLand使用[JetBrains Runtime](https://github.com/JetBrains/JetBrainsRuntime)（一个基于[OpenJDK](https://github.com/openjdk/jdk)的分支），该运行时环境已包含在IDE中。JetBrains Runtime修复了各种已知的OpenJDK和Oracle JDK的错误，并提供更好的性能和稳定性。然而，在某些情况下，您可能需要使用其他Java运行时或特定版本的JetBrains Runtime。

> Changing the boot Java runtime may cause unexpected problems. Do not change it unless you were specifically asked to do so by [JetBrains support](https://www.jetbrains.com/support/).
>
> 更改启动Java运行时可能会导致意外问题。除非经[JetBrains支持团队](https://www.jetbrains.com/support/)特别要求，否则不要更改它。

> The runtime for GoLand is not the same runtime used for your applications. Define an SDK for each of your projects, which includes the necessary development and runtime environment.
>
> ​	GoLand的运行时与您的应用程序所使用的运行时不同。为每个项目定义一个包含所需开发和运行时环境的SDK。

### Switch the Java runtime used to run GoLand﻿ 切换用于运行GoLand的Java运行时

1. From the main menu, select Help | Find Action or press Ctrl+Shift+A.

1. Find and select the Choose Boot Java Runtime for the IDE action.

2. Select the new desired runtime and click OK.

   If necessary, you can change the location where GoLand will download the selected runtime.

3. Wait for GoLand to restart with the new runtime.

4. 从主菜单中选择 Help | Find Action 或按下 Ctrl+Shift+A。

5. 查找并选择 Choose Boot Java Runtime for the IDE 操作。

6. 选择新的期望运行时并点击 OK。

   如果需要，您可以更改GoLand将下载所选运行时的位置。

7. 等待GoLand以新的运行时重新启动。

When you open the Choose Boot Runtime for the IDE dialog for the first time, it may take a while to load the list of JetBrains Runtime builds from the server.

​	首次打开Choose Boot Runtime for the IDE对话框时，从服务器加载JetBrains Runtime构建列表可能需要一些时间。

![Choose Boot Runtime for the IDE](ChangeBootRuntime_img/choose-boot-java-runtime-for-ide.png)

To use a different Java runtime available on your computer, select Add Custom Runtime… under Advanced in the New field. GoLand lists all the JDKs and JREs that it was able to detect. Select one or click Add JDK to specify the location of the desired Java home directory.

​	要使用计算机上可用的其他Java运行时，请在高级选项中选择 "Add Custom Runtime…"。GoLand会列出所有它能够检测到的JDK和JRE。选择一个或者点击 "Add JDK" 指定所需Java主目录的位置。

To reset back to the default runtime that the IDE initially used, click Use Default Runtime.

​	要重置回IDE最初使用的默认运行时，请点击 "Use Default Runtime"。

> When using a non-default Java runtime for GoLand, it will not update with the IDE and may not be compatible with the new version. Reset back to the default runtime when updating GoLand to get the latest compatible version of JetBrains Runtime.
>
> ​	在为GoLand使用非默认的Java运行时时，它将不会与IDE一起更新，也可能与新版本不兼容。在更新GoLand时，重置回默认运行时以获取最新兼容的JetBrains Runtime版本。

The path to the selected runtime is stored in the **goland.jdk** or **goland64.jdk** file in the GoLand [configuration directory](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory). If there are problems with the selected runtime, you can delete this file to revert to the default runtime.

​	所选运行时的路径存储在GoLand的[配置目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory)中的 **goland.jdk** 或 **goland64.jdk** 文件中。如果选择的运行时出现问题，您可以删除此文件以恢复默认运行时。

You can also override the runtime used for GoLand by adding the `GOLAND_JDK` environment variable with the path to the desired JDK home directory.

​	您还可以通过添加 `GOLAND_JDK` 环境变量并设置为所需JDK主目录的路径来覆盖GoLand使用的运行时。