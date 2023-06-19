+++
title = "Run anything"
weight = 20
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Run anything﻿

https://www.jetbrains.com/help/go/running-anything.html#send_http_requests

Last modified: 09 November 2022

Double Ctrl

Run Anything is a quick way to launch [run/debug configurations](https://www.jetbrains.com/help/go/run-debug-configuration.html), applications, scripts, commands, tasks, and open recent projects. It also helps you use proper command syntax by generating suggestions as you type. When you call a command, Run Anything delegates the further work to the appropriate tools.

![The Run Anything popup](RunAnything_img/go_run_anything_overview.png)

## Open the Run Anything popup﻿

- Press Ctrl twice.

  Alternatively, click ![the Run Anything icon](RunAnything_img/app.actions.run_anything.svg) on the toolbar.

  > ### 
  >
  > 
  >
  > To disable the Double-Ctrl mapping for this action, select Disable double modifier key shortcuts on the Advanced Settings page of the IDE settings Ctrl+Alt+S

  The icon is hidden by default. To add the icon to the toolbar, open the Settings dialog (Ctrl+Alt+S), go to Appearance and Behavior | Menus and Toolbars, expand the Main Toolbar node, and add the Run Anything action, for example, below Search Everywhere. See [Menus and toolbars](https://www.jetbrains.com/help/go/customize-actions-menus-and-toolbars.html) for details.

## Launch a run/debug configuration﻿

1. Start typing the run/debug configuration name and select it from the suggestion list.

   ![Start run/debug configurations from the Run Anything popup](RunAnything_img/go_run_anything_run_config.png)

2. To [debug](https://www.jetbrains.com/help/go/debugging-code.html) a run configuration, hold Shift when launching it.

## Run commands﻿

- Start typing the command name and navigate the suggestion list using the arrow keys. When you press Space, you accept the current suggestion and get further suggestions specific to this command.

  ![Run Anything: npm script](RunAnything_img/go_run_anything_npm.png)

- To get the list of available commands, type `?`. The list of commands depends on the installed/enabled plugins. If a command is not on the suggestion list, it will be executed in the terminal.

  ![List of the available commands in Run Anything](RunAnything_img/go_run_anything_commands_hints.png)

## Open a recent project﻿

You can also quickly reopen a [recent project](https://www.jetbrains.com/help/go/creating-and-managing-projects.html) from the Run Anything popup. Search for the project by the name or type `open` to shorten the list of suggestions, then select the required project from the list, and press Enter:

![Opening a recent project from the Run Anything popup](RunAnything_img/go_run_anything_open.png)

## Send HTTP requests﻿

If, while [composing an HTTP request](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html), you specified its name, you can find and send this HTTP request from the Run Anything popup.

1. Start typing the name of an HTTP request and select it from the suggestion list:

   ![Send HTTP requests](RunAnything_img/run_anything_http.png)

2. If your request contains [environment variables](https://www.jetbrains.com/help/go/exploring-http-syntax.html#environment-variables), press Shift while selecting a request. This will open the popup menu where you can select the environment to be used for the request.

   ![Select HTTP request environment](RunAnything_img/http_request_choose_environment.png)