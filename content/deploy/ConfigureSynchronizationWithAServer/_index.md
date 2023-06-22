+++
title = "配置与服务器的同步"
weight = 10
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Configure synchronization with a server﻿ 配置与服务器的同步

https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html

Last modified: 21 April 2023

最后修改日期：2023年4月21日

​	GoLand区分原地（in-place）、本地（local）和远程（remote）服务器，但在GoLand的上下文中，这些术语的含义与常规含义略有不同：

- 在原地服务器配置中，服务器在您的计算机上运行，并且您直接在服务器上进行开发。

  原地服务器的文档根目录是项目根目录的父目录，可以是直接父目录或非直接父目录。文档根目录是服务器根目录或网站根目录。通常，它是网站的公共访问基础文件夹。

- 在本地服务器配置中，您进行开发，然后将源代码复制到服务器上。

  本地服务器是在本地或挂载文件夹中运行的服务器，其文档根目录不是项目根目录的父目录。

- 在远程服务器配置中，服务器在另一台计算机上（远程主机）运行。要访问服务器上的文件，请使用FTP/SFTP/FTPS/WebDAV协议。



## 开始之前

​	通过默认启用的FTP/SFTP/WebDAV连接插件提供与服务器的同步、上传、下载和文件管理功能。如果插件已禁用，请在设置对话框的插件页面中激活它。有关详细信息，请参阅[插件](https://www.jetbrains.com/help/go/managing-plugins.html)。

## 服务器访问配置

​	GoLand通过服务器访问配置来控制与服务器的交互。无论您的服务器是在远程主机上还是在您的计算机上，每次使用服务器之前，都需要定义一个服务器访问配置。

​	服务器访问配置定义了以下内容： 

- 服务器类型（原地、本地或远程）。
- 服务器运行的计算机（主机）。对于原地和本地服务器，GoLand假设它是您的项目所在的当前计算机。
- 服务器访问配置根目录：可以通过服务器配置访问的服务器层次结构中的最高文件夹。
- 访问服务器配置根目录的URL地址。
- 用于传输数据的协议和连接参数。
- 本地文件夹（即项目根目录下的文件夹）、服务器上的目标文件夹（本地或远程）以及访问服务器上数据的URL地址之间的对应关系。这个对应关系称为映射。

​	您可以定义多个配置，从而实现灵活的上传/下载设置切换。

​	如果您需要将代码部署到多个服务器，可以创建[服务器组](https://www.jetbrains.com/help/go/server-groups.html)，避免逐个服务器部署。

## 默认服务器访问配置

​	您可以将服务器配置设置为默认配置，在以下情况下，GoLand会默默应用它： 

- [自动上传更改的文件](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#automaticUploadOnUpdate)。
- 手动[上传](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#manually)和[下载](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#download_file_folder)文件时，不选择目标主机。
- [比较本地文件和文件夹](https://www.jetbrains.com/help/go/comparing-deployed-files-and-folders-with-their-local-versions.html)与其远程版本。
- [编辑远程主机上的单个文件](https://www.jetbrains.com/help/go/editing-individual-files-on-remote-hosts.html)。

1. 在设置对话框（Ctrl+Alt+S）中，转到Build, Execution, Deployment | Deployment，在中央窗格中选择所需的服务器访问配置，然后单击工具栏上的![the Use as default button](index_img/app.actions.setDefault.svg)。

   或者，单击GoLand状态栏中的默认部署服务器小部件，从弹出菜单中选择所需的服务器或服务器组。

2. 要[配置上传到默认服务器](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html)，转到Build, Execution, Deployment | Deployment | Options。
