+++
title = "断点"
weight = 10
date = 2023-06-20T10:40:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Breakpoints﻿ 断点

https://www.jetbrains.com/help/go/using-breakpoints.html

Last modified: 03 May 2023

最后修改日期：2023年5月3日

Breakpoints are special markers that suspend program execution at a specific point. This lets you examine the program state and behavior. Breakpoints can be simple (for example, suspending the program on reaching some line of code) or involve more complex logic (checking against [additional conditions](https://www.jetbrains.com/help/go/using-breakpoints.html#breakpoint_condition), writing [log messages](https://www.jetbrains.com/help/go/using-breakpoints.html#log), and so on).

​	断点是在特定点暂停程序执行的特殊标记。这使您可以检查程序的状态和行为。断点可以是简单的（例如，在达到某行代码时暂停程序），也可以涉及更复杂的逻辑（检查[附加条件](https://www.jetbrains.com/help/go/using-breakpoints.html#breakpoint_condition)，编写[日志消息](https://www.jetbrains.com/help/go/using-breakpoints.html#log)等）。

Once set, a breakpoint remains in your project until you remove it explicitly, except for [temporary breakpoints](https://www.jetbrains.com/help/go/using-breakpoints.html#remove_once_hit)).

​	一旦设置了断点，在您明确删除之前，它将一直存在于您的项目中，除非是[临时断点](https://www.jetbrains.com/help/go/using-breakpoints.html#remove_once_hit)。


> If a file with breakpoints was modified externally, for example, updated through a VCS or changed in an external editor, and the line numbers have changed, breakpoints will be moved accordingly. Note that GoLand must be running when such changes are made, otherwise they will pass unnoticed.
>
> ​	如果带有断点的文件在外部被修改，例如通过版本控制系统（VCS）进行更新或在外部编辑器中更改，并且行号已更改，则断点将相应移动。请注意，在进行此类更改时，GoLand 必须正在运行，否则将不会注意到这些更改。

## 断点的类型 Types of breakpoints﻿

The following types of breakpoints are available in GoLand:

​	在 GoLand 中提供了以下类型的断点： 

- Line breakpoints: suspend the program upon reaching the line of code where the breakpoint was set. This type of breakpoints can be set on any executable line of code.
- 行断点：在达到设置断点的代码行时暂停程序。可以在任何可执行的代码行上设置此类型的断点。
- Exception breakpoints: suspend the program when `panic()` is thrown.
- 异常断点：在 `panic()` 抛出时暂停程序。

## 设置断点 Set breakpoints﻿

### 设置行断点 Set line breakpoints﻿

- Click the gutter at the executable line of code where you want to set the breakpoint. Alternatively, place the caret at the line and press Ctrl+F8.

- 在您想设置断点的可执行代码行的装订线处单击。或者，将光标放在该行上，然后按 Ctrl+F8。

  ![Debug a line breakpoint](Breakpoints_img/go_debug_line_breakpoint.png)

### 设置异常断点 Set exception breakpoints﻿

1. Click View Breakpoints 在调试工具窗口的左侧部分单击“查看断点”按钮![View Breakpoints button](Breakpoints_img/app.debugger.viewBreakpoints.svg) in the left part of the Debug tool window or press Ctrl+Shift+F8.，或按 Ctrl+Shift+F8。

2. In the Breakpoints dialog, select Go error breakpoint or JavaScript Exception Breakpoint.

3. 在“断点”对话框中，选择“Go 错误断点”或“JavaScript 异常断点”。

   ![Create an exception breakpoint](Breakpoints_img/go_create_exception_breakpoint.png)

## 管理断点 Manage breakpoints﻿

### 删除断点  Remove breakpoints﻿

- For non-exception breakpoints: click the breakpoint in the gutter.
- 对于非异常断点：在装订线上单击断点。
- For all breakpoints: from the main menu, select Run | View Breakpoints Ctrl+Shift+F8, select the breakpoint, and click Remove Delete.
- 对于所有断点：从主菜单中选择“运行 | 查看断点”(Ctrl+Shift+F8)，选择断点，然后单击“删除”（删除键）。

To avoid accidentally removing a breakpoint and losing its parameters, you can choose to remove breakpoints by dragging them to the editor or clicking the middle mouse button. To do this, go to Settings | Build, Execution, Deployment | Debugger and select Drag to the editor or click with middle mouse button. Clicking a breakpoint will then [enable or disable](https://www.jetbrains.com/help/go/using-breakpoints.html#disable) it.

​	为了避免意外删除断点并丢失其参数，您可以选择通过将其拖到编辑器或单击鼠标中键来删除断点。要执行此操作，转到“设置 | 构建、执行、部署 | 调试器”并选择“拖到编辑器或单击鼠标中键”。然后，单击断点将会[启用或禁用](https://www.jetbrains.com/help/go/using-breakpoints.html#disable)它。

### 静音断点 Mute breakpoints﻿

If you don't need to stop at your breakpoints for some time, you can mute them. This allows you to resume normal program operation without leaving the debugger session. After that, you can unmute breakpoints and continue debugging.

​	如果您在一段时间内不需要在断点处停下来，您可以将其静音。这样可以在不离开调试器会话的情况下恢复正常的程序操作。之后，您可以取消静音断点并继续调试。 

- Click the Mute Breakpoints button 单击调试工具窗口工具栏中的“静音断点”按钮 ![Mute Breakpoints button](Breakpoints_img/app.debugger.muteBreakpoints.svg) in the toolbar of the Debug tool window.。

### 启用/禁用断点 Enable/disable breakpoints﻿

When you remove a breakpoint, its [internal configuration](https://www.jetbrains.com/help/go/using-breakpoints.html#breakpoint-properties) is lost. To temporarily turn an individual breakpoint off without losing its parameters, you can disable it:

​	当您删除断点时，会丢失其[内部配置](https://www.jetbrains.com/help/go/using-breakpoints.html#breakpoint-properties)。要在不丢失其参数的情况下暂时关闭单个断点，可以禁用它： 

- For non-exception breakpoints: right-click it and set the Enabled option as required. You can also toggle them with the middle mouse button if removing breakpoints is not [assigned](https://www.jetbrains.com/help/go/using-breakpoints.html#remove) to it.
- 对于非异常断点：右键单击断点，根据需要设置“启用”选项。如果鼠标中键未[分配](https://www.jetbrains.com/help/go/using-breakpoints.html#remove)删除断点，则还可以使用鼠标中键切换断点的启用状态。
- For all breakpoints: click View Breakpoints Ctrl+Shift+F8 and check/uncheck the breakpoint on the list.
- 对于所有断点：单击“查看断点”(Ctrl+Shift+F8)，在列表上选中或取消选中断点。

### 移动/复制断点  Move/copy breakpoints﻿

- To move a breakpoint, drag it to another line.
- To copy a breakpoint, hold Ctrl and drag a breakpoint to another line. This creates a breakpoint with the same parameters at the destination.
- 要移动断点，将其拖动到另一行。
- 要复制断点，按住 Ctrl 键并将断点拖动到另一行。这会在目标位置创建具有相同参数的断点。

## 配置断点属性 Configure breakpoints' properties﻿

Depending on the breakpoint type, you can configure additional properties which allow you to tailor its operation for specific needs. The most used options are available via [intentions](https://www.jetbrains.com/help/go/using-breakpoints.html#intentions).

​	根据断点类型，您可以配置其他属性，以满足特定需求。最常用的选项可通过[意图](https://www.jetbrains.com/help/go/using-breakpoints.html#intentions)访问。 

- To access breakpoint intentions, place the caret at the line with the breakpoint and press Alt+Enter. Use this option when you need to quickly configure basic breakpoint properties.
- To access the full list of properties, right-click the breakpoint and click More or press Ctrl+Shift+F8. Use this option for a bird's eye view of all breakpoints and full control over their configuration.
- 要访问断点意图，请将插入符号放置在带有断点的行上，然后按 Alt+Enter。当您需要快速配置基本断点属性时，可以使用此选项。
- 要访问完整的属性列表，请右键单击断点，然后单击“更多”或按 Ctrl+Shift+F8。使用此选项可以全面查看所有断点并完全控制其配置。

### 意图参考 Intentions reference﻿

| 意图     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 移除断点 | [移除](https://www.jetbrains.com/help/go/using-breakpoints.html#remove)所选行上的断点。 |
| 禁用断点 | [禁用](https://www.jetbrains.com/help/go/using-breakpoints.html#disable)所选行上的断点。 |
| 编辑断点 | 打开具有最常用的[属性](https://www.jetbrains.com/help/go/using-breakpoints.html#properties)的对话框。要查看更多属性，请单击“更多”或按 Ctrl+Shift+F8。 |



### 断点属性 Breakpoints' properties﻿

#### 启用 Enabled﻿



Clear the checkbox to temporarily disable a breakpoint without removing it from the project. Disabled breakpoints are skipped during [stepping](https://www.jetbrains.com/help/go/stepping-through-the-program.html).

​	清除复选框以临时禁用项目中的断点，而无需将其删除。禁用的断点在[步进](https://www.jetbrains.com/help/go/stepping-through-the-program.html)过程中会被跳过。

You can configure GoLand to enable/disable breakpoints on clicking rather than removing them altogether. To do this, go to Settings | Build, Execution, Deployment | Debugger and set the Remove breakpoint option to Drag to the editor or click with middle mouse button.

​	您可以配置 GoLand，使其在点击时启用/禁用断点，而不是完全删除它们。要这样做，转到“设置” | “构建、执行、部署” | “调试器”，并将“删除断点”选项设置为“拖到编辑器”或“使用鼠标中键单击”。

#### 暂停 Suspend﻿

Specifies whether to pause the program execution when the breakpoint is hit.

​	指定是否在命中断点时暂停程序执行。

Non-suspending breakpoints are useful when you need to log some expression without pausing the program (for example, when you need to know how many times a method was called) or if you need to create a master breakpoint that will enable [dependent breakpoints](https://www.jetbrains.com/help/go/using-breakpoints.html#disable-until-hit) when hit.

​	当您需要记录某些表达式而不暂停程序时（例如，当您需要知道某个方法被调用的次数）或者当您需要创建一个在命中时启用[依赖断点](https://www.jetbrains.com/help/go/using-breakpoints.html#disable-until-hit)的主断点时，非暂停断点非常有用。



#### 条件 Condition﻿



This option is used to specify a condition that is checked each time the breakpoint is hit. If the condition evaluates to `true`, the selected actions are performed. Otherwise, the breakpoint is ignored.

​	此选项用于指定每次命中断点时检查的条件。如果条件评估为 `true`，则执行所选操作。否则，忽略断点。


> The condition must be valid at the line where the breakpoint is set.
>
> ​	条件必须在设置断点的行上有效。

The result of the expression is taken from the return statement. When there is no return statement, the result is taken from the last line of code.

​	表达式的结果取自返回语句。当没有返回语句时，结果取自代码的最后一行。

When evaluating expressions, make sure you are aware of their possible side effects as they may potentially affect the behavior and/or the result of the program.

​	在评估表达式时，请确保您了解其可能的副作用，因为它们可能会影响程序的行为和/或结果。

#### 日志选项 Logging options﻿



When a breakpoint is hit, the following can be logged to the console:

​	当命中断点时，以下内容可以记录到控制台：

- "Breakpoint hit" message: a log message like `Breakpoint reached`

- “断点命中”消息：类似于 `Breakpoint reached` 的日志消息。

- Stack trace: the stack trace for the current frame. This is useful if you want to check what paths have led to this point without interrupting the program execution.

- 栈跟踪：当前帧的堆栈跟踪。如果您想要检查导致此点的路径而不中断程序执行，这将非常有用。

- Evaluate and log: the result of an arbitrary expression, for example, `"Initializing"` or `len(users)`.

- 评估和记录：任意表达式的结果，例如 `"Initializing"` 或 `len(users)`。

  ![The Evaluate and log setting](Breakpoints_img/go_breakpoints_evaluate_and_log.png)

  The result of the expression is taken from the return statement. When there is no return statement, the result is taken from the last line of code which doesn't even have to be an expression: a literal works too. This can be used to produce a custom message or to keep track of some values as the program executes.

  表达式的结果取自返回语句。当没有返回语句时，结果取自代码的最后一行，该行甚至不必是一个表达式：文字也可以。这可用于生成自定义消息或在程序执行时跟踪某些值。
  
  When evaluating expressions, make sure you are aware of their possible side effects as they may potentially affect the behavior and/or the result of the program.
  
  在评估表达式时，请确保您了解其可能的副作用，因为它们可能会影响程序的行为和/或结果。

#### 命中后移除 Remove once hit﻿



Specifies whether the breakpoint should be removed from the project after it has been hit once.

​	指定是否在命中断点后从项目中删除断点。

#### 命中特定断点前禁用 Disable until hitting the following breakpoint﻿



When a breakpoint is selected in the Disable until hitting the following breakpoint box, it acts as a trigger for the current breakpoint. This [disables](https://www.jetbrains.com/help/go/using-breakpoints.html#enabled) the current breakpoint until the specified breakpoint has been hit.

​	在“禁用直到命中以下断点”框中选择断点时，它将充当当前断点的触发器。这会在命中指定的断点之前[禁用](https://www.jetbrains.com/help/go/using-breakpoints.html#enabled)当前断点。

You can also choose whether to disable it again after this has happened or leave it enabled.

​	您还可以选择在此发生后再次禁用它，或者保持其启用状态。

This option is useful when you only need to suspend the program under certain conditions or after certain actions. In this case, the trigger breakpoint usually isn't required to stop the program execution and is made [non-suspending](https://www.jetbrains.com/help/go/using-breakpoints.html#suspend_policy).

​	此选项在仅需要在特定条件或操作后暂停程序时非常有用。在这种情况下，通常不需要触发断点来停止程序执行，并且将其设置为[非暂停](https://www.jetbrains.com/help/go/using-breakpoints.html#suspend_policy)。

## 断点状态 Breakpoint statuses﻿

Breakpoints can have the following statuses:

​	断点可以具有以下状态：

| 状态   | 描述                                                         |
| ------ | ------------------------------------------------------------ |
| 无效   | 如果在断点行上没有可执行代码，调试器会将其标记为无效。这是最常见的原因是断点所在行上没有可执行的代码。 |
| 静音   | 所有断点都处于临时非活动状态，因为它们已被[静音](https://www.jetbrains.com/help/go/using-breakpoints.html#mute)。 |
| 禁用   | 此断点处于临时非活动状态，因为它已被[禁用](https://www.jetbrains.com/help/go/using-breakpoints.html#disable)。 |
| 非暂停 | 为该断点设置了[暂停策略](https://www.jetbrains.com/help/go/using-breakpoints.html#suspend_policy)，因此在命中时不会暂停执行。 |



## 断点图标 Breakpoint icons﻿

Depending on their [type](https://www.jetbrains.com/help/go/using-breakpoints.html#breakpoint-types) and [status](https://www.jetbrains.com/help/go/using-breakpoints.html#breakpoint-statuses), breakpoints are marked with the following icons:

​	根据其[类型](https://www.jetbrains.com/help/go/using-breakpoints.html#breakpoint-types)和[状态](https://www.jetbrains.com/help/go/using-breakpoints.html#breakpoint-statuses)，断点的图标有以下标记：



|                              | 行                                                           | 异常                                                         |
| ---------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Regular 常规                 | ![line breakpoint](Breakpoints_img/app.debugger.db_set_breakpoint.svg) | ![exception breakpoint](Breakpoints_img/app.debugger.db_exception_breakpoint.svg) |
| Disabled 已禁用              | ![disabled line breakpoint](Breakpoints_img/app.debugger.db_disabled_breakpoint.svg) | ![disabled exception breakpoint](Breakpoints_img/app.debugger.db_disabled_exception_breakpoint.svg) |
| Muted  静音                  | ![muted line breakpoint](Breakpoints_img/app.debugger.db_muted_breakpoint.svg) |                                                              |
| Muted disabled  已静音已禁用 | ![muted disabled line breakpoint](Breakpoints_img/app.debugger.db_muted_disabled_breakpoint.svg) |                                                              |
| Non-suspending  非暂停       | ![non-suspending line breakpoint](Breakpoints_img/app.debugger.db_no_suspend_breakpoint.svg) |                                                              |
| Invalid  无效                | ![invalid breakpoint](Breakpoints_img/app.debugger.db_invalid_breakpoint.svg) |                                                              |

## 提高效率的提示 Productivity tips﻿

### 使用断点进行调试打印 Use breakpoints for debug printing

Use [non-suspending](https://www.jetbrains.com/help/go/using-breakpoints.html#suspend_policy) [logging](https://www.jetbrains.com/help/go/using-breakpoints.html#log) breakpoints (sometimes referred to as watchpoints in other debuggers) instead of inserting print statements in your code. This provides a more flexible and centralized way of handling debug log messages.

​	使用[非暂停](https://www.jetbrains.com/help/go/using-breakpoints.html#suspend_policy)的[日志记录](https://www.jetbrains.com/help/go/using-breakpoints.html#log)断点（在其他调试器中有时称为 watchpoints）代替在代码中插入打印语句。这提供了一种更灵活和集中处理调试日志消息的方式。

### 更快地设置日志记录断点 Set logging breakpoints more quickly

To set a [non-suspending](https://www.jetbrains.com/help/go/using-breakpoints.html#suspend_policy) [logging](https://www.jetbrains.com/help/go/using-breakpoints.html#log) breakpoint, hold Shift and click the gutter. This will not suspend the program execution and instead log a message like `Breakpoint reached`. If you want to log some expression that is in front of you in the editor, select it before holding Shift and clicking the gutter.

​	要设置[非暂停](https://www.jetbrains.com/help/go/using-breakpoints.html#suspend_policy)的[日志记录](https://www.jetbrains.com/help/go/using-breakpoints.html#log)断点，按住 Shift 键并单击行号栏（gutter）。这不会暂停程序执行，而是记录一条消息，如“达到断点”。如果您想记录编辑器中当前的某个表达式，请在按住 Shift 键并单击行号栏之前先选择该表达式。

### 添加断点描述 Add breakpoint descriptions

If you have many breakpoints in your project, you can add descriptions to breakpoints for ease of search. To do this, right-click a breakpoint in the Breakpoints dialog Ctrl+Shift+F8 and select Edit description from the menu. Now when you start typing the breakpoint name, it gets the focus.

​	如果您的项目中有很多断点，您可以为断点添加描述以便于搜索。要做到这一点，右键单击断点对话框中的断点（Ctrl+Shift+F8），然后从菜单中选择“编辑描述”。现在，当您开始输入断点名称时，它将获得焦点。

### 分组断点 Group breakpoints

You can organize breakpoints into groups, for example, if you need to mark out breakpoints for a specific problem. To do this, in the Breakpoints dialog Ctrl+Shift+F8, select a breakpoint you want to place in a group and select Move to group from the menu.

​	您可以将断点分组，例如，如果您需要为特定问题标记出断点。要做到这一点，在断点对话框（Ctrl+Shift+F8）中选择要放置在分组中的断点，然后从菜单中选择“移动到组”。
