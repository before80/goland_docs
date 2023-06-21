+++
title = "将服务器组织成组﻿"
weight = 60
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Organize servers into groups﻿ 将服务器组织成组﻿

https://www.jetbrains.com/help/go/server-groups.html

Last modified: 17 March 2022

最后修改日期：2022年3月17日

Server groups let you group server configurations together and work with them as with a single entity. If you need to deploy code to multiple servers, you can use a server group and avoid deploying to each server individually.

​	服务器组允许您将服务器配置分组并将它们作为单个实体进行操作。如果您需要将代码部署到多个服务器，您可以使用服务器组，避免逐个服务器进行部署。

### 创建服务器组﻿ Create a server group﻿

1. Press Ctrl+Alt+S to open the IDE settings and select Build, Execution, Deployment | Deployment.

2. 按下 Ctrl+Alt+S 打开IDE设置，选择 "构建、执行、部署" | "部署"。

   Alternatively, from the main menu, select Tools | Deployment | Configuration....

   或者，从主菜单选择 "工具" | "部署" | "配置..."。

3. In the left-hand pane that lists all the existing server configurations, click Add 在左侧列出所有现有服务器配置的窗格中，点击添加 ![Add item](OrganizeServersIntoGroups_img/app.general.add.svg) and select Server group in the popup menu.，然后在弹出菜单中选择 "服务器组"。

4. In the Create new group dialog that opens, type the name of the group to be created and click OK. The Create new group dialog closes and you return to the [Connection](https://www.jetbrains.com/help/go/deployment-connection-tab.html) tab of the [Deployment](https://www.jetbrains.com/help/go/settings-deployment.html) node.

5. 在打开的 "创建新组" 对话框中，输入要创建的组的名称，然后点击 "确定"。创建新组对话框关闭，您回到[连接](https://www.jetbrains.com/help/go/deployment-connection-tab.html)选项卡下的[部署](https://www.jetbrains.com/help/go/settings-deployment.html)节点。

6. To create a new server configuration inside the group, select the group in the left-hand pane and click either the Add new server link in the right-hand pane or the 要在组内创建一个新的服务器配置，选择左侧窗格中的组，然后在右侧窗格中单击 "添加新服务器" 链接或者工具栏上的 ![Add button](OrganizeServersIntoGroups_img/app.general.add.svg) toolbar button. Then configure the newly created server depending on its type as described in [Configure synchronization with a server](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html). 按钮。然后根据其类型配置新创建的服务器，如[配置与服务器的同步](https://www.jetbrains.com/help/go/configuring-synchronization-with-a-remote-host.html)中所述。

   To add an existing server configuration to the group, drag it into the group. To remove a server configuration, drag it out of the group.

   要将现有的服务器配置添加到组中，将其拖入组中。要删除服务器配置，将其拖出组。

   ![https://resources.jetbrains.com/help/img/idea/2023.1/ps_add_remove_servers_server_group.png](OrganizeServersIntoGroups_img/ps_add_remove_servers_server_group.animated.gif)

7. Click 单击工具栏上的 ![the Use as default button](OrganizeServersIntoGroups_img/app.actions.setDefault.svg) on the toolbar to have GoLand silently apply the current server group in the following cases: 按钮，使GoLand在以下情况下默默应用当前服务器组：

   - [Automatic upload of changed files](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#automaticUploadOnUpdate).
   - Manual [upload](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#manually) and [download](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#download_file_folder) of files without choosing the target host.
   - [Editing individual files on remote hosts](https://www.jetbrains.com/help/go/editing-individual-files-on-remote-hosts.html).
   - [自动上传更改的文件](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#automaticUploadOnUpdate)。
   - 手动[上传](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#manually)和[下载](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html#download_file_folder)文件，而无需选择目标主机。
   - [在远程主机上编辑单个文件](https://www.jetbrains.com/help/go/editing-individual-files-on-remote-hosts.html)。

   > You can also click the Default Deployment Server widget in the GoLand status bar and select the desired server or server group from the popup menu.
   >
   > 您还可以在GoLand状态栏中单击默认部署服务器小部件，并从弹出菜单中选择所需的服务器或服务器组。

8. Use the For current project checkbox to configure the server group visibility, which also applies to all servers contained in the group.

9. 使用 "对于当前项目" 复选框配置服务器组的可见性，该设置也适用于组中包含的所有服务器。

   - Select the checkbox to restrict the use of the group to the current project. Such group cannot be reused outside the current project. It does not appear in the list of available configurations in other projects.
   - When the checkbox is cleared, the group is visible in all GoLand projects. Its settings can be reused across several projects.
   - 选中复选框以将组的使用限制为当前项目。这样的组不能在当前项目之外重用。它不会出现在其他项目中可用配置的列表中。
   - 清除复选框时，该组在所有GoLand项目中可见。其设置可以在多个项目之间重用。


The created server group can now be used for [uploading and downloading files](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html) to the contained servers.

​	现在可以使用创建的服务器组进行[上传和下载文件](https://www.jetbrains.com/help/go/uploading-and-downloading-files.html)到包含的服务器。