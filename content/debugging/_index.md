+++
title = "调试"
linkTitle = "调试"
date = 2023-06-20T10:40:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
[menu.main]
    weight = 11

+++
# Debugging﻿ - 调试

https://www.jetbrains.com/help/go/debugging-code.html

Last modified: 05 March 2023

最后修改日期：2023年3月5日

​	在调试会话中，您可以通过调试器附加到程序上来运行程序。调试器的目的是干预程序的执行并为您提供底层发生情况的信息。这有助于检测和修复程序中的错误。


> ​	有多种方式可以进行调试会话，但为了简单起见，本文档假设您是从GoLand构建和运行项目。这是最常见的情况，并且与更高级的技术相比有更少的限制。有关附加到进程和调试远程应用程序的过程，请参阅[使用调试器附加到正在运行的Go进程](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html)。

### 调试前准备

1. Configure common [debugging properties and behavior](https://www.jetbrains.com/help/go/settings-debugger.html) in Settings | Build, Execution, Deployment | Debugger.

2. 在Settings | Build, Execution, Deployment | Debugger中配置常见的[调试属性和行为](https://www.jetbrains.com/help/go/settings-debugger.html)。

   如果您是初次进行调试，开箱即用的配置将适合您。有关每个调试器功能的主题提供参考并解释了相关的设置。如果您是高级用户并且正在寻找特定的属性，请参阅[调试器](https://www.jetbrains.com/help/go/settings-debugger.html)参考部分。

3. 如果您要使用自定义配置，则需要定义一个运行/调试配置。如果您需要将一些参数传递给程序或在启动前执行一些特殊操作，这是必需的。有关如何设置运行/调试配置的更多信息，请参阅[运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html)部分。大多数情况下，调试简单的程序不需要这样做，这些程序不需要参数或具有任何特殊要求。



## 通用调试过程

​	没有适用于所有应用程序的通用调试过程。根据实际需求，您可能需要按不同的顺序使用不同的操作。本主题提供了一般的指导方针，代表了典型的调试步骤。关于何时以及如何使用特定功能的详细信息，请参阅相应的主题。

1. 定义程序需要停止的位置。使用[断点](https://www.jetbrains.com/help/go/using-breakpoints.html)来完成此操作。断点是特殊的标记，表示当调试器需要步入并冻结程序状态的地方和/或条件。被调试器冻结的程序被称为已暂停。

2. [以调试模式运行程序](https://www.jetbrains.com/help/go/starting-the-debugger-session.html)

   就像正常运行程序一样，您可以同时进行调试。

3. 在程序被暂停后，使用调试器来[获取程序状态的信息](https://www.jetbrains.com/help/go/examining-suspended-program.html)以及它在运行过程中的变化。

   调试器提供有关变量值、分析器标签、goroutine的当前状态等信息。

   虽然这些工具允许您在特定的时刻检查程序状态，但[逐步执行](https://www.jetbrains.com/help/go/stepping-through-the-program.html)功能使您能够控制程序的逐步执行。通过结合使用这些工具，您可以推断出错误的来源并测试程序的鲁棒性。
