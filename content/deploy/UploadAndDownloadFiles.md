+++
title = "上传和下载文件"
weight = 30
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Upload and download files﻿ 上传和下载文件

https://www.jetbrains.com/help/go/uploading-and-downloading-files.html

Last modified: 11 January 2023

最后修改日期：2023年1月11日

GoLand provides the following main ways to upload project files and folders to deployment servers:

​	GoLand提供以下主要方式将项目文件和文件夹上传到部署服务器： 

- Manually, at any time through a menu command.
- Automatically, every time a file is updated, or before starting a debugging session, or during a commit to your version control system.
- 手动方式，通过菜单命令随时进行上传。
- 自动方式，在文件更新时、调试会话开始前或提交到版本控制系统时自动上传。

For downloading files and folders, GoLand supports only the manual mode.

​	对于下载文件和文件夹，GoLand仅支持手动模式。

GoLand shows the logs in the File Transfer tool window (View | Tool Windows | File Transfer).

​	GoLand会在“文件传输”工具窗口（查看 | 工具窗口 | 文件传输）中显示日志。

### 手动上传文件或文件夹 Upload a file or folder manually﻿

- In the Project tool window, right-click a file or folder, then select Deployment | Upload to from the context menu, and choose the target deployment server or server group from the list.

- 在“项目”工具窗口中，右键单击文件或文件夹，然后从上下文菜单中选择“部署 | 上传到”，并从列表中选择目标部署服务器或服务器组。

  If the default server or server group is appointed, you can also select Upload to <default deployment server or server group>.
  
  如果指定了默认服务器或服务器组，您还可以选择“上传到<默认部署服务器或服务器组>”。

### 上传本地修改的文件  Upload locally changed files﻿

1. Switch to the Local Changes view to view the locally changed files.
2. Right-click a file, then select Deployment | Upload to from the context menu, and choose the target deployment server or server group from the list. If the default server or server group group is appointed, you can also select Upload to <default deployment server or server group>.
3. 切换到“本地更改”视图以查看本地修改的文件。
4. 右键单击文件，然后从上下文菜单中选择“部署 | 上传到”，并从列表中选择目标部署服务器或服务器组。如果指定了默认服务器或服务器组，您还可以选择“上传到<默认部署服务器或服务器组>”。

See [Manage files under version control](https://www.jetbrains.com/help/go/adding-files-to-version-control.html) for details.

​	有关详细信息，请参阅[管理版本控制下的文件](https://www.jetbrains.com/help/go/adding-files-to-version-control.html)。

### 在与VCS存储库同步后上传文件  Upload files after synchronizing with a VCS repository﻿

1. Synchronize the contents of your local files with the VCS repository by pressing Ctrl+T or selecting VCS | <VCS> | Update from the main menu.
2. 通过按下Ctrl+T或选择主菜单中的VCS | <VCS> | 更新，将本地文件的内容与VCS存储库进行同步。
3. Switch to the [Update Info](https://www.jetbrains.com/help/go/version-control-tool-window-update-info-tab.html) tab of the Version Control tool window Alt+9.
4. 切换到“版本控制”工具窗口的“更新信息”选项卡（Alt+9）。
5. Right-click a file, then select Deployment | Upload to from the context menu, and choose the target deployment server or server group from the list. If the default server or server group is appointed, you can also select Upload to <default deployment server or server group>.
6. 右键单击文件，然后从上下文菜单中选择“部署 | 上传到”，并从列表中选择目标部署服务器或服务器组。如果指定了默认服务器或服务器组，您还可以选择“上传到<默认部署服务器或服务器组>”。

### 在提交后立即上传已检入文件  Upload checked-in files immediately after commit﻿

1. Start checking in your changes.
2. 开始进行提交更改。
3. In the After Commit area, choose the target server or server group from the Upload files to list. Choose one of the existing configurations or create a new one: click 在“提交后”区域，从“将文件上传到”列表中选择目标服务器或服务器组。选择现有配置之一或创建新配置：单击 ![the Browse button](UploadAndDownloadFiles_img/app.general.ellipsis.svg) and [configure access to the relevant server](https://www.jetbrains.com/help/go/creating-in-place-server-configuration.html) or [set up a server group](https://www.jetbrains.com/help/go/server-groups.html) in the [Deployment](https://www.jetbrains.com/help/go/settings-deployment.html) dialog that opens. 并[配置访问相关服务器](https://www.jetbrains.com/help/go/creating-in-place-server-configuration.html)或在打开的[部署](https://www.jetbrains.com/help/go/settings-deployment.html)对话框中[设置服务器组](https://www.jetbrains.com/help/go/server-groups.html)。
4. To have your selection applied automatically in the future, select the Always use selected server or group of servers checkbox.
5. 若要将所选内容自动应用于将来，请选中“始终使用所选服务器或服务器组”复选框。

### 配置将更改的文件自动上传到默认服务器或服务器组 Configure automatic upload of changed files to the default server or server group﻿

GoLand considers a local file changed as soon as it is saved either automatically or manually (File | Save All or Ctrl+S), see [Write and edit source code](https://www.jetbrains.com/help/go/working-with-source-code.html). Changed files can be automatically uploaded only to the [default deployment server](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html#default_server).

​	只要文件被自动或手动保存（文件 | 全部保存或Ctrl+S），GoLand就会将本地文件视为已更改，详见[编写和编辑源代码](https://www.jetbrains.com/help/go/working-with-source-code.html)。更改的文件只能自动上传到[默认部署服务器](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html#default_server)。

1. Open the [Options](https://www.jetbrains.com/help/go/settings-deployment-options.html) dialog by doing one of the following:

2. 打开“选项”对话框，有以下几种方式：

   - From the main menu, choose Tools | Deployment | Options.
   - In the Settings dialog (Ctrl+Alt+S), go to Build, Execution, Deployment | Deployment | Options.
   - 从主菜单中选择“工具 | 部署 | 选项”。
   - 在设置对话框（Ctrl+Alt+S）中，转到“构建、执行、部署 | 部署 | 选项”。

3. From the Upload changed files automatically to the default server list, choose when you want GoLand to upload changed files:

4. 在“自动将更改的文件上传到默认服务器”列表中，选择GoLand何时上传更改的文件：

   - To upload any manually or automatically saved file, choose Always.
   - To upload only manually saved files, choose On explicit save action.
   - To suppress automatic upload, choose Never.
   - 若要上传任何手动或自动保存的文件，请选择“始终”。
   - 若要仅上传手动保存的文件，请选择“仅在显式保存操作时”。
   - 若要禁止自动上传，请选择“从不”。

5. If you enabled automatic upload, optionally configure the scope it should apply to:

6. 如果启用了自动上传，请选择应用于的范围：

   - Select Skip external changes to exclude local changes that were made using a third-party tool (a VCS, a script, and so on) from automatic upload.

   - 选择“跳过外部更改”以排除使用第三方工具（VCS、脚本等）进行的本地更改，这些更改将不会自动上传。

   - Select Delete remote files when local are deleted to have GoLand automatically delete remote files during automatic uploads in case the local ones are deleted.

   - 选择“删除本地删除的远程文件”以在自动上传期间，当删除本地文件时，GoLand会自动删除远程文件。

     Note that this option serves as an extra safety measure and may result in unwanted files remaining on the remote server. As an example, consider a local file **Foo.php**, which is renamed to **Bar.php**. Since renaming a file is technically indistinguishable from deleting the file and creating a new one, the following will happen after automatic upload:

     请注意，此选项作为额外的安全措施，可能导致不需要的文件留在远程服务器上。举例来说，考虑一个本地文件**Foo.php**被重命名为**Bar.php**。由于重命名文件在技术上与删除文件并创建新文件无法区分，自动上传后会发生以下情况： 
     
     - If the option is enabled, the remote server will only contain **Bar.php**.
     - If the option is disabled, the remote server will contain both **Foo.php** and **Bar.php** after automatic upload. You will probably need to delete **Foo.php** manually afterwards.
     - 如果启用了该选项，则远程服务器只包含**Bar.php**。
     - 如果禁用了该选项，则远程服务器在自动上传后将同时包含**Foo.php**和**Bar.php**。您可能需要手动删除**Foo.php**。



> Enabling the Upload changed files automatically to the default server option also enables [Upload to default server](https://www.jetbrains.com/help/go/saving-and-reverting-changes.html#actions-on-save) in Settings | Tools | Actions on Save.
>
> ​	启用“自动将更改的文件上传到默认服务器”选项还会在“设置 | 工具 | 保存时操作”中启用“上传到默认服务器”

### 下载文件或文件夹 Download a file or folder﻿

- In the Remote Host tool window, select the required file or folder and choose Download from here from the context menu of the selection.
- 在“远程主机”工具窗口中，选择所需文件或文件夹，然后从选择的上下文菜单中选择“从此处下载”。

### 从默认部署服务器下载文件 Download a file from the default deployment server﻿

- From the main menu, choose Tools | Deployment | Download from <default server>.

- 从主菜单中选择“工具 | 部署 | 从<默认服务器>下载”。

  GoLand will prompt you to overwrite local files, if any.
  
  如果有必要，GoLand将提示您覆盖本地文件。