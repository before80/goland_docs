+++
title = "Running with coverage"
weight = 20
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Running with coverage﻿

https://www.jetbrains.com/help/go/running-test-with-coverage.html

Last modified: 03 March 2023

GoLand provides a dedicated action that allows you to run tests with code coverage measurement. The code coverage data is processed according to the option selected on the [Coverage](https://www.jetbrains.com/help/go/coverage-settings.html) page of the Settings dialog (Ctrl+Alt+S).

### Run a test with code coverage﻿

1. Do one of the following:

   - Open the desired file in the editor, and choose Run <name> with Coverage from the context menu. When running tests with coverage, note that you can run the entire test class, or each individual test method, depending on the caret location.
   - Open the desired file in the Project tool window and choose Run <name> with Coverage from the context menu. You can also select a directory with test files and choose the corresponding command from the context menu to run several tests with coverage.
   - Select the desired run/debug configuration, and then from the main menu choose Run | Run <run/debug configuration name> with coverage.
   - On the main toolbar, click the Run <run/debug configuration name> with Coverage button ![Run <run/debug configuration name> with coverage](RunningWithCoverage_img/app.general.runWithCoverage.svg). This will launch the selected run/debug configuration.

2. If the Show options before applying coverage to the editor checkbox has been selected on the [Coverage](https://www.jetbrains.com/help/go/coverage-settings.html) page of the Settings dialog (Ctrl+Alt+S), a dialog appears where you can choose whether you want to replace the active coverage suites, add the collected data to the active suites, or not to apply coverage data. You can also opt to skip this dialog in the future.

   In case any other option has been selected, the respective action will be performed silently.

3. [Explore the collected coverage data](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html) in the [Coverage Tool Window](https://www.jetbrains.com/help/go/coverage-tool-window.html).

![Run a test with code coverage](RunningWithCoverage_img/go_running_with_coverage.png)