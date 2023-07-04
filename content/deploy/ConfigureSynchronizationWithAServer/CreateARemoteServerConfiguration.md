+++
title = "创建远程服务器配置"
weight = 30
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Create a remote server configuration﻿ - 创建远程服务器配置

https://www.jetbrains.com/help/go/creating-a-remote-server-configuration.html

Last modified: 11 January 2023

最后修改日期：2023年1月11日

File | Settings | Build, Execution, Deployment | Deployment for Windows and Linux

GoLand | Settings | Build, Execution, Deployment | Deployment for macOS

​	在远程服务器配置中，服务器在另一台计算机上（远程主机）上运行。要访问服务器上的文件，请使用FTP/SFTP/FTPS/WebDAV协议。

​	要在此设置中配置对服务器的访问，您需要指定以下内容： 

4. 连接设置：服务器主机、端口和用户凭据。
5. 服务器配置的根文件夹和访问它的URL地址。
6. 项目根文件夹、从项目根文件夹复制数据到服务器上的文件夹以及访问在服务器上复制的数据的URL地址之间的对应关系。这种对应关系称为映射。

![Remote server configuration](CreateARemoteServerConfiguration_img/go_remote_server_configuration.png)

### 指定服务器配置的名称、类型和可见性

1. 按下Ctrl+Alt+S打开IDE设置，选择Build, Execution, Deployment | Deployment。

   或者，从主菜单中选择Tools | Deployment | Configuration...。

3. 在列出所有现有服务器配置的左侧窗格中，单击 ![Add item](CreateARemoteServerConfiguration_img/app.general.add.svg)并根据您将用于与服务器交换数据的协议选择服务器配置类型。

   - FTP：选择此选项以使GoLand通过FTP [文件传输协议](https://en.wikipedia.org/wiki/File_Transfer_Protocol)访问服务器。
   - SFTP：选择此选项以使GoLand通过[SFTP](https://en.wikipedia.org/wiki/SFTP)文件传输协议访问服务器。
   - FTPS：选择此选项以使GoLand通过FTP文件传输协议通过SSL访问服务器（[FTPS](https://en.wikipedia.org/wiki/FTPS)扩展）。
   - WebDAV：选择此选项以使GoLand通过WebDAV文件传输协议访问服务器（[WebDAV](https://en.wikipedia.org/wiki/WebDAV)扩展）。
   
4. In the Create New Server dialog that opens, type the name of the connection to the server and click OK.

5. 在打开的“创建新服务器”对话框中，输入与服务器的连接的名称，然后单击“确定”。

6. 单击工具栏上的 ![the Use as default button](CreateARemoteServerConfiguration_img/app.actions.setDefault.svg)按钮，以使GoLand在以下情况下静默应用当前配置：

   - [自动上传更改的文件](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#automaticUploadOnUpdate)。
   - 手动[上传](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#manually)和[下载](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#download_file_folder)文件而不选择目标主机。
   - [将本地文件和文件夹与其远程版本进行比较](https://www.jetbrains.com/help/go/comparing-deployed-files-and-folders-with-their-local-versions.html)。
   - [在远程主机上编辑单个文件](https://www.jetbrains.com/help/go/editing-individual-files-on-remote-hosts.html)。
   
   >   您还可以单击GoLand状态栏中的Default Deployment ServerDefault Deployment Server小部件，然后从弹出菜单中选择所需的服务器或服务器组。
   
6. 使用Visible only for this project复选框来配置服务器访问配置的可见性。

   - 选择复选框以限制配置的使用范围仅限于当前项目。这样的配置无法在当前项目之外重用，它不会出现在其他项目中可用配置的列表中。
   - 清除复选框时，配置在所有GoLand项目中可见。其设置可以在多个项目中重复使用。



### 指定在主机注册期间定义的用户凭据

1. 对于FTP和FTPS服务器，请指定注册模式：

   - 若要以常规模式登录，请在“用户名”字段中指定登录名。
   - 要使用您的电子邮件地址作为密码启用[匿名访问](https://www.businessdictionary.com/definition/anonymous-FTP.html)，请选择Login as anonymous复选框。

2. 指定与服务器进行身份验证的方式：

   - 对于FTP和WebDAV服务器，请输入您的密码，并选择Save password复选框以让GoLand记住它。

   - 对于SFTP服务器，请选择已创建的SSH配置之一，或单击 ![the Browse button](CreateARemoteServerConfiguration_img/app.general.ellipsis.svg)并根据[创建SSH配置](https://www.jetbrains.com/help/go/create-ssh-configurations.html)中的说明创建新配置。

   - 对于FTPS服务器，请指定您的用户名和密码。在[高级](https://www.jetbrains.com/help/go/deployment-connection-tab.html#advanced-settings-area)设置区域中，选择要应用的安全机制。

     - 选择Explicit 以应用[显式（主动）安全](https://www.smartftp.com/support/kb/what-is-the-difference-between-implicit-ssl-and-explicit-ssl-f189.html)。在建立连接后立即，您的计算机上的FTP客户端发送一个命令给服务器，通过默认的FTP端口建立安全的控制连接。

       默认情况下选择此方法。

     - 选择Implicit 以应用[隐式（被动）安全](https://www.smartftp.com/support/kb/what-is-the-difference-between-implicit-ssl-and-explicit-ssl-f189.html)。在这种情况下，建立与服务器的连接时会自动提供安全性，服务器为安全连接指定一个单独的端口。

       请注意，此方法已被视为已弃用，不建议使用。



![Remote server configuration](CreateARemoteServerConfiguration_img/go_remote_server_configuration.png)

### 启用对服务器的连接并指定服务器配置根目录 

1. 对于FTP/FTPS/WebDAV服务器，请指定要与之交换数据的服务器的主机名和监听的端口。FTP/FTPS的默认端口值为21。对于WebDAV，默认值为6180。

   对于SFTP服务器，使用所选的[SSH配置](https://www.jetbrains.com/help/go/create-ssh-configurations.html)中指定的值。

2. 在Root path字段中，指定相对于服务器上的根文件夹的服务器配置根。此文件夹将是通过当前服务器配置访问的文件夹结构中的最高级文件夹。

   执行以下操作之一： 

   - 接受default **/** path，指向服务器上的根文件夹。
   - 手动输入路径，或单击 ![Browse button](CreateARemoteServerConfiguration_img/app.general.openDisk.svg)并在打开的Choose Root Path对话框中选择所需的文件夹。
   - 单击Autodetect。GoLand会检测FTP/SFTP服务器上的用户主文件夹设置，并根据它们设置根路径。只有在您指定了凭据时，该按钮才处于启用状态。

   

3. 在Web server URL字段中，输入访问服务器配置根目录的URL地址。服务器配置根是本地或远程服务器上的文件树中的最高级文件夹，通过服务器配置可以访问它。对于就地服务器，它是项目根目录。

   HTTP和HTTPS协议都受支持。

7. 单击字段中的 ![Open URL in browser icon](CreateARemoteServerConfiguration_img/app.toolwindows.webToolWindow.svg)，确保指定的服务器根URL地址可访问且指向正确的Web页面。

5. （可选）对于SFTP服务器，请选择Use Rsync for download/upload/sync，以便GoLand使用[Rsync](https://rsync.samba.org/)进行文件上传和下载，这可以提高文件传输速度。

   单击Rsync Settings链接，并在打开的对话框中配置Rsync设置：

   - 提供 `rsync` 和 `ssh` 可执行文件的路径。

     - 在macOS和Linux上，`rsync` 和 `ssh` 工具已预安装，并且其路径会自动填充。
     - 在Windows上，您需要首先手动安装 [Cygwin](https://www.cygwin.com/) 并安装 `rsync` 和 `openssh` 包。这些工具的可执行文件通常位于 **<Cygwin安装路径>\bin** 文件夹中。

   - 如果需要，在Rsync options字段中覆盖Rsync命令行参数。

     默认情况下，使用 `-zar` 选项，因此Rsync会压缩传输的数据 (`z`)，保留传输的文件和文件夹的权限、所有权和时间戳 (`a`)，并递归传输所有文件和子文件夹 (`r`)。

     有关可用选项的完整列表，请参考[Rsync文档](https://linux.die.net/man/1/rsync)。


   > Rsync用于[上传和下载](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html)操作。所有其他与部署相关的操作，包括[访问远程主机上的文件](https://www.jetbrains.com/help/go/accessing-files-on-remote-hosts.html)、[将部署的文件和文件夹与本地版本进行比较](https://www.jetbrains.com/help/go/comparing-deployed-files-and-folders-with-their-local-versions.html)等，都通过SFTP执行。


### 将本地文件夹映射到服务器文件夹和访问它们的URL地址

​	配置映射，即设置项目文件夹、将项目文件复制到的服务器文件夹以及访问服务器上复制数据的URL地址之间的对应关系。最简单的方式是将整个项目根文件夹映射到服务器上的一个文件夹。在这种情况下，只要您在[选项对话框](https://www.jetbrains.com/help/go/settings-deployment-options.html)中选中了Create Empty directories复选框，项目文件夹结构将在服务器上重复。

1. 按下Ctrl+Alt+S打开IDE设置，并选择Build, Execution, Deployment | Deployment。

   或者，从主菜单中选择Tools | Deployment | Configuration...。

3. 点击Mappings 选项卡。

5. 在Local Path字段中，指定所需本地文件夹的完整路径。在最简单的情况下，它就是项目的根目录。

4. 在Deployment Path字段中，指定GoLand将从Local Path字段指定的文件夹上传数据到服务器上的文件夹。输入相对于服务器配置根目录的文件夹路径。

   如果指定名称的文件夹尚不存在，只要您在[选项对话框](https://www.jetbrains.com/help/go/settings-deployment-options.html)中选中了Create Empty directories复选框，GoLand将创建该文件夹。

   

9. 在Web Path字段中，输入相对于服务器配置根目录的服务器上的文件夹路径。实际上，输入您在Deployment Path字段中输入的相对路径即可。



![Remote server mappings](CreateARemoteServerConfiguration_img/go_remote_server_mappings.png)