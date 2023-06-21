+++
title = "将部署的文件和文件夹与其本地版本进行比较"
weight = 40
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Compare deployed files and folders with their local versions﻿ 将部署的文件和文件夹与其本地版本进行比较

https://www.jetbrains.com/help/go/comparing-deployed-files-and-folders-with-their-local-versions.html

Last modified: 21 April 2023

最近修改日期：2023年4月21日

The correspondence between files and folders in your GoLand project and their versions on a server is set through [deployment server mappings](https://www.jetbrains.com/help/go/creating-local-server-configuration.html). For the sake of simplicity, any file or folder in your GoLand project is called local and any file or folder on the server is called remote, even if the server is actually installed on your machine. For details, see [Configure synchronization with a server](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html).

​	您的GoLand项目中的文件和文件夹与服务器上的版本之间的对应关系是通过[部署服务器映射](https://www.jetbrains.com/help/go/creating-local-server-configuration.html)设置的。为了简化起见，您的GoLand项目中的任何文件或文件夹称为本地文件，而服务器上的任何文件或文件夹称为远程文件，即使实际上服务器安装在您的计算机上。有关详细信息，请参阅[配置与服务器的同步](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)。

### 访问服务器 Access a server﻿

1. Open the [Remote Host tool window](https://www.jetbrains.com/help/go/remote-host-tool-window.html) by choosing Tools | Deployment | Browse Remote Host or View | Tool Windows | Remote Host from the main menu.
2. 通过选择主菜单中的“工具” | “部署” | “浏览远程主机”或“视图” | “工具窗口” | “远程主机”，打开[远程主机工具窗口](https://www.jetbrains.com/help/go/remote-host-tool-window.html)。
3. Select the required deployment server from the list. The tool window shows a tree view of files and folders under the server root. If no relevant server is available in the list, click 从列表中选择所需的部署服务器。工具窗口会显示服务器根目录下的文件和文件夹的树形视图。如果列表中没有相关的服务器可用，请单击![the Browse button](CompareDeployedFilesAndFoldersWithTheirLocalVersions_img/app.general.ellipsis.svg), and in the Deployment dialog that opens [configure access to the required server](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html).，在打开的“部署”对话框中[配置对所需服务器的访问权限](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)。

## 比较服务器上的文件和文件夹与其本地版本 Comparing files and folders on the server with their local versions﻿

Each remote file or folder is [mapped](https://www.jetbrains.com/help/go/creating-local-server-configuration.html) to one and only one local file or folder. Therefore for each remote file or folder, GoLand detects its local version so you can compare them at any time in the Difference viewer.

​	每个远程文件或文件夹都会[映射](https://www.jetbrains.com/help/go/creating-local-server-configuration.html)到一个且仅一个本地文件或文件夹。因此，对于每个远程文件或文件夹，GoLand会检测其本地版本，以便您随时在差异查看器中进行比较。


> The remote files in the Difference Viewer have the `read-only` status. This means that you cannot update them directly in the Difference Viewer. Make all the necessary changes to the local version of the file and upload the updated file to the server.
>
> ​	差异查看器中的远程文件具有“只读”状态。这意味着您不能直接在差异查看器中更新它们。请对文件的本地版本进行所有必要的更改，然后将更新后的文件上传到服务器

### 比较远程文件与其本地版本  Compare a remote file with its local version﻿

1. Open the [Remote Host tool window](https://www.jetbrains.com/help/go/remote-host-tool-window.html) (Tools | Deployment | Browse Remote Host or View | Tool Windows | Remote Host) and select the required deployment server from the list.
2. 打开[远程主机工具窗口](https://www.jetbrains.com/help/go/remote-host-tool-window.html)（通过工具菜单中的“部署” | “浏览远程主机”或“视图” | “工具窗口” | “远程主机”）并从列表中选择所需的部署服务器。
3. Select the file, and then select Compare with local version from its context menu.
4. 选择文件，然后从其上下文菜单中选择“与本地版本比较”。
5. In the [Differences Viewer for Files](https://www.jetbrains.com/help/go/differences-viewer.html) dialog that opens, explore the differences and apply them, if necessary, using the 在打开的[文件差异查看器](https://www.jetbrains.com/help/go/differences-viewer.html)对话框中，查看差异并根据需要应用差异，使用![Replace from right](CompareDeployedFilesAndFoldersWithTheirLocalVersions_img/app.diff.arrow.svg) button. For details, see [Viewing Differences Between Files](https://www.jetbrains.com/help/go/comparing-files-and-folders.html#twofiles).按钮。有关详细信息，请参阅[查看文件之间的差异](https://www.jetbrains.com/help/go/comparing-files-and-folders.html#twofiles)。

### 比较远程文件夹与其本地版本  Compare a remote folder with its local version﻿

1. Open the [Remote Host tool window](https://www.jetbrains.com/help/go/remote-host-tool-window.html) (Tools | Deployment | Browse Remote Host or View | Tool Windows | Remote Host) and select the required deployment server from the list.
2. 打开[远程主机工具窗口](https://www.jetbrains.com/help/go/remote-host-tool-window.html)（通过工具菜单中的“部署” | “浏览远程主机”或“视图” | “工具窗口” | “远程主机”）并从列表中选择所需的部署服务器。
3. Select the folder and choose Sync with local from the context menu of the selection.
4. 选择文件夹，然后从选择的上下文菜单中选择“与本地同步”。
5. In the [Differences Viewer for Folders](https://www.jetbrains.com/help/go/differences-viewer-for-folders.html) that opens, explore the differences and synchronize the files, where applicable. See comparing two folders in the difference viewer.
6. 在打开的[文件夹差异查看器](https://www.jetbrains.com/help/go/differences-viewer-for-folders.html)中，查看差异并根据需要同步文件。有关在差异查看器中比较两个文件夹的详细信息，请参阅相关文档。

## 比较本地文件和文件夹与服务器上的版本 Comparing local files and folders with their versions on the server﻿

Because a local file or folder can be mapped to an unlimited number of remote counterparts, GoLand can uniquely identify remote versions of local files or folders only when they are mapped through the [default deployment server](https://www.jetbrains.com/help/go/creating-in-place-server-configuration.html). If no such default deployment server is appointed, you have to choose the relevant configuration manually. Note that [server groups](https://www.jetbrains.com/help/go/server-groups.html) are displayed in the server selection list only for consistency purposes: currently, it is not possible to compare local files with the ones deployed to a server group.

​	由于本地文件或文件夹可以映射到无限数量的远程对应物，只有当它们通过[默认部署服务器](https://www.jetbrains.com/help/go/creating-in-place-server-configuration.html)进行映射时，GoLand才能唯一识别本地文件或文件夹的远程版本。如果没有指定默认的部署服务器，您必须手动选择相关的配置。请注意，为了保持一致，服务器组仅在服务器选择列表中显示，当前无法比较本地文件与部署到服务器组的文件。


> The remote files in the Difference Viewer have the `read-only` status. This means that you cannot update them directly in the Difference Viewer. Make all the necessary changes to the local version of the file and upload the updated file to the server.
>
> ​	差异查看器中的远程文件具有“只读”状态。这意味着您不能直接在差异查看器中更新它们。请对文件的本地版本进行所有必要的更改，然后将更新后的文件上传到服务器。

### 比较本地文件与其远程版本  Compare a local file with its remote version﻿

1. Select the file in the [Project](https://www.jetbrains.com/help/go/project-tool-window.html) tool window.
2. 在[项目](https://www.jetbrains.com/help/go/project-tool-window.html)工具窗口中选择文件。
3. In the context menu, select Deployment | Compare with Deployed Version on <default server access configuration> if a default server is appointed. Otherwise, select Sync with Deployed to and then choose the relevant server from the list.
4. 在上下文菜单中，选择“部署” | “与默认服务器版本进行比较访问配置”（如果已指定默认服务器）。否则，选择“与部署进行同步”，然后从列表中选择相关的服务器。
5. In the [Differences Viewer for Files](https://www.jetbrains.com/help/go/differences-viewer.html) dialog, that opens, explore the differences and apply them, if necessary, using the 在打开的[文件差异查看器](https://www.jetbrains.com/help/go/differences-viewer.html)对话框中，查看差异并根据需要应用差异，使用![Apply from right icon](CompareDeployedFilesAndFoldersWithTheirLocalVersions_img/app.diff.arrow.svg) button. For details, see [Viewing Differences Between Files](https://www.jetbrains.com/help/go/comparing-files-and-folders.html#twofiles).按钮。有关详细信息，请参阅[查看文件之间的差异](https://www.jetbrains.com/help/go/comparing-files-and-folders.html#twofiles)。

### 比较本地文件夹与其远程版本  Compare a local folder with its remote version﻿

1. Select the folder in the [Project](https://www.jetbrains.com/help/go/project-tool-window.html) tool window.
2. From the context menu of the selection, choose Sync with Deployed to <default deployment server> if a default server is appointed. Otherwise, choose Sync with Deployed to and then choose the relevant server from the list.
3. In the [Differences Viewer for Folders](https://www.jetbrains.com/help/go/differences-viewer-for-folders.html) that opens, explore the differences and synchronize the files, where applicable. See comparing two folders in the difference viewer.
4. 在[项目](https://www.jetbrains.com/help/go/project-tool-window.html)工具窗口中选择文件夹。
5. 在选择的上下文菜单中，如果已指定默认服务器，请选择“与部署同步到<默认部署服务器>”。否则，请选择“与部署同步”，然后从列表中选择相关的服务器。
6. 在打开的[文件夹差异查看器](https://www.jetbrains.com/help/go/differences-viewer-for-folders.html)中，查看差异并根据需要同步文件。有关在差异查看器中比较两个文件夹的详细信息，请参阅相关文档。

### 比较已更改的本地文件与其远程版本 Compare locally changed files with their remote versions﻿

1. Switch to the Local Changes view to view the locally changed files.
2. Right-click a file, then select Deployment | Compare with Deployed to from the context menu, and choose the target deployment server from the list. If the default server group is appointed, you can also select Compare with Deployed to <default deployment server>.
3. 切换到本地更改视图以查看已更改的本地文件。
4. 在文件上右键单击，然后从上下文菜单中选择“部署” | “与部署进行比较”，并从列表中选择目标部署服务器。如果已指定默认服务器组，则还可以选择“与部署进行比较<默认部署服务器>”。

See [Manage files under version control](https://www.jetbrains.com/help/go/adding-files-to-version-control.html) for details.

​	有关详细信息，请参阅[管理版本控制下的文件](https://www.jetbrains.com/help/go/adding-files-to-version-control.html)。

### 比较与VCS存储库同步的文件与其远程版本  Compare the files synchronized with a VCS repository with their remote versions﻿

1. Synchronize the contents of your local files with the VCS repository by pressing Ctrl+T or selecting VCS | <VCS> | Update from the main menu.
2. Switch to the [Update Info](https://www.jetbrains.com/help/go/version-control-tool-window-update-info-tab.html) tab of the Version Control tool window Alt+9.
3. Right-click a file, then select Deployment | Compare with Deployed to from the context menu, and choose the target deployment server from the list. If the default server is appointed, you can also select Compare with Deployed to <default deployment server>.
4. 通过按下Ctrl+T或选择主菜单中的VCS | <VCS> | 更新，将本地文件的内容与VCS存储库同步。
5. 切换到版本控制工具窗口Alt+9的[更新信息](https://www.jetbrains.com/help/go/version-control-tool-window-update-info-tab.html)选项卡。
6. 右键单击文件，然后从上下文菜单中选择“部署” | “与部署进行比较”，并从列表中选择目标部署服务器。如果已指定默认服务器，则还可以选择“与部署进行比较<默认部署服务器>”。