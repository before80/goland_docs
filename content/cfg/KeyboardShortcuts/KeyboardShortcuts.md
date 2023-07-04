+++
title = "键盘快捷键"
weight = 10
date = 2023-06-17T19:06:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Keyboard shortcuts﻿ - 键盘快捷键

https://www.jetbrains.com/help/go/configuring-keyboard-and-mouse-shortcuts.html

Last modified: 18 January 2023

File | Settings | Keymap for Windows and Linux

GoLand | Settings | Keymap for macOS

Ctrl+Alt+S ![the Settings icon](KeyboardShortcuts_img/app.general.settings.svg)

GoLand includes several predefined keymaps and lets you customize frequently used shortcuts.

​	GoLand 包含几个预定义的按键映射，并允许您自定义常用的快捷键。

To view the keymap configuration, open the Settings dialog Ctrl+Alt+S and select Keymap.

​	要查看按键映射配置，请打开设置对话框 Ctrl+Alt+S，然后选择按键映射。

![Keymap settings](KeyboardShortcuts_img/keymap_settings.png)

GoLand automatically suggests a predefined keymap based on your environment. Make sure that it matches the OS you are using or select the one that matches shortcuts from another IDE or editor you are used to (for example, Emacs or Sublime).

​	GoLand 根据您的环境自动提供预定义的按键映射建议。确保它与您使用的操作系统匹配，或选择与您熟悉的其他 IDE 或编辑器的快捷键相匹配的按键映射（例如 Emacs 或 Sublime）。

> On macOS, the default keymap is macOS. There is also IntelliJ IDEA Classic, which is a legacy keymap that resembles the default keymap for Windows. Another keymap specific to macOS is macOS System Shortcuts that follows the [Default Mac OS X System Key Bindings](http://www.hcs.harvard.edu/~jrus/Site/System Bindings.html) conventions.
>
> ​	在 macOS 上，默认的按键映射是 macOS。还有 IntelliJ IDEA Classic，它是一种类似于 Windows 默认按键映射的传统按键映射。另一个特定于 macOS 的按键映射是 macOS System Shortcuts，它遵循[默认的 Mac OS X 系统按键绑定](http://www.hcs.harvard.edu/~jrus/Site/System Bindings.html)约定。

A keymap is a list of actions with corresponding keyboard and mouse shortcuts and abbreviations. You cannot change predefined keymaps. Instead, when you modify any shortcut of a predefined keymap, GoLand creates a copy of that keymap, which you can configure. Click 按键映射是一组具有相应键盘和鼠标快捷键和缩写的操作列表。您无法更改预定义的按键映射。相反，当您修改预定义按键映射中的任何快捷键时，GoLand 会创建该按键映射的副本，您可以进行配置。单击![The Show Scheme Actions icon](KeyboardShortcuts_img/app.general.gearPlain.svg) to duplicate the selected keymap, rename, remove, or restore it to default values. For information about keymap files, see [Location of user-defined keymaps](https://www.jetbrains.com/help/go/configuring-keyboard-and-mouse-shortcuts.html#custom_keymap_location). 以复制所选的按键映射，重命名、删除或恢复为默认值。有关按键映射文件的信息，请参阅[用户定义的按键映射的位置](https://www.jetbrains.com/help/go/configuring-keyboard-and-mouse-shortcuts.html#custom_keymap_location)。

Some actions inherit their keyboard shortcuts or mouse shortcuts from other actions. On the Keymap page, you can navigate to the parent action using the inherited from link. When you change a shortcut of a parent action, all shortcuts of its child actions change accordingly. When you change a shortcut of a child action, it does not affect the shortcuts of its parent action, but the inheritance link is removed making both actions independent.

​	某些操作继承其键盘快捷键或鼠标快捷键自其他操作。在按键映射页面上，您可以使用“继承自”链接导航到父操作。当您更改父操作的快捷键时，其所有子操作的快捷键也会相应更改。当您更改子操作的快捷键时，它不会影响父操作的快捷键，但会删除继承链接，使两个操作独立。

![Shortcut inheritance](KeyboardShortcuts_img/inherited_shortcuts.png)



To find an action by name, type it in the search field of the Keymap page. If you know the shortcut of an action, click 要按名称查找操作，请在按键映射页面的搜索字段中输入名称。如果您知道操作的快捷键，请单击 ![The Find Action by Shortcut icon](KeyboardShortcuts_img/app.actions.searchWithHistory.svg) and press the key combination in the Find Shortcut dialog.，然后在“查找快捷键”对话框中按下组合键。

When consulting this page and other pages in GoLand documentation, you can see keyboard shortcuts for the keymap that you use in the IDE — choose it using the selector at the top of a page.

​	在查阅本页和 GoLand 文档中的其他页面时，您可以看到在 IDE 中使用的按键映射的键盘快捷键 - 使用页面顶部的选择器选择它。

> To view the keymap reference as PDF, select Help | Keyboard Shortcuts PDF from the main menu.
>
> ​	要查看按键映射参考作为 PDF，请从主菜单中选择帮助 | 键盘快捷键 PDF。

### Add a keyboard shortcut﻿ 添加键盘快捷键

1. On the Keymap page of the Settings dialog Ctrl+Alt+S, right-click an action and select Add Keyboard Shortcut.

2. 在设置对话框的按键映射页面 Ctrl+Alt+S 上，右键单击一个操作，然后选择Add Keyboard Shortcut。

3. In the Keyboard Shortcut dialog, press the necessary key combination.

4. 在Keyboard Shortcut对话框中，按下所需的键盘组合键。

   > Pressing some keys or key combinations, such as Enter or Escape, will result in the actual action, such as closing the dialog. If you want to use them as shortcuts, click 按下某些键或键组合（如 Enter 或 Escape）将触发实际的操作，例如关闭对话框。如果您想将它们用作快捷键，请在“键盘快捷键”对话框中单击![The Set shortcuts with special keys icon](KeyboardShortcuts_img/app.general.add.svg) in the Keyboard Shortcut dialog and select the necessary key or combination.，然后选择所需的键或组合。

5. If necessary, select the Second stroke checkbox to define a complex shortcut with two sequential key combinations.

6. 如有必要，选中“第二个键击”复选框以定义具有两个连续键盘组合键的复杂快捷键。

7. 单击OK 以保存快捷键。

8. Click OK to save the shortcut.

The key combination that you press is displayed in the Keyboard Shortcut dialog, as well as a warning if it conflicts with existing shortcuts.

​	您按下的键盘组合键将显示在“键盘快捷键”对话框中，如果它与现有快捷键冲突，还会显示警告。

### Add a mouse shortcut﻿ 添加鼠标快捷键

1. On the Keymap page of the Settings dialog Ctrl+Alt+S, right-click an action and select Add Mouse Shortcut.
2. 在设置对话框的按键映射页面 Ctrl+Alt+S 上，右键单击一个操作，然后选择Add Mouse Shortcut。
3. In the Mouse Shortcut dialog, move the mouse pointer to the central area and click or scroll as necessary.
4. 在Mouse Shortcut对话框中，将鼠标指针移动到中心区域，根据需要单击或滚动。
5. Click OK to save the shortcut.
6. 单击OK 以保存快捷键。

The performed mouse manipulations are displayed in the Mouse Shortcut dialog, as well as a warning if it conflicts with existing shortcuts.

​	所执行的鼠标操作将显示在Mouse Shortcut对话框中，如果它与现有快捷键冲突，还会显示警告。

### Add an abbreviation﻿ 添加缩写

An abbreviation can be used to quickly find an action without a shortcut. For example, you can press Ctrl+Shift+A and type the name of the Jump to Colors and Fonts action to quickly modify the color and font settings of the element under the current caret position. If you assign an abbreviation for this action (like JCF), you can then type it instead of the full action name.

​	缩写可用于快速查找没有快捷键的操作。例如，您可以按 Ctrl+Shift+A 并输入“Jump to Colors and Fonts”操作的名称，以便快速修改当前插入符位置下的元素的颜色和字体设置。如果您为此操作分配了一个缩写（例如 JCF），您可以直接输入它，而不是输入完整的操作名称。

1. On the Keymap page of the Settings dialog Ctrl+Alt+S, right-click an action and select Add Abbreviation.
2. 在设置对话框的按键映射页面 Ctrl+Alt+S 上，右键单击一个操作，然后选择Add Abbreviation（缩写）。
3. In the Abbreviation dialog, type the desired abbreviation and click OK.
4. 在Abbreviation （缩写）对话框中，输入所需的缩写，然后单击OK。

### Reset action shortcuts to default﻿ 将操作快捷键重置为默认值

If you changed, added, or removed a shortcut for an action, you can reset it to the initial configuration.

​	如果您更改、添加或删除了操作的快捷键，可以将其重置为初始配置。 

- On the Keymap page of the Settings dialog Ctrl+Alt+S, right-click an action and select Reset Shortcuts.
- 在设置对话框的按键映射页面 Ctrl+Alt+S 上，右键单击一个操作，然后选择“重置快捷键”。

## Location of user-defined keymaps﻿ 用户定义的按键映射的位置

When you modify one of the default keymaps, GoLand creates a custom keymap file in the **keymaps** directory under the GoLand [IDE configuration directory](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory):

​	当您修改默认按键映射之一时，GoLand 会在 GoLand [IDE 配置目录](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory)的 **keymaps** 目录中创建一个自定义按键映射文件：



{{< tabpane text=true >}}

{{< tab header="Windows" >}}

Syntax

**%APPDATA%\JetBrains\<product><version>\keymaps**

Example

**C:\Users\JohnS\AppData\Roaming\JetBrains\GoLand2023.1\keymaps**

{{< /tab >}}

{{< tab header="macOS" >}}

Syntax

**~/Library/Application Support/JetBrains/<product><version>/keymaps**

Example

**~/Library/Application Support/JetBrains/GoLand2023.1/keymaps**

{{< /tab >}}

{{< tab header="Linux" >}}

Syntax

**~/.config/JetBrains/<product><version>/keymaps**

Example

**~/.config/JetBrains/GoLand2023.1/keymaps**

{{< /tab >}}

{{< /tabpane >}}

A custom keymap file contains only the differences relative to its parent keymap. For example, if you modify the default Windows keymap, your custom keymap will be its child. The file will contain only the shortcuts that you added or modified, while all other shortcuts of your custom keymap will be the same as the default Windows keymap.

​	自定义按键映射文件仅包含与其父按键映射相对应的差异。例如，如果您修改了默认的 Windows 按键映射，则您的自定义按键映射将成为其子级。该文件仅包含您添加或修改的快捷键，而您的自定义按键映射的所有其他快捷键将与默认的 Windows 按键映射相同。

You can share your custom keymaps with team members or between your IDE instances. Copy the corresponding keymap file and put it in the **keymaps** directory on another GoLand installation. Then select the copied keymap on the Keymap settings page.

​	您可以与团队成员或在您的 IDE 实例之间共享自定义按键映射。将相应的按键映射文件复制到另一个 GoLand 安装的 **keymaps** 目录中。然后在按键映射设置页面上选择复制的按键映射。

## Conflicts with global OS shortcuts﻿ 与全局操作系统快捷键的冲突

Predefined keymaps do not cover every possible platform, version, and configuration. Some shortcuts can conflict with global system actions and shortcuts for third-party software. To fix these conflicts, you can reassign or disable the conflicting shortcut.

​	预定义的按键映射无法涵盖每个可能的平台、版本和配置。某些快捷键可能与全局系统操作和第三方软件的快捷键冲突。要解决这些冲突，您可以重新分配或禁用冲突的快捷键。

GoLand detects conflicts with system shortcuts and notifies you with a popup message:

​	GoLand 检测到与系统快捷键的冲突，并通过弹出消息通知您：

![Notification on conflicting shortcuts](KeyboardShortcuts_img/keymap_conflicts_message.png)

Click Modify shortcuts to open the Keymap settings dialog where you can make the necessary adjustments:

​	单击Modify shortcuts以打开按键映射设置对话框，您可以进行必要的调整：

![Adjust conflicting shortcuts](KeyboardShortcuts_img/cl_keymap_conflicts.png)

Here are a few examples of possible system shortcut conflicts with the default keymap in GoLand. Make sure that function keys are enabled on your system.

​	以下是在 GoLand 中默认按键映射可能与系统快捷键冲突的一些示例。请确保您的系统启用了功能键。

{{< tabpane text=true >}}

{{< tab header="macOS" >}}

| 快捷键 | 系统操作                  | GoLand 操作  |
| ------ | ------------------------- | ------------ |
| ⌃Space | 选择上一个输入源          | 基本代码完成 |
| ⇧⌘A    | 在终端中搜索 Man 页面索引 | 查找操作     |

{{< /tab >}}

{{< tab header="Ubuntu" >}}

| 快捷键                      | 系统操作              | GoLand 操作       |
| --------------------------- | --------------------- | ----------------- |
| Ctrl+Alt+S                  | 遮挡窗口              | 打开设置对话框    |
| Ctrl+Alt+L                  | 锁定屏幕              | 重新格式化代码    |
| Ctrl+Alt+T                  | 启动终端              | 包围选择          |
| Ctrl+Alt+F12                | 打开 tty12 虚拟控制台 | 文件路径          |
| Ctrl+Alt+LeftCtrl+Alt+Right | 在工作区间切换        | 撤销/恢复导航操作 |
| Alt+F7                      | 移动窗口              | 查找用法          |
| Alt+F8                      | 调整窗口大小          | 求值表达式        |

{{< /tab >}}

{{< /tabpane >}}