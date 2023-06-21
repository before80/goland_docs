+++
title = "内存分析器"
weight = 20
date = 2023-06-21T13:50:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Memory profiler﻿ 内存分析器

https://www.jetbrains.com/help/go/memory-profiler.html

Last modified: 16 January 2023

最近修改日期：2023年1月16日

You can run the Memory profiler only for Go tests and benchmarks

​	您只能针对 Go 测试和基准测试运行内存分析器。

Memory profiler shows what functions allocate heap memory. This statistics can help you to find memory leaks and optimize the overall memory usage.

​	内存分析器显示哪些函数分配了堆内存。这些统计信息可以帮助您找到内存泄漏并优化整体内存使用情况。

## 运行内存分析  Run Memory profiling﻿

1. Open the **_test.go** file.
2. 打开 **_test.go** 文件。
3. Near the function or method that you want to profile, click the Run Application icon 在您想要进行分析的函数或方法附近，单击代码编辑区域的运行应用程序图标 ![the Run Application icon](MemoryProfiler_img/app.runConfigurations.testState.run_dark.svg) in the gutter area and select Run <configuration_name> with 'Memory Profiler'.，然后选择使用 'Memory Profiler' 运行 <configuration_name>。

![https://resources.jetbrains.com/help/img/idea/2023.1/go_memory_profiling.png](MemoryProfiler_img/go_memory_profiling.animated.gif)

## 解读结果 Interpreting the results﻿

### 火焰图 Flame Chart

The Flame Graph tab shows you function calls and the amount of memory that was allocated for each call. Each block represents a function in the stack. On the Y-axis, there is a stack depth going from bottom up. The X-axis shows the stack profile sorted from the most memory-consuming functions (space and number of objects) to the least consuming ones.

​	火焰图选项卡显示了函数调用以及每次调用分配的内存量。每个方块代表堆栈中的一个函数。在 Y 轴上，从底部到顶部是堆栈深度。X 轴上的堆栈剖面按照最耗费内存的函数（空间和对象数量）到最少耗费的函数排序。

When you read the flame chart, note that large objects affect memory consumption and garbage collection time, while a large number of small allocations affects execution speed. It might be useful to investigate both cases.

​	在阅读火焰图时，请注意大对象会影响内存消耗和垃圾回收时间，而大量小的分配会影响执行速度。研究这两种情况可能会有所帮助。

In the Flame Graph tab, you can hover the mouse over any block to view the details.

​	在火焰图选项卡上，您可以将鼠标悬停在任何方块上以查看详细信息。

![Memory profiling details](MemoryProfiler_img/go_memory_profiling_details.png)

, where其中： 

- 13,020,338: direct memory usage, in bytes.
- 100.00% of parent: percentage between different procedures that belong to a single parent call.
- 95.17% of all: percentage of memory usage for the procedure and all of its callees.
- 13,020,338：直接内存使用量（以字节为单位）。
- 100.00% of parent：属于单个父调用的不同过程之间的百分比。
- 95.17% of all：该过程及其所有被调用者的内存使用百分比。

### 调用树 Call Tree

The Call Tree tab shows the call tree with the percentage of each procedure in the total memory usage. It organizes the data to show you where the application uses most of the memory or more objects in the memory. To configure and filter the Call Tree view, use the Presentation Settings button 调用树选项卡显示了每个过程在总内存使用中所占的百分比的调用树。它按照数据组织方式展示应用程序在哪些地方使用了大部分内存或更多的内存对象。要配置和过滤调用树视图，请使用演示设置按钮 (![the Presentation Settings button](MemoryProfiler_img/app.actions.show.svg).)。

![Presentation settings for the call tree](MemoryProfiler_img/go_profiler_memory_calltree.png)

### 方法列表

The Method List tab shows the list of methods that are sorted by the number of allocated objects. The Back Traces tab shows where the selected method has been called. The Merged Callees tab shows call traces that started from the selected method.

​	方法列表选项卡显示按分配对象数量排序的方法列表。回溯选项卡显示了调用选定方法的层次结构。合并调用者选项卡显示了从选定方法开始的调用跟踪。
