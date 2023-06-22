+++
title = "设置日志选项"
weight = 40
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Setting log options﻿ - 设置日志选项

https://www.jetbrains.com/help/go/setting-log-options.html

Last modified: 01 November 2022

上次修改日期：2022年11月1日

​	使用运行/调试配置对话框中的日志选项卡来配置应用程序或服务器生成的日志文件在控制台中的显示方式。

​	如果您的应用程序或服务器生成日志文件，则默认条目将自动添加到运行/调试配置对话框中的日志文件列表中。

### 配置日志选项

1. 从[Run/Debug Configuration](https://www.jetbrains.com/help/go/run-debug-configurations-dialog.html)列表中选择Edit Configurations。

4. 在[运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configurations-dialog.html)对话框中，点击Logs 选项卡。

   ![Logs tab](SettingLogOptions_img/py_logs_tab.png)

   Edit Log Files Aliases表显示了日志文件的列表。

5. 点击添加按钮![the Add button](SettingLogOptions_img/app.general.add.svg)。

6. 在"别名"字段中，输入日志条目的别名。

5. 在"日志文件位置"字段中，指定在运行或调试期间要显示的日志文件。您可以通过以下两种方式指定文件：

   - 指定特定文件的完整路径。手动输入路径或点击浏览按钮![the Browse button](SettingLogOptions_img/app.actions.menu-open.svg)选择文件。
   - 指定基本目录并添加定义要显示的[fileset](http://ant.apache.org/manual/Types/fileset.html)的[Ant模式](http://ant.apache.org/manual/dirtasks.html#patterns)。

10. （可选）选中"显示所有模式匹配的文件"复选框，为与指定的Ant模式匹配的每个日志文件打开一个单独的选项卡。

12. 点击 OK.

13. 在Edit Log Files Aliases表中，选中Is Active复选框，以便在运行工具窗口或调试工具窗口中显示日志条目的相应选项卡。

15. 要跳过所选日志的先前内容，选中Skip Content列中的复选框。



![Configure log entries](SettingLogOptions_img/go_configure_log_entries.png)