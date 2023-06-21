+++
title = "部署应用"
linkTitle = "部署应用"
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
[menu.main]
  weight = 14
+++
# Deploy your application﻿ 部署您的应用程序

https://www.jetbrains.com/help/go/deploying-applications.html

Last modified: 08 October 2021

最近修改日期：2021年10月8日

GoLand assumes that all development, debugging, and testing is done on your computer and then the code is deployed to a production environment.

​	GoLand假设所有的开发、调试和测试都在您的计算机上完成，然后将代码部署到生产环境中。

The reason to stick to this "local development - deployment" model lies in the way GoLand provides code completion, code inspections, code navigation, and other coding assistance features. All this functionality is based on the project files index which GoLand builds when the project is loaded and updates on the fly as you edit your code.

​	坚持这种“本地开发-部署”的模式的原因在于GoLand提供的代码完成、代码检查、代码导航和其他编码辅助功能。所有这些功能都基于项目文件索引，当项目加载时，GoLand会构建该索引，并在您编辑代码时实时更新。

To provide efficient coding assistance, GoLand needs to re-index code fast, which requires fast access to project files. The latter can be ensured only for local files, that is, files that are stored on you hard disk and are accessible through the file system.

​	为了提供高效的编码辅助功能，GoLand需要快速重新索引代码，这需要快速访问项目文件。只有对于本地文件，也就是存储在您硬盘上并通过文件系统访问的文件，才能确保这一点。