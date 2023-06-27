+++
title = "Directories used by the IDE"
weight = 10
date = 2023-06-17T19:06:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Directories used by the IDE﻿ - IDE使用的目录

https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html

Last modified: 26 April 2023

最后修改日期：2023年4月26日

​	默认情况下，GoLand将每个IDE实例的特定于用户的文件（配置、缓存、插件、日志等）存储在用户的主目录中。但是，如果需要，您可以更改存储这些文件的位置。

> ​	从GoLand 2020.1版本开始，默认IDE目录的位置已更改。如果您使用旧版本，新安装将从旧目录导入配置。有关以前IDE版本中默认目录的位置信息，请参阅相应的帮助版本，例如：[https://www.jetbrains.com/help/go/2019.3/tuning-the-ide.html#default-dirs](https://www.jetbrains.com/help/go/2019.3/tuning-the-ide.html#default-dirs)。

### 更改IDE目录的位置

​	您可以移动默认的IDE目录，例如，如果用户配置文件驱动器空间不足或位于较慢的磁盘上，如果主目录被加密（导致IDE速度变慢）或位于网络驱动器上，如果您想创建便携式安装或从主目录备份中排除缓存等。

1. 从主菜单中选择 Help | Edit Custom Properties。

4. 设置对应于所需目录的属性：

   | 属性                | 路径                                                         |
   | ------------------- | ------------------------------------------------------------ |
   | `idea.config.path`  | [配置目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory) |
   | `idea.system.path`  | [系统目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#system-directory) |
   | `idea.plugins.path` | [插件目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#plugins-directory) |
   | `idea.log.path`     | [日志目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#logs-directory) |

   ​	请使用正斜杠 `/`指定路径，包括Windows路径（例如，`C:/idea/system`）。

   ​	您可以插入任何其他属性作为变量。例如，使用 `${user.home}`（标准Java系统属性）来指定相对于用户主目录的路径：

   ```plaintext
   idea.config.path=${user.home}/MyIdeaConfiguration
   ```

   
   
5. 重新启动GoLand后，它将使用相应目录的新位置。


### 清理旧的IDE目录

​	每次安装新的GoLand主版本时，它都会使用一组新的IDE目录，并自动删除那些在过去`180`天内没有更新的旧版IDE的缓存和日志目录。配置和插件目录将永远保留，除非您手动删除它们。 

1. 从主菜单中选择 Help | Delete Leftover IDE Directories。
4. 在 Delete Leftover IDE Storage Directories 对话框中，选择您不打算使用的IDE版本，并点击 Delete。

## 配置目录

​	GoLand配置目录包含用户定义的IDE设置，例如键位映射（keymaps）、颜色方案、自定义[VM选项](https://www.jetbrains.com/help/go/tuning-the-ide.html#configure-jvm-options)、[平台属性](https://www.jetbrains.com/help/go/tuning-the-ide.html#configure-platform-properties)等。

{{< tabpane text=true >}}

{{< tab header="Windows" >}}

Syntax

`%APPDATA%\JetBrains\<product><version>`

Example

`C:\Users\JohnS\AppData\Roaming\JetBrains\GoLand2023.1`

{{< /tab >}}

{{< tab header="macOS" >}}

Syntax

`~/Library/Application Support/JetBrains/<product><version>`

Example

`~/Library/Application Support/JetBrains/GoLand2023.1`

{{< /tab >}}

{{< tab header="Linux" >}}

Syntax

`~/.config/JetBrains/<product><version>`

Example

`~/.config/JetBrains/GoLand2023.1`

{{< /tab >}}

{{< /tabpane >}}

​	您可以使用[idea.config.path](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#idea.config.path)属性更改GoLand配置目录的位置。

​	要共享您的个人IDE设置，请将配置目录中的文件复制到另一个GoLand安装的相应文件夹中。确保GoLand未运行，以避免在关闭IDE时擦除复制的文件。根据您修改的设置，GoLand配置目录可能包含以下子文件夹：

| 目录              | 用户设置                                                     |
| ----------------- | ------------------------------------------------------------ |
| **codestyles**    | 自定义[代码样式方案](https://www.jetbrains.com/help/go/configuring-code-style.html) |
| **colors**        | 自定义[编辑器颜色和字体方案](https://www.jetbrains.com/help/go/configuring-colors-and-fonts.html) |
| **fileTemplates** | 用户定义的[文件模板](https://www.jetbrains.com/help/go/using-file-and-code-templates.html) |
| **filetypes**     | 用户定义的文件类型                                           |
| **inspection**    | [代码检查配置](https://www.jetbrains.com/help/go/code-inspection.html) |
| **keymaps**       | 自定义[键盘快捷键](https://www.jetbrains.com/help/go/configuring-keyboard-and-mouse-shortcuts.html) |
| **options**       | 各种选项，例如功能使用统计和宏                               |
| **scratches**     | [临时文件和缓冲区](https://www.jetbrains.com/help/go/scratches.html) |
| **settingsSync**  | 使用[设置同步](https://www.jetbrains.com/help/go/sharing-your-ide-settings.html#IDE_settings_sync)共享的IDE设置 |
| **templates**     | 用户定义的[Live模板](https://www.jetbrains.com/help/go/using-live-templates.html) |
| **tools**         | 用户定义的外部工具配置文件                                   |
| **shelf**         | [搁置的更改](https://www.jetbrains.com/help/go/work-on-several-features-simultaneously.html#shelve) |

## 系统目录

​	GoLand系统目录包含缓存和本地历史文件。

{{< tabpane text=true >}}

{{< tab header="Windows" >}}

Syntax

`%LOCALAPPDATA%\JetBrains\<product><version>`

Example

`C:\Users\JohnS\AppData\Local\JetBrains\GoLand2023.1`

{{< /tab >}}

{{< tab header="macOS" >}}

Syntax

`~/Library/Caches/JetBrains/<product><version>`

Example

`~/Library/Caches/JetBrains/GoLand2023.1`

{{< /tab >}}

{{< tab header="Linux" >}}

Syntax

`~/.cache/JetBrains/<product><version>`

Example

`~/.cache/JetBrains/GoLand2023.1`

{{< /tab >}}

{{< /tabpane >}}

​	您可以使用[idea.system.path](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#idea.system.path)属性更改GoLand系统目录的位置。

## 插件目录﻿

​	GoLand插件目录包含用户安装的插件。

{{< tabpane text=true >}}

{{< tab header="Windows" >}}

Syntax

`%APPDATA%\JetBrains\<product><version>\plugins`

Example

`C:\Users\JohnS\AppData\Roaming\JetBrains\GoLand2023.1\plugins`

{{< /tab >}}

{{< tab header="macOS" >}}

Syntax

`~/Library/Application Support/JetBrains/<product><version>/plugins`

Example

`~/Library/Application Support/JetBrains/GoLand2023.1/plugins`

{{< /tab >}}

{{< tab header="Linux" >}}

Syntax

`~/.local/share/JetBrains/<product><version>`

Example

`~/.local/share/JetBrains/GoLand2023.1`

{{< /tab >}}

{{< /tabpane >}}

​	您可以使用[idea.plugins.path](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#idea.plugins.path)属性更改GoLand插件目录的位置。

> ​	如果您通过[Toolbox App](https://www.jetbrains.com/toolbox/app/)安装了GoLand，插件目录将位于安装目录中。要找到安装目录，打开Toolbox App中的IDE实例的设置，展开配置并查找安装位置字段。应该有一个以 **.plugins** 结尾的目录。
>
> ​	您还可以在VM选项文件中查看插件目录的位置。从主菜单中选择 Help | Edit Custom VM Options。例如，选项可能如下所示：
>
> ```plaintext
>-Didea.plugins.path=/Users/jsmith/Library/Application Support/JetBrains/Toolbox/apps/IDEA-U/ch-2/212.5080.55/IntelliJ IDEA.app.plugins
> ```

## 日志目录﻿

​	GoLand日志目录包含产品日志和线程转储文件。

{{< tabpane text=true >}}

{{< tab header="Windows" >}}

Syntax

`%LOCALAPPDATA%\JetBrains\<product><version>\log`

Example

`C:\Users\JohnS\AppData\Local\JetBrains\GoLand2023.1\log`

{{< /tab >}}

{{< tab header="macOS" >}}

Syntax

`~/Library/Logs/JetBrains/<product><version>`

Example

`~/Library/Logs/JetBrains/GoLand2023.1`

{{< /tab >}}

{{< tab header="Linux" >}}

Syntax

`~/.cache/JetBrains/<product><version>/log`

Example

`~/.cache/JetBrains/GoLand2023.1/log`

{{< /tab >}}

{{< /tabpane >}}

​	您可以使用[idea.log.path](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#idea.log.path)属性更改GoLand日志目录的位置。

> ​	您可以使用相应的帮助菜单操作打开日志目录的位置：在Windows上选择 Show Log in Explorer，在macOS上选择 Show Log in Finder。