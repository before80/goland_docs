+++
title = "HTTP 响应处理 API 参考"
weight = 10
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# HTTP Response handling API reference﻿ - HTTP 响应处理 API 参考

https://www.jetbrains.com/help/go/http-response-handling-api-reference.html

Last modified: 21 April 2023

最近修改日期：2023年4月21日

HTTP Response handler scripts are written in JavaScript ES6, with coding assistance and documentation handled by the bundled `HTTP Response Handler` library. The library exposes two objects to be used for composing response handler scripts:

​	HTTP 响应处理脚本是使用 JavaScript ES6 编写的，其中的编码辅助和文档由捆绑的 "HTTP 响应处理器" 库处理。该库提供了两个对象，用于编写响应处理脚本： 

- [client](https://www.jetbrains.com/help/go/http-client-reference.html) stores the session metadata, which can be modified inside the script. The `client`'s state is preserved until you close GoLand.
- [response](https://www.jetbrains.com/help/go/http-response-reference.html) holds information about the received response: its content type, status, response body, and so on.
- [client](https://www.jetbrains.com/help/go/http-client-reference.html) 存储会话元数据，可以在脚本内部进行修改。`client` 的状态会保留，直到关闭 GoLand。
- [response](https://www.jetbrains.com/help/go/http-response-reference.html) 包含接收到的响应的信息：内容类型、状态、响应主体等。