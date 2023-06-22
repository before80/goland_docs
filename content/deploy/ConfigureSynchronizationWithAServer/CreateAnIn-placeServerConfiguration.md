+++
title = "创建就地服务器配置"
weight = 10
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Create an in-place server configuration﻿ -  创建就地服务器配置

https://www.jetbrains.com/help/go/creating-in-place-server-configuration.html

Last modified: 21 April 2023

File | Settings | Build, Execution, Deployment | Deployment for Windows and Linux

GoLand | Settings | Build, Execution, Deployment | Deployment for macOS



​	在就地服务器配置中，服务器在您的计算机上运行，您可以直接在服务器上进行开发。

​	就地服务器的文档根目录是项目根目录的父目录，可以是直接的父目录或非直接的父目录。文档根目录是服务器根目录或网站根目录。通常，它是网站的公共可访问基本文件夹。

​	要在此设置中配置对服务器的访问，您只需要指定服务器文档根目录的URL地址、指定项目根文件夹，并指定访问它的URL地址。

![In-place server configuration](CreateAnIn-placeServerConfiguration_img/go_in_place_server_configuration.png)

### 指定服务器配置的名称、类型和可见性

1. 按下Ctrl+Alt+S打开IDE设置，选择Build, Execution, Deployment | Deployment。

   或者，从主菜单中选择Tools | Deployment | Configuration...。

3. 在左侧窗格中列出所有现有服务器配置的地方，单击Add![Add item](CreateAnIn-placeServerConfiguration_img/app.general.add.svg)并从列表中选择In-place。

4. 在打开的Create new server对话框中，键入要创建的服务器的名称，然后单击OK。创建新服务器对话框关闭，并返回到[连接](https://www.jetbrains.com/help/go/deployment-connection-tab.html)选项卡下的[部署](https://www.jetbrains.com/help/go/settings-deployment.html)节点。

6. 单击工具栏上的 ![the Use as default button](CreateAnIn-placeServerConfiguration_img/app.actions.setDefault.svg)按钮，让GoLand在以下情况下静默应用当前配置：

   - [自动上传已更改的文件](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#automaticUploadOnUpdate)。
   - 手动[上传](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#manually)和[下载](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#download_file_folder)文件，而不选择目标主机。
   - 将本地文件和文件夹与其远程版本进行比较。
   - [在远程主机上编辑单个文件](https://www.jetbrains.com/help/go/editing-individual-files-on-remote-hosts.html)。
   
   > 您还可以单击GoLand状态栏中的默认部署服务器小部件，并从弹出菜单中选择所需的服务器或服务器组。
   
5. 使用Visible only for this project复选框来配置服务器访问配置的可见性。

   - 选中复选框以限制配置的使用范围仅限于当前项目。此类配置不能在当前项目之外重用。它不会出现在其他项目中可用配置的列表中。

     服务器记录存储在与项目一起的 **.idea** 目录中，这允许[通过版本控制系统](https://www.jetbrains.com/help/go/version-control-integration.html)在团队成员之间共享它们。

     

     左侧窗格中的服务器访问配置列表中，当前项目中可见的配置会用 ![Visible only in current project icon](CreateAnIn-placeServerConfiguration_img/app.general.projectConfigurable.svg)图标进行标记。

   - 清除复选框时，配置在所有GoLand项目中可见。其设置可以在多个项目中重用。



![In-place server configuration](CreateAnIn-placeServerConfiguration_img/go_in_place_server_configuration.png)

### 指定服务器文档根目录的URL地址

1. Press Ctrl+Alt+S to open the IDE settings and select Build, Execution, Deployment | Deployment.

2. 按下Ctrl+Alt+S打开IDE设置，选择Build, Execution, Deployment | Deployment。

   或者，从主菜单中选择Tools | Deployment | Configuration...。

3. 在Web server URL字段中，键入与服务器配置文件中定义的服务器文档根目录相关联的URL地址。该URL地址将成为构建应用程序的URL地址的起点。

   支持HTTP和HTTPS协议。




​	例如，默认的文档根目录设置为 **htdocs** 文件夹，访问其中数据的默认URL地址为 `http://localhost`。如果您更改了默认端口`80`，则必须明确指定端口：`http://localhost:<port>`。



### 指定项目根文件夹和访问它的URL地址

1. 按下Ctrl+Alt+S打开IDE设置，选择Build, Execution, Deployment | Deployment。

   或者，从主菜单中选择Tools | Deployment | Configuration...。

3. 单击[Mappings](https://www.jetbrains.com/help/go/deployment-mappings-tab.html)选项卡。

5. 在Local path字段中，指定项目根文件夹的完整路径。可以手动输入路径，也可以单击 ![Browse button](CreateAnIn-placeServerConfiguration_img/app.general.openDisk.svg)并在打开的对话框中选择文件夹。

6. 在Web path字段中，输入相对于服务器配置文件中指定的服务器文档根目录的项目根文件夹的路径。



![Mappings of the in-place server](CreateAnIn-placeServerConfiguration_img/go_in_place_server_mappings.png)