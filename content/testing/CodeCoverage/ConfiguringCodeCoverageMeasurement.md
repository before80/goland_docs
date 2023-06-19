+++
title = "Configuring code coverage measurement"
weight = 10
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Configuring code coverage measurement﻿

https://www.jetbrains.com/help/go/configuring-code-coverage-measurement.html

Last modified: 03 May 2023

### Configure code coverage behavior﻿

1. Press Ctrl+Alt+S to open the IDE settings and select Build, Execution, Deployment | Coverage.
2. Define how the collected coverage data will be processed:
   - Show options before applying coverage to the editor: show the Code Coverage dialog every time you run a new run configuration with code coverage.
   - Do not apply collected coverage: discard the new code coverage results.
   - Replace active suites with the new one: discard the active suites and use the new one every time you launch a new run configuration with code coverage.
   - Add to the active suites: add new code coverage suites to the active suites every time you launch a new run configuration with code coverage.
3. Select the Activate Coverage View checkbox to open the [Coverage](https://www.jetbrains.com/help/go/coverage-tool-window.html) tool window automatically.

### Change colors of the coverage highlighting﻿

1. Press Ctrl+Alt+S to open the IDE settings and select Editor | Color Scheme | General.
2. Alternatively, click ![the Edit Coverage Colors button](ConfiguringCodeCoverageMeasurement_img/app.general.settings.svg) in the popup that opens on clicking the coverage indication line in the gutter.
3. In the list of components, expand the Line Coverage node and select a type of coverage: for example, Full, Partial or Uncovered.
4. Click the Foreground field to open the Select Color dialog.
5. Select a color, apply the changes, and close the dialog.

![Configure code coverage colors](ConfiguringCodeCoverageMeasurement_img/coverageColors.png)