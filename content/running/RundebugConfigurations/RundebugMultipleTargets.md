+++
title = "运行/调试多个目标"
weight = 30
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Run/debug multiple targets﻿ - 运行/调试多个目标

https://www.jetbrains.com/help/go/run-debug-multiple.html

Last modified: 09 November 2022

上次修改日期：2022年11月9日

​	GoLand提供了多种同时运行/调试多个内容的方法，例如客户端-服务器应用程序或需要启动多个不同进程或任务的复杂测试。无论哪种情况，第一步都是为需要启动的每个任务或进程[创建运行配置](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly)。一旦所有必要的配置都准备好，您有几种启动它们的选项： 

- 使用复合运行配置[并行启动多个配置](https://www.jetbrains.com/help/go/run-debug-multiple.html#compound-configs)
- 使用"启动前"任务[按顺序启动多个配置](https://www.jetbrains.com/help/go/run-debug-multiple.html#before_launch)

​	当同时启动多个配置时，每个配置将在运行或调试工具窗口的单独标签中可用。

## 使用复合运行/调试配置并行启动 

​	复合运行/调试配置允许您同时启动多个运行/调试配置。


> ​	复合配置中不同配置的启动顺序不能保证。

### 创建复合运行/调试配置

1. 为每个要在会话中启动的应用程序和/或进程[创建运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly)。

3. 从主菜单中选择 Run | Edit Configurations。或者按下 Alt+Shift+F10，然后按 0。

5. 在运行/调试配置对话框中，单击![the Add button](RundebugMultipleTargets_img/app.general.add.svg)或按下 Alt+Insert，然后选择 Compound。

6. 在名称字段中指定运行/调试配置的名称。此名称将显示在可用的运行/调试配置列表中。

8. 选择将此运行/调试配置存储为项目文件，以便其他团队成员可以使用。

10. 要将新的运行/调试配置包含在复合配置中，请单击添加 ![the Add button](RundebugMultipleTargets_img/app.general.add.svg)并从列表中选择所需的配置。

7. 应用更改并关闭对话框。

   ![Create a compound Run/Debug configuration](RundebugMultipleTargets_img/go_create_compound_configuration.png)


​	设置完复合配置后，您可以带有或不带有调试启动它。

## 使用Before Launch任务按顺序启动

​	您可以使用运行/调试配置的Before Launch任务[执行许多不同的操作](https://www.jetbrains.com/help/go/run-debug-configuration.html)，其中之一是启动其他运行/调试配置。

### 配置Before Launch任务

1. 为每个要在会话中启动的应用程序和/或进程[创建运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly)。
3. 从主菜单中选择 Run | Edit Configurations。或者按下 Alt+Shift+F10，然后按 0。
5. 在运行/调试配置对话框中，选择应该最后启动的配置。
7. 展开配置设置中的Before Launch部分。
9. 单击![Add](RundebugMultipleTargets_img/app.general.add.png)添加，然后![App run configurations test state run](RundebugMultipleTargets_img/app.runConfigurations.testState.run.svg)运行其他配置，并选择所需的配置。
10. 确保添加了所有必要的配置。使用 ![App actions move up](RundebugMultipleTargets_img/app.actions.moveUp.svg)和![App actions move down](RundebugMultipleTargets_img/app.actions.moveDown.svg)进行启动顺序的调整（位于顶部的配置将首先启动)。
11. 应用更改并关闭对话框。

​	在设置了应该最后启动的配置的Before Launch任务后，您可以带有或不带有调试启动它。