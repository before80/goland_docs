+++
title = "高级配置"
weight = 60
date = 2023-06-17T19:06:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Advanced configuration - 高级配置﻿

https://www.jetbrains.com/help/go/tuning-the-ide.html

Last modified: 04 August 2022

最后修改日期：2022年8月4日

​	除了可用的 IDE 设置标准选项外，GoLand 还允许您对底层平台和 Java 运行时进行低级配置。

> ​	如果您不确定自己在做什么，这可能会导致意外问题，并使您的 GoLand 安装无法正常运行。请联系[JetBrains 支持](https://intellij-support.jetbrains.com/hc/en-us)获取关于可能有助于解决问题的选项和值的说明。

## JVM 选项

​	GoLand 在 Java 虚拟机（JVM）上运行，该虚拟机具有控制性能的各种选项。用于运行 GoLand 的默认选项在 IDE 安装目录中指定为：

{{< tabpane text=true >}}

{{< tab header="Windows" >}}

`<IDE_HOME>\bin\goland64.exe.vmoptions`

{{< /tab >}}

{{< tab header="macOS" >}}

`GoLand.app/Contents/bin/goland.vmoptions`

{{< /tab >}}

{{< tab header="Linux" >}}

`<IDE_HOME>/bin/goland64.vmoptions`

{{< /tab >}}

{{< /tabpane >}}

> ​	请勿更改默认文件中的 JVM 选项，因为在更新 GoLand 时将替换它。此外，在 macOS 的情况下，编辑此文件会违反应用程序签名。

### 配置 JVM 选项

​	请执行以下操作，以在[配置目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory)中创建具有 JVM 选项的默认文件的副本，该文件将覆盖原始文件： 

- 从主菜单中，选择Help | Edit Custom VM Options。
- 如果您没有打开任何项目，在欢迎屏幕上，单击Configure ，然后选择Edit Custom VM Options。
- 如果无法启动 GoLand，请手动将带有 JVM 选项的默认文件复制到 GoLand 的[配置目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory)中。

​	如果您无法对 GoLand 配置目录进行写访问，可以添加 `GOLAND_VM_OPTIONS` 环境变量，以指定首选 JVM 选项文件的位置。该文件将覆盖原始默认文件和位于 GoLand 配置目录中的副本。

> ​	如果您使用的是 Toolbox App，它管理安装和配置目录，并允许您为每个 IDE 实例配置 JVM 选项。打开 Toolbox App，单击与相关 IDE 实例旁边的![The screw nut icon](index_img/toolbox_settings_screw_icon.png)，然后选择Settings。

### 查找 JVM 选项文件

​	如果您不确定 GoLand 获取其 JVM 选项的位置，请检查以下内容： 

1. `GOLAND_VM_OPTIONS` 环境变量指定的位置。如果指定的文件存在，它将覆盖所有其他 JVM 选项文件。
3. 如果 Toolbox App管理您当前的 GoLand 实例，请打开 Toolbox 应用程序，单击与相关 IDE 实例旁边的![The screw nut icon](index_img/toolbox_settings_screw_icon.png)，然后选择Settings。在Configuration下找到Java Virtual Machine options，并单击Edit。
4. 如果您正在运行独立的 GoLand 实例，请检查[配置目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory)。
6. 如果在上述位置中没有定义 JVM 选项文件，GoLand 将使用[默认的 JVM 选项文件](https://www.jetbrains.com/help/go/tuning-the-ide.html#default-jvm-options)。请勿修改它。仅使用它来检查 GoLand 使用的默认选项。

### 常见选项

​	在大多数情况下，JVM 选项的默认值应该是最佳的。以下是最常修改的选项：

| 选项           | 描述                                                         |
| -------------- | ------------------------------------------------------------ |
| `-Xmx`         | 限制 JVM 为运行 GoLand 分配的最大内存堆大小。默认值取决于平台。如果遇到减速问题，您可以增加此值，例如将该选项更改为 `-Xmx2048m` 以将值设置为 2048 兆字节。有关更多信息，请参见[增加 IDE 的内存堆大小](https://www.jetbrains.com/help/go/increasing-memory-heap.html)。 |
| `-Xms`         | 指定 JVM 为运行 GoLand 分配的初始内存。默认值取决于平台。通常设置为允许的最大内存（[-Xmx](https://www.jetbrains.com/help/go/tuning-the-ide.html#xmx)）的大约一半，例如 `-Xms1024m`。 |
| `-XX:NewRatio` | 指定堆的年轻代和老年代之间的比率。在大多数情况下，推荐使用 2 到 4 之间的比率。这将相应地设置年轻代的大小为老年代的 1/2 到 1/4，适用于您经常只在一个项目上工作并一次只打开少量文件的情况。但是，如果您经常打开新文件并在多个项目之间切换，可能需要增加年轻代的大小。在这种情况下，请尝试将 `-XX:NewRatio=1` 设置为使年轻代与老年代一样大，以便对象能够在年轻代中保留更长的时间。 |

​	有关可用 JVM 选项的更多信息，请参阅[java](https://docs.oracle.com/en/java/javase/11/tools/java.html)命令参考。

## 平台属性

GoLand enables you to customize various platform-specific properties, such as the path to user-installed plugins and the maximum supported file size. The default properties used to run GoLand are specified in the IDE installation directory:

​	GoLand 允许您自定义各种特定于平台的属性，例如用户安装的插件路径和支持的最大文件大小。用于运行 GoLand 的默认属性在 IDE 安装目录中指定为：

{{< tabpane text=true >}}

{{< tab header="Windows" >}}

`<IDE_HOME>\bin\idea.properties`

{{< /tab >}}

{{< tab header="macOS" >}}

`GoLand.app/Contents/bin/idea.properties`

{{< /tab >}}

{{< tab header="Linux" >}}

`<IDE_HOME>/bin/idea.properties`

{{< /tab >}}

{{< /tabpane >}}

> ​	请勿在默认文件中更改平台属性，因为更新 GoLand 时会被替换。此外，在 macOS 中，编辑此文件会违反应用程序签名。

### 配置平台属性

​	请执行以下操作之一，创建一个空的**idea.properties**文件，并放置在[配置目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory)中，这将覆盖原始文件中的值： 

- 从主菜单中，选择Help | Edit Custom Properties。
- 如果没有打开任何项目，在欢迎屏幕上，单击Configure ，然后选择Edit Custom Properties。
- 如果无法启动 GoLand，请在 GoLand [配置目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory)中手动创建一个空的**idea.properties**文件。

​	如果您没有对 GoLand 配置目录的写入访问权限，您可以添加`GOLAND_PROPERTIES`环境变量来指定**idea.properties**文件的位置。该文件中的属性将覆盖原始默认文件和位于 GoLand 配置目录中的文件中的相应属性。

### 常见属性

​	用户经常更改[默认 IDE 目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html)的位置。有关更多信息，请参见[更改 IDE 目录的位置](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#change-ide-dirs)。

​	可能影响性能的限制：

| 属性                             | 描述                                                         |
| -------------------------------- | ------------------------------------------------------------ |
| `idea.max.content.load.filesize` | GoLand 能够打开的文件的最大大小（以千字节为单位）。使用大文件可能会影响编辑器性能并增加内存消耗。默认值为`20000`。 |
| `idea.max.intellisense.filesize` | GoLand 提供代码辅助的文件的最大大小（以千字节为单位）。使用大文件的代码辅助可能会影响编辑器性能并增加内存消耗。默认值为`2500`。 |
| `idea.cycle.buffer`              | 控制台循环缓冲区的最大大小（以千字节为单位）。如果控制台输出大小超过此值，最旧的行将被删除。要禁用循环缓冲区，请将`idea.cycle.buffer.size`设置为`disabled`。 |
| `idea.max.vcs.loaded.size.kb`    | GoLand 用于在[比较更改](https://www.jetbrains.com/help/go/comparing-files-and-folders.html)时显示过去文件内容的最大大小（以千字节为单位）。默认值为`20480`。 |

​	GoLand提供了许多其他属性，用于定义与环境的交互（窗口管理器、启动器（launchers）、文件系统等）。其中大部分作为隐藏设置（也就是它们不会明确显示），在某些情况下您可能需要启用或禁用它们。只有在[JetBrains Support](https://intellij-support.jetbrains.com/hc/en-us)的建议下才更改这些属性。

