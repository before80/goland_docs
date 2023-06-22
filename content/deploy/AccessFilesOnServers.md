+++
title = "Access files on servers"
weight = 20
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Access files on servers 访问服务器上的文件﻿

https://www.jetbrains.com/help/go/accessing-files-on-remote-hosts.html

Last modified: 21 April 2023

最近修改日期：2023年4月21日

​	一旦您在本地应用程序源代码和服务器上的应用程序源代码之间[设置了同步](https://www.jetbrains.com/help/go/deploying-applications.html)，您就可以创建新文件夹，移动、重命名和删除现有文件和文件夹。您还可以[比较](https://www.jetbrains.com/help/go/comparing-deployed-files-and-folders-with-their-local-versions.html)服务器上的文件和文件夹与其本地版本。

​	为简单起见，GoLand项目中的任何文件或文件夹称为本地文件，而服务器上的任何文件或文件夹称为远程文件，即使服务器实际上安装在您的计算机上。有关详细信息，请参阅[配置与服务器的同步](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)。



​	GoLand使用[服务器配置](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)来控制对服务器（FTP、FTPS、SFTP、WebDAV或本地或挂载文件夹）的访问。

### 访问远程服务器

1. 通过选择Tools | Deployment | Browse Remote Host or View | Tool Windows | Remote Host菜单中的选项，打开[远程主机工具窗口](https://www.jetbrains.com/help/go/remote-host-tool-window.html)。
3. 从列表中选择所需的部署服务器。工具窗口显示服务器根目录下的文件和文件夹的树形视图。如果列表中没有相关的服务器可用，单击![the Browse button](AccessFilesOnServers_img/app.general.ellipsis.svg)，在打开的Deployment 对话框中[配置对所需服务器的访问权限](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)。

​	从远程主机工具窗口，您可以右键单击文件和目录，在服务器上创建、移动、重命名和删除文件和文件夹，以及上传和下载所需的项目。