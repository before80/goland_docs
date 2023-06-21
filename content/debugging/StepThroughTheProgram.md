+++
title = "逐步执行程序"
weight = 40
date = 2023-06-20T10:40:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Step through the program 逐步执行程序

https://www.jetbrains.com/help/go/stepping-through-the-program.html﻿

Last modified: 03 February 2023

最后修改日期：2023年2月3日

Stepping is the process of controlling step-by-step execution of the program.

逐步执行是控制程序逐步执行的过程。

GoLand provides a set of stepping actions, which are used depending on your strategy (for example, whether you need to go directly to the next line or enter the methods invoked on your way there).

​	GoLand提供了一组逐步执行操作，这些操作根据您的策略使用（例如，是否需要直接进入下一行或进入调用的方法）。

The stepping buttons are located on the Debug window toolbar.

​	逐步执行按钮位于调试窗口的工具栏上。

## 逐过当前行 Step over﻿

Steps over the current line of code and takes you to the next line even if the highlighted line has method calls in it. The implementation of the methods is skipped, and you move straight to the next line of the caller method.

​	跳过当前代码行并进入下一行，即使高亮显示的行中有方法调用。方法的实现将被跳过，您将直接进入调用者方法的下一行。

 

- Click the Step Over button 单击“逐过”按钮 ![Step Over button](StepThroughTheProgram_img/app.actions.traceOver.svg) or press F8. 或按下F8。

In the following example, line 29 is about to be executed. If you step over, the debugger will move straight to line 30 without jumping into the New() function.

​	在下面的示例中，即将执行第29行。如果您选择逐过，调试器将直接跳转到第30行，而不进入“New()”函数。

If there are breakpoints inside the skipped methods, the debugger will stop at them. To skip any breakpoints on the way, use [Force step over](https://www.jetbrains.com/help/go/stepping-through-the-program.html#force-step-over).

​	如果跳过的方法内部存在断点，调试器将在这些断点处停止。要跳过途中的任何断点，请使用[强制逐过](https://www.jetbrains.com/help/go/stepping-through-the-program.html#force-step-over)。

![https://resources.jetbrains.com/help/img/idea/2023.1/go_debug_examining_step_over_example_2.png](StepThroughTheProgram_img/go_debug_examining_step_over_example_2.animated.gif)

## 逐入方法 Step into﻿

Steps into the method to show what happens inside it. Use this option when you are not sure the method is returning a correct result.

​	进入方法以查看其内部发生的情况。当您不确定方法是否返回正确结果时，请使用此选项。 

- Click the Step Into button 单击“逐入”按钮 ![Step Into button](StepThroughTheProgram_img/app.actions.traceInto.svg) or press F7. 或按下F7。

In the following example, line 29 is about to be executed. If you step into, the debugger will jump into the implementation of the `New` function allowing you to examine in detail how its result is produced.

在下面的示例中，即将执行第29行。如果您选择逐入，调试器将进入“New”函数的实现，允许您详细检查其结果是如何产生的。

![https://resources.jetbrains.com/help/img/idea/2023.1/go_debug_examining_step_into_example_1.png](StepThroughTheProgram_img/go_debug_examining_step_into_example_1.animated.gif)

If there are several method calls on the line, GoLand asks you which method to enter. This feature is called [Smart step into](https://www.jetbrains.com/help/go/stepping-through-the-program.html#smart-step-into).

​	如果一行代码中有多个方法调用，GoLand会询问您要进入哪个方法。这个功能被称为[智能逐入](https://www.jetbrains.com/help/go/stepping-through-the-program.html#smart-step-into)。

## 智能逐入 Smart step into﻿

Smart step into is helpful when there are several method calls on a line, and you want to be specific about which method to enter. This feature allows you to select the method call you are interested in.

​	当一行代码中有多个方法调用时，智能逐入非常有用，您可以明确指定要进入的方法调用。这个功能允许您选择感兴趣的方法调用。

1. From the main menu, select Run | Debugging Actions | Smart Step Into or press Shift+F7.

2. 从主菜单中选择“运行” | “调试操作” | “智能逐入”或按下Shift+F7。

3. Click the method. You can also select it using the arrow keys or tabs and press Enter/F7.

4. 单击方法调用。您还可以使用箭头键或制表符进行选择，然后按Enter/F7。

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_debug_examining_smart_step_into_1.png](StepThroughTheProgram_img/go_debug_examining_smart_step_into_1.animated.gif)

## 逐出方法 Step out﻿

Steps out of the current method and takes you to the caller method.

​	退出当前方法并返回到调用者方法。

 

- Click the Step Out button 单击“逐出”按钮 ![Step Out button](StepThroughTheProgram_img/app.actions.stepOut.svg) or press Shift+F8. 或按下Shift+F8。

In the example, stepping out skips all iterations of the loop and takes you straight to the `main` method (the caller).

​	在示例中，逐出会跳过循环的所有迭代，并直接返回到`main`方法（调用者）。

![https://resources.jetbrains.com/help/img/idea/2023.1/go_debug_examining_step_out_example.png](StepThroughTheProgram_img/go_debug_examining_step_out_example.animated.gif)

## 运行到光标位置 Run to cursor﻿

Continues the execution until the position of the caret is reached.

​	继续执行，直到达到光标所在的位置。 

1. Place the caret at the line where you want the program to pause.
2. 将光标放在要程序暂停的行上。
3. Click the Run to Cursor button 单击“运行到光标位置”按钮 ![Run to Cursor button](StepThroughTheProgram_img/app.actions.runToCursor.svg) or press Alt+F9. 或按下Alt+F9。

Also, you can Run to Cursor by clicking the line number in the gutter.

​	另外，您还可以通过单击差错栏中的行号来运行到光标位置。

![https://resources.jetbrains.com/help/img/idea/2023.1/go_debug_examining_run_to_cursor_mouse.png](StepThroughTheProgram_img/go_debug_examining_run_to_cursor_mouse.animated.gif)

You can configure whether you want Run to Cursor to work on clicking a line number in Settings | Build, Execution, Deployment | Debugger.

​	您可以在“设置” | “构建、执行、部署” | “调试器”中配置是否希望在单击行号时启用“运行到光标位置”。

In the example, Run to cursor will continue the execution and stop at line 7 as if there were a breakpoint. If there are breakpoints in the `count()` method, the program will be suspended there.

​	在示例中，运行到光标位置将继续执行并在第7行停止，就像有一个断点一样。如果在`count()`方法中有断点，程序将在那里暂停。

To skip any breakpoints on the way, use [Force run to cursor](https://www.jetbrains.com/help/go/stepping-through-the-program.html#force-run-to-cursor).

​	要跳过途中的任何断点，请使用[强制运行到光标位置](https://www.jetbrains.com/help/go/stepping-through-the-program.html#force-run-to-cursor)。

## 强制运行到光标位置 Force run to cursor﻿

Continues the execution until the position of the caret is reached. All breakpoints on the way are ignored.

​	继续执行，直到达到光标所在的位置。忽略途中的所有断点。 

1. Place the caret at the line where you want the program to pause.
2. From the main menu, select Run | Debugging Actions | Force Run to Cursor or press Ctrl+Alt+F9.
3. 将光标放在要程序暂停的行上。
4. 从主菜单中选择“运行” | “调试操作” | “强制运行到光标位置”或按下Ctrl+Alt+F9。

In the example, Force run to cursor will continue the execution and stop at line 7 as if there were a breakpoint. The breakpoint inside `count()` will not have any effect.

​	在示例中，强制运行到光标位置将继续执行并在第7行停止，就像有一个断点一样。`count()`方法内部的断点将不会起作用。

## 强制逐过 Force step over﻿

Steps over the current line of code and takes you to the next line even if the highlighted line has method calls in it. If there are breakpoints in the called methods, they are ignored.

​	跳过当前代码行并进入下一行，即使高亮显示的行中有方法调用。如果调用的方法中有断点，它们将被忽略。 

- From the main menu, select Run | Debugging Actions | Force Step Over or press Alt+Shift+F8.
- 从主菜单中选择“运行” | “调试操作” | “强制逐过”或按下Alt+Shift+F8。

When a breakpoint is reached , the [Debug](https://www.jetbrains.com/help/go/debug-tool-window.html) tool window becomes active and enables you to get control over the program's execution. For this purpose, you can use the Run menu commands, or the icons on the [stepping toolbar](https://www.jetbrains.com/help/go/debug-tool-window.html#steptoolbar) of in the Debug tool window.

​	当达到断点时，[调试](https://www.jetbrains.com/help/go/debug-tool-window.html)工具窗口将变为活动状态，并使您能够控制程序的执行。为此，您可以使用运行菜单命令或调试工具窗口中的[逐步执行工具栏](https://www.jetbrains.com/help/go/debug-tool-window.html#steptoolbar)上的图标。

Each stepping action advances the execution point to the next execution location, depending on the action you choose.

​	每个逐步执行操作都会根据您选择的操作将执行点移动到下一个执行位置。