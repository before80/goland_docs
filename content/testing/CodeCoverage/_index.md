+++
title = "代码覆盖率"
weight = 50
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Code coverage﻿ 代码覆盖率

https://www.jetbrains.com/help/go/code-coverage.html

Last modified: 21 April 2023

最后修改日期：2023年4月21日

Code coverage results are displayed in tool windows and in the editor. The tool windows show the following information:

​	代码覆盖率的结果会显示在工具窗口和编辑器中。工具窗口显示以下信息： 

- For a directory: the percentage of covered files and statements.
- For a file: the percentage of the covered statements.
- 对于目录：已覆盖文件和语句的百分比。
- 对于文件：已覆盖语句的百分比。

When a file is opened in the editor, each line is highlighted with regard to its code coverage status:

​	当在编辑器中打开文件时，每一行都会根据其代码覆盖状态进行高亮显示： 

- Lines executed during simulation are marked green.
- Lines not executed during simulation are marked red.
- 在模拟期间执行的行标记为绿色。
- 在模拟期间未执行的行标记为红色。

The coverage measurement results comprise a [coverage suite](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html). You can have the results of a new simulation merged with any existing suite. In this case, a line will be considered covered if it is covered by at least one of the simulations.

​	代码覆盖率测量结果包括一个[覆盖率套件](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html)。您可以将新模拟的结果与任何现有套件合并。在这种情况下，如果一行至少被一个模拟所覆盖，则认为该行已覆盖。

A coverage suite is generated every time a test or application with code coverage measurement is executed. It is possible to have an unlimited amount of coverage suites.

​	每次执行带有代码覆盖率测量的测试或应用程序时，都会生成一个覆盖率套件。可以拥有无限数量的覆盖率套件。

## 运行并生成代码覆盖率报告 Run with code coverage﻿

### 在项目中使用代码覆盖率的一般步骤   General steps for using code coverage in a project﻿

1. Specify how you want to [process the coverage results](https://www.jetbrains.com/help/go/configuring-code-coverage-measurement.html#cov_suites).
2. 指定如何[处理代码覆盖率结果](https://www.jetbrains.com/help/go/configuring-code-coverage-measurement.html#cov_suites)。
3. [Create a run/debug configuration](https://www.jetbrains.com/help/go/run-debug-configuration.html#run-debug-configuration-templates-for-tests) for the target code, if you are going to measure code coverage for testing.
4. 如果要为测试测量代码覆盖率，请为目标代码[创建一个运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html#run-debug-configuration-templates-for-tests)。
5. [Configure code coverage measurement](https://www.jetbrains.com/help/go/configuring-code-coverage-measurement.html) in the desired run/debug configuration.
6. 在所需的运行/调试配置中[配置代码覆盖率测量](https://www.jetbrains.com/help/go/configuring-code-coverage-measurement.html)。
7. [Run with coverage](https://www.jetbrains.com/help/go/running-test-with-coverage.html), using the dedicated command from the main menu Run | Run with Coverage, or click the Run with Coverage button [使用代码覆盖率运行](https://www.jetbrains.com/help/go/running-test-with-coverage.html)，使用主菜单 Run | Run with Coverage 中的专用命令，或单击“Run with Coverage”按钮 ![the Run with Coverage button](index_img/app.general.runWithCoverage.svg).
8. Once the run with coverage has been executed, you can perform the following actions:
9. 执行代码覆盖率运行后，您可以执行以下操作：
   - Use the [various coverage suites](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html).
   - [View code coverage data](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html).
   - 使用[各种覆盖率套件](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html)。
   - [查看代码覆盖率数据](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html)。