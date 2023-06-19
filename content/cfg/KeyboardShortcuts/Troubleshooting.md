+++
title = "Keyboard shortcut not working?"
weight = 40
date = 2023-06-17T19:06:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Keyboard shortcut not working?﻿

https://www.jetbrains.com/help/go/keyboard-shortcuts-troubleshooting.html#are-there-conflicts-between-ide-actions

Last modified: 25 October 2022

## Are you using the right keymap?﻿

First of all, check whether the shortcut should work as you expect. It may be obvious for shortcuts like Ctrl+C and Ctrl+V, but shortcuts like Alt+Up or Ctrl+W often perform different actions depending on the application and the operating system.

Taking into account different expectations regarding shortcuts, GoLand lets you choose between keymaps (predefined sets of shortcuts). If you worked with a specific editor or IDE before, you can switch to a keymap with the corresponding name, such as Visual Studio, Sublime Text, or VSCode, and use the same shortcuts as in that editor or IDE.

1. Press Ctrl+Alt+S to open the IDE settings and select Keymap.
2. Make sure that you are using the correct keymap.
3. Use the search field to check whether the shortcuts are mapped as expected.

Alternatively, you can select the desired keymap at the top of this documentation page, and check the list of shortcuts to study keyboard mappings in that keymap.

If you think that the default mapping for a specific shortcut is incorrect for a particular keymap, let us know by filing an issue in our [issue tracker](https://youtrack.jetbrains.com/issues/IDEA).

## Do you have a non-English keyboard layout?﻿

All keymaps in GoLand are designed for the [QWERTY US English keyboard layout](https://en.wikipedia.org/wiki/QWERTY#United_States). If you use a keyboard layout for another Latin-script alphabet, some shortcuts may not work because characters used in those shortcuts may not have dedicated keyboard keys.

For example, there is no dedicated keyboard key for the forward slash `/` in the German keyboard layout, and therefore it is impossible to use the Ctrl+/ shortcut to comment the current line.

The recommended workaround in this case is to [install](https://www.jetbrains.com/help/go/managing-plugins.html#install_plugin_from_repo) the [Keymap Nationalizer](https://plugins.jetbrains.com/plugin/14625-keymap-nationalizer) plugin, which will generate a non-conflicting keymap for your keyboard layout. Alternatively, you can fix specific shortcuts by [assigning another shortcut](https://www.jetbrains.com/help/go/configuring-keyboard-and-mouse-shortcuts.html#add-keyboard-shortcut) instead of the one that doesn't work.

Regardless of the workaround, we're still looking for a solution that would work out-of-the-box for any keyboard layout. The progress is tracked in [this issue](https://youtrack.jetbrains.com/issue/IDEA-165950).

## Does the shortcut include function keys?﻿

If the shortcut includes function keys F1... F12, it may not work because these keys are often mapped to utility actions by default, such as changing speaker volume or screen brightness.

You can make such shortcuts work in one of the following ways:

- On keyboards that have a Fn key, press this key together with the original key combination.
- Change the default behaviour of function keys. The procedure varies depending on your computer manufacturer; if you are running GoLand on macOS, refer to [this article](https://support.apple.com/en-us/HT204436).

## Does the keystroke reach the IDE?﻿

On the Keymap settings page, click Find Actions by Shortcut, and then press the key combination.

If the field in the Find Shortcut popup remains empty after you press a key combination, this means that some other program or your operating system intercepted the shortcut.

### Check conflicting applications﻿

Check the applications that have to react to shortcuts even when another application has focus. These normally include screen recording software or tunnelling tools such as Microsoft Remote Desktop.

When you find the conflicting shortcut, decide which application should react on this shortcut and either [assign another shortcut](https://www.jetbrains.com/help/go/configuring-keyboard-and-mouse-shortcuts.html#add-keyboard-shortcut) in GoLand or change the shortcut in the conflicting application.

### Check for conflicts with your operating system﻿



macOS

Linux

Windows





There are several known conflicts in most of predefined keymaps, for example:

| Shortcut | System action                     | GoLand action         |
| -------- | --------------------------------- | --------------------- |
| ⌃Space   | Select the previous input source  | Basic code completion |
| ⇧⌘A      | Search man Page Index in Terminal | Find Action           |

Try the macOS System Shortcuts keymap, which was designed to avoid conflicts with native macOS shortcuts. If you still find conflicts when using this keymap, file an issue in our [issue tracker](https://youtrack.jetbrains.com/issues/IDEA).

If you don't want to use this keymap, [assign another non-conflicting shortcut](https://www.jetbrains.com/help/go/configuring-keyboard-and-mouse-shortcuts.html#add-keyboard-shortcut) in GoLand.

## Does the IDE process the shortcut correctly?﻿

When the shortcut that you pressed appears in the Find Shortcut popup, this means that the IDE can handle this shortcut. Check the list of actions mapped to this shortcut:

- If the expected action doesn't appear in the list, [assign a shortcut](https://www.jetbrains.com/help/go/configuring-keyboard-and-mouse-shortcuts.html#add-keyboard-shortcut) manually as a workaround, and file an issue in our [issue tracker](https://youtrack.jetbrains.com/issues/IDEA).

- If the expected action appears together with other actions, it is by design in most cases because those actions should be available in different contexts. In the example below, the Ctrl+Shift+U shortcut is assigned to both Toggle Case, which works in the editor, and [Unshelve](https://www.jetbrains.com/help/go/shelving-and-unshelving-changes.html), which works in the Commit window.

  If the shortcut doesn't work as expected or doesn't work at all in specific context, remove shortcuts from other actions (right-click and choose Remove shortcut) as a workaround, and file an issue in our [issue tracker](https://youtrack.jetbrains.com/issues/IDEA).

- If you have custom plugins installed on the Plugins page, there may be a chance that one of them intercepts the shortcut. Try disabling custom plugins and see whether it helps.

- If the expected action appears in the list without other actions, but it still doesn't work as expected in the expected IDE context, [assign some other shortcut](https://www.jetbrains.com/help/go/configuring-keyboard-and-mouse-shortcuts.html#add-keyboard-shortcut) manually as a workaround, and file an issue in our [issue tracker](https://youtrack.jetbrains.com/issues/IDEA).