+++
title = "Arrange tool windows"
weight = 20
date = 2023-06-17T19:06:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Arrange tool windows - 整理工具窗口﻿

https://www.jetbrains.com/help/go/manipulating-the-tool-windows.html#lay_out_container

Last modified: 18 April 2023

最后修改：2023年4月18日

​	默认情况下，[工具窗口](https://www.jetbrains.com/help/go/tool-windows.html)附加在主窗口的边缘。您可以将它们分离出来作为独立窗口使用，方法如[工具窗口查看模式](https://www.jetbrains.com/help/go/viewing-modes.html)中所述。

## 移动工具窗口

1. 单击并拖动[工具窗口栏](https://www.jetbrains.com/help/go/tool-windows.html#bars_and_buttons)上的工具窗口按钮。

3. 或者，您可以单击工具窗口的选项菜单![The tool window options menu](ArrangeToolWindows_img/app.general.gearPlain.svg)，或右键单击[工具窗口标题栏](https://www.jetbrains.com/help/go/tool-windows.html#general-tool-windows-layout)，然后在 Move to 下选择要附加工具窗口的位置。

   ![Tool window options menu: Move to](ArrangeToolWindows_img/go_tool_window_move_to.png)

> ​	您可以将工具窗口的当前位置和自定义大小保存为[布局](https://www.jetbrains.com/help/go/tool-window-layouts.html)。

## 调整工具窗口大小

### 调整工具窗口的大小

- 单击并拖动工具窗口的边框。

- 要调整活动工具窗口的大小，按Ctrl+Alt+Shift+Left，Ctrl+Alt+Shift+Right，Ctrl+Alt+Shift+Up，Ctrl+Alt+Shift+Down或使用主菜单中的 Window | Active Tool Window | Resize。

- 要将工具窗口拉伸到最大宽度或高度，按Ctrl+Shift+Quote或从主菜单中选择Window | Active Tool Window | Resize | Maximize Tool Window。



### 保存自定义工具窗口大小

​	如果您更喜欢单独调整每个工具窗口的大小，可以配置IDE以记住您的自定义布局。

- 按Ctrl+Alt+S打开IDE设置，选择Appearance & Behaviour | Appearance。

- 在工具窗口部分，选择 Remember size for each tool window 选项。

  当禁用此选项时，工具窗口具有统一的默认宽度，并且在切换工具窗口时它们的大小保持不变。

- 应用更改并关闭对话框。

## 优化宽屏显示器

​	GoLand提供了几个选项来优化宽屏显示器上工具窗口的位置。

1. 在设置对话框中（Ctrl+Alt+S），选择Appearance & Behavior | Appearance。

2. 在工具窗口下，配置以下内容：

   - 宽屏工具窗口布局：通过限制水平工具窗口的宽度，使垂直工具窗口的高度最大化。

     {{< tabpane text=true >}}

     {{< tab header="Widescreen layout disabled" >}}

     ![The Widescreen tool window layout option is disabled](ArrangeToolWindows_img/go_WideScreenOFF.png)

     {{< /tab >}}

     {{< tab header="Widescreen layout enabled" >}}

     ![The Widescreen tool window layout option is enabled](ArrangeToolWindows_img/go_WideScreenON.png)

     {{< /tab >}}

     {{< /tabpane >}}

   - 左侧并排布局和右侧并排布局：在顶部和底部附加的垂直工具窗口中，以两列而不是重叠的方式显示。

     {{< tabpane text=true >}}

     {{< tab header="Side-by-side layout disabled" >}}

     ![Side-by-side layout is off](ArrangeToolWindows_img/go_WideScreenOFF.png)

     {{< /tab >}}

     {{< tab header="Side-by-side layout enabled" >}}

     ![Side-by-side layout is on](ArrangeToolWindows_img/go_side_by_side_left.png)

     {{< /tab >}}

     {{< /tabpane >}}

5. 点击OK应用更改。



## 将工具窗口移动到单独的框架 

​	您可以自由拖动工具窗口和编辑器选项卡到单独的框架，并排列您需要的布局。例如，您可以在一个屏幕上只有编辑器，在第二个屏幕上有一个独立的IDE窗口中的工具。

### 在单独的框架中排列工具窗口 

- 单击并拖动[工具窗口栏](https://www.jetbrains.com/help/go/tool-windows.html#bars_and_buttons)上的工具窗口按钮到您需要的屏幕上。

  如果您已经将选项卡分离到单独的框架中，您可以拖动工具窗口按钮并将其附加到工具窗口栏。
