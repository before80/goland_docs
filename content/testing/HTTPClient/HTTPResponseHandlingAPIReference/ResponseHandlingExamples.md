+++
title = "响应处理示例"
weight = 40
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Response handling examples - 响应处理示例﻿

https://www.jetbrains.com/help/go/http-response-handling-examples.html

Last modified: 21 April 2023

最近修改日期：2023年4月21日

​	在本主题中，我们将介绍一些 HTTP 响应处理示例。要尝试示例，请探索 [请求集合](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#open-requests-collection) 中的 `auth-requests` 和 `test-responses` 请求集合。

## 检查响应头部、响应内容和内容类型

​	在此示例中，我们将创建几个测试来验证以下内容： 

- 请求成功执行，即响应状态为 200。
- 响应体中包含头部。
- 响应的内容类型为 `application/json`。

​	要创建一个测试，我们调用 [client](https://www.jetbrains.com/help/go/http-client-reference.html) 对象的 `test` 方法。在测试中，我们可以通过调用 `client` 对象的 `assert` 方法并引用 [response](https://www.jetbrains.com/help/go/http-response-reference.html) 对象的各种属性来断言特定条件。

```javascript
### Check response status, headers, and content-type 检查响应状态、头部和内容类型
GET https://httpbin.org/get

> {%
    client.test("Request executed successfully", function() {
        client.assert(response.status === 200, "Response status is not 200");
    });

    client.test("Headers option exists", function() {
        client.assert(response.body.hasOwnProperty("headers"), "Cannot find 'headers' option in response");
    });

    client.test("Response content-type is json", function() {
        var type = response.contentType.mimeType;
        client.assert(type === "application/json", "Expected 'application/json' but received '" + type + "'");
    });
%}
```



## 使用全局变量

​	在此示例中，我们将从接收到的响应中捕获一个值，并将其存储在[全局变量](https://www.jetbrains.com/help/go/http-client-reference.html#global-variables-storage-reference)中，然后可以在后续请求中使用该变量。

​	第一个请求涉及一个响应处理脚本，该脚本将来自接收到的响应体中的身份验证令牌保存到 `auth_token` 变量下的 [client.global](https://www.jetbrains.com/help/go/http-client-reference.html#global-variables-storage-reference) 中。为了实现这一点，我们使用 `client.global.set(VariableName, VariableValue)` 结构。作为 `VariableValue` 参数，我们使用服务器返回的响应体（在我们的示例中是 `httpbin.org`）中 `json.token` 字段的值。然后将该值分配给 `"auth_token"` 变量。

```shell
POST https://httpbin.org/post
Content-Type: application/json

{
    "token": "my-secret-token"
}

//Saving a variable
> {%
    client.global.set("auth_token", response.body.json.token);
%}
```




> ​	由于 [httpbin POST 实现](http://httpbin.org/#/HTTP_Methods/post_post)，我们使用 `response.body.json.token` 检索令牌。根据您正在交互的实际网络服务，响应结构可能会有所不同，您可能需要使用不同的构造方式，例如 `response.body.token`

​	请求执行后，可以通过 `{{auth_token}}` 在后续请求中以及通过 `client.global.get("auth_token")` 在响应处理脚本中访问 `auth_token` 变量。

```http
//Accessing a variable 访问变量
GET https://httpbin.org/headers
Authorization: Bearer {{auth_token}}
```



​	要从响应头部获取值，请使用 [headers](https://www.jetbrains.com/help/go/http-response-reference.html#headers-reference) 对象的 `valueOf` 方法。如果接收到具有相同名称的多个头部（对于 Set-Cookie 头部而言是常见情况），请改用 `valuesOf` 方法。这将返回所有响应头部值的数组。

```shell
POST https://httpbin.org/cookies

//Saving a cookie from the first Set-Cookie header 从第一个 Set-Cookie 头部中保存一个 cookie
> {%
    client.global.set("my_cookie", response.headers.valuesOf("Set-Cookie")[0]);
%}
```



## 处理事件流中的每一行

​	如果订阅了事件流，服务器将在有新数据可用时自动将事件发送到客户端。这些数据可以采用 Server-Sent Events 或分行 JSON（NDJSON）的形式。在 GoLand 中，您可以使用 HTTP 客户端的 [response.body.onEachLine](https://www.jetbrains.com/help/go/http-response-reference.html#linestreamresponse_reference) 方法，在事件流的每一行上调用一个函数。

​	假设您有一个服务器定期发送金价信息。在此示例中，我们将编写一个响应处理脚本，执行以下操作： 

4. 获取从服务器接收到的每个数据块（JSON 对象）并记录价格值。运行请求后，可以在“Services”工具窗口的“Response Handler”选项卡中查看记录的信息。
5. 当事件数量超过 10 时停止处理接收到的数据。请注意，这不会取消订阅事件流-只要 HTTP 连接打开，您将继续接收事件（请查看“Services”工具窗口的“Console”选项卡）。
6. 对获取到的数据块进行测试：如果价格小于 45，则测试失败。您可以在“Services”工具窗口的“Tests”选项卡中查看测试结果

```javascript
GET localhost/stocks/subscribe?symbol=GOLD

> {%
var updatesCount = 0;
response.body.onEachLine(
    (symbolUpdate, unsubscribe) => {
        updatesCount++;
        client.log(symbolUpdate.pricePresentation);
        if (updatesCount > 10) {
            unsubscribe();
            return;
        }

        client.test("Price test " + updatesCount, () => {
            client.assert(symbolUpdate.lastPrice >= 45, "Price must be >= 45");
            client.log(symbolUpdate.pricePresentation);
        });
    }
)
%}
```