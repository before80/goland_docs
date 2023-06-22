+++
title = "从上传和下载中排除文件和文件夹﻿"
weight = 50
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Exclude files and folders from uploading and downloading 从上传和下载中排除文件和文件夹﻿﻿

https://www.jetbrains.com/help/go/excluding-files-and-folders-from-deployment.html

Last modified: 17 March 2022

最后修改日期：2022年3月17日

​	抑制对源代码以外的文件或文件夹进行上传、下载和同步，可以确保源代码不会被意外更新。对于非源代码文件，这样做可以节省系统资源，因为不再无谓地复制媒体、缓存或临时文件。

​	在以下情况下，您可能需要抑制上传/下载：

1. 您将要使用外部创建并上传的源代码。要在GoLand中处理这些远程源代码，您需要将它们下载并整理到项目中。但是，有些源代码是您根本不应该更新的。另一方面，远程主机上的文件夹也可能包含大量您在工作中实际上不需要的媒体、缓存、临时文件等。
3. 您已经从服务器下载了数据并将其整理到GoLand项目中。然而，出于这样或那样的原因，您需要保护服务器上的某些文件或文件夹免受上传/下载的影响，例如防止意外覆盖。
5. 应用程序的本地副本包含源代码和其他您不需要上传的数据。此外，您希望防止某些源代码被错误地覆盖。在这种情况下，您可以抑制所有不应该上传的文件和文件夹的上传/下载。


> ​	无论哪种情况，排除都会递归应用。如果文件夹的路径被明确标记为已排除或文件夹名称与模式匹配，那么它的所有子文件夹（如果有的话）的内容也将受到保护，不会被上传/下载。
>
> ​	还要注意，单独的文件只能通过[按名称排除它们](https://www.jetbrains.com/help/go/excluding-files-and-folders-from-deployment.html#exclude_by_name)来保护免受上传/下载的影响。

## 排除服务器上的文件夹在项目创建后不进行上传/下载﻿

### 将文件夹添加到已排除路径列表﻿ 

1. 打开[部署](https://www.jetbrains.com/help/go/settings-deployment.html)对话框，方法如下：
   - Choose Tools | Deployment | Configuration from the main menu.
   - 从主菜单选择Tools | Deployment | Configuration。
   - 在设置对话框 (Ctrl+Alt+S) 中，选择 Deployment under Build, Execution, Deployment。

3. 在[部署](https://www.jetbrains.com/help/go/settings-deployment.html)对话框中，单击 [已排除的路径](https://www.jetbrains.com/help/go/deployment-excluded-paths-tab.html) 选项卡。该选项卡显示之前排除的本地和远程文件夹的列表。

5. 单击Add 按钮 ![the Add button](ExcludeFilesAndFoldersFromUploadingAndDownloading_img/app.general.add.svg)，并选择 Deployment path。

6. 双击添加到列表中的空行。

8. 在添加的行的末尾，单击Browse 按钮 ![the Browse button](ExcludeFilesAndFoldersFromUploadingAndDownloading_img/app.general.openDisk.svg)。

9. 在Choose remote excluded path对话框中，导航到要排除的文件夹。


   您也可以手动输入路径，但请注意，只接受绝对路径。

   ![Add a folder to the list of excluded paths](ExcludeFilesAndFoldersFromUploadingAndDownloading_img/go_remote_server_add_folder_to_excluded_path.png)

### 在Remote Host工具窗口中将文件夹添加到已排除路径列表

1. 从主菜单选择 Tools | Deployment | Browse Remote Host或 View | Tool Windows | Remote Host。

5. 在打开的[远程主机](https://www.jetbrains.com/help/go/remote-host-tool-window.html)工具窗口中，从列表中选择相应的[服务器配置](https://www.jetbrains.com/help/go/creating-in-place-server-configuration.html)。

6. 选择要排除的文件夹，然后在选择的项目上下文菜单中选择 Exclude Path。

   ![Exclude a folder in the Remote Host tool window](ExcludeFilesAndFoldersFromUploadingAndDownloading_img/go_exclude_folder_in_remote_host_tool_window.png)

## 排除本地文件夹的上传/下载

1. 打开[部署](https://www.jetbrains.com/help/go/settings-deployment.html)对话框，方法如下：

   - 从主菜单选择Tools | Deployment | Configuration。
   - 在设置对话框 (Ctrl+Alt+S) 中，选择 Deployment under Build, Execution, Deployment。

3. 在[部署](https://www.jetbrains.com/help/go/settings-deployment.html)对话框中，单击 [已排除的路径](https://www.jetbrains.com/help/go/deployment-excluded-paths-tab.html) 选项卡。

5. 单击Add 按钮 ![the Add button](ExcludeFilesAndFoldersFromUploadingAndDownloading_img/app.general.add.svg)，并选择 Local path。

6. 在添加的行的末尾，单击 Browse 按钮 ![Browse button](ExcludeFilesAndFoldersFromUploadingAndDownloading_img/app.general.openDisk.svg)，然后导航到要排除的文件夹。

   您也可以手动输入路径，但请注意，只接受绝对路径。

   ![Exclude a local folder](ExcludeFilesAndFoldersFromUploadingAndDownloading_img/go_remote_server_exclude_local_folder.png)

## 按名称排除文件和文件夹的上传/下载

1. 打开[选项](https://www.jetbrains.com/help/go/settings-deployment-options.html)对话框，方法如下：

   - 从主菜单选择 Tools | Deployment | Options。
   - 在设置对话框 (Ctrl+Alt+S) 中，转到Build, Execution, Deployment | Deployment | Options。

2. 在打开的[选项](https://www.jetbrains.com/help/go/settings-deployment-options.html)对话框中，将定义这些文件和文件夹名称的模式指定为Exclude items by name 字段。

   使用分号 `;` 作为分隔符，星号 `*` 匹配零个或多个字符，问号 `?` 匹配单个字符。

   例如，如果您有一个名为 **stylesheets** 的文件夹，其中包含三个文件 **style.css**、**style1.css** 和 **style2.scss**，那么 `style*` 将排除整个文件夹，`style?.css` 将排除 **style.css**，`style?.*` 将排除 **style1.css** 和 **style2.scss**。

   从[正则表达式.info](https://www.regular-expressions.info/quickstart.html)了解更多信息。

   排除操作递归应用。这意味着如果匹配的文件夹有子文件夹，则这些子文件夹的内容也不会被部署。

   ![Exclude files by name](ExcludeFilesAndFoldersFromUploadingAndDownloading_img/go_remote_server_exclude_files_by_name.png)


## 取消排除标记

- 选择要上传/下载的文件或文件夹，然后从上下文菜单中选择 Remove Path from Excluded。

  将文件夹恢复到上传/下载会影响其所有子文件夹和文件。
