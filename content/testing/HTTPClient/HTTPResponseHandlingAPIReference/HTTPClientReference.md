+++
title = "HTTP Client reference"
weight = 10
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# HTTP Client reference﻿

https://www.jetbrains.com/help/go/http-client-reference.html#client-methods

Last modified: 21 April 2023

The `client` object holds the HTTP Client session metadata, such as the list of global variables. The HTTP Client session is started when GoLand starts, and ends when GoLand is closed. Values are not preserved between GoLand restarts.

The `client` provides access to the [global](https://www.jetbrains.com/help/go/http-client-reference.html#global-variables-storage-reference) nested object that serves as a variable storage.

## Properties﻿

| Property | Description                                                  |
| -------- | ------------------------------------------------------------ |
| `global` | The [global variables storage](https://www.jetbrains.com/help/go/http-client-reference.html#global-variables-storage-reference), which is used for setting, retrieving, or removing variables.Once you assign a value to a global variable (`client.global.set(VariableName, VariableValue)`), you can access it as `{{VariableName}}` in subsequent HTTP requests or using `client.global.get("VariableName")` in response handler scripts and pre-request scripts. See [Use global variables](https://www.jetbrains.com/help/go/http-response-handling-examples.html#script-var-example) for a more detailed example. |

## Methods﻿

| Method   | Parameters                              | Description                                                  |
| -------- | --------------------------------------- | ------------------------------------------------------------ |
| `test`   | `testName` (string)`func` (function)    | Creates a test with the name `testName` and body `func`. All tests are executed after the response handler script. Test results are displayed in the Tests tab of the Services tool window. |
| `assert` | `condition` (boolean)`message` (string) | Checks that the specified `condition` is `true`; throws an exception otherwise. The optional `message` parameter serves as an exception message. |
| `log`    | `text`                                  | Prints `text` to the response handler or test stdout and then terminates the line. |
| `exit`   | —                                       | Terminates execution of the response handler script.         |

## Global variables storage﻿

The `global` object serves as a variable storage and is used for setting, retrieving, or removing variables. These variables are global because, once set, they can be accessed from any HTTP request.

### Methods﻿

| Method     | Parameters                            | Description                                                  |
| ---------- | ------------------------------------- | ------------------------------------------------------------ |
| `set`      | `varName` (string)`varValue` (string) | Saves the variable with the `varName` name to the storage and sets its value to `varValue`. See [Use global variables](https://www.jetbrains.com/help/go/http-response-handling-examples.html#script-var-example) for a more detailed example. |
| `get`      | `varName` (string)                    | Returns the value of the `varName` variable.                 |
| `isEmpty`  |                                       | Checks whether the `global` object has no variables defined. |
| `clear`    | `varName` (string)                    | Removes the `varName` variable from the variables storage.   |
| `clearAll` |                                       | Removes all variables from the variables storage.            |