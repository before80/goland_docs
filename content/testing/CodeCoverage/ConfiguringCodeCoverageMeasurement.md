+++
title = "Configuring code coverage measurement"
weight = 10
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Configuring code coverage measurement﻿ - 配置代码覆盖率测量

https://www.jetbrains.com/help/go/configuring-code-coverage-measurement.html

Last modified: 03 May 2023

最后修改日期：2023年5月3日

### 配置代码覆盖率行为

1. 按下Ctrl+Alt+S打开IDE设置，选择Build, Execution, Deployment | Coverage。
2. 定义如何处理收集的覆盖率数据：
   - 在将覆盖率应用于编辑器之前显示选项：每次使用代码覆盖率运行新的运行配置时都显示代码覆盖率对话框。
   - 不应用收集的覆盖率：丢弃新的代码覆盖率结果。
   - 使用新的套件替换活动套件：每次使用代码覆盖率运行新的运行配置时，丢弃活动套件并使用新的套件。
   - 将新的覆盖率套件添加到活动套件中：每次使用代码覆盖率运行新的运行配置时，将新的代码覆盖率套件添加到活动套件中。
5. 选中Activate Coverage View复选框，以自动打开[覆盖率](https://www.jetbrains.com/help/go/coverage-tool-window.html)工具窗口。

### 更改覆盖率高亮的颜色

1. 按下Ctrl+Alt+S打开IDE设置，选择Editor | Color Scheme | General。
3. 或者，单击在边距中点击覆盖率指示线时弹出的窗口中的![the Edit Coverage Colors button](ConfiguringCodeCoverageMeasurement_img/app.general.settings.svg)。
4. 在组件列表中，展开Line Coverage节点，然后选择一种覆盖率类型，例如Full（全部覆盖）、Partial（部分覆盖）或Uncovered（未覆盖）。
6. 单击前景色字段以打开“选择颜色”对话框。
8. 选择一种颜色，应用更改，并关闭对话框。

![Configure code coverage colors](ConfiguringCodeCoverageMeasurement_img/coverageColors.png)