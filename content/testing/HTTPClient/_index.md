+++
title = "HTTP 客户端"
weight = 50
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# HTTP Client﻿ - HTTP 客户端

https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html

Last modified: 03 May 2023

最后修改日期：2023年5月3日

​	使用 HTTP 客户端插件，您可以直接在 GoLand 的[代码编辑器](https://www.jetbrains.com/help/go/using-code-editor.html)中创建、编辑和执行 HTTP 请求。

![https://resources.jetbrains.com/help/img/idea/2023.1/basic_request.png](index_img/basic_request.animated.gif)

​	在以下两种主要情况下，您需要组合和运行 HTTP 请求： 

- 当您开发一个符合规范、可访问且正确响应的 RESTful Web 服务，并希望确保其按预期工作时。
- 当您开发一个与 RESTful Web 服务进行交互的应用程序时。在这种情况下，在开始开发之前，了解访问该服务和所需的输入数据是很有帮助的。在开发过程中，您还可以从应用程序外部调用此 Web 服务。当应用程序的输出结果与代码中未检测到逻辑错误时，您可以怀疑瓶颈是与 Web 服务的交互。因此，调用该 Web 服务可能有助于定位错误。

 请求存储在**.http**和**.rest**文件中，并标有![HTTP file icon](index_img/restClient.com.intellij.ws.rest.client.icons.http_requests_filetype.svg)图标。

​	对于 HTTP 文件，支持以下功能： 

- [代码高亮](https://www.jetbrains.com/help/go/configuring-colors-and-fonts.html)
- [代码自动完成](https://www.jetbrains.com/help/go/auto-completing-code.html)，支持主机、方法类型、头字段和通过 OpenAPI 定义的端点
- [代码折叠](https://www.jetbrains.com/help/go/working-with-source-code.html#code_folding)，支持请求、请求部分和响应处理脚本
- 根据您的 HTTP 请求代码样式进行[重新格式化](https://www.jetbrains.com/help/go/reformat-and-rearrange-code.html)请求。
- 请求头字段和文档标签的[内联文档](https://www.jetbrains.com/help/go/viewing-reference-information.html)
- 查看 HTTP 请求的[结构](https://www.jetbrains.com/help/go/viewing-structure-of-a-source-file.html)
- 在请求消息体中进行 Web 语言的[语言注入](https://www.jetbrains.com/help/go/using-language-injections.html)
- [Live templates](https://www.jetbrains.com/help/go/using-live-templates.html)

​	如果需要，在开始之前，您可以在设置对话框（Ctrl+Alt+S）的[HTTP 代理](https://www.jetbrains.com/help/go/settings-http-proxy.html)页面上[配置代理设置](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#configureProxy)。

## 创建 HTTP 请求文件

​	您可以从头文件或者物理文件中使用 HTTP 请求。每个文件可以包含多个请求，您可以根据需要创建多个文件。

​	[头文件](https://www.jetbrains.com/help/go/scratches.html)可用于在开发过程中测试 HTTP 请求。头文件不会存储在项目内部，因此 GoLand 可以修改它们并添加有关请求的其他信息。当从头文件执行 HTTP 请求时，响应输出文件的链接将添加到请求下方，并添加到[请求历史记录](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#requests_history)文件的顶部。

### 创建 HTTP 请求头文件

- 按下 Ctrl+Alt+Shift+Insert，并选择 HTTP 请求。

​	物理文件可用于记录、测试和验证 HTTP 请求。物理文件存储在项目内部，GoLand 不会对其进行修改。当从物理文件执行 HTTP 请求时，不会修改该文件。关于执行的请求的信息以及指向响应输出文件的链接将添加到[请求历史记录](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#requests_history)文件的顶部。

### 创建物理 HTTP 请求文件

- 在文件菜单中，指向新建，然后单击 HTTP 请求。

### 移动 HTTP 请求

​	您可以使用[移动](https://www.jetbrains.com/help/go/move-refactorings.html)重构（F6）将 HTTP 请求从头文件移动到物理文件，或者在物理文件之间移动。

1. 在编辑器中，将光标定位到要移动的请求上，并执行以下操作之一：

   - 从主菜单或上下文菜单中，选择Refactor | Move。
   - 按下 Alt+Enter 并选择移动 HTTP 请求[intention action](https://www.jetbrains.com/help/go/intention-actions.html)。
   - 按下 F6。

2. 在打开的移动 HTTP 请求对话框中，执行以下操作：

   1. 在路径字段中，选择列表中的一个现有**.http**文件，或单击![the Browse button](index_img/app.general.ellipsis.svg)以定位文件。

      您也可以手动输入文件的完整路径。如果指定的文件名不存在，将自动创建具有提供的名称的新文件。

   2. 在请求列表中，选择要移动的请求旁边的复选框。



## 组合 HTTP 请求

​	GoLand 使用编辑器格式的 HTTP 请求，提供了一种简单的方式来创建、执行和存储有关 HTTP 请求的信息。您可以在[创建的 HTTP 请求文件](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#creating-http-request-files)中直接输入它们，使用以下通用语法：

```
###
Method Request-URI HTTP-Version
Header-field: Header-value

Request-Body
```

​	在`###`分隔符之后，您可以输入以`#`或`//`开头的任何注释。


> ​	为了在运行/调试配置、全局搜索和运行命令等场景中快速找到您的请求，您可以为其[指定一个名称](https://www.jetbrains.com/help/go/exploring-http-syntax.html#http_request_names)。


> ​	您可以使用编辑器 | 颜色方案 | HTTP 请求设置来[自定义颜色和样式](https://www.jetbrains.com/help/go/configuring-colors-and-fonts.html#customize-color-scheme)，以突出显示请求的语法（名称、注释、参数、头部等）。

​	为了加快组合 HTTP 请求的速度，您可以：

- 点击工具栏的工具 | HTTP 客户端 | 在 HTTP 客户端中创建请求。如果编辑器中打开了请求文件，这将在打开的文件中添加请求模板。否则，将创建一个新的**.http**头文件。

- 单击请求编辑面板顶部的![App general add](index_img/app.general.add.svg)图标。在弹出菜单中，选择要添加的请求类型。

  ![Add an HTTP request](index_img/ps_add-http-request.png)

​	或者，使用[Live Templates](https://www.jetbrains.com/help/go/using-live-templates.html)。在编辑器中，可以按下 Ctrl+J 查看可用模板的列表。例如，gtr 将展开为一个简单的 GET 请求；mptr 将展开为一个`multipart/form-data` POST 请求。

![https://resources.jetbrains.com/help/img/idea/2023.1/expand_post_template.png](index_img/expand_post_template.animated.gif)

​	获取 HTTP 客户端功能的概述，您可以探索 HTTP 请求集合，这是一组精选的组合请求。

### 打开 HTTP 请求集合中的请求

1. 点击请求编辑面板顶部的示例快捷链接。

2. 在弹出菜单中，选择要打开的 HTTP 请求集合：

   ![Open HTTP Requests Collection popup](index_img/open-http-requests-collection.png)



> ​	有关语法和功能概述，请参阅[探索 HTTP 请求语法](https://www.jetbrains.com/help/go/exploring-http-syntax.html)，有关完整格式说明，请参阅[编辑器中的 HTTP 请求规范](https://github.com/JetBrains/http-request-in-editor-spec/blob/master/spec.md)。

### 转换 cURL 请求

​	如果您使用 [cURL](https://curl.haxx.se/) 请求，您可以在 cURL 请求和 HTTP 请求编辑器格式之间进行转换。

### 将 cURL 转换为 HTTP 请求

- 将 cURL 请求粘贴到一个 HTTP 请求文件中。GoLand 将把它转换为 HTTP 请求格式，并将原始的 cURL 请求注释起来，以供以后参考。

  ![cURL request converted to HTTP request on paste](index_img/http-client-convert-curl-on-paste.png)

- 或者，在 HTTP 请求编辑面板顶部点击 ![Convert cURL to HTTP request](index_img/app.toolbarDecorator.import.svg)，然后选择转换 cURL 为 HTTP 请求。

  在转换 cURL 为 HTTP 请求对话框中，键入或粘贴要转换的 cURL 请求。

  ![The Convert cURL to HTTP Request dialog](index_img/http-client-convert-curl-to-http-request.png)

​	考虑以下示例 cURL 请求：

```bash
curl 'http://httpbin.org/' -H 'Connection: keep-alive' -H 'Accept: text/html' -H 'Accept-Encoding: gzip, deflate' -H 'Accept-Language: en-US,en;q=0.9,es;q=0.8'
```

​	GoLand 将将其转换为以下格式：

```http
# curl 'http://httpbin.org/' -H 'Connection: keep-alive' -H 'Accept: text/html' -H 'Accept-Encoding: gzip, deflate' -H 'Accept-Language: en-US,en;q=0.9,es;q=0.8'
GET http://httpbin.org/
Connection: keep-alive
Accept: text/html
Accept-Encoding: gzip, deflate
Accept-Language: en-US,en;q=0.9,es;q=0.8

###
```

​	转换器支持以下 cURL 选项：

| 选项                                                         | 描述                                                       |
| ------------------------------------------------------------ | ---------------------------------------------------------- |
| [-X, --request](https://curl.haxx.se/docs/manpage.html#-X)   | 请求使用的方法。                                           |
| [-H, --header](https://curl.haxx.se/docs/manpage.html#-H)    | 包含在请求中的请求头。                                     |
| [-u, --user](https://curl.haxx.se/docs/manpage.html#-u)[--basic](https://curl.haxx.se/docs/manpage.html#--basic)[--digest](https://curl.haxx.se/docs/manpage.html#--digest) | 要提供给请求的用户凭证，以及要使用的授权方法。             |
| [-d, --data, --data-ascii](https://curl.haxx.se/docs/manpage.html#-d)[--data-binary](https://curl.haxx.se/docs/manpage.html#--data-binary)[--data-raw](https://curl.haxx.se/docs/manpage.html#--data-raw)[--data-urlencode](https://curl.haxx.se/docs/manpage.html#--data-urlencode) | 要在 POST 请求中发送的数据。                               |
| [-F, --form](https://curl.haxx.se/docs/manpage.html#-F)      | 要在 POST 请求中发送的 multipart/form-data 消息。          |
| [--url](https://curl.haxx.se/docs/manpage.html#--url)        | 要获取的 URL（主要用于在配置文件中指定 URL 时）。          |
| [-i, --include](https://curl.haxx.se/docs/manpage.html#-i)   | 定义是否在输出中包含 HTTP 响应头。                         |
| [-v, --verbose](https://curl.haxx.se/docs/manpage.html#-v)   | 启用详细操作模式。                                         |
| [-L, --location](https://curl.haxx.se/docs/manpage.html#-L)  | 在所请求的页面已移动到不同位置的情况下，启用重新发送请求。 |

### 将 HTTP 请求转换为

1. 将插入符放在要转换为 cURL 格式的 HTTP 请求上。

2. 单击 Alt+Enter，然后选择 Convert to cURL and copy to clipboard（转换为 cURL 并复制到剪贴板）。

   或者，您可以在 HTTP 请求编辑面板顶部单击 Convert 快捷链接，然后选择 Convert HTTP Request Under Caret to cURL and Copy（转换光标下的 HTTP 请求为 cURL 并复制）。


​	这将根据 HTTP 请求生成一个 cURL 请求，并将其复制到剪贴板。

### 使用上下文操作生成请求 

​	如果您的代码字符串文字或 JSON、YAML、TOML 和 Properties 文件中包含以 `http` 或 `https` 开头的 URL，您可以快速生成一个 HTTP 请求。

1. 单击一个 URL，然后按下 Alt+Enter。

2. 在打开的上下文菜单中，单击 Generate request in HTTP Client（在 HTTP 客户端中生成请求）。

   这将在 **generated-requests.http** 临时文件中创建一个新的 GET HTTP 请求，并指定的 URL。

   


![Generate request in HTTP Client](index_img/http_generate_from_context.png)

### 使用 OpenAPI 规范创建请求

​	在使用 OpenAPI 规范文件时，您可以创建指定端点的 HTTP 请求。

### 创建一个到端点的 HTTP 请求 

- 在 OpenAPI 规范文件中，单击编辑器侧沟槽中端点定义旁边的 ![the Open in HTTP Client button](index_img/swagger.icons.endpointGutter.svg)图标。
- 或者，打开 View | Tool Windows | Endpoints，右键单击一个端点，然后选择 Generate Request in HTTP Client（在 HTTP 客户端中生成请求）。

​	GoLand 将创建一个新的 HTTP 请求，并将其保存在 **generated-requests.http** [临时文件](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#creating-http-request-files)中。

### 重命名端点及其使用

​	使用 [重命名重构](https://www.jetbrains.com/help/go/rename-refactorings.html) 可以同时重命名已定义的端点及其在 HTTP 请求中的使用。 

1. 执行以下任一操作：
   - 在 OpenAPI 规范文件中，将插入符放在要重命名的端点定义上。
   - 在 HTTP 请求文件中，将插入符放在要重命名的 URL 路径片段上。
3. 从主菜单或上下文菜单中选择 Refactor | Rename（重构 | 重命名），或按 Shift+F6。
5. 在打开的重命名对话框中，指定新的端点名称。
7. 预览并应用更改。

​	GoLand 将重命名端点及其使用。

### 使用响应处理程序脚本

​	使用响应处理程序脚本，您可以以编程方式对收到的 HTTP 响应做出反应。通过使用这些脚本，您可以自动处理收到的数据，并根据您指定的条件进行验证。响应处理程序脚本作为请求的一部分提供，并在接收到响应后立即执行。要查看响应处理的示例，请打开带有授权或测试的请求集合。

​	您可以将响应处理程序脚本直接插入到请求中，也可以引用外部文件中的脚本。

### 将脚本插入请求中

- 要在请求中插入脚本，请在脚本前面添加 `>`，并用 `{% %}` 包裹起来：

  ```http
  GET host/api/test
  
  > {%
  // Response Handler Script
  ...
  %}
  ```

  

- 要从外部文件插入脚本，请在脚本前面添加 `>`：

  ```http
  GET host/api/test
  
  > scripts/my-script.js
  ```

  


​	响应处理程序脚本使用 JavaScript ECMAScript 6 编写，配有捆绑的 `HTTP Response Handler` 库提供编码辅助和文档支持。对于内联脚本，此功能会自动启用。对于外部脚本，您需要手动启用它。

### 启用响应处理程序脚本的 JavaScript 编码辅助

1. 在编辑器中打开脚本文件。
3. 在上下文菜单中，选择 Use JavaScript Library | HTTP Response Handler（使用 JavaScript 库 | HTTP 响应处理程序）。

​	`HTTP Response Handler` 库提供了两个对象，用于组成响应处理程序脚本： 

- `client` 对象存储会话元数据，可以在脚本内部进行修改。`client` 状态将保留，直到关闭 GoLand。在 `client.global` 中保存的每个变量作为 `{{variable_name}}` 可以在后续的 HTTP 请求中访问。
- `response` 包含接收到的响应的信息：内容类型、状态、响应正文等。

​	要在编辑器中打开 HTTP Response Handler 库，将插入符置于库对象上，并按 Ctrl+B。

​	响应处理程序脚本可以包括测试，使您可以将 HTTP 客户端用作测试框架。要创建测试，请调用 `client.test(testName, function)` 方法。在测试内部，您可以通过调用 `client.assert(condition, message)` 方法来断言条件，例如：

```javascript
GET https://httpbin.org/status/200

> {%
    client.test("Request executed successfully", function() {
        client.assert(response.status === 200, "Response status is not 200");
    });
%}
```



## 执行 HTTP 请求

1. 如果您要测试自己的 Web 服务，请确保其已部署并正在运行。
3. 如果您定义了[环境](https://www.jetbrains.com/help/go/exploring-http-syntax.html#environment-variables)，请选择要在请求的编辑器面板顶部的 Run with 列表中使用的环境。
5. 在沟槽中，单击请求旁边的 ![The Run button](index_img/app.actions.execute.svg)。

​	如果在一个 **.http** 文件中定义了多个 HTTP 请求，您可以按顺序运行它们。要执行此操作，请单击请求的编辑器面板顶部的 ![Run all HTTP requests](index_img/app.actions.runAll.svg)。

​	执行请求时，GoLand 会自动为其创建一个专用的临时 [HTTP 请求运行/调试配置](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#http-request-run-debug-configurations)。如有必要，您可以将其[保存为永久的运行/调试配置](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#save-temporary-http-request-run-debug-configuration)。

### 在浏览器中打开请求

​	您可以在设置对话框（Ctrl+Alt+S）的[Web 浏览器和预览](https://www.jetbrains.com/help/go/settings-tools-web-browsers.html)页面指定的浏览器中打开 HTTP 请求。 

- 按下 Alt+Enter 并选择打开 web 浏览器[意图操作（intention action）](https://www.jetbrains.com/help/go/intention-actions.html)。

### 使用 HTTP 请求运行/调试配置

​	当您从编辑器中[执行 HTTP 请求](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#execute_request_procedure)时，GoLand 会自动创建一个临时的运行/调试配置，其中包含请求参数。临时的运行/调试配置与永久的运行/调试配置的工作方式相同。您可以使用[运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configurations-dialog.html)对话框更改其设置，并可选择将其保存为永久配置。

### 修改 HTTP 请求运行/调试配置

1. 执行以下任一操作：
   - 在编辑器中，右键单击请求，在上下文菜单中选择 Modify Run Configuration。
   - 或者，从主菜单选择 Run | Edit Configurations，然后在 HTTP Request 列表中选择所需的运行/调试配置。
2. 更改所需的配置参数：
   - 在 Environment 列表中，选择将在请求中使用的环境（[environment](https://www.jetbrains.com/help/go/exploring-http-syntax.html#using_request_vars)）集定义的一组环境变量。
   - 在 File 字段中，提供到[HTTP 请求文件](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#creating-http-request-files)的路径。您可以手动输入路径并在键入时使用路径完成 Ctrl+Space，或单击 ![Open from disk](index_img/app.general.openDisk.svg)，然后在打开的对话框中选择所需的文件夹。
   - 如果请求文件包含多个请求，在 Request 列表中选择要执行的请求的名称。

### 保存临时的 HTTP 请求运行/调试配置

- 在运行/调试配置选择器中，选择 Save <configuration name>。
- 在运行/调试配置对话框中，选择配置并单击 ![the Save button](index_img/app.actions.menu-saveall.svg)。

### 使用运行/调试配置执行请求 

- 在运行/调试配置选择器中，选择所需的运行配置。然后，单击主工具栏上的 ![Run button](index_img/app.actions.execute.svg)或按 Shift+F10。
- 按下 Alt+Shift+F10，从列表中选择所需的运行配置，然后按 Enter。

## 查看来自 Web 服务的响应

​	当您执行 HTTP 请求时，GoLand 会自动将响应保存到 **.idea/httpRequests/** 目录下的单独文件中。您可以查看最近保存的 50 个响应，并使用[请求历史记录](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#requests_history)导航到相应的文件。如果请求是从 scratch 文件执行的，则在原始请求下方还会添加到其响应输出的链接：

![HTTP response](index_img/http_response_in_scratch.png)

### 查看接收到的响应

1. 切换到 [Services 工具窗口](https://www.jetbrains.com/help/go/services-tool-window.html)，该窗口在接收到响应后会自动打开。

3. 默认情况下，服务器响应以请求头中通过 [content-type](http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.17) 字段指定的格式显示。要将响应转换为其他格式，单击 ![Response view settings](index_img/app.general.inspectionsEye.svg)，然后选择 Text、JSON、XML 或 HTML。

   ![HTTP response in the Services tool window](index_img/idea_http-run-response.png)

​	如果响应包含二进制文件，该文件也会保存在 **.idea/httpRequests/** 目录下。如果响应是图像，则可以在 Services 工具窗口中预览它。

![HTTP response with an image](index_img/http_response_with_image.png)

​	如果您有[响应处理程序脚本](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#using-response-handler-scripts)，则作为脚本一部分执行的测试结果会显示在 Services 工具窗口的 Tests 选项卡中。您可以单击每个测试来快速导航到相应的响应处理程序脚本中的测试源代码。

![The Tests tab of the Services tool window](index_img/http-request-failed-tests.png)

​	如果您订阅了事件流，GoLand 会在 Services 工具窗口中显示事件。在此处，您还可以查看客户端-服务器连接的状态，并单击 ![Stop](index_img/app.actions.suspend.svg)终止它。根据内容类型（`text/event-stream` 或 `application/x-ndjson`），响应将格式化为纯文本或换行符分隔的 JSON。您可以编写响应处理程序脚本来[处理事件流的每一行](https://www.jetbrains.com/help/go/http-response-handling-examples.html#stream_scripting)。

![Server-sent events](index_img/http_client_json_event_stream.png)

​	当前不支持将[重定向（Redirecting）](https://www.jetbrains.com/help/go/exploring-http-syntax.html#response-redirect)流事件到文件。

### 在编辑器中打开响应文件

1. 将插入符置于要打开的响应链接处。
3. 从主菜单选择 View | Jump to Source，或按 Ctrl+B 或 F4

​	或者，您可以按 Ctrl+单击响应行：

### 在 scratch 文件中比较响应

​	当从 scratch 文件执行请求时，会在原始请求下方添加响应输出文件的链接。 

- 进行以下操作之一：

  - 将插入符置于响应文件的链接处。按下 Alt+Enter 并选择 `Compare with <response name>` 意图操作。

  - 在沟槽中单击 ![Compare responses](index_img/app.actions.diff.svg)并从列表中选择 `Compare with <response name>`：

    ![Compare responses in request history](index_img/ps_compare_responses_menu.png)


### 在请求历史记录中比较响应

​	当从实际文件执行请求时，响应输出的链接会添加到[请求历史记录](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#requests_history)中。 

1. 将插入符置于响应文件的链接处。从主菜单选择 View | Jump to Source，或按下 Ctrl+B 或 F4，在新的编辑器选项卡中打开此文件。
3. 从主菜单选择 View | Compare With，或按下 Ctrl+D。GoLand 将提示您从 **httpRequests** 文件夹中打开一个响应文件。
5. 选择要将当前文件与之比较的响应文件，然后单击打开。

​	两个响应文件将在[差异查看器（Differences viewer）](https://www.jetbrains.com/help/go/differences-viewer.html)中打开，以便比较它们的内容：

![Compare HTTP responses](index_img/compare_http_responses_diff.png)

## 查看请求历史记录

​	GoLand 自动将最近执行的 50 个请求保存到项目级别的 **http-requests-log.http** 文件中，该文件存储在 **.idea/httpRequests/** 目录下。通过请求历史记录，您可以快速导航到特定的响应，以及[重新发出任何请求](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#run_request)。如果从请求历史记录中重新发出请求，则其执行信息和响应输出的链接将添加到请求历史记录文件的顶部。


> ​	要防止将请求保存到请求历史记录中，在请求之前添加一行以 [@no-log](https://www.jetbrains.com/help/go/exploring-http-syntax.html#enable-disable-saving-request) 标记的注释行。这在请求包含某些敏感数据并且您不希望记录它时很有帮助。

### 打开请求历史记录

- 单击请求编辑面板顶部的 ![Show HTTP request history](index_img/app.vcs.history.svg)。
- 从主菜单选择 Tools | HTTP Client | Show HTTP Requests History。

### 将输出重定向到自定义文件或目录

- HTTP 客户端可以将输出重定向到自定义文件或目录。它支持两个操作符进行强制和软性重定向： 
  - `>>` 操作符总是创建一个新文件，如果已存在请求的文件名，则在文件名后添加 `-n` 后缀。
  - `>>!` 操作符如果文件已存在，则重写该文件。

## 管理 Cookie

​	通过响应接收到的 Cookie 会自动保存在专用的 **http-client.cookies** 文件中，该文件存储在 **.idea/httpRequests/** 目录下。可以保存的 Cookie 数量最多为 300 个。每个后续请求到与 Cookie 指定的域名和路径匹配的 URL 都会自动包含 Cookie 的名称和值，前提是尚未达到过期日期。

![the http-cookies file](index_img/ps_http_cookie.png)


> 您可以在请求之前添加一行以 [@no-cookie-jar](https://www.jetbrains.com/help/go/exploring-http-syntax.html#enable-disable-saving-cookies) 标记的注释行，以防止将接收到的 Cookie 保存到 Cookie 存储中。这在请求包含某些敏感数据并且您不希望记录它时很有帮助

​	如果要在 HTTP 请求中设置自定义 Cookie，可以使用 `Cookie` 头部。将 Cookie 输入为由分号分隔的 `name=value` 对列表，例如：

```http
GET http://localhost:80/api
Cookie: theme=dark; country=France
```



## gRPC 请求﻿


> ​	要使用 gRPC 请求，您需要安装并启用以下插件：[Protocol Buffers](https://plugins.jetbrains.com/plugin/14004-protocol-buffers) 和 [gRPC](https://plugins.jetbrains.com/plugin/16889-grpc)

​	HTTP 客户端支持 gRPC 请求。要使 HTTP 客户端将您的请求视为 gRPC 请求，请以 `GRPC` 关键字开始它们。

​	基于 `.proto` 文件，GoLand 提供了对 gRPC 的自动完成：所有已知的 gRPC 服务、特定服务器的一元和服务器流方法，以及请求正文中接受消息的字段。如果您的项目中没有 `.proto` 文件，如果服务器支持[gRPC 反射](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md)，仍然可以使用代码完成，该功能提供了关于可访问服务的信息。

![https://resources.jetbrains.com/help/img/idea/2023.1/http_client_supports_g_rpc_requests.png](index_img/http_client_supports_g_rpc_requests.animated.gif)

### 从 proto 文件生成 gRPC 请求

- 在 proto 文件中，单击 RPC 方法附近的![gRPC](index_img/grpc. icons.procedure.svg) Generate request in HTTP Client。

  ![https://resources.jetbrains.com/help/img/idea/2023.1/go_generate_a_g_rpc_request_from_proro_files.png](index_img/go_generate_a_g_rpc_request_from_proro_files.animated.gif)

### 从 Endpoints 工具窗口生成 gRPC 请求﻿

​	与 HTTP 请求一样，您还可以使用 Endpoints 工具窗口生成 gRPC 请求。 

1. 打开 Endpoints 工具窗口：View | Tool Windows | Endpoints。如果项目中定义了 gRPC 端点，您将看到它们。
3. 选择一个端点。这将在 HTTP 客户端选项卡中为其生成一个示例请求。
5. 完成请求并单击提交请求。您可能需要使用您自己的值替换默认的地址和端口。对于请求正文，请使用基于 proto 文件中的数据结构的代码完成。
7. 在 HTTP 客户端选项卡的较低部分预览响应。

![the HTTP Client tab](index_img/endpoints_grpc_request_response.png)

### 发送 gRPC 元数据﻿

- 在您的 `GRPC` 请求下面，使用以下语法输入 gRPC 元数据：`Metadata-key: Value`。

  例如：

  ```http
  GRPC localhost:8080
  X-Myhostname: Example.org
  ```

  



> ​	目前，HTTP 客户端中支持的可以执行的 RPC 类型为一元和服务器流。与普通的 HTTP 请求一样，请求正文和响应都是普通的 JSON 文件。

### 从 PROTO 文件导航到 Go 代码

- 您可以从 Go 代码中导航并访问消息、服务和方法的声明，以及从 PROTO 文件中导航并访问它们的 Go 实现。

  单击消息、服务或方法的声明旁边的导航到实现图标，或其实现。

  ![06221040](_index_img/06221040.gif)

  


## WebSocket 请求

​	HTTP 客户端支持 WebSocket 请求。要将请求视为 WebSocket 请求，请以 `WEBSOCKET` 关键字开始，并跟随服务器地址。请求的结构如下：

```javascript
WEBSOCKET ws://localhost:8080/websocket
Content-Type: application-json // Used for content highlighting only 仅用于内容高亮

// Request body, for example: 请求正文，例如：
{
  "message": "First message sent on connection"
}
===  // message separator 消息分隔符
{
  "message": "Second message" // will be sent right after the previous one 将在前一条消息之后立即发送
}
=== wait-for-server  // keyword used to wait for the server response 用于等待服务器响应的关键字
{
  "message": "Send this after the server response"
}
```




> ​	虽然 WebSocket 连接中不使用 `Content-Type` 头部，但您可以在 GoLand 的 WebSocket 请求中使用它来突出显示传输数据的语法。

为了加快组成 WebSocket 请求的速度，您可以： 

- 在 **.http** 文件的编辑器面板顶部点击 ![App general add](index_img/app.general.add.svg)，然后选择 WebSocket 请求。
- 在 **.http** 文件中输入 `wsr`，然后按 Enter 键应用 WebSocket 活动模板。

### 发送多个消息

- 使用 `===` 分隔符发送多个消息：

  ```json
  {
    "message": "First message sent on connection"
  }
  ===  // message separator 消息分隔符
  {
    "message": "Second message"
  }
  ===
  {
    "message": "Third message"
  }
  ```

  


### 在服务器响应后发送消息

- 在消息之前，输入 `=== wait-for-server`。

  这将使 HTTP 客户端在发送消息之前等待服务器响应。您可以通过重复 `=== wait-for-server` 行来等待多个响应。例如，以下消息将在 3 个服务器响应后发送：

  ```json
  === wait-for-server
  === wait-for-server
  === wait-for-server
  {
    "message": "This messages is sent after 3 server responses"
  }
  ```

  


### 交互式发送消息﻿

​	一旦建立连接，您就可以直接从服务工具窗口与服务器进行交互。您可以发送消息并查看每条新消息的服务器响应。 

1. 在服务工具窗口中，选择已打开的连接。
6. 在窗口下部的“要发送到 WebSocket 的消息”下面，输入消息内容。
7. 在其右侧，选择消息格式：纯文本、JSON、XML 或 HTML。
8. 按 Ctrl+Enter 键发送请求。

​	在窗口的上部，您将看到服务器的响应。

![The Services tool window](index_img/websocket_interactive.png)

## GraphQL﻿

​	GoLand 支持在 HTTP 请求正文中发送 GraphQL 操作。您可以通过 HTTP 或 WebSocket 发送它们。


> ​	要在请求正文中获得 GraphQL 语言支持（语法突出显示、快速导航到模式等），您可以安装并启用 [GraphQL](https://plugins.jetbrains.com/plugin/8097-graphql) 插件。

### 组合带有 GraphQL 查询的 HTTP 请求

1. 在 **.http** 文件中，输入 `GRAPHQL` 关键字，后跟服务器地址。

2. 在请求正文中，组合您的 GraphQL 操作（查询、变更或订阅），例如：

   ```http
   ### HTTP request with GraphQL query
   GRAPHQL http://localhost:8080/graphql
   
   query {
     toDos {
       title,
       completed,
       author {
         username
       }
     }
   }
   ```

   


​	为了加快组成带有 GraphQL 查询的 HTTP 请求的速度，您可以： 

- 在 **.http** 文件的编辑器面板顶部点击 ![App general add](index_img/app.general.add.svg)，然后选择 GraphQL 查询请求。
- 在 **.http** 文件中输入 `gqlr`，然后按 Enter 键应用 GraphQL 活动模板。



### 使用 GraphQL 变量

​	在 HTTP 请求正文中，如果您想将一些动态数据单独传递给查询字符串，可以使用 GraphQL 变量。

- 在查询部分之后，输入一个 JSON 变量字典：

  ```javascript
  query ($name: String!, $capital: String!) {
    country(name: $name, capital: $capital) {
      name
      capital
    }
  }
  
  {
    "name": "France",
    "capital": "Paris"
  }
  ```

  

  您还可以使用 [HTTP 客户端环境变量](https://www.jetbrains.com/help/go/exploring-http-syntax.html#using_request_vars) 作为 GraphQL 变量值。例如，在此 JSON 中，`"{{Author}}"` 是一个环境变量；它在运行时的值取决于您在发送请求时选择的环境：

  ```json
  {
    "author": "{{Author}}"
  }
  ```

  



> ​	您可以通过在请求正文中按下 Alt+Enter（显示上下文操作）并选择添加 GraphQL JSON 变量块来快速添加 GraphQL 查询的变量块。

## 配置代理设置 

1. 在设置对话框中（Ctrl+Alt+S），选择外观和行为下的系统设置，然后选择 HTTP 代理。
2. 在打开的 [HTTP 代理](https://www.jetbrains.com/help/go/settings-http-proxy.html) 对话框中，选择手动代理配置，并指定以下内容：
   - 在Host name和Port number字段中输入代理主机名和端口号。
   - 要启用授权，请选择Proxy authentication复选框，并在相应字段中输入用户名和密码。

## 设置客户端 SSL/TLS 证书 

​	如果 HTTP 服务器要求进行 SSL/TLS 身份验证以进行安全通信，则在发送 HTTPS 请求之前，您可能需要指定客户端证书。在 HTTP 客户端中，您可以使用 [private environment file](https://www.jetbrains.com/help/go/exploring-http-syntax.html#environment-variables) 设置客户端证书。

### 指定证书路径

1. 在 **.http** 文件中，选择Add Environment to Private File…选项。

2. 打开的 **http-client.private.env.json** 文件中，将 `SSLConfiguration` 对象添加到所需的环境中。在 `clientCertificate` 中输入您的客户端证书的路径。如果证书密钥存储在单独的文件中，请在 `clientCertificateKey` 中输入其路径。例如：

   ```json
   {
       "dev": {
           "MyVar": "SomeValue",
           "SSLConfiguration": {
               "clientCertificate": "cert.pem",
               "clientCertificateKey": "MyFolder/key.pem"
           }
       }
   }
   ```

   

   > ​	您可以指定绝对路径或相对于 **http-client.private.env.json** 文件的路径。如果环境文件存储在临时文件中，您还可以指定相对于项目根目录的路径。开始输入路径以获取代码完成弹出窗口。

   或者，您可以将 `clientCertificate` 和 `clientCertificateKey` 描述为对象，这样您可以除了路径之外还可以指定证书格式。例如：

   ```json
   {
       "dev": {
           "SSLConfiguration": {
               "clientCertificate": {
                   "path": "file.crt",
                   "format": "PEM"
               },
               "clientCertificateKey": {
                   "path": "file.key",
                   "format": "DER"
               }
           }
       }
   }
   ```

   



### 设置证书密码

​	如果在生成客户端证书时使用了密码短语，则您应该将其提供给 HTTP 客户端。

1. 在 **http-client.private.env.json** 文件中，将 `"hasCertificatePassphrase": true` 添加到 `SSLConfiguration` 对象，例如：

   ```json
   {
       "dev": {
           "SSLConfiguration": {
               "clientCertificate": "file.crt",
               "hasCertificatePassphrase": true
           }
       }
   }
   ```

   

3. 单击左侧导航栏的 ![App actions edit](index_img/app.actions.edit.svg)图标，或者将光标放置在 `hasCertificatePassphrase` 上，然后按下 Alt+Enter 并选择 Set value for 'Certificate passphrase'。

4. 在打开的窗口中，输入您的证书密码。



![HTTP Client Secured Value window](index_img/http_client_set_passphrase.png)

​	如果您不想现在输入密码，可以省略第二步。在这种情况下，当您执行 HTTPS 请求时，GoLand 将提示您输入密码。

### 禁用证书验证

​	出于开发目的，您可能会遇到使用自签名或过期证书的主机。如果您信任此主机，可以禁用对其证书的验证。

- 在 **http-client.private.env.json** 文件中，将 `verifyHostCertificate": false` 添加到 `SSLConfiguration` 对象。例如：

  ```json
  {
      "sslTest": {
          "SSLConfiguration": {
              "verifyHostCertificate": false
          }
      }
  }
  ```

  


​	如果您使用此环境运行请求，GoLand 将不会验证主机证书。