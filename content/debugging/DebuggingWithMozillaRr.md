+++
title = "使用Mozilla rr进行调试"
weight = 70
date = 2023-06-20T10:40:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Debugging with Mozilla rr﻿ - 使用Mozilla rr进行调试

https://www.jetbrains.com/help/go/debugging-with-mozilla-rr.html

Last modified: 16 January 2023

最近修改：2023年1月16日

​	Mozilla rr及其功能仅适用于Linux机器。

​	请确保您的CPU与Mozilla rr兼容。在Mozilla rr的官方网站的限制部分查看限制列表：[官方Mozilla rr网站](https://rr-project.org/)。

​	Mozilla rr是一个工具，您可以使用它来记录、重放和调试应用程序。Mozilla rr的主要思想是帮助您捕获非平凡的错误。

​	Mozilla rr记录了整个程序执行过程。这意味着您只能在程序结束执行时调试记录的跟踪。对于服务器和其他长时间运行的应用程序，您必须终止正在运行的应用程序（例如通过控制台发送SIGTERM信号）。记录完成后，您可以在调试器中重放执行过程，按需多次进行。详细了解Mozilla rr，请访问[官方Mozilla rr网站](https://rr-project.org/)。

### 使用Mozilla rr调试代码 Debug code with Mozilla rr﻿

1. 安装Mozilla rr。有关安装说明，请参阅[构建和安装](https://github.com/mozilla/rr/wiki/Building-And-Installing)。
3. 在GoLand中设置断点。要设置断点，请单击希望调试器停止代码执行的代码行旁边的沟槽。有关断点的更多信息，请参阅[调试](https://www.jetbrains.com/help/go/debugging-code.html)和[断点](https://www.jetbrains.com/help/go/using-breakpoints.html)。
5. 在沟槽上单击运行图标（![The Run icon](DebuggingWithMozillaRr_img/app.runConfigurations.testState.run.svg))，然后选择Record and Debug <configuration_name>。在调试器工具窗口中，您可以查看不同代码执行阶段的变量、进程和线程的状态。

![https://resources.jetbrains.com/help/img/idea/2023.1/go_navigate_through_trace.png](DebuggingWithMozillaRr_img/go_navigate_through_trace.animated.gif)

### 导航浏览记录的跟踪

1. 转到 Run | Debug Saved Trace.
2. 在Trace directory字段中，指定跟踪目录的路径。
4. 单击OK。
6. 在调试器工具窗口中，单击Resume Program图标![The Resume Program icon ](DebuggingWithMozillaRr_img/app.actions.resume_dark.svg)，以继续程序的执行，或单击下方的Rewind图标，以向后运行调试会话，直到前一个断点。

![Navigate through the recorded trace](DebuggingWithMozillaRr_img/go_navigate_controls.png)

### 收集Mozilla rr跟踪

1. 使用Go构建运行/调试配置来构建一个可执行文件。为了方便找到可执行文件，请在Go构建配置的Output directory字段中指定当前项目目录。有关创建运行/调试配置的更多信息，请参阅[创建运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly)。

2. 打开终端并运行以下Mozilla rr命令：`rr record <path_to_the_application_executable>`

   结果，Mozilla rr跟踪文件将出现在以下文件夹中：**~/.local/share/rr/<executable_name>**

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_collect_mozilla_rr_trace.png](DebuggingWithMozillaRr_img/go_collect_mozilla_rr_trace.animated.gif)


### 使用Mozilla rr进行远程调试

1. 在远程机器上[收集Mozilla rr跟踪](https://www.jetbrains.com/help/go/debugging-with-mozilla-rr.html#collecting-mozilla-rr-traces)。

3. 在远程机器上，通过打开终端并运行以下命令启动调试器：`dlv --headless --api-version=2 -l localhost:2345 replay /path/to/trace/dir /path/to/binary`。

5. 在本地机器上，创建Go远程运行/调试配置。在Go远程配置中，指定远程机器的IP地址和端口。有关创建运行/调试配置的更多信息，请参阅[创建运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly)。

7. 在本地机器上，确保在配置列表中选择了Go远程运行/调试配置。

9. 在本地机器上，单击Run | Debug <remote_configuration_name>。或者按下Shift+F9。


   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_remote_debug_with_mozilla_rr.png](DebuggingWithMozillaRr_img/go_remote_debug_with_mozilla_rr.animated.gif)

