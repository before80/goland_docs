+++
title = "使用分析器标签"
weight = 80
date = 2023-06-20T10:40:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Using profiler labels﻿ 使用分析器标签

https://www.jetbrains.com/help/go/using-profiler-labels.html

Last modified: 17 March 2022

最近修改：2022年3月17日

​	Goroutines是与其他函数或方法同时运行的函数或方法。要创建一个Goroutine，使用`go`关键字后跟一个函数调用（例如，`go func(p string, rid int64)`）。但是使用大量的Goroutine会使程序更难调试。为了区分Goroutine，您可以使用自定义数据对Goroutine进行标记。

​	自Go 1.9以来，您可以记录额外的信息，以提供有关执行路径的更多上下文信息。您可以将任何一组标签记录为配置文件数据的一部分，并稍后使用这些标签来检查配置文件输出。

​	例如，您有一个队列处理程序，用于处理在某个地方创建的事件。处理程序可以设置标签以标识这些事件的创建位置。

​	在调试和核心转储分析过程中，上下文信息可能会很有帮助。例如，您可以使用此信息更轻松地找到特定的Goroutine。

## 添加标签

​	`runtime/pprof`包提供了几个新函数，您可以使用这些函数来添加标签。最常用的是`Do`函数。`Do`函数接受上下文，向该上下文添加标签，并将新的上下文传递给f函数。

​	`Do`函数仅为当前Goroutine编写标签。如果您在f函数中创建新的Goroutine，可以将上下文作为参数传递。

```go
func main() {
    ctx := context.Background()
    for i := 0; i < 10; i++ {
        labels := pprof.Labels("path", "/api/profile", "userId", strconv.Itoa(rand.Intn(100)))
        go pprof.Do(ctx, labels, f)
    }
    time.Sleep(time.Second)
}
```



## 在GoLand中查看标签

​	为了说明的目的，从GitHub上复制以下[代码示例](https://github.com/apronichev/documentation-code-examples/blob/master/debuggerProfilerLabels/main.go)。

​	在调用`println("ok")`的地方设置断点。要设置断点，请在第21行的沟槽上单击。运行`main`函数的调试。要开始调试，请在`main`函数附近的沟槽上单击运行图标（![the Run icon](UsingProfilerLabels_img/app.actions.execute.svg))，然后选择Debug <run_debug_configuration_name>。从Goroutines列表中，观察可用的Goroutine。

![List of goroutines without labels](UsingProfilerLabels_img/go_list_of_goroutines_without_labels.png)

​	按下Ctrl+F2停止调试。删除`f(ctx)`调用并取消注释`Do`函数。通过按N/A重新运行调试过程。探索Goroutine列表。Goroutine名称包括以下信息：`/api/profile, userId: <some number>`。您可以使用此信息在调试或核心转储分析

![List of goroutines with labels](UsingProfilerLabels_img/go_list_of_goroutines_with_labels.png)

## 有用的链接 

- [在调试过程中如何查找Goroutine](https://blog.jetbrains.com/go/2020/03/03/how-to-find-goroutines-during-debugging/)：阅读有关在GoLand中使用分析器标签的教程。
- [Go中的分析器标签](https://rakyll.org/profiler-labels/)：阅读有关分析器标签的更多信息。