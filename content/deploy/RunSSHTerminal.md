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

​	从主菜单启动SSH会话：Tools | Start SSH Session

Configure SSH terminal: Settings | Tools | SSH Terminal

​	配置SSH终端：Settings | Tools | SSH Terminal

​	您可以直接从GoLand启动SSH会话。通过在专用的SSH终端中运行命令，您可以通过SSH隧道访问远程Web服务器或Vagrant实例（虚拟机），主要用于上传和下载文件。

### 准备在SSH终端中工作

1. 确保目标环境中有一个可用的SSH服务器：远程Web服务器或Vagrant实例（虚拟机）。

2. 在目标环境的SSH服务器上注册一个帐户，并根据服务器策略生成一对SSH密钥或密码。

3. 指定目标环境并配置与之建立连接的设置：
   1. 在设置对话框（Ctrl+Alt+S）中，转到Tools | SSH Terminal。
   2. 在连接设置区域，指定目标环境：
      - 当前Vagrant：选择此选项以在当前运行的[Vagrant虚拟机](https://www.jetbrains.com/help/go/vagrant-support.html)上执行SSH终端中的命令。
      - SSH配置：选择此选项以在通过[SSH配置](https://www.jetbrains.com/help/go/create-ssh-configurations.html)之一访问的本地或远程Web服务器上执行SSH终端中的命令。
        - 在每次运行时选择SSH配置：如果选择了此选项，您将需要从弹出窗口中选择所需的配置，每次从主菜单选择工具 | 启动SSH会话。
        - 如果列表中没有所需的SSH配置，请单击设置配置链接，并在[SSH配置](https://www.jetbrains.com/help/go/settings-tools-ssh-configurations.html)页面中定义一个。
   5. 从默认编码列表中选择要在SSH终端中使用的所需编码。



### 启动SSH终端

1. 从主菜单中选择Tools | Start SSH Session。或者，调用帮助 | 查找动作 Ctrl+Shift+A对话框，搜索`start ssh..`，然后选择Start SSH Session。

2. 根据在设置对话框（Ctrl+Alt+S）的Tools | SSH Terminal页面中定义的连接设置，可能会出现以下几种行为类型：

   - 如果选择了Current Vagrant选项，SSH终端将提供对当前运行的Vagrant虚拟机的访问。

     详细信息，请参阅[Vagrant](https://www.jetbrains.com/help/go/vagrant-support.html)。

   - 如果选择了SSH configuratio选项，SSH终端将通过所选列表中的SSH配置来控制服务器上的数据访问。详细信息，请参阅[创建SSH配置](https://www.jetbrains.com/help/go/create-ssh-configurations.html)。

   - 如果选择了SSH configuration on every run选项，GoLand将显示一个列表，供您选择所需的SSH配置。
