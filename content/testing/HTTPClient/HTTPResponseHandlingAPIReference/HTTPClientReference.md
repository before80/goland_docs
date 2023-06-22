+++
title = "HTTP 客户端参考"
weight = 10
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# HTTP Client reference﻿ - HTTP 客户端参考

https://www.jetbrains.com/help/go/http-client-reference.html

Last modified: 21 April 2023

最近修改日期：2023年4月21日

​	`client` 对象保存了 HTTP 客户端会话的元数据，例如全局变量列表。HTTP 客户端会话在 GoLand 启动时开始，关闭 GoLand 时结束。在 GoLand 重新启动之间不会保留任何值。

​	`client` 提供对 [global](https://www.jetbrains.com/help/go/http-client-reference.html#global-variables-storage-reference) 嵌套对象的访问，用作变量存储。

## 属性

| 属性     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| `global` | [全局变量存储](https://www.jetbrains.com/help/go/http-client-reference.html#global-variables-storage-reference)，用于设置、检索或删除变量。一旦为全局变量分配了值（`client.global.set(VariableName, VariableValue)`），您可以在后续的 HTTP 请求中通过 `{{VariableName}}` 访问它，或者在响应处理脚本和预请求脚本中使用 `client.global.get("VariableName")`。有关更详细的示例，请参阅[使用全局变量](https://www.jetbrains.com/help/go/http-response-handling-examples.html#script-var-example)。 |

## 方法

| 方法     | 参数                                     | 描述                                                         |
| -------- | ---------------------------------------- | ------------------------------------------------------------ |
| `test`   | `testName`（字符串）`func`（函数）       | 创建一个名称为 `testName`、内容为 `func` 的测试。所有的测试都会在响应处理脚本之后执行。测试结果会显示在服务工具窗口的测试选项卡中。 |
| `assert` | `condition`（布尔值）`message`（字符串） | 检查指定的 `condition` 是否为 `true`，否则抛出异常。可选的 `message` 参数作为异常消息。 |
| `log`    | `text`（字符串）                         | 将 `text` 打印到响应处理或测试的标准输出，然后换行。         |
| `exit`   | —                                        | 终止响应处理脚本的执行。                                     |

## 全局变量存储﻿

​	`global` 对象用作变量存储，用于设置、检索或删除变量。这些变量是全局的，因为一旦设置，它们可以从任何 HTTP 请求中访问。

### 方法

| 方法       | 参数                                    | 描述                                                         |
| ---------- | --------------------------------------- | ------------------------------------------------------------ |
| `set`      | `varName`（字符串）`varValue`（字符串） | 将名为 `varName` 的变量保存到存储中，并将其值设置为 `varValue`。有关更详细的示例，请参阅[使用全局变量](https://www.jetbrains.com/help/go/http-response-handling-examples.html#script-var-example)。 |
| `get`      | `varName`（字符串）                     | 返回 `varName` 变量的值。                                    |
| `isEmpty`  |                                         | 检查 `global` 对象是否没有定义变量。                         |
| `clear`    | `varName`（字符串）                     | 从变量存储中删除 `varName` 变量。                            |
| `clearAll` |                                         | 从变量存储中删除所有变量。                                   |