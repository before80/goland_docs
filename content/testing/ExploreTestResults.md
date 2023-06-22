+++
title = "浏览测试结果"
weight = 40
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Explore test results﻿ - 浏览测试结果

https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html

Last modified: 24 April 2023

上次修改日期：2023年4月24日

​	打开运行工具窗口：View | Tool Windows | Run (Alt+4)

​	在GoLand完成运行您的测试后，它会在运行工具窗口的Test Runner选项卡中显示结果。

​	右侧的控制台显示当前测试会话的输出。它允许您查看有关测试执行的详细信息以及测试失败或被忽略的原因。

​	位于测试结果列表上方的测试运行器工具栏允许您[显示和隐藏](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#sort-test-results)成功和被忽略的测试，[显示每个测试运行所需的时间](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#stats)，[导出](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#export)，[导入](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#import-test-results)和[排序](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#sort-test-results)测试结果。

![Test results shown on the Test Runner tab of the Run tool window](ExploreTestResults_img/go_tests_finished.png)



​	在Test Runner选项卡上的每个测试旁边，IDE会显示标记测试状态的图标：



| 图标                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![Test error](ExploreTestResults_img/app.runConfigurations.toolbarError.svg) | Test error. This status is assigned to tests that caused an exception from the tested source code.测试错误。此状态适用于由测试源代码引发异常的测试。 |
| ![Test failed](ExploreTestResults_img/app.runConfigurations.toolbarFailed.svg) | 测试失败。如果至少有一个子测试失败，则将其所有父级测试标记为失败。 |
| ![Test ignored](ExploreTestResults_img/app.runConfigurations.showIgnored.svg) | 测试被忽略。                                                 |
| ![Test in progress](ExploreTestResults_img/app.process.step_1.svg) | Test in progress.测试进行中。                                |
| ![Test passed](ExploreTestResults_img/app.runConfigurations.toolbarPassed.svg) | 测试通过。                                                   |
| ![Terminated](ExploreTestResults_img/app.runConfigurations.toolbarTerminated.svg) | 测试已终止。此状态适用于被停止的测试。如果至少有一个测试收到此状态，则所有未完成的测试及其父级测试都将被标记为已终止。 |

### 排序和筛选测试结果

​	如果您只想关注失败的测试或重新组织测试结果，可以使用Test Runner工具栏上的以下选项： 

- 禁用![the Show Passed button](ExploreTestResults_img/app.runConfigurations.showPassed.svg) Show Passed选项以隐藏成功的测试。
- 禁用![the Show Ignored button](ExploreTestResults_img/app.runConfigurations.showIgnored.svg)Show Ignored选项以隐藏被忽略的测试。
- 单击![the Sort Alphabetically button](ExploreTestResults_img/app.objectBrowser.sorted.svg)按字母顺序排序测试结果。
- 单击![the Sort by Duration button](ExploreTestResults_img/app.runConfigurations.sortbyDuration.svg)按持续时间排序测试结果。

### 跟踪测试执行

​	在GoLand中，您可以监视当前测试的执行。如果测试套件包含多个测试，测试列表会展开，逐个显示测试方法的运行情况。

- 要监视测试执行，请单击Test Runner工具栏上的![ the Settings button](ExploreTestResults_img/app.general.gearPlain.svg)，并启用Track Running Test选项。

  ![Track test execution](ExploreTestResults_img/go_track_test_execution.png)

### 管理测试结果﻿

- 单击Test Runner工具栏上的![the Settings button](ExploreTestResults_img/app.general.gearPlain.svg)，并启用以下选项：
  - [Track Running Test](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#track-test-execution)：监视当前测试的执行。
  - [Show Inline Statistics](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#stats)：查看测试的执行时间。
  - Suites Always on Top：在应用排序时，始终将测试节点置于列表顶部。
  - Scroll to Stack Trace：如果测试在失败之前生成了大量输出（例如日志记录），选择Test Runner选项卡上的测试后，此选项会自动将输出控制台滚动到断言失败处。
  - Navigate with Single Click：自动在编辑器中打开所选测试的代码。
  - Set Auto Test Delay：将鼠标指向此节点以显示可用的文件保存和重新运行测试之间的延迟列表。选定的值会显示选中标记。
  - Select First Failed Test When Finished：在完成测试会话时自动选择列表中的第一个失败的测试。

### 查看统计信息

- 要查看测试的执行时间，请单击Test Runner工具栏上的![the Settings button](ExploreTestResults_img/app.general.gearPlain.svg)，并启用Show Inline Statistics选项。

  ![Test runner in the Run tool window](ExploreTestResults_img/go_test_runner.png)

### 跳转到测试声明﻿

- 从Test Runner选项卡上的列表中选择所需的测试，然后按F4键。


> ​	要加快导航速度，请使用[单击导航(Navigate with Single Click)](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#manage-test-results)选项。

### 查看以前测试的结果

​	GoLand会自动保存最近10次测试的结果。要打开最近测试列表：

- 单击Test Runner工具栏上的![Test History](ExploreTestResults_img/app.vcs.history.svg)图标，然后从列表中选择所需的测试。

  对于每个测试，列表显示了[运行配置](https://www.jetbrains.com/help/go/run-debug-configuration.html)名称和时间戳：

  ![Viewing results of previous tests](ExploreTestResults_img/go_view_test_results.png)

  如果您希望保留测试结果或与团队共享，还可以将测试结果[导出](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#export)到文件中。

## 导出和导入测试结果

### 将测试结果导出到文件中

1. 在Test Runner工具栏上，单击![Export Test Results](ExploreTestResults_img/app.toolbarDecorator.export.svg)。

2. 选择要保存文件的格式：

   - HTML：从预定义模板生成HTML文件。
   - XML：如果您希望稍后将此文件导入GoLand，则使用此格式。
   - 使用您自定义的[XSL](https://www.w3schools.com/xml/xsl_intro.asp)模板，从原始XML输出生成HTML文件。单击此选项旁边的![Browse button](ExploreTestResults_img/app.general.openDisk.svg)，然后选择`*.xsl`代码样式定义文件。

4. 指定输出文件的名称和位置。

4. 如果要在导出后在浏览器中打开文件，请选中Open exported file in browser复选框。单击确定。

   ![Export test results to a file](ExploreTestResults_img/go_export_test_results.png)


### 导入测试结果

1. 要加载以前导出的文件，请在Test Runner工具栏上单击![Import Tests from File](ExploreTestResults_img/app.toolbarDecorator.import.svg)。

   如果您尚未运行任何测试，并且没有可用的带有Test Runner工具栏的工具窗口，请按Ctrl+Shift+A，然后输入`Import Tests from File`。

2. 在打开的对话框中，选择包含测试结果的**.xml**文件，然后单击打开。
