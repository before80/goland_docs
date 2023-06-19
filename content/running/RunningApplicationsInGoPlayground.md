+++
title = "Running applications in Go Playground"
weight = 60
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Running applications in Go Playground﻿

https://www.jetbrains.com/help/go/running-applications-in-go-playground.html

Last modified: 23 February 2023

You can run your Go code in GoLand by using the Go playground server to process it. When you use the Open in | Playground action, GoLand creates a scratch file with your code and displays a toolbar that contains the same options that you see in the Go playground.

You can format and share your code, change the Go version, run your code by using the Go playground server, or run it locally.

GoLand displays a toolbar with the Go Playground controls for Go scratch files.

![the Go playground inside GoLand](RunningApplicationsInGoPlayground_img/go_the_go_playground_inside_go_land.png)

### Running your code in the Go Playground﻿

1. Select code that you want to run in the Go Playground.

2. Right-click the selection and navigate to Open In | Playground.

3. Click the Run icon (![the Run icon](RunningApplicationsInGoPlayground_img/app.actions.execute.svg)) on the toolbar.

   Note: if you run your code from the context menu or from the gutter, GoLand runs your code locally. Also, you can run your code locally by selecting the Run locally.

   <video src="https://resources.jetbrains.com/help/img/idea/2023.1/go_running_your_code_in_the_go_playground.mp4" preload="auto" style="margin: 0px; padding: 0px; border: 0px; font: inherit; vertical-align: baseline; width: 648.8px; height: 413px;"></video>

   

   

   00:01/00:09

   

### Load code from file or URL﻿

1. From the main menu, select File | New | Scratch File or press Ctrl+Alt+Shift+Insert.

2. From the New Scratch File window, select Go.

3. On the toolbar, click the Load icon (![the Load icon](RunningApplicationsInGoPlayground_img/app.actions.download.svg)).

4. In the dialog, select the source of your code: File or URL.

5. Click OK.

   <video src="https://resources.jetbrains.com/help/img/idea/2023.1/go_load_code_from_file_or_url.mp4" preload="auto" style="margin: 0px; padding: 0px; border: 0px; font: inherit; vertical-align: baseline; width: 648.8px; height: 410px;"></video>

   

   

   00:01/00:13

   

### Format code with the Go Playground formatter﻿

1. Open your code in a scratch file. For more information about scratch files, see [Scratch files](https://www.jetbrains.com/help/go/scratches.html).

   To create a new file, select File | New | Scratch File from the main menu or press Ctrl+Alt+Shift+Insert.

2. On the toolbar, click the Format icon (![the Format icon](RunningApplicationsInGoPlayground_img/app.actions.annotate.svg)).

   ![Format code with the Go Playground formatter](RunningApplicationsInGoPlayground_img/go_format_code_with_the_go_playground_formatter.png)

### Share code in the Go Playground from scratch files﻿

1. Open your code in a scratch file. For more information about scratch files, see [Scratch files](https://www.jetbrains.com/help/go/scratches.html).

   To create a new file, select File | New | Scratch File from the main menu or press Ctrl+Alt+Shift+Insert.

2. On the toolbar, click the Format icon (![the Format icon](RunningApplicationsInGoPlayground_img/app.actions.annotate.svg)).

   Depending on the selected version, GoLand adds a version parameter to the generated link to the Go Playground.

   ![version parameter in shared links to the Go Playground](RunningApplicationsInGoPlayground_img/go_version_parameter_in_shared_links_to_the_go_playground.png)

### Selecting Go version﻿

1. Open your code in a scratch file. For more information about scratch files, see [Scratch files](https://www.jetbrains.com/help/go/scratches.html).

   To create a new file, select File | New | Scratch File from the main menu or press Ctrl+Alt+Shift+Insert.

2. From the Go version drop-down, select the version that you want.

   Depending on the selected version, GoLand adds a version parameter to the generated link to the Go Playground.

### Selecting context of a module﻿

1. Open your code in a scratch file. For more information about scratch files, see [Scratch files](https://www.jetbrains.com/help/go/scratches.html).

   To create a new file, select File | New | Scratch File from the main menu or press Ctrl+Alt+Shift+Insert.

2. From the Go version drop-down, select the version that you want.