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

​	您的GoLand项目中的文件和文件夹与服务器上的版本之间的对应关系是通过[部署服务器映射](https://www.jetbrains.com/help/go/creating-local-server-configuration.html)设置的。为了简化起见，您的GoLand项目中的任何文件或文件夹称为本地文件，而服务器上的任何文件或文件夹称为远程文件，即使实际上服务器安装在您的计算机上。有关详细信息，请参阅[配置与服务器的同步](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)。

### 访问服务器

1. 通过选择主菜单中的Tools | Deployment | Browse Remote Host or View | Tool Windows | Remote Host，打开[远程主机工具窗口](https://www.jetbrains.com/help/go/remote-host-tool-window.html)。
3. 从列表中选择所需的部署服务器。工具窗口会显示服务器根目录下的文件和文件夹的树形视图。如果列表中没有相关的服务器可用，请单击![the Browse button](CompareDeployedFilesAndFoldersWithTheirLocalVersions_img/app.general.ellipsis.svg)，在打开的Deployment 对话框中[配置对所需服务器的访问权限](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)。

## 比较服务器上的文件和文件夹与其本地版本

​	每个远程文件或文件夹都会[映射](https://www.jetbrains.com/help/go/creating-local-server-configuration.html)到一个且仅一个本地文件或文件夹。因此，对于每个远程文件或文件夹，GoLand会检测其本地版本，以便您随时在差异查看器中进行比较。


> ​	差异查看器中的远程文件具有`read-only`状态。这意味着您不能直接在差异查看器中更新它们。请对文件的本地版本进行所有必要的更改，然后将更新后的文件上传到服务器

### 比较远程文件与其本地版本

1. 打开[远程主机工具窗口](https://www.jetbrains.com/help/go/remote-host-tool-window.html)（通过工具菜单中的Tools | Deployment | Browse Remote Host or View | Tool Windows | Remote Host）并从列表中选择所需的部署服务器。
3. 选择文件，然后从其上下文菜单中选择Compare with local version。
5. 在打开的[文件差异查看器](https://www.jetbrains.com/help/go/differences-viewer.html)对话框中，查看差异并根据需要应用差异，使用![Replace from right](CompareDeployedFilesAndFoldersWithTheirLocalVersions_img/app.diff.arrow.svg)按钮。有关详细信息，请参阅[查看文件之间的差异](https://www.jetbrains.com/help/go/comparing-files-and-folders.html#twofiles)。

### 比较远程文件夹与其本地版本

1. 打开[远程主机工具窗口](https://www.jetbrains.com/help/go/remote-host-tool-window.html)（通过工具菜单中的Tools | Deployment | Browse Remote Host or View | Tool Windows | Remote Host）并从列表中选择所需的部署服务器。
3. 选择文件夹，然后从选择的上下文菜单中选择Sync with local。
5. 在打开的[文件夹差异查看器](https://www.jetbrains.com/help/go/differences-viewer-for-folders.html)中，查看差异并根据需要同步文件。有关在差异查看器中比较两个文件夹的详细信息，请参阅相关文档。

## 比较本地文件和文件夹与服务器上的版本 

​	由于本地文件或文件夹可以映射到无限数量的远程对应物，只有当它们通过[默认部署服务器](https://www.jetbrains.com/help/go/creating-in-place-server-configuration.html)进行映射时，GoLand才能唯一识别本地文件或文件夹的远程版本。如果没有指定默认的部署服务器，您必须手动选择相关的配置。请注意，为了保持一致，服务器组仅在服务器选择列表中显示，当前无法比较本地文件与部署到服务器组的文件。


> ​	差异查看器中的远程文件具有`read-only`状态。这意味着您不能直接在差异查看器中更新它们。请对文件的本地版本进行所有必要的更改，然后将更新后的文件上传到服务器。

### 比较本地文件与其远程版本

1. 在[项目](https://www.jetbrains.com/help/go/project-tool-window.html)工具窗口中选择文件。
3. 在上下文菜单中，选择`Deployment | Compare with Deployed Version on <default server access configuration>`（如果已指定默认服务器）。否则，选择Sync with Deployed，然后从列表中选择相关的服务器。
5. 在打开的[文件差异查看器](https://www.jetbrains.com/help/go/differences-viewer.html)对话框中，查看差异并根据需要应用差异，使用![Apply from right icon](CompareDeployedFilesAndFoldersWithTheirLocalVersions_img/app.diff.arrow.svg)按钮。有关详细信息，请参阅[查看文件之间的差异](https://www.jetbrains.com/help/go/comparing-files-and-folders.html#twofiles)。

### 比较本地文件夹与其远程版本

4. 在[项目](https://www.jetbrains.com/help/go/project-tool-window.html)工具窗口中选择文件夹。
5. 在选择的上下文菜单中，如果已指定默认服务器，请选择`Sync with Deployed to <default deployment server>`。否则，请选择Sync with Deployed，然后从列表中选择相关的服务器。
6. 在打开的[文件夹差异查看器](https://www.jetbrains.com/help/go/differences-viewer-for-folders.html)中，查看差异并根据需要同步文件。有关在差异查看器中比较两个文件夹的详细信息，请参阅相关文档。

### 比较已更改的本地文件与其远程版本

1. 切换到本地更改视图以查看已更改的本地文件。
4. 在文件上右键单击，然后从上下文菜单中选择Deployment | Compare with Deployed，并从列表中选择目标部署服务器。如果已指定默认服务器组，则还可以选择`Compare with Deployed to <default deployment server>`。

​	有关详细信息，请参阅[管理版本控制下的文件](https://www.jetbrains.com/help/go/adding-files-to-version-control.html)。

### 比较与VCS存储库同步的文件与其远程版本  

4. 通过按下Ctrl+T或选择主菜单中的VCS | <VCS> | Update，将本地文件的内容与VCS存储库同步。
5. 切换到版本控制工具窗口Alt+9的[更新信息](https://www.jetbrains.com/help/go/version-control-tool-window-update-info-tab.html)选项卡。
6. 右键单击文件，然后从上下文菜单中选择Deployment | Compare with Deployed，并从列表中选择目标部署服务器。如果已指定默认服务器，则还可以选择`Compare with Deployed to <default deployment server>`。