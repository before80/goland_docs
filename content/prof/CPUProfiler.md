+++
title = "CPU 分析器"
weight = 10
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# CPU profiler - CPU 分析器﻿

https://www.jetbrains.com/help/go/cpu-profiler.html

Last modified: 01 March 2023

最近修改日期：2023年3月1日

You can run the CPU profiler only for Go tests and benchmarks

​	您只能针对 Go 测试和基准测试运行 CPU 分析器。

CPU Profiler shows what functions consume what percent of CPU time This information can provide you a better understanding of how your application is executed, and how exactly resources are allocated.

​	CPU 分析器显示了哪些函数占用了 CPU 时间的百分比。这些信息可以帮助您更好地理解应用程序的执行方式以及资源的分配情况。

Once the analysis is finished, the profiler visualizes the output data in the re.ports.

​	分析完成后，分析器将以报告的形式可视化输出数据。

### 分析器配置 Profiler configuration﻿

GoLand features two pre-defined Async Profiler configurations: the CPU profiler and the memory allocation profiler that you can find in Settings | Build, Execution, Deployment | Java Profiler.

​	GoLand 提供了两个预定义的 Async Profiler 配置：CPU 分析器和内存分配分析器，您可以在“设置” | “构建、执行、部署” | “Java 分析器”中找到。

These configurations are adjusted to provide the most accurate results, that is why they don't require any modifications. However, if you still need to change the settings, refer to [Async Profiler on GitHub](https://github.com/jvm-profiling-tools/async-profiler) for more information.

​	这些配置已经经过调整以提供最准确的结果，因此它们不需要进行任何修改。然而，如果您仍然需要更改设置，请参考 [GitHub 上的 Async Profiler](https://github.com/jvm-profiling-tools/async-profiler) 获取更多信息。

### 选择分析器配置 Select the profiler configuration﻿

1. In the Settings dialog (Ctrl+Alt+S), select Build, Execution, Deployment | Go Profiler.
2. 在“设置”对话框（Ctrl+Alt+S）中，选择“构建、执行、部署” | “Go 分析器”。
3. Select one of the pre-defined CPU or memory profiling configuration or create a new one by clicking 选择一个预定义的 CPU 或内存分析配置，或者通过点击 ![the Add button](CPUProfiler_img/app.general.add.svg). 创建一个新配置。
4. Apply the changes and close the dialog.
5. 应用更改并关闭对话框。

## 运行分析 Run profiling﻿

### 运行 CPU 分析  Run CPU profiling﻿

1. Open the **_test.go** file.
2. 打开 **_test.go** 文件。
3. Near the function or method that you want to profile, click the Run Application icon 在您想要进行分析的函数或方法附近，单击代码编辑区域的运行应用程序图标 ![the Run Application icon](CPUProfiler_img/app.runConfigurations.testState.run_dark.svg) in the gutter area and select Run <configuration_name> with 'CPU Profiler'.，然后选择使用 'CPU Profiler' 运行 <configuration_name>。

![https://resources.jetbrains.com/help/img/idea/2023.1/go_cpu_profiling.png](CPUProfiler_img/go_cpu_profiling.animated.gif)

## 阅读分析报告 Read the profiling report﻿

In the Profiler tool window, the collected data is presented on three tabs: Flame Graph, Call Tree, and Method List. The left-hand part lists application threads; by clicking on each thread you can go in more details.

​	在分析器工具窗口中，收集的数据在三个选项卡上显示：Flame Graph、Call Tree 和 Method List。左侧列出了应用程序的线程；通过单击每个线程，可以查看更详细的信息。

### 火焰图

The Flame Graph tab shows you function calls and the percentage of time for execution of each call. Each block represents a function in the stack (a stack frame). On the Y-axis, there is a stack depth going from bottom up. The X-axis shows the stack profile sorted from the most CPU-consuming functions to the least consuming ones.

​	火焰图选项卡显示了函数调用以及每个调用的执行时间百分比。每个方块代表堆栈中的一个函数（一个堆栈帧）。在 Y 轴上，从底部到顶部是堆栈深度。X 轴上的堆栈剖面按照最耗费 CPU 时间的函数到最少耗费的函数排序。

When you read the flame graph, focus on the widest blocks. These blocks are the functions that are presented in the profile most.

​	在阅读火焰图时，重点关注最宽的方块。这些方块代表在分析中出现最频繁的函数。

Hover the mouse over any block to view the details:

​	将鼠标悬停在任何方块上可以查看详细信息：

![block details in the flame chart](CPUProfiler_img/go_profiler_flamechart_hover.png)


> For more information about flame graphs, see [Flame Graphs](http://www.brendangregg.com/flamegraphs.html).
>
> ​	有关火焰图的更多信息，请参见 [Flame Graphs](http://www.brendangregg.com/flamegraphs.html)。

### 调用树 Call Tree﻿

The Call Tree tab represents information about a program’s call stacks that were sampled during profiling:

​	调用树选项卡显示了在分析期间采样的程序调用堆栈的信息： 

- The method name
- Percentage of total sample time (can be toggled to the parent call view)
- The total sample count
- The number of filtered calls
- 方法名称
- 总采样时间的百分比（可以切换到父调用视图）
- 总采样计数
- 过滤后的调用次数

The optional number right after the percentage presents a filtered sequence of calls. Click it to expand this sequence. The filtering rules can be configured in the settings.

​	百分比后面的可选数字表示经过过滤的调用序列。单击它可以展开此序列。过滤规则可以在设置中配置。

To configure and filter the Call Tree view, use the Presentation Settings button (要配置和过滤调用树视图，请使用演示设置按钮 (![the Presentation Settings button](CPUProfiler_img/app.actions.show.svg)).)。

![call tree tab in the profiler results](CPUProfiler_img/go_profiler_calltree.png)

### 方法列表

The Method List collects all methods in the profiled data and sorts them by cumulative sample time. Every item in this list has a Back Trace tree and a Merge Callees tree.

​	方法列表收集了分析数据中的所有方法，并按累计采样时间排序。列表中的每个项目都有一个回溯树和一个合并调用者树。

The Back Traces tab shows the hierarchy of callers. Use this view to trace which methods call the selected method. Merge Callees tries to summarize all methods that are called by the selected one.

​	回溯选项卡显示了调用者的层次结构。使用此视图跟踪调用了选定方法的方法。合并调用者树尝试总结由选定方法调用的所有方法。

![method list tab in the profiler results](CPUProfiler_img/go_profiler_methodlist.png)