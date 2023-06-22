+++
title = "管理代码覆盖套件"
weight = 30
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Managing code coverage suites - 管理代码覆盖套件﻿

https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html

Last modified: 21 April 2023

最后修改日期：2023年4月21日

​	GoLand提供了一个工具，用于选择要显示、隐藏、添加和删除覆盖套件。

### 选择覆盖套件﻿

​	只有在至少运行一个带有[覆盖率](https://www.jetbrains.com/help/go/running-test-with-coverage.html)的测试后，覆盖套件列表才会可用。 

1. 从主菜单中选择Run | Show Coverage Data（Ctrl+Alt+F6）。
3. 单击Show selected。对话框关闭。在编辑器中，GoLand会为选定的测试套件打开测试覆盖结果。
5. 要隐藏覆盖结果，请选择所需类旁边的复选框，然后单击No Coverage。

![View code coverage results](ManagingCodeCoverageSuites_img/go_view_coverage_results.png)

### 上传或删除覆盖套件

​	考虑以下情况：从构建服务器获取了包含代码覆盖信息的文件。您可以从磁盘加载此文件并在GoLand中查看它。此外，您还可以打开IDE之前生成的覆盖率数据。

1. 从主菜单中选择Run | Show Coverage Data（Ctrl+Alt+F6）。

3. 单击![the Add button](ManagingCodeCoverageSuites_img/app.general.add.svg)，然后在打开的对话框中选择所需的**.ic**文件。

   由GoLand生成的覆盖率数据文件默认保存在IDE的[系统目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#system-directory)的**coverage**文件夹中。

4. 要从列表和存储中删除套件，请在列表中选择它，然后单击![the Delete button](ManagingCodeCoverageSuites_img/app.general.remove.svg)。