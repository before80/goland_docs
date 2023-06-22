+++
title = "创建本地服务器配置"
weight = 20
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Create a local server configuration﻿ - 创建本地服务器配置

https://www.jetbrains.com/help/go/creating-local-server-configuration.html

Last modified: 11 January 2023

最后修改日期：2023年1月11日

File | Settings | Build, Execution, Deployment | Deployment  for  Windows和Linux 的部署

GoLand | Settings | Build, Execution, Deployment | Deployment for macOS

GoLand | Settings | Build, Execution, Deployment | Deployment for  macOS 的部署

​	在本地服务器配置中，您进行开发，然后将源代码复制到服务器上。

​	本地服务器是在本地或挂载文件夹中运行的服务器，其文档根目录不是项目根目录的父目录。



​	要在此设置中配置对服务器的访问，您需要指定以下内容： 

1. 服务器配置根目录和访问它的URL地址。
4. 项目根目录、要将数据从项目根目录复制到的服务器上的文件夹，以及访问服务器上复制数据的URL地址之间的对应关系。这个对应关系称为映射。

![Local or mounted server configuration](CreateALocalServerConfiguration_img/go_local_mounted_server_configuration.png)

### 指定服务器配置的名称、类型和可见性

1. 按下Ctrl+Alt+S打开IDE设置，选择Build, Execution, Deployment | Deployment。

   或者，从主菜单中选择Tools | Deployment | Configuration...。

3. 在列出所有现有服务器配置的左侧窗格中，单击Add ![Add item](CreateALocalServerConfiguration_img/app.general.add.svg)，在弹出菜单中选择Local or mounted folder。

4. 在打开的 Create new server对话框中，输入要创建的服务器的名称，然后单击OK。创建新服务器对话框将关闭，您将返回到[Deployment](https://www.jetbrains.com/help/go/settings-deployment.html)节点的[Connection](https://www.jetbrains.com/help/go/deployment-connection-tab.html)选项卡。

6. 单击工具栏上的![the Use as default button](CreateALocalServerConfiguration_img/app.actions.setDefault.svg)按钮，让GoLand在以下情况下默默应用当前配置：

   - [自动上传更改的文件](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#automaticUploadOnUpdate)。
   - 手动[上传](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#manually)和[下载](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#download_file_folder)文件时，不选择目标主机。
   
   - [比较本地文件和文件夹](https://www.jetbrains.com/help/go/comparing-deployed-files-and-folders-with-their-local-versions.html)与其远程版本。
   
   - [编辑远程主机上的单个文件](https://www.jetbrains.com/help/go/editing-individual-files-on-remote-hosts.html)。

     > ​	您还可以单击GoLand状态栏中的默认部署服务器小部件，从弹出菜单中选择所需的服务器或服务器组。

5. 使用 Visible only for this project复选框来配置服务器访问配置的可见性。

   - 选择复选框以将配置的使用限制在当前项目中。此类配置不能在当前项目之外重用。它不会出现在其他项目中可用配置的列表中。

     

     服务器记录存储在与项目一起的 **.idea** 目录中，这允许通过版本控制系统在团队成员之间共享它们。

     

     在左侧窗格的服务器访问配置列表中，当前项目中可见的配置使用 ![Visible only in current project icon](CreateALocalServerConfiguration_img/app.general.projectConfigurable.svg)图标标记。

   - 当取消选中复选框时，配置在所有GoLand项目中可见。其设置可以在多个项目中重复使用。



### 指定服务器配置根目录和访问它的URL地址 

1. 按下Ctrl+Alt+S打开IDE设置，选择Build, Execution, Deployment | Deployment。

   或者，从主菜单中选择Tools | Deployment | Configuration...。

3. 单击Connection 选项卡。

3. 在Folder 字段中，指定服务器配置的根目录。

   服务器配置根目录是通过服务器配置可以访问的服务器上文件树中的最高文件夹。最简单的方法是使用服务器配置文件中定义的服务器的文档根目录。但是，您也可以指定文档根目录下的任何其他现有文件夹。

   

4. 在Web server URL字段中，指定服务器配置根目录的URL地址。该URL地址将成为构建应用程序的URL地址的起始点。根据您选择的服务器配置根目录，执行以下操作之一：

   - 在服务器配置文件中定义的服务器的文档根目录关联的URL地址。

   - 以以下格式输入URL地址：

     **<Server document root URL>/<path to the folder relative to the server document root>**


   

   支持HTTP和HTTPS协议。



![Local or mounted server configuration](CreateALocalServerConfiguration_img/go_local_mounted_server_configuration.png)

### 将项目文件夹映射到服务器上的文件夹，并指定访问它们的URL地址

​	配置映射，即设置项目文件夹、要将项目文件复制到的服务器上的文件夹以及访问服务器上复制数据的URL地址之间的对应关系。最简单的方法是将整个项目根目录映射到服务器上的一个文件夹。在这种情况下，项目文件夹结构将在服务器上重复，前提是您在[选项对话框](https://www.jetbrains.com/help/go/settings-deployment-options.html)中选择了“创建空文件夹”复选框。

1. 按下Ctrl+Alt+S打开IDE设置，选择Build, Execution, Deployment | Deployment.。

   或者，从主菜单中选择Tools | Deployment | Configuration...。

3. 单击Mappings选项卡。

5. 在Local Path字段中，指定所需本地文件夹的完整路径。在最简单的情况下，它是项目根目录。

4. 在Deployment Path字段中，指定GoLand将从“本地路径”字段中指定的文件夹上传数据到的服务器上的文件夹。根据服务器配置根目录的路径进行相对路径指定。

   如果具有指定名称的文件夹尚不存在，GoLand将创建它，前提是您在[选项对话框](https://www.jetbrains.com/help/go/settings-deployment-options.html)中选择了Create Empty directories 复选框。

   

9. 在Web Path字段中，输入相对于服务器配置根目录的服务器上的文件夹的路径。实际上，输入在Deployment Path字段中输入的相对路径。



![Local or mounted server mappings](CreateALocalServerConfiguration_img/go_local_mounted_server_mappings.png)