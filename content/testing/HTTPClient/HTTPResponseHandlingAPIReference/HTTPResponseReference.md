+++
title = "HTTP 响应参考"
weight = 30
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# HTTP Response reference﻿ - HTTP 响应参考

https://www.jetbrains.com/help/go/http-response-reference.html

Last modified: 21 April 2023

最近修改日期：2023年4月21日

## 响应属性

​	`response` 对象保存了接收到的 HTTP 响应的信息（响应内容、头部、状态等），并提供对 [headers](https://www.jetbrains.com/help/go/http-response-reference.html#headers-reference) 和 [contentType](https://www.jetbrains.com/help/go/http-response-reference.html#content-type-reference) 嵌套对象的访问。

| 属性                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| `body`（字符串 \| [LineStreamResponse](https://www.jetbrains.com/help/go/http-response-reference.html#linestreamresponse_reference) \| 对象） | 响应内容，可以是字符串、LineStreamResponse 对象或 JSON 对象。 |
| `headers`（[ResponseHeaders](https://www.jetbrains.com/help/go/http-response-reference.html#headers-reference)） | [响应头部存储对象](https://www.jetbrains.com/help/go/http-response-reference.html#headers-reference)。 |
| `status`（整数）                                             | 响应状态，例如 200 或 404。                                  |
| `contentType`（[ContentType](https://www.jetbrains.com/help/go/http-response-reference.html#content-type-reference)） | [contentType 对象](https://www.jetbrains.com/help/go/http-response-reference.html#content-type-reference)，保存了 Content-Type 响应头部值的数据。 |

## Headers 对象

​	`ResponseHeaders` 对象用于获取有关响应头部值的数据。

### 方法﻿

| 方法       | 参数                   | 描述                                                         |
| ---------- | ---------------------- | ------------------------------------------------------------ |
| `valueOf`  | `headerName`（字符串） | 获取 `headerName` 响应头部的第一个值，如果 `headerName` 响应头部不存在，则返回 `null`。 |
| `valuesOf` | `headerName`（字符串） | 获取包含 `headerName` 响应头部所有值的数组。如果 `headerName` 响应头部不存在，则返回空数组。 |

## ContentType 对象﻿

​	`ContentType` 数据对象包含了来自 Content-Type 响应头部的信息。

### 属性

| 属性                 | 描述                                                         |
| -------------------- | ------------------------------------------------------------ |
| `mimeType`（字符串） | 响应的 MIME 类型，例如 text/plain、text/xml、application/json。 |
| `charset`（字符串）  | 响应字符集的字符串表示，例如 utf-8。                         |

## LineStreamResponse 对象

​	`LineStreamResponse` 接口用于将响应作为一系列行进行处理。它实现了一个 `onEachLine(line, unsubscribe)` 方法，该方法依次循环遍历流中的每一行。该方法接受两个参数：

### 实参

| 实参                         | 描述                                 |
| ---------------------------- | ------------------------------------ |
| `line`（字符串或 JSON 对象） | 作为流的一部分接收到的行（事件）。   |
| `unsubscribe`                | 用于终止 `onEachLine` 块执行的函数。 |

## 请求属性

​	`request` 对象保存了关于 HTTP 请求的信息，可以在预请求脚本和响应处理脚本中使用。

|                                                              |                                                              |                                                              |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 属性                                                         | 在预请求脚本中使用的情况                                     | 在响应处理脚本中使用的情况                                   |
| `body`                                                       | 使用以下两种方法获取的请求 [body](https://www.jetbrains.com/help/go/exploring-http-syntax.html#provide-request-body)：`getRaw()`：以原始格式返回请求的 body。如果请求 body 包含变量，则显示变量名而不是其值。`tryGetSubstituted()`：返回已替换所有已知变量值的请求 body。 | 请求 [body](https://www.jetbrains.com/help/go/exploring-http-syntax.html#provide-request-body) 的字符串表示形式，例如 `client.log(request.body())`。 |
| `environment`                                                | 具有 `get(name)` 方法，用于检索由 `name` 标识的 [环境变量](https://www.jetbrains.com/help/go/exploring-http-syntax.html#environment-variables) 的值，如果不存在，则返回 `null`。 |                                                              |
| `headers`                                                    | 具有以下两个方法：`all`：返回包含当前请求的所有头部值的数组。`findByName(name)`：检索由 `name` 参数标识的头部的值。 |                                                              |
| 数组的每个元素都是请求头部，具有以下方法：`name`：头部名称，例如 `Content-Type`。`getRawValue`：以原始格式返回头部的值。如果头部包含变量，则显示变量名而不是其值。`tryGetSubstitutedValue()`：返回已替换所有已知变量值的头部。 | 数组的每个元素都是请求头部，具有以下方法：`name`：头部名称，例如 `Content-Type`。`value()`：头部的值，例如 `application/json`。 |                                                              |
| `url`                                                        | 使用以下两种方法获取的请求 URL：`getRaw()`：以原始格式返回请求的 URL。如果 URL 包含变量，则显示变量名而不是其值。`tryGetSubstituted()`：返回已替换所有已知变量值的请求 URL。 | 请求 URL 的字符串表示形式。                                  |
| `variables`                                                  | 具有 `get(name)` 方法，用于检索由 `name` 标识的[每请求变量](https://www.jetbrains.com/help/go/exploring-http-syntax.html#per_request_variables)的值，如果不存在，则返回 `null`。 |                                                              |

