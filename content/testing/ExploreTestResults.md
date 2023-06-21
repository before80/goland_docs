+++
title = "浏览测试结果"
weight = 40
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Explore test results﻿ 浏览测试结果

https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html

Last modified: 24 April 2023

上次修改日期：2023年4月24日

Open the Run tool window: View | Tool Windows | Run (Alt+4)

​	打开运行工具窗口：查看 | 工具窗口 | 运行 (Alt+4)

After GoLand finishes running your tests, it shows the results in the Run tool window on the Test Runner tab.

​	在GoLand完成运行您的测试后，它会在运行工具窗口的“测试运行器”选项卡中显示结果。

The console on the right shows the output of the current test session. It allows you to see the detailed information on the test execution and why your tests failed or were ignored.

​	右侧的控制台显示当前测试会话的输出。它允许您查看有关测试执行的详细信息以及测试失败或被忽略的原因。

The Test Runner toolbar located above the list of test results allows you to [show and hide](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#sort-test-results) successful and ignored tests, [display how much time](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#stats) it took to run each test, [export](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#export), [import](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#import-test-results), and [sort](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#sort-test-results) test results.

​	位于测试结果列表上方的测试运行器工具栏允许您[显示和隐藏](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#sort-test-results)成功和被忽略的测试，[显示每个测试运行所需的时间](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#stats)，[导出](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#export)，[导入](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#import-test-results)和[排序](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#sort-test-results)测试结果。

![Test results shown on the Test Runner tab of the Run tool window](ExploreTestResults_img/go_tests_finished.png)



Next to each test on the Test Runner tab, the IDE displays an icon that marks the test status:

​	在“测试运行器”选项卡上的每个测试旁边，IDE会显示标记测试状态的图标：



| 图标                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![Test error](ExploreTestResults_img/app.runConfigurations.toolbarError.svg) | Test error. This status is assigned to tests that caused an exception from the tested source code.测试错误。此状态适用于由测试源代码引发异常的测试。 |
| ![Test failed](ExploreTestResults_img/app.runConfigurations.toolbarFailed.svg) | Test failed. If at least one child test fails, all its parent tests are marked as failed.测试失败。如果至少有一个子测试失败，则将其所有父级测试标记为失败。 |
| ![Test ignored](ExploreTestResults_img/app.runConfigurations.showIgnored.svg) | Test ignored.测试被忽略。                                    |
| ![Test in progress](ExploreTestResults_img/app.process.step_1.svg) | Test in progress.测试进行中。                                |
| ![Test passed](ExploreTestResults_img/app.runConfigurations.toolbarPassed.svg) | Test passed successfully.测试通过。                          |
| ![Terminated](ExploreTestResults_img/app.runConfigurations.toolbarTerminated.svg) | Test terminated. This status is assigned to tests that were stopped.If at least one test receives this status, then all unfinished tests and their parent tests are marked as terminated.测试已终止。此状态适用于被停止的测试。如果至少有一个测试收到此状态，则所有未完成的测试及其父级测试都将被标记为已终止。 |

### 排序和筛选测试结果﻿ Sort and filter test results﻿

Use the following options on the Test Runner toolbar if you want to focus only on the failed tests or if you want to reorganize test results:

​	如果您只想关注失败的测试或重新组织测试结果，可以使用“测试运行器”工具栏上的以下选项： 

- Disable the 禁用![the Show Passed button](ExploreTestResults_img/app.runConfigurations.showPassed.svg) Show Passed option to hide successful tests.“显示已通过”选项以隐藏成功的测试。
- Disable the 禁用![the Show Ignored button](ExploreTestResults_img/app.runConfigurations.showIgnored.svg) Show Ignored option to hide ignored tests.“显示已忽略”选项以隐藏被忽略的测试。
- 单击![the Sort Alphabetically button](ExploreTestResults_img/app.objectBrowser.sorted.svg) to sort test results alphabetically.按字母顺序排序测试结果。
- 单击![the Sort by Duration button](ExploreTestResults_img/app.runConfigurations.sortbyDuration.svg) to sort test results by duration.按持续时间排序测试结果。

### 跟踪测试执行﻿ Track test execution﻿

In GoLand, you can monitor execution of the current test. If a test suite contains multiple tests, the list of tests expands to show test methods as they run one by one.

​	在GoLand中，您可以监视当前测试的执行。如果测试套件包含多个测试，测试列表会展开，逐个显示测试方法的运行情况。

- To monitor test execution, click 要监视测试执行，请单击“测试运行器”工具栏上的![ the Settings button](ExploreTestResults_img/app.general.gearPlain.svg) on the Test Runner toolbar and enable the Track Running Test option.，并启用“Track Running Test”选项。

  ![Track test execution](ExploreTestResults_img/go_track_test_execution.png)

### 管理测试结果﻿  Manage test results﻿

- Click 单击“测试运行器”工具栏上的![the Settings button](ExploreTestResults_img/app.general.gearPlain.svg) on the Test Runner toolbar and enable the following options:，并启用以下选项：
  - [Track Running Test](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#track-test-execution): monitor execution of the current test.
  - [Show Inline Statistics](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#stats): view the execution time for tests.
  - Suites Always on Top: always place test nodes on top of the list when you apply sorting.
  - Scroll to Stack Trace: if a test produced a lot of output (for example, logging) before failing, this option automatically scrolls the output console to the assertion failure once you select the test on the Test Runner tab.
  - Navigate with Single Click: open the code for the selected test automatically in the editor.
  - Set Auto Test Delay: point to this node to reveal the list of available delays between file saving and rerunning tests. The selected value gets the check mark.
  - Select First Failed Test When Finished: automatically select the first failed test in the list upon completing the test session.
  - [Track Running Test](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#track-test-execution)：监视当前测试的执行。
  - [Show Inline Statistics](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#stats)：查看测试的执行时间。
  - Suites Always on Top：在应用排序时，始终将测试节点置于列表顶部。
  - Scroll to Stack Trace：如果测试在失败之前生成了大量输出（例如日志记录），选择“测试运行器”选项卡上的测试后，此选项会自动将输出控制台滚动到断言失败处。
  - Navigate with Single Click：自动在编辑器中打开所选测试的代码。
  - Set Auto Test Delay：将鼠标指向此节点以显示可用的文件保存和重新运行测试之间的延迟列表。选定的值会显示选中标记。
  - Select First Failed Test When Finished：在完成测试会话时自动选择列表中的第一个失败的测试。

### 查看统计信息﻿ View statistics﻿

- To view the execution time for tests, click 要查看测试的执行时间，请单击“测试运行器”工具栏上的![the Settings button](ExploreTestResults_img/app.general.gearPlain.svg) on the Test Runner toolbar and enable the Show Inline Statistics option.，并启用“Show Inline Statistics”选项。

  ![Test runner in the Run tool window](ExploreTestResults_img/go_test_runner.png)

### 跳转到测试声明﻿  Jump to test declaration﻿

- Select the necessary test from the list on the Test Runner tab and press F4.
- 从“测试运行器”选项卡上的列表中选择所需的测试，然后按F4键。


> To make navigation even faster, use the [Navigate with Single Click](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#manage-test-results) option.
>
> ​	要加快导航速度，请使用[单击导航](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#manage-test-results)选项。

### 查看以前测试的结果﻿ View results of previous tests﻿

GoLand automatically saves results of the last 10 tests. To open the list of recent tests:

​	GoLand会自动保存最近10次测试的结果。要打开最近测试列表：

- Click the 单击“测试运行器”工具栏上的![Test History](ExploreTestResults_img/app.vcs.history.svg) icon on the Test Runner toolbar and select the necessary test from the list.图标，然后从列表中选择所需的测试。

  For each test, the list displays the [run configuration](https://www.jetbrains.com/help/go/run-debug-configuration.html) name and a time stamp:

  对于每个测试，列表显示了[运行配置](https://www.jetbrains.com/help/go/run-debug-configuration.html)名称和时间戳：

  ![Viewing results of previous tests](ExploreTestResults_img/go_view_test_results.png)
  
  You can also [export](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#export) test results to a file if you want to keep them or share with your team.
  
  如果您希望保留测试结果或与团队共享，还可以将测试结果[导出](https://www.jetbrains.com/help/go/viewing-and-exploring-test-results.html#export)到文件中。

## 导出和导入测试结果﻿ Export and import test results﻿

### 将测试结果导出到文件中﻿ Export test results to a file﻿

1. Click 在“测试运行器”工具栏上，单击![Export Test Results](ExploreTestResults_img/app.toolbarDecorator.export.svg) on the Test Runner toolbar.

2. Select the format in which you want to save the file:

3. 选择要保存文件的格式：

   - HTML: generate an HTML file from a pre-defined template.
   - HTML：从预定义模板生成HTML文件。
   - XML: use this format if you want to import this file later to GoLand.
   - XML：如果您希望稍后将此文件导入GoLand，则使用此格式。
   - Custom, apply XSL template: use your custom [XSL](https://www.w3schools.com/xml/xsl_intro.asp) template to generate an HTML file from the raw XML output. Click Custom, apply XSL template：使用您自定义的[XSL](https://www.w3schools.com/xml/xsl_intro.asp)模板，从原始XML输出生成HTML文件。单击此选项旁边的![Browse button](ExploreTestResults_img/app.general.openDisk.svg) next to this option and select the `*.xsl` code style definition file.，然后选择`*.xsl`代码样式定义文件。
   - 

4. Specify the name of the output file and its location.

5. 指定输出文件的名称和位置。

6. If you want to open the file in your browser after you export it, select the Open exported file in browser checkbox. Click OK.

7. 如果要在导出后在浏览器中打开文件，请选中“在浏览器中打开导出的文件”复选框。单击确定。

   ![Export test results to a file](ExploreTestResults_img/go_export_test_results.png)

### 导入测试结果﻿ Import test results﻿

1. To load a previously exported file, click 要加载以前导出的文件，请在“测试运行器”工具栏上单击![Import Tests from File](ExploreTestResults_img/app.toolbarDecorator.import.svg) on the Test Runner toolbar.

   If you haven't run any tests yet, and the tool window with the Test Runner toolbar is not available, press Ctrl+Shift+A and type `Import Tests from File`.

   如果您尚未运行任何测试，并且没有可用的带有“测试运行器”工具栏的工具窗口，请按Ctrl+Shift+A，然后输入“Import Tests from File”。

2. In the dialog that opens, select the **.xml** file with test results and click Open.

3. 在打开的对话框中，选择包含测试结果的**.xml**文件，然后单击打开。
