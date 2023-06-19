+++
title = "Code coverage"
weight = 50
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Code coverage﻿

https://www.jetbrains.com/help/go/code-coverage.html

Last modified: 21 April 2023

Code coverage results are displayed in tool windows and in the editor. The tool windows show the following information:

- For a directory: the percentage of covered files and statements.
- For a file: the percentage of the covered statements.

When a file is opened in the editor, each line is highlighted with regard to its code coverage status:

- Lines executed during simulation are marked green.
- Lines not executed during simulation are marked red.

The coverage measurement results comprise a [coverage suite](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html). You can have the results of a new simulation merged with any existing suite. In this case, a line will be considered covered if it is covered by at least one of the simulations.

A coverage suite is generated every time a test or application with code coverage measurement is executed. It is possible to have an unlimited amount of coverage suites.

## Run with code coverage﻿

### General steps for using code coverage in a project﻿

1. Specify how you want to [process the coverage results](https://www.jetbrains.com/help/go/configuring-code-coverage-measurement.html#cov_suites).
2. [Create a run/debug configuration](https://www.jetbrains.com/help/go/run-debug-configuration.html#run-debug-configuration-templates-for-tests) for the target code, if you are going to measure code coverage for testing.
3. [Configure code coverage measurement](https://www.jetbrains.com/help/go/configuring-code-coverage-measurement.html) in the desired run/debug configuration.
4. [Run with coverage](https://www.jetbrains.com/help/go/running-test-with-coverage.html), using the dedicated command from the main menu Run | Run with Coverage, or click the Run with Coverage button ![the Run with Coverage button](index_img/app.general.runWithCoverage.svg).
5. Once the run with coverage has been executed, you can perform the following actions:
   - Use the [various coverage suites](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html).
   - [View code coverage data](https://www.jetbrains.com/help/go/switching-between-code-coverage-suites.html).