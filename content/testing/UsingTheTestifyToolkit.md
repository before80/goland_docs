+++
title = "Using the Testify toolkit"
weight = 60
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Using the Testify toolkit﻿

https://www.jetbrains.com/help/go/using-the-testify-toolkit.html#run-tests-with-testify

Last modified: 16 January 2023

Programming is not always a straightforward process. Especially, when you need to add a small piece of code to an application and ensure that the whole application works as intended. In this case, testing can help you to maintain code quality and improve its reliability.

GoLand supports the Testify toolkit. Testify provides several packages to work with assertions, mock objects, and testing suites. With Testify, you can run your suites and methods as regular test functions. For more information about the toolkit, read the description of [Testify on GitHub](https://github.com/stretchr/testify).

### Run tests with Testify﻿

1. Run `go get -u github.com/stretchr/testify` in the terminal. Alternatively, use the intention action Alt+Enter to download and install the toolkit.
2. Click the Run test icon ![The Run test icon](UsingTheTestifyToolkit_img/app.actions.execute.svg) and select Run <configuration>.

![https://resources.jetbrains.com/help/img/idea/2023.1/go_run_testify.png](UsingTheTestifyToolkit_img/go_run_testify.animated.gif)


> Ensure that the test file has the **_test** postfix (for example, **testify_test.go**).

### Compare expected and actual values﻿

You can compare expected and actual values for failed assertion tests.

- To see the difference, click the Click to see difference link in the Run pane.

  ![Compare expected and actual values](UsingTheTestifyToolkit_img/go_compare_expected_actual_results.png)