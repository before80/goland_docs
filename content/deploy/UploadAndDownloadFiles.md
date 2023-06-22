+++
title = "上传和下载文件"
weight = 30
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Upload and download files﻿ -上传和下载文件

https://www.jetbrains.com/help/go/uploading-and-downloading-files.html

Last modified: 11 January 2023

最后修改日期：2023年1月11日

​	GoLand提供以下主要方式将项目文件和文件夹上传到部署服务器： 

- 手动方式，通过菜单命令随时进行上传。
- 自动方式，在文件更新时、调试会话开始前或提交到版本控制系统时自动上传。

​	对于下载文件和文件夹，GoLand仅支持手动模式。

​	GoLand会在File Transfer工具窗口（View | Tool Windows | File Transfer）中显示日志。

### 手动上传文件或文件夹 

- 在“项目”工具窗口中，右键单击文件或文件夹，然后从上下文菜单中选择Deployment | Upload，并从列表中选择目标部署服务器或服务器组。

  如果指定了默认服务器或服务器组，您还可以选择`Upload to <default deployment server or server group>`。


### 上传本地修改的文件

1. 切换到Local Changes视图以查看本地修改的文件。
4. 右键单击文件，然后从上下文菜单中选择Deployment | Upload，并从列表中选择目标部署服务器或服务器组。如果指定了默认服务器或服务器组，您还可以选择`Upload to <default deployment server or server group>`。

​	有关详细信息，请参阅[管理版本控制下的文件](https://www.jetbrains.com/help/go/adding-files-to-version-control.html)。

### 在与VCS存储库同步后上传文件

1. 通过按下Ctrl+T或选择主菜单中的VCS | <VCS> | Update，将本地文件的内容与VCS存储库进行同步。
3. 切换到Version Control 工具窗口的[Update Info](https://www.jetbrains.com/help/go/version-control-tool-window-update-info-tab.html)选项卡（Alt+9）。
5. 右键单击文件，然后从上下文菜单中选择Deployment | Upload，并从列表中选择目标部署服务器或服务器组。如果指定了默认服务器或服务器组，您还可以选择`Upload to <default deployment server or server group>`。

### 在提交后立即上传已检入文件

1. 开始进行提交更改。
3. 在After Commit区域，从Upload files to列表中选择目标服务器或服务器组。选择现有配置之一或创建新配置：单击 ![the Browse button](UploadAndDownloadFiles_img/app.general.ellipsis.svg)并[配置访问相关服务器](https://www.jetbrains.com/help/go/creating-in-place-server-configuration.html)或在打开的[部署](https://www.jetbrains.com/help/go/settings-deployment.html)对话框中[设置服务器组](https://www.jetbrains.com/help/go/server-groups.html)。
4. 若要将所选内容自动应用于将来，请选中“始终使用所选服务器或服务器组”复选框。

### 配置将更改的文件自动上传到默认服务器或服务器组

​	只要文件被自动或手动保存（File | Save All 或Ctrl+S），GoLand就会将本地文件视为已更改，详见[编写和编辑源代码](https://www.jetbrains.com/help/go/working-with-source-code.html)。更改的文件只能自动上传到[默认部署服务器](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html#default_server)。

1. 打开[Options](https://www.jetbrains.com/help/go/settings-deployment-options.html)对话框，有以下几种方式：

   - 从主菜单中选择Tools | Deployment | Options。
   - 在设置对话框（Ctrl+Alt+S）中，转到Build, Execution, Deployment | Deployment | Options。

2. 在Upload changed files automatically to the default server列表中，选择GoLand何时上传更改的文件：

   - 若要上传任何手动或自动保存的文件，请选择Always。
   - 若要仅上传手动保存的文件，请选择On explicit save action。
   - 若要禁止自动上传，请选择Never。

3. 如果启用了自动上传，请选择应用于的范围：

   - 选择“跳过外部更改”以排除使用第三方工具（VCS、脚本等）进行的本地更改，这些更改将不会自动上传。

   - 选择Delete remote files when local are deleted以在自动上传期间，当删除本地文件时，GoLand会自动删除远程文件。

     请注意，此选项作为额外的安全措施，可能导致不需要的文件留在远程服务器上。举例来说，考虑一个本地文件**Foo.php**被重命名为**Bar.php**。由于重命名文件在技术上与删除文件并创建新文件无法区分，自动上传后会发生以下情况： 

     - 如果启用了该选项，则远程服务器只包含**Bar.php**。
     - 如果禁用了该选项，则远程服务器在自动上传后将同时包含**Foo.php**和**Bar.php**。您可能需要手动删除**Foo.php**。




> ​	启用Upload changed files automatically to the default server选项还会在Settings | Tools | Actions on Save中启用[Upload to default server](https://www.jetbrains.com/help/go/saving-and-reverting-changes.html#actions-on-save)。

### 下载文件或文件夹

- 在Remote Host工具窗口中，选择所需文件或文件夹，然后从选择的上下文菜单中选择“从此处下载”。

### 从默认部署服务器下载文件

- 从主菜单中选择Tools | Deployment | Download from <default server>。

  如果有必要，GoLand将提示您覆盖本地文件。
