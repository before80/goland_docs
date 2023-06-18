+++
title = "Linux native menu"
weight = 80
date = 2023-06-17T19:06:58+08:00
description = ""
isCJKLanguage = true
draft = false
+++
# Linux native menu﻿

https://www.jetbrains.com/help/go/linux-native-menu.html

Last modified: 04 April 2023

> This is an experimental feature in GoLand.

In GoLand for Linux, you can use the global main menu similar to macOS – a horizontal menu attached to the top of the screen. By default, this menu is enabled, although not all Linux desktop environments support it natively.

### Disable the native menu﻿

1. Press Ctrl+Shift+A to open the Find Action dialog, then type `Experimental features`, and press Enter.
2. Clear the checkbox next to the linux.native.menu item, apply the changes, and close the dialog.
3. Restart GoLand.

## Troubleshoot﻿

The native menu might not display on some desktop environments. If you have followed the steps described on this page, but the menu doesn't appear, try installing [JavaFX Runtime for Plugins](https://plugins.jetbrains.com/plugin/14250-javafx-runtime-for-plugins) from the JetBrains plugin repository.