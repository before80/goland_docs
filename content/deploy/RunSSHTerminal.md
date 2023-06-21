+++
title = "运行SSH终端"
weight = 70
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Run SSH terminal﻿ 运行SSH终端

https://www.jetbrains.com/help/go/running-ssh-terminal.html

Last modified: 21 April 2023

最后修改日期：2023年4月21日

Add SSH configurations: Settings | Tools | SSH Configurations

Start an SSH session from the main menu: Tools | Start SSH Session

从主菜单启动SSH会话：工具 | 启动SSH会话

Configure SSH terminal: Settings | Tools | SSH Terminal

配置SSH终端：设置 | 工具 | SSH终端

You can launch an SSH Session right from GoLand. By running commands in a dedicated SSH terminal, you can access data on a remote Web server or a Vagrant instance (virtual machine) via an SSH tunnel, mainly upload and download files.

​	您可以直接从GoLand启动SSH会话。通过在专用的SSH终端中运行命令，您可以通过SSH隧道访问远程Web服务器或Vagrant实例（虚拟机），主要用于上传和下载文件。

### 准备在SSH终端中工作 Prepare to work in the SSH Terminal﻿

1. Make sure an SSH server is available in the destination environment: a remote Web server or a Vagrant instance (virtual machine).

2. 确保目标环境中有一个可用的SSH服务器：远程Web服务器或Vagrant实例（虚拟机）。

3. Register an account on the SSH server in the destination environment and generate a pair of SSH keys or a password, depending on the server policy.

4. 在目标环境的SSH服务器上注册一个帐户，并根据服务器策略生成一对SSH密钥或密码。

   

5. Appoint the destination environment and specify the settings to establish connection with it:

6. 指定目标环境并配置与之建立连接的设置：

   1. In the Settings dialog (Ctrl+Alt+S), go to Tools | SSH Terminal.
   2. 在设置对话框（Ctrl+Alt+S）中，转到工具 | SSH终端。
   3. In the Connection settings area, appoint the destination environment:
   4. 在连接设置区域，指定目标环境：
      - Current Vagrant: select this option to have the commands in the SSH Terminal executed on the currently running [Vagrant virtual machine](https://www.jetbrains.com/help/go/vagrant-support.html).
      - 当前Vagrant：选择此选项以在当前运行的[Vagrant虚拟机](https://www.jetbrains.com/help/go/vagrant-support.html)上执行SSH终端中的命令。
      - SSH configuration: select this option to have the commands in the SSH Terminal executed on the local or remote Web server accessible through one of the [SSH configurations](https://www.jetbrains.com/help/go/create-ssh-configurations.html).
      - SSH配置：选择此选项以在通过[SSH配置](https://www.jetbrains.com/help/go/create-ssh-configurations.html)之一访问的本地或远程Web服务器上执行SSH终端中的命令。
        - Select SSH configuration on every run: if this option is selected, you will have to choose the desired configuration from the popup, every time you choose Tools | Start SSH Session from the main menu.
        - 在每次运行时选择SSH配置：如果选择了此选项，您将需要从弹出窗口中选择所需的配置，每次从主菜单选择工具 | 启动SSH会话。
        - If the desired SSH configuration does not appear in the list, click the Set up configurations link, and define one in the [SSH Configurations](https://www.jetbrains.com/help/go/settings-tools-ssh-configurations.html) page.
        - 如果列表中没有所需的SSH配置，请单击设置配置链接，并在[SSH配置](https://www.jetbrains.com/help/go/settings-tools-ssh-configurations.html)页面中定义一个。
   5. From the Default encoding list, select the desired encoding to be used in the SSH terminal.
   6. 从默认编码列表中选择要在SSH终端中使用的所需编码。


### 启动SSH终端 Launch the SSH Terminal﻿

1. From the main menu, choose Tools | Start SSH Session. Alternatively, invoke the Help | Find Action Ctrl+Shift+A dialog, search for *start ssh..*, and select Start SSH Session.

2. 从主菜单中选择工具 | 启动SSH会话。或者，调用帮助 | 查找动作 Ctrl+Shift+A对话框，搜索“start ssh..”，然后选择“启动SSH会话”。

3. Depending on the connection settings, defined in on the Tools | SSH Terminal page of the Settings dialog (Ctrl+Alt+S), the following types of behavior are possible:

4. 根据在设置对话框（Ctrl+Alt+S）的工具 | SSH终端页面中定义的连接设置，可能会出现以下几种行为类型：

   - If the Current Vagrant option has been selected, the SSH Terminal will provide access to the currently running Vagrant virtual machine.

   - 如果选择了“当前的Vagrant”选项，SSH终端将提供对当前运行的Vagrant虚拟机的访问。

     For details, see [Vagrant](https://www.jetbrains.com/help/go/vagrant-support.html).

     详细信息，请参阅[Vagrant](https://www.jetbrains.com/help/go/vagrant-support.html)。

   - If the SSH configuration option has been selected, the SSH Terminal will provide control over the data on the server accessible through the SSH configuration selected from the list. For details, see [Create SSH configurations](https://www.jetbrains.com/help/go/create-ssh-configurations.html).

   - 如果选择了“SSH配置”选项，SSH终端将通过所选列表中的SSH配置来控制服务器上的数据访问。详细信息，请参阅[创建SSH配置](https://www.jetbrains.com/help/go/create-ssh-configurations.html)。

   - If the Select SSH configuration on every run option has been selected, GoLand will show a list to choose the desired SSH configuration from.

   - 如果选择了“在每次运行时选择SSH配置”选项，GoLand将显示一个列表，供您选择所需的SSH配置。
