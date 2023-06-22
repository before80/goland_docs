+++
title = "运行/调试配置模板列表"
weight = 20
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# List of run/debug configuration templates﻿ - 运行/调试配置模板列表

https://www.jetbrains.com/help/go/list-of-run-debug-configurations.html

Last modified: 06 March 2023

上次修改日期：2023年3月6日

​	本页面列出了GoLand中可用的[运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html)模板。关于如何在您的项目中使用它们的详细说明，请参考相关的操作指南。


> ​	某个运行/调试配置是否在您的IDE中可用可能取决于已安装和启用的[插件](https://www.jetbrains.com/help/go/managing-plugins.html)。

| 名称                                                         | 用途                                                         | 必需的插件                       |
| ------------------------------------------------------------ | ------------------------------------------------------------ | -------------------------------- |
| [Compound](https://www.jetbrains.com/help/go/run-debug-multiple.html#compound-configs) | 并行运行多个运行/调试配置。这在您想要启动各种自动化测试或客户端-服务器应用程序时非常有用。每个配置的控制选项将在运行或调试工具窗口的单独标签中可用。 |                                  |
| [Database script](https://www.jetbrains.com/help/go/run-debug-configuration-database-script.html) | 运行您的数据库脚本并对创建的数据源进行操作。                 | Database                         |
| [Dockerfile](https://www.jetbrains.com/help/go/dockerfile-run-configuration.html) | 当您从Dockerfile中运行容器时，将自动创建该配置。此配置会从Dockerfile构建映像，然后从该映像派生容器。 | Docker                           |
| [Docker镜像](https://www.jetbrains.com/help/go/docker-image-run-configuration.html) | 当您从现有镜像中运行容器时，将自动创建该配置。您可以从本地现有的Docker镜像中运行它，这些镜像您之前已经[Pull](https://www.jetbrains.com/help/go/docker-images.html#pull-image)或[Build](https://www.jetbrains.com/help/go/docker-images.html#build-image)过。 | Docker                           |
| [Docker Compose](https://www.jetbrains.com/help/go/docker-compose-run-configuration.html) | 当您从[Docker Compose文件](https://docs.docker.com/compose/overview/)运行多容器Docker应用程序时，将自动创建该配置。 | Docker                           |
| [Go Build](https://www.jetbrains.com/help/go/go-build.html)  | 运行和调试您的Go应用程序。                                   | Go                               |
| [Go Remote](https://www.jetbrains.com/help/go/go-remote.html) | 在远程服务器上调试Go应用程序。                               | Go                               |
| [Go Test](https://www.jetbrains.com/help/go/go-test.html)    | 运行和调试您的Go测试。                                       | Go                               |
| [Grunt.js](https://www.jetbrains.com/help/go/run-debug-configuration-grunt.html) | 运行和调试Grunt.js任务。                                     |                                  |
| [Gulp.js](https://www.jetbrains.com/help/go/run-debug-configuration-gulp-js.html) | 运行和调试Gulp.js任务。                                      |                                  |
| [HTTP请求](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#http-request-run-debug-configurations) | 直接在GoLand中执行HTTP请求，可以作为单独请求或作为复合运行/调试配置的一部分。 | HTTP Client                      |
| [JavaScript调试](https://www.jetbrains.com/help/go/run-debug-configuration-javascript-debug.html) | 调试在内置或外部Web服务器上运行的JavaScript应用程序，以及调试Dart Web应用程序。 | JavaScript调试器                 |
| [Jest](https://www.jetbrains.com/help/go/run-debug-configuration-jest.html) | 运行和调试[Jest](https://facebook.github.io/jest/)测试。     |                                  |
| [NPM](https://www.jetbrains.com/help/go/run-debug-configuration-npm.html) | 本地运行和调试[npm](https://docs.npmjs.com/misc/scripts)和[Yarn](https://yarnpkg.com/en/)脚本，即GoLand本身启动已安装在计算机上的Node.js并开始执行脚本。 |                                  |
| [Protractor](https://www.jetbrains.com/help/go/run-debug-configuration-protractor.html) | 使用Protractor测试运行和调试AngularJS单元测试。              |                                  |
| [React Native](https://www.jetbrains.com/help/go/run-debug-configuration-react-native.html) | 运行和调试[React Native](http://www.reactnative.com/)应用程序。 |                                  |
| [Shell脚本](https://www.jetbrains.com/help/go/run-debug-configuration-shell-script.html) | 运行[Shell脚本](https://www.jetbrains.com/help/go/shell-scripts.html)。 | Shell脚本                        |
| [tSQLt测试](https://www.jetbrains.com/help/go/tsqlt-test.html) | 运行针对Microsoft SQL Server的存储过程、函数、视图和触发器的测试。 | Database（Microsoft SQL Server） |
| [utPLSQL测试](https://www.jetbrains.com/help/go/utplsql-test.html) | 运行用于PL/SQL中可用的包、函数、过程、触发器、视图和其他对象的测试。 | Database（Oracle）               |