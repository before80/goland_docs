+++
title = "创建SSH配置"
weight = 60
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Create SSH configurations﻿ 创建SSH配置

https://www.jetbrains.com/help/go/create-ssh-configurations.html

Last modified: 21 April 2023

Required plugins: FTP/SFTP/WebDAV Connectivity (bundled)



In GoLand, you can save the remote server SSH connection parameters as a dedicated SSH configuration. The created configuration can be then used for configuring remote interpreters, [connecting to SFTP deployment servers](https://www.jetbrains.com/help/go/creating-a-remote-server-configuration.html), and [launching SSH sessions](https://www.jetbrains.com/help/go/running-ssh-terminal.html).

​	在GoLand中，您可以将远程服务器SSH连接参数保存为专用的SSH配置。创建的配置可以用于配置远程解释器，[连接到SFTP部署服务器](https://www.jetbrains.com/help/go/creating-a-remote-server-configuration.html)和[启动SSH会话](https://www.jetbrains.com/help/go/running-ssh-terminal.html)。

1. In the Settings dialog (Ctrl+Alt+S), go to Tools | SSH Configurations.

2. 在设置对话框（Ctrl+Alt+S）中，转到工具 | SSH配置。

3. In the left-hand pane that lists all the existing SSH configurations, click 在列出所有现有SSH配置的左侧窗格中，单击![Add item](CreateSSHConfigurations_img/app.general.add.svg).

4. Use the Visible only for this project checkbox to configure the visibility of the server access configuration.

5. 使用“仅对此项目可见”复选框配置服务器访问配置的可见性。

   - Select the checkbox to restrict the use of the SSH configuration to the current project. Such SSH configuration cannot be reused outside the current project. It does not appear in the list of available configurations in other projects.

   - 选择该复选框以将SSH配置的使用限制为当前项目。此类SSH配置无法在当前项目之外重复使用。它不会出现在其他项目中可用配置的列表中。

     The SSH configurations are stored in the **.idea** directory together with the project, which allows sharing them between team members [through a VCS](https://www.jetbrains.com/help/go/version-control-integration.html).

     SSH配置与项目一起存储在**.idea**目录中，可以通过版本控制系统（VCS）在团队成员之间共享。

     

   - When the checkbox is cleared, the SSH configuration is visible in all GoLand projects. Its settings can be reused across several projects.

   - 如果清除复选框，则SSH配置在所有GoLand项目中可见。其设置可以在多个项目中重复使用。

6. In the Host, User name, and Port fields, specify the connection parameters. If necessary, you can provide the outgoing port in the Local port field. Otherwise, the port is selected automatically.

7. 在主机、用户名和端口字段中，指定连接参数。如果需要，在本地端口字段中提供出站端口。否则，端口将自动选择。

8. Choose the way to authenticate to the server. Do one of the following:

9. 选择身份验证服务器的方式。执行以下操作之一：

   - Password: to access the host with a password. To save the password in GoLand, select the Save password checkbox.

   - Key pair (OpenSSH or PuTTY): to use [SSH authentication](https://www.ssh.com/) with a key pair. To apply this authentication method, you must have a private key on the client machine and a public key on the remote server. GoLand supports private keys that are generated with the [OpenSSH](https://www.openssh.com/) utility.

     Specify the path to the file where your private key is stored and type the passphrase (if any) in the corresponding fields. To have GoLand remember the passphrase, select the Save passphrase checkbox.

   - OpenSSH config and authentication agent: to use SSH keys that are managed by a credentials helper application (for example, [Pageant](https://the.earth.li/~sgtatham/putty/0.70/htmldoc/Chapter9.html#pageant) on Windows or [ssh-agent](https://en.wikipedia.org/wiki/Ssh-agent) on macOS and Linux).

   - 密码：使用密码访问主机。要在GoLand中保存密码，请选中“保存密码”复选框。

   - 密钥对（OpenSSH或PuTTY）：使用密钥对进行[SSH身份验证](https://www.ssh.com/)。要应用此身份验证方法，您必须在客户端机器上拥有私钥和远程服务器上的公钥。GoLand支持使用[OpenSSH](https://www.openssh.com/)工具生成的私钥。

     指定存储私钥的文件路径，并在相应字段中输入密钥密码（如果有）。要使GoLand记住密钥密码，请选中“保存密钥密码”复选框。

   - OpenSSH配置和身份验证代理：使用由凭据助手应用程序（例如Windows上的[Pageant](https://the.earth.li/~sgtatham/putty/0.70/htmldoc/Chapter9.html#pageant)或macOS和Linux上的[ssh-agent](https://en.wikipedia.org/wiki/Ssh-agent)）管理的SSH密钥。

   See the [Generating a new SSH key and adding it to the ssh-agent](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/) tutorial for details on working with SSH keys.

   有关使用SSH密钥的详细信息，请参阅[生成新的SSH密钥并将其添加到ssh-agent](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)教程。

10. Click the Test connection button to make sure that the settings are correct and GoLand can connect to the target server.

11. 单击“测试连接”按钮，确保设置正确，并且GoLand能够连接到目标服务器。


## 支持的OpenSSH指令

- [Host](https://man.openbsd.org/ssh_config#Host)
- [ClearAllForwardings](https://man.openbsd.org/ssh_config#ClearAllForwardings)
- [Compression](https://man.openbsd.org/ssh_config#Compression)
- [ConnectTimeout](https://man.openbsd.org/ssh_config#ConnectTimeout)
- [ForwardX11](https://man.openbsd.org/ssh_config#ForwardX11)
- [ForwardX11Trusted](https://man.openbsd.org/ssh_config#ForwardX11Trusted)
- [GSSAPIAuthentication](https://man.openbsd.org/ssh_config#GSSAPIAuthentication)
- [HashKnownHosts](https://man.openbsd.org/ssh_config#HashKnownHosts)
- [Hostname](https://man.openbsd.org/ssh_config#Hostname)
- [IdentitiesOnly](https://man.openbsd.org/ssh_config#IdentitiesOnly)
- [LocalForward](https://man.openbsd.org/ssh_config#LocalForward)
- [PreferredAuthentications](https://man.openbsd.org/ssh_config#PreferredAuthentications)
- [ProxyCommand](https://man.openbsd.org/ssh_config#ProxyCommand)
- [RemoteForward](https://man.openbsd.org/ssh_config#RemoteForward)
- [ServerAliveCountMax](https://man.openbsd.org/ssh_config#ServerAliveCountMax)
- [AliveInterval](https://man.openbsd.org/ssh_config#ServerAliveInterval)
- [StrictHostKeyChecking](https://man.openbsd.org/ssh_config#StrictHostKeyChecking)
- [UserKnownHostsFile](https://man.openbsd.org/ssh_config#UserKnownHostsFile)
- [XAuthLocation](https://man.openbsd.org/ssh_config#XAuthLocation)
- [ForwardAgent](https://man.openbsd.org/ssh_config#ForwardAgent)