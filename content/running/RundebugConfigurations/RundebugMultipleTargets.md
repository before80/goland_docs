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

GoLand provides several ways to run/debug multiple things at once, for example, a client-server app or a complex test, which requires launching several different processes or tasks. The first step in any case would be to [create run configurations](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly) for each of the tasks or processes that need to be launched. Once all necessary configurations are in place, you have several options of launching them:

GoLand提供了多种同时运行/调试多个内容的方法，例如客户端-服务器应用程序或需要启动多个不同进程或任务的复杂测试。无论哪种情况，第一步都是为需要启动的每个任务或进程[创建运行配置](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly)。一旦所有必要的配置都准备好，您有几种启动它们的选项： 

- [Launch multiple configurations in parallel](https://www.jetbrains.com/help/go/run-debug-multiple.html#compound-configs) using a compound run configuration
- [Launch multiple configurations in sequence](https://www.jetbrains.com/help/go/run-debug-multiple.html#before_launch) using the Before Launch tasks
- 使用复合运行配置[并行启动多个配置](https://www.jetbrains.com/help/go/run-debug-multiple.html#compound-configs)
- 使用"启动前"任务[按顺序启动多个配置](https://www.jetbrains.com/help/go/run-debug-multiple.html#before_launch)

When multiple configurations are launched at once, each will be available in a separate tab in the Run or Debug tool window.

​	当同时启动多个配置时，每个配置将在运行或调试工具窗口的单独标签中可用。

## 使用复合运行/调试配置并行启动 Parallel launch with a compound run/debug configuration﻿

A Compound run configuration lets you launch several run/debug configurations simultaneously.

复合运行/调试配置允许您同时启动多个运行/调试配置。


> The exact order of launching different configurations within the compound configuration is not guaranteed.
>
> 复合配置中不同配置的启动顺序不能保证。

### 创建复合运行/调试配置 Create a compound run/debug configuration﻿

1. [Create a run/debug configuration](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly) for each app and/or process that should be launched in your session.

2. 为每个要在会话中启动的应用程序和/或进程[创建运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly)。

3. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.

4. 从主菜单中选择 Run | Edit Configurations。或者按下 Alt+Shift+F10，然后按 0。

5. In the Run/Debug Configurations dialog, click 在运行/调试配置对话框中，单击![the Add button](RundebugMultipleTargets_img/app.general.add.svg) or press Alt+Insert, then select Compound.  或按下 Alt+Insert，然后选择 Compound。

6. Specify the run/debug configuration name in the Name field. This name will be shown in the list of the available run/debug configurations.

7. 在名称字段中指定运行/调试配置的名称。此名称将显示在可用的运行/调试配置列表中。

8. Select Store as project file to make this run/debug configuration available to other team members.

9. 选择将此运行/调试配置存储为项目文件，以便其他团队成员可以使用。

10. To include a new run/debug configuration into the compound configuration , click Add 要将新的运行/调试配置包含在复合配置中，请单击添加 ![the Add button](RundebugMultipleTargets_img/app.general.add.svg) and select the desired one from the list.  并从列表中选择所需的配置。

11. Apply changes and close the dialog.

12. 应用更改并关闭对话框。

    ![Create a compound Run/Debug configuration](RundebugMultipleTargets_img/go_create_compound_configuration.png)

Once you set up the compound configuration, you can launch it with or without debugging.

​	设置完复合配置后，您可以带有或不带有调试启动它。

## 使用"启动前"任务按顺序启动 Sequential launch with the Before Launch task﻿

You can use run/debug configuration's Before Launch tasks [for many different things](https://www.jetbrains.com/help/go/run-debug-configuration.html), and one of them is to launch other run/debug configurations.

​	您可以使用运行/调试配置的"启动前"任务[执行许多不同的操作](https://www.jetbrains.com/help/go/run-debug-configuration.html)，其中之一是启动其他运行/调试配置。

### 配置"启动前"任务 Configure 'Before Launch' tasks﻿

1. [Create a run/debug configuration](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly) for each app and/or process that should be launched in your session.
2. 为每个要在会话中启动的应用程序和/或进程[创建运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly)。
3. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.
4. 从主菜单中选择 Run | Edit Configurations。或者按下 Alt+Shift+F10，然后按 0。
5. In the Run/Debug Configuration dialog, select the configuration that should be launched last.
6. 在运行/调试配置对话框中，选择应该最后启动的配置。
7. Expand the Before Launch section in the configuration settings.
8. 展开配置设置中的"启动前"部分。
9. 单击![Add](RundebugMultipleTargets_img/app.general.add.png) Add, then   添加，然后![App run configurations test state run](RundebugMultipleTargets_img/app.runConfigurations.testState.run.svg) Run Another Configuration, and then select the desired configuration. 运行其他配置，并选择所需的配置。
10. Make sure that all necessary configurations are added. Use the 确保添加了所有必要的配置。使用 ![App actions move up](RundebugMultipleTargets_img/app.actions.moveUp.svg) Up Alt+Up and  Up Alt+Up 和![App actions move down](RundebugMultipleTargets_img/app.actions.moveDown.svg) Down Alt+Down to arrange the launch order (configurations at the top will be launched first). Down Alt+Down 进行启动顺序的调整（位于顶部的配置将首先启动）。
11. Apply the changes and close the dialog.
12. 应用更改并关闭对话框。

Once you set up Before Launch tasks in the configuration that should be started last, you can launch it with or without debugging.

​	在设置了应该最后启动的配置的"启动前"任务后，您可以带有或不带有调试启动它。