+++
title = "代码覆盖率"
weight = 50
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Code coverage﻿ - 代码覆盖率

https://www.jetbrains.com/help/go/code-coverage.html

Last modified: 21 April 2023

最后修改日期：2023年4月21日

​	代码覆盖率的结果会显示在工具窗口和编辑器中。工具窗口显示以下信息： 

- 对于目录：已覆盖文件和语句的百分比。
- 对于文件：已覆盖语句的百分比。

​	当在编辑器中打开文件时，每一行都会根据其代码覆盖状态进行高亮显示： 

- 在模拟期间执行的行标记为绿色。
- 在模拟期间未执行的行标记为红色。

​	代码覆盖率测量结果包括一个[覆盖率套件](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html)。您可以将新模拟的结果与任何现有套件合并。在这种情况下，如果一行至少被一个模拟所覆盖，则认为该行已覆盖。

​	每次执行带有代码覆盖率测量的测试或应用程序时，都会生成一个覆盖率套件。可以拥有无限数量的覆盖率套件。

## 运行并生成代码覆盖率报告

### 在项目中使用代码覆盖率的一般步骤

1. 指定如何[处理代码覆盖率结果](https://www.jetbrains.com/help/go/configuring-code-coverage-measurement.html#cov_suites)。
3. 如果要为测试测量代码覆盖率，请为目标代码[创建一个运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html#run-debug-configuration-templates-for-tests)。
5. 在所需的运行/调试配置中[配置代码覆盖率测量](https://www.jetbrains.com/help/go/configuring-code-coverage-measurement.html)。
7. [使用代码覆盖率运行](https://www.jetbrains.com/help/go/running-test-with-coverage.html)，使用主菜单 Run | Run with Coverage 中的专用命令，或单击“Run with Coverage”按钮 ![the Run with Coverage button](index_img/app.general.runWithCoverage.svg)。
5. 执行代码覆盖率运行后，您可以执行以下操作：
   - 使用[各种覆盖率套件](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html)。
   - [查看代码覆盖率数据](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html)。