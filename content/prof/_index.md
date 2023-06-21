+++
title = "性能测试"
linkTitle = "性能测试"
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
[menu.main]
  weight = 13
+++
# Profiling for tests﻿ 测试的性能分析

https://www.jetbrains.com/help/go/profiling-tests-and-benchmarks.html

Last modified: 16 January 2023

最近修改日期：2023年1月16日

Profiling is an analysis of your program performance. During profiling, you see the CPU and memory usage, the frequency and duration of function and method calls. This information might be helpful if you want to optimize your program performance.

​	性能分析是对程序性能的分析。在性能分析过程中，您可以查看CPU和内存的使用情况，函数和方法调用的频率和持续时间。这些信息对于优化程序性能非常有帮助。

GoLand collects and visualizes CPU profiles, traces, and heap profiles for your Go tests and benchmarks. To collect all the necessary data, GoLand uses the pprof package. GoLand includes four profilers that you can run from the user interface: CPU, memory, blocking (contention), and mutex.

​	GoLand 可以收集和可视化 Go 测试和基准测试的 CPU 分析、跟踪和堆分析。为了收集所有必要的数据，GoLand 使用了 pprof 包。GoLand 包括四个性能分析器，您可以从用户界面中运行：CPU、内存、阻塞（争用）和互斥。

### 运行性能分析

- The procedure of running a profiler is common for all profilers.

- 所有性能分析器的运行过程是相同的。

  Near the function or method that you want to profile, click the Run Application icon 在您想要进行性能分析的函数或方法附近，单击代码编辑区域的运行应用程序图标 ![the Run Application icon](index_img/app.runConfigurations.testState.run_dark.svg) in the gutter area and select Run <configuration_name> with '<profiler_name> Profiler'.，然后选择使用 '<profiler_name> Profiler' 运行 <configuration_name>。

  ![Run profiling](index_img/go_profiling_tests_and_benchmarks.png)

### 导入性能分析结果

- You can run your profiler code manually, import the results, and display them in GoLand.

- 您可以手动运行性能分析器代码，导入结果并在 GoLand 中显示它们。

  To import profiling results, quickly press Shift two times, type Open Profiler Snapshot, and press Enter. Select the result from the list or select Open Profiler Snapshot to upload the result from your hard drive.

  轻松按两次 Shift 键，输入“Open Profiler Snapshot”，然后按 Enter 键来导入性能分析结果。从列表中选择结果，或选择“Open Profiler Snapshot”来上传来自硬盘的结果。
  
  ![https://resources.jetbrains.com/help/img/idea/2023.1/go_import_profiler_results.png](index_img/go_import_profiler_results.animated.gif)