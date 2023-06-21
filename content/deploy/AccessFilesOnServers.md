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

Once you have [set up synchronization](https://www.jetbrains.com/help/go/deploying-applications.html) between your local application sources and the application sources on a server, you can create new folders, move, rename, and delete existing files and folders. You can also [compare](https://www.jetbrains.com/help/go/comparing-deployed-files-and-folders-with-their-local-versions.html) files and folders on the server with their local versions.

​	一旦您在本地应用程序源代码和服务器上的应用程序源代码之间设置了同步，您就可以创建新文件夹，移动、重命名和删除现有文件和文件夹。您还可以比较服务器上的文件和文件夹与其本地版本。

For the sake of simplicity, any file or folder in your GoLand project is called local and any file or folder on the server is called remote, even if the server is actually installed on your machine. For details, see [Configure synchronization with a server](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html).

​	为简单起见，GoLand项目中的任何文件或文件夹称为本地文件，而服务器上的任何文件或文件夹称为远程文件，即使服务器实际上安装在您的计算机上。有关详细信息，请参阅[配置与服务器的同步](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)。



GoLand uses [server configurations](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html) to control access to servers (FTP, FTPS, SFTP, WebDAV, or Local or Mounted Folder).

​	GoLand使用[服务器配置](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)来控制对服务器（FTP、FTPS、SFTP、WebDAV或本地或挂载文件夹）的访问。

### 访问远程服务器  Access a remote server﻿

1. Open the [Remote Host tool window](https://www.jetbrains.com/help/go/remote-host-tool-window.html) by choosing Tools | Deployment | Browse Remote Host or View | Tool Windows | Remote Host from the main menu.
2. 通过选择“工具” | “部署” | “浏览远程主机”或“视图” | “工具窗口” | “远程主机”菜单中的选项，打开[远程主机工具窗口](https://www.jetbrains.com/help/go/remote-host-tool-window.html)。
3. Select the required deployment server from the list. The tool window shows a tree view of files and folders under the server root. If no relevant server is available in the list, click 从列表中选择所需的部署服务器。工具窗口显示服务器根目录下的文件和文件夹的树形视图。如果列表中没有相关的服务器可用，单击![the Browse button](AccessFilesOnServers_img/app.general.ellipsis.svg), and in the Deployment dialog that opens [configure access to the required server](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html).，在打开的“部署”对话框中[配置对所需服务器的访问权限](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)。

From the Remote Host tool window, you can right-click files and directories to create, move, rename, and delete files and folders on the server, as well as upload and download the desired items.

​	从远程主机工具窗口，您可以右键单击文件和目录，在服务器上创建、移动、重命名和删除文件和文件夹，以及上传和下载所需的项目。