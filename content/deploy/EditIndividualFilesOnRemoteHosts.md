+++
title = "在远程主机上编辑单个文件"
weight = 50
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Edit individual files on remote hosts﻿ 在远程主机上编辑单个文件

https://www.jetbrains.com/help/go/editing-individual-files-on-remote-hosts.html

Last modified: 21 April 2023

最后修改日期：2023年4月21日

Once you have [set up synchronization](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html) with a remote host, you can open individual files directly from the remote host and edit them in GoLand, without adding/downloading them to a local project.

​	一旦您已经[设置了与远程主机的同步](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)，您可以直接从远程主机打开单个文件并在GoLand中进行编辑，而无需将它们添加/下载到本地项目中。

Debugging, refactorings, and some other GoLand features are not supported for such files. To take advantage of advanced GoLand functionality, consider including the files into a project, see [Access files on servers](https://www.jetbrains.com/help/go/accessing-files-on-remote-hosts.html) for details.

​	对于此类文件，不支持调试、重构和其他一些GoLand功能。要利用GoLand的高级功能，请考虑将文件包含到项目中，详细信息请参阅[访问远程主机上的文件](https://www.jetbrains.com/help/go/accessing-files-on-remote-hosts.html)。

### 在远程主机上编辑文件 Edit a file on a remote host﻿

1. If you have set a [default remote host](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html#default_server), select Deployment | Edit Remote File from the context menu in the [Project tool window](https://www.jetbrains.com/help/go/project-tool-window.html), Commit tool window Alt+0, or the code editor.

2. 如果您已经设置了[默认的远程主机](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html#default_server)，在[项目工具窗口](https://www.jetbrains.com/help/go/project-tool-window.html)、提交工具窗口Alt+0或代码编辑器中，从上下文菜单中选择部署 | 编辑远程文件。

   Otherwise, do the following:

   否则，请执行以下操作：

   1. Open the [Remote Host tool window](https://www.jetbrains.com/help/go/remote-host-tool-window.html) by choosing Tools | Deployment | Browse Remote Host or View | Tool Windows | Remote Host from the main menu.

   2. 通过选择工具 | 部署 | 浏览远程主机或查看 | 工具窗口 | 远程主机来打开[远程主机工具窗口](https://www.jetbrains.com/help/go/remote-host-tool-window.html)。

   3. Select the required deployment server from the list. The tool window shows a tree view of files and folders under the server root. If no relevant server is available in the list, click 从列表中选择所需的部署服务器。该工具窗口显示服务器根目录下的文件和文件夹的树形视图。如果列表中没有相关的服务器可用，请单击![the Browse button](EditIndividualFilesOnRemoteHosts_img/app.general.ellipsis.svg), and in the Deployment dialog that opens [configure access to the required server](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html).，并在打开的部署对话框中[配置对所需服务器的访问](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)。

   4. Double-click the desired file or select Edit Remote File from the context menu.

   5. 双击所需的文件或在上下文菜单中选择编辑远程文件。

      ![Edit file on remote host](EditIndividualFilesOnRemoteHosts_img/go_edit_file_on_remote_server.png)

3. The file opens in the GoLand editor, without being added or downloaded to the local project.

4. 文件将在GoLand编辑器中打开，而无需添加或下载到本地项目中。

   When you work with a remote file, a special toolbar appears at the top of the editor, showing the editing status (The file is identical to remote one or The file has been modified. Upload?).

   当您使用远程文件时，编辑器顶部会出现一个特殊的工具栏，显示编辑状态（文件与远程文件相同或文件已修改。上传？）。

   Remote files can be distinguished from local ones by the annotation that includes the server name (in our case it is <MyServer>).

   通过注释，远程文件可以与本地文件区分开来（在我们的例子中是<MyServer>）。

5. When you are done editing the file, do one of the following:

6. 当您完成对文件的编辑后，请执行以下操作之一：

   - To upload the file to the remote host, click 要将文件上传到远程主机，点击![the Upload current remote file button](EditIndividualFilesOnRemoteHosts_img/app.actions.upload.svg) or press Alt+Shift+Q.或按Alt+Shift+Q。
   - To compare the currently opened file with the last uploaded version, click 要将当前打开的文件与上次上传的版本进行比较，点击![the Compare with last uploaded version button](EditIndividualFilesOnRemoteHosts_img/app.actions.diff.svg). The files are opened in the GoLand [Differences viewer for files](https://www.jetbrains.com/help/go/differences-viewer.html).。文件将在GoLand的[文件差异查看器](https://www.jetbrains.com/help/go/differences-viewer.html)中打开。
   - To discard the changes introduced to the file after the last upload, click 要放弃上次上传后对文件所做的更改，点击![the Revert to last uploaded version button](EditIndividualFilesOnRemoteHosts_img/app.actions.rollback.svg).


Note that any changes to an individual file are discarded as soon as you close the file or the currently opened project unless these changes have been uploaded. To prevent losing your data, GoLand displays the following dialog when you attempt to close the edited file or the entire project.

​	请注意，除非这些更改已经上传，否则在关闭编辑的文件或当前打开的项目时，将放弃对单个文件的任何更改。为了避免丢失数据，当您尝试关闭编辑的文件或整个项目时，GoLand会显示以下对话框。

![Confirm uploading message](EditIndividualFilesOnRemoteHosts_img/go_remote_file_unsaved.png)