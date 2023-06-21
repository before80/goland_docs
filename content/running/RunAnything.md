+++
title = "运行任何内容"
weight = 20
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Run anything﻿ - 运行任何内容

https://www.jetbrains.com/help/go/running-anything.html

Last modified: 09 November 2022

上次修改日期：2022年11月9日

Double Ctrl

Run Anything is a quick way to launch [run/debug configurations](https://www.jetbrains.com/help/go/run-debug-configuration.html), applications, scripts, commands, tasks, and open recent projects. It also helps you use proper command syntax by generating suggestions as you type. When you call a command, Run Anything delegates the further work to the appropriate tools.

​	Run Anything是一种快速启动运行/调试配置、应用程序、脚本、命令、任务以及打开最近项目的方式。它还通过在输入时生成建议来帮助您使用正确的命令语法。当您调用一个命令时，"Run Anything" 会将进一步的工作委托给相应的工具。

![The Run Anything popup](RunAnything_img/go_run_anything_overview.png)

## 打开 "Run Anything" 弹出窗口 Open the Run Anything popup﻿

- Press Ctrl twice.

- 按两次 Ctrl 键。

  Alternatively, click 或者，单击工具栏上的![the Run Anything icon](RunAnything_img/app.actions.run_anything.svg) on the toolbar.

  > To disable the Double-Ctrl mapping for this action, select Disable double modifier key shortcuts on the Advanced Settings page of the IDE settings Ctrl+Alt+S
  >
  > 若要禁用此操作的双 Ctrl 键映射，请在IDE设置的高级设置页面中选择"禁用双修饰键快捷键"（Ctrl+Alt+S）。
  
  The icon is hidden by default. To add the icon to the toolbar, open the Settings dialog (Ctrl+Alt+S), go to Appearance and Behavior | Menus and Toolbars, expand the Main Toolbar node, and add the Run Anything action, for example, below Search Everywhere. See [Menus and toolbars](https://www.jetbrains.com/help/go/customize-actions-menus-and-toolbars.html) for details.

  ​	该图标默认是隐藏的。要将该图标添加到工具栏中，打开设置对话框（Ctrl+Alt+S），转到外观和行为 | 菜单和工具栏，展开"主工具栏"节点，添加"Run Anything" 操作，例如在"全局搜索"下方。有关详细信息，请参见[菜单和工具栏](https://www.jetbrains.com/help/go/customize-actions-menus-and-toolbars.html)。

## 启动运行/调试配置 Launch a run/debug configuration﻿

1. Start typing the run/debug configuration name and select it from the suggestion list.

2. 开始输入运行/调试配置的名称，并从建议列表中选择它。

   ![Start run/debug configurations from the Run Anything popup](RunAnything_img/go_run_anything_run_config.png)

3. To [debug](https://www.jetbrains.com/help/go/debugging-code.html) a run configuration, hold Shift when launching it.

4. 若要对运行配置进行[调试](https://www.jetbrains.com/help/go/debugging-code.html)，在启动时按住 Shift 键。


## 运行命令 Run commands﻿

- Start typing the command name and navigate the suggestion list using the arrow keys. When you press Space, you accept the current suggestion and get further suggestions specific to this command.

- 开始输入命令名称，并使用箭头键浏览建议列表。按下空格键时，您接受当前建议，并获得与该命令特定的进一步建议。

  ![Run Anything: npm script](RunAnything_img/go_run_anything_npm.png)

- To get the list of available commands, type `?`. The list of commands depends on the installed/enabled plugins. If a command is not on the suggestion list, it will be executed in the terminal.

- 要获取可用命令的列表，请键入 `?`。命令列表取决于已安装/启用的插件。如果一个命令不在建议列表中，它将在终端中执行。

  ![List of the available commands in Run Anything](RunAnything_img/go_run_anything_commands_hints.png)

## 打开最近项目 Open a recent project﻿

You can also quickly reopen a [recent project](https://www.jetbrains.com/help/go/creating-and-managing-projects.html) from the Run Anything popup. Search for the project by the name or type `open` to shorten the list of suggestions, then select the required project from the list, and press Enter:

​	您还可以从 "Run Anything" 弹出窗口快速重新打开[最近的项目](https://www.jetbrains.com/help/go/creating-and-managing-projects.html)。通过名称搜索项目，或者输入 `open` 来缩小建议列表的范围，然后从列表中选择所需的项目，按 Enter 键即可：

![Opening a recent project from the Run Anything popup](RunAnything_img/go_run_anything_open.png)

## 发送 HTTP 请求 Send HTTP requests﻿

If, while [composing an HTTP request](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html), you specified its name, you can find and send this HTTP request from the Run Anything popup.

如果在[编写 HTTP 请求](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html)时指定了其名称，您可以从 "Run Anything" 弹出窗口中找到并发送该 HTTP 请求。

1. Start typing the name of an HTTP request and select it from the suggestion list:

2. 开始输入一个 HTTP 请求的名称，并从建议列表中选择它：

   ![Send HTTP requests](RunAnything_img/run_anything_http.png)

3. If your request contains [environment variables](https://www.jetbrains.com/help/go/exploring-http-syntax.html#environment-variables), press Shift while selecting a request. This will open the popup menu where you can select the environment to be used for the request.

4. 如果您的请求包含[环境变量](https://www.jetbrains.com/help/go/exploring-http-syntax.html#environment-variables)，在选择请求时按住 Shift 键。这将打开弹出菜单，在其中您可以选择用于该请求的环境。

   ![Select HTTP request environment](RunAnything_img/http_request_choose_environment.png)
