+++
title = "Exploring Windows minidumps"
weight = 60
date = 2023-06-20T10:40:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Exploring Windows minidumps﻿

https://www.jetbrains.com/help/go/exploring-windows-minidumps.html#90d9f7f4

Last modified: 16 January 2023


> You can create Windows minidumps only on Microsoft Windows operation systems. But you can analyze and debug your application on all supported operation systems.

Windows minidump files record the state of a program as it is running, or as at the moment of a crash. To read a minidump file, you must have the binaries of your application and the dump file.

### Create a binary file of your application﻿

1. Open the Run/Debug Configuration dialog in one of the following ways:

   - Select Run | Edit Configurations from the main menu.
   - With the [Navigation bar](https://www.jetbrains.com/help/go/guided-tour-around-the-user-interface.html#navigation-bar) visible (View | Appearance | Navigation Bar), choose Edit Configurations from the run/debug configuration selector.
   - Press Alt+Shift+F10 and then press 0.

2. In the [Run/Debug Configuration](https://www.jetbrains.com/help/go/run-debug-configurations-dialog.html) dialog, click the Add New Configuration icon (![the Add New Configuration icon](ExploringWindowsMinidumps_img/app.general.add.svg)) on the toolbar or press Alt+Insert. The list shows the default run/debug configurations. Select the desired configuration type (for example, Go build).

   The fields that appear in the right-hand pane display the default settings for the selected configuration type.

3. In the Name field, type the configuration name.

4. In the Files field, add the name of the file that you want to run (for example, **main.go**).

5. In the Output Directory field, specify the path where you want to store the created binary file.

6. Apply the changes and close the dialog.

### Create the minidump file on Windows﻿

1. Start the application and use it as usual.

   You can run the generated EXE file or run the application from GoLand. To run the application from GoLand, click the Run icon ![The Run icon](ExploringWindowsMinidumps_img/app.actions.execute.svg) in the gutter near the main function and select Run 'go build <configuration_name>'.

2. Open the Windows Task Manager Ctrl+Alt+Delete, click the Processes tab.

3. Right-click your application and select Create dump file.

![Create the minidump file on Windows](ExploringWindowsMinidumps_img/go_create_minidump_on_windows.png)

### Open the minidump file in GoLand﻿

1. Navigate to Run | Open Core Dump.
2. In the Executable field, specify a path to the **EXE** file.
3. In the Core Dump field, specify a path to the dump file.
4. Click OK.

![Open the minidump file in GoLand](ExploringWindowsMinidumps_img/go_open_minidump_file.png)