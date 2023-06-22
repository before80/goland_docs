+++
title = "使用覆盖率运行"
weight = 20
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Running with coverage﻿ 使用覆盖率运行

https://www.jetbrains.com/help/go/running-test-with-coverage.html

Last modified: 03 March 2023

最后修改日期：2023年3月3日

​	GoLand提供了一个专门的操作，允许您使用代码覆盖率测量来运行测试。代码覆盖率数据将根据设置对话框（Ctrl+Alt+S）中[覆盖率](https://www.jetbrains.com/help/go/coverage-settings.html)页面上选择的选项进行处理。

### 运行带有代码覆盖率的测试

1. 执行以下操作之一：

   - 在编辑器中打开所需的文件，然后从上下文菜单中选择Run <name> with Coverage。在运行带有覆盖率的测试时，请注意可以根据插入符位置运行整个测试类或每个单独的测试方法。
   - 在“项目”工具窗口中打开所需的文件，然后从上下文菜单中选择Run <name> with Coverage。您还可以选择包含测试文件的目录，并选择相应的命令从上下文菜单中运行多个带有覆盖率的测试。
   - 选择所需的运行/调试配置，然后从主菜单中选择Run | Run <run/debug configuration name> with coverage。
   - 在主工具栏中，单击Run <run/debug configuration name> with Coverage按钮![Run <run/debug configuration name> with coverage](RunningWithCoverage_img/app.general.runWithCoverage.svg)。这将启动所选的运行/调试配置。

2. 如果在设置对话框（Ctrl+Alt+S）的[覆盖率](https://www.jetbrains.com/help/go/coverage-settings.html)页面上选择了“在将覆盖应用于编辑器之前显示选项”复选框，将出现一个对话框，您可以在其中选择是否要替换活动覆盖套件、将收集的数据添加到活动覆盖套件中，或者不应用覆盖数据。您还可以选择以后跳过此对话框。

   如果选择了其他选项，则将静默执行相应的操作。

5. 在[覆盖工具窗口](https://www.jetbrains.com/help/go/coverage-tool-window.html)中[查看收集的覆盖率数据](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html)。


![Run a test with code coverage](RunningWithCoverage_img/go_running_with_coverage.png)