+++
title = "在Go Playground中运行应用程序"
weight = 60
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Running applications in Go Playground﻿ - 在Go Playground中运行应用程序

https://www.jetbrains.com/help/go/running-applications-in-go-playground.html

Last modified: 23 February 2023

最后修改日期：2023年2月23日

​	您可以通过使用Go Playground服务器在GoLand中运行您的Go代码。当您使用Open in | Playground操作时，GoLand会创建一个临时文件来存储您的代码，并显示一个包含与Go Playground相同选项的工具栏。

​	您可以格式化和分享您的代码，更改Go版本，通过使用Go Playground服务器运行代码，或在本地运行代码。

​	GoLand在Go临时文件的工具栏中显示Go Playground的控制选项。

![the Go playground inside GoLand](RunningApplicationsInGoPlayground_img/go_the_go_playground_inside_go_land.png)

### 在Go Playground中运行您的代码

1. 选择您想要在Go Playground中运行的代码。

3. 右键单击选择内容，导航到Open In | Playground。

5. 在工具栏上，点击运行图标（![the Run icon](RunningApplicationsInGoPlayground_img/app.actions.execute.svg) )。

   注意：如果您从上下文菜单或gutter中运行代码，GoLand会在本地运行您的代码。此外，您还可以通过选择Run locally在本地运行代码。

   ![06201035](RunningApplicationsInGoPlayground_img/06201035.gif)

   

### 从文件或URL加载代码

1. 从主菜单中选择File | New | Scratch File，或按下Ctrl+Alt+Shift+Insert。

3. 在新的临时文件窗口中，选择Go。

5. 在工具栏上，点击加载图标（![the Load icon](RunningApplicationsInGoPlayground_img/app.actions.download.svg))。

6. 在对话框中，选择代码的来源：File或URL。

5. 点击OK。

   ![06201036](RunningApplicationsInGoPlayground_img/06201036.gif)


### 使用Go Playground格式化代码

1. 在一个临时文件中打开您的代码。有关临时文件的更多信息，请参阅[临时文件（Scratch files）](https://www.jetbrains.com/help/go/scratches.html)。

   要创建一个新文件，请从主菜单中选择File | New | Scratch File，或按下Ctrl+Alt+Shift+Insert。

3. 在工具栏上，点击格式化图标（![the Format icon](RunningApplicationsInGoPlayground_img/app.actions.annotate.svg))。

   ![Format code with the Go Playground formatter](RunningApplicationsInGoPlayground_img/go_format_code_with_the_go_playground_formatter.png)

### 在Go Playground中分享临时文件中的代码

1. 在一个临时文件中打开您的代码。有关临时文件的更多信息，请参阅[临时文件（Scratch files）](https://www.jetbrains.com/help/go/scratches.html)。

   要创建一个新文件，请从主菜单中选择File | New | Scratch File，或按下Ctrl+Alt+Shift+Insert。

3. 在工具栏上，点击格式化图标（![the Format icon](RunningApplicationsInGoPlayground_img/app.actions.annotate.svg))。

   根据所选择的版本，GoLand会将版本参数添加到生成的链接中，用于在Go Playground中分享代码。

   ![version parameter in shared links to the Go Playground](RunningApplicationsInGoPlayground_img/go_version_parameter_in_shared_links_to_the_go_playground.png)

### 选择Go版本

1. 在一个临时文件中打开您的代码。有关临时文件的更多信息，请参阅[临时文件](https://www.jetbrains.com/help/go/scratches.html)。

   要创建一个新文件，请从主菜单中选择File | New | Scratch File，或按下Ctrl+Alt+Shift+Insert。

2. 在Go版本下拉菜单中，选择您想要的版本。

   根据所选择的版本，GoLand会将版本参数添加到生成的链接中，用于在Go Playground中分享代码。


### 选择模块的上下文

1. 在一个临时文件中打开您的代码。有关临时文件的更多信息，请参阅[临时文件](https://www.jetbrains.com/help/go/scratches.html)。

   要创建一个新文件，请从主菜单中选择File | New | Scratch File，或按下Ctrl+Alt+Shift+Insert。

3. 在Go版本下拉菜单中，选择您想要的版本。
