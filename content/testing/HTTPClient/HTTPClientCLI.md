+++
title = "HTTP Client CLI"
weight = 30
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# HTTP Client CLI﻿

https://www.jetbrains.com/help/go/http-client-cli.html#test-requests

Last modified: 21 April 2023

最后修改日期：2023年4月21日

​	除了GoLand插件之外，HTTP Client还作为CLI工具提供。它允许您在终端中运行HTTP请求，无需使用IDE，或将HTTP请求测试包含在CI工作流中。



### 安装HTTP Client CLI 

​	您可以将HTTP Client CLI作为[Docker镜像](https://hub.docker.com/r/jetbrains/intellij-http-client)或ZIP归档文件获取。

- 要获取HTTP Client CLI的Docker镜像，请拉取镜像：

  `docker pull jetbrains/intellij-http-client`

- 要获取ZIP归档文件，请使用cURL：

  `curl -f -L -o ijhttp.zip "https://jb.gg/ijhttp/latest"`

  > ​	ZIP分发需要已安装JDK 17。


​	当下载HTTP Client CLI后，您可以运行`./ijhttp`来获取可用参数的列表。运行`./ijhttp --version`来检查HTTP Client CLI的版本。

### 运行HTTP请求

1. [创建一个`.http`请求文件](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#composing-http-requests)。如果要一次运行多个HTTP请求，您的文件可以包含多个请求。

   > ​	对于gRPC、WebSocket和GraphQL请求的支持将在HTTP Client CLI版本2023.2中添加。

2. 运行HTTP Client CLI：

   {{< tabpane text=true >}}

   {{< tab header="On host machine" >}}

   将文件名传递给`./ijhttp`命令，例如：

   ```
   ./ijhttp myrequest.http
   ```

   {{< /tab >}}

   {{< tab header="In Docker" >}}

   使用`.http`文件运行一个容器：

   ```
   docker run --rm -i -t -v $PWD:/workdir jetbrains/intellij-http-client run.http
   ```

   此命令在主机机器上的当前工作目录（`$PWD`）与容器中的`workdir`目录之间创建了一个绑定挂载。

   > ​	注意，在此命令中需要使用`/workdir`：所有的`.http`文件将在容器内的此目录中运行。

   {{< /tab >}}

   {{< /tabpane >}}


​	命令输出包含已发送的请求的信息、测试状态和[环境变量](https://www.jetbrains.com/help/go/http-client-cli.html#environment-variables)。

![https://resources.jetbrains.com/help/img/idea/2023.1/http_client_cli.png](HTTPClientCLI_img/http_client_cli.animated.gif)

### 更改日志级别

​	默认情况下，HTTP Client CLI仅输出已发送的请求和环境变量的信息。您可以使用`-L`选项更改日志级别。 

- 使用`-L HEADERS`记录请求和响应头的信息。
- 或者使用`-L VERBOSE`记录请求和响应头以及正文的信息。

### 将响应保存到文件﻿

- 如果要将HTTP响应保存到单独的文件中，在`.http`文件中添加`>>`或`>>!`（请参阅[重定向响应](https://www.jetbrains.com/help/go/exploring-http-syntax.html#response-redirect)）。例如：

  ```none
  GET https://example.org/get
  
  >> myFolder/myFile.json
  ```

  

- 如果要保存来自HTTP Client CLI的输出，请使用标准终端命令，如`>`。例如：

  `./ijhttp rest-api.http > yourFile.txt`

  保存的HTTP Client CLI输出中的详细程度取决于指定的[日志级别](https://www.jetbrains.com/help/go/http-client-cli.html#change-log-level)。


### 在Docker中解析localhost

​	如果您的主机机器上运行着一个服务器，并且在Docker容器中运行HTTP请求，您可能需要将`localhost`解析为主机机器的本地主机。

- 使用`-D`选项，例如：

  `docker run --rm -i -t -v $PWD:/workdir jetbrains/intellij-http-client -D run.http`

  > ​	如果使用的是Docker-for-Linux 20.10.0+，还应在命令中添加`--add-host host.docker.internal:host-gateway`选项：
  >
  > ```none
  >docker run --rm -i -t -v $PWD:/workdir --add-host host.docker.internal:host-gateway jetbrains/intellij-http-client -D run.http
  > ```
  >
  > 


This way, requests intended for `localhost` will be本地主机。

### 环境变量

​	就像在GoLand HTTP Client中一样，您可以在HTTP请求中使用[环境变量](https://www.jetbrains.com/help/go/exploring-http-syntax.html#using_request_vars)。您可以使用来自HTTP环境文件的变量，或者可以直接在CLI命令中传递变量值。

### 使用公共环境变量

- 使用`--env-file`选项指定变量文件的路径，使用`--env`指定环境的名称。例如：

  `./ijhttp --env-file http-client.env.json --env dev rest-api.http`

- 或者，通过`-V`选项传递变量值。如果要传递多个变量，请重复`-V`选项：

  `ijhttp -V host=localhost:8080 -V planet=tatooine rest-api.http`


​	您可以组合两个选项：

```
./ijhttp --env-file http-client.env.json --env dev -V host=localhost:8080 rest-api.http
```

### 使用私有环境变量

- 使用`--private-env-file`选项指定变量文件的路径，使用`--env`指定环境的名称。例如：

  `./ijhttp --private-env-file http-client.private.env.json --env dev rest-api.http`

- 您还可以通过`-P`选项传递变量值。如果要传递多个变量，请重复`-P`选项：

  `ijhttp -P password=mypassword123 -P user=johndoe rest-api.http`


​	您可以组合两个选项：

```
./ijhttp --private-env-file http-client.private.env.json --env dev -P password=mypassword123 rest-api.http
```

### 测试请求

​	就像在HTTP Client插件中一样，您的`.http`文件可以包含用JavaScript ES6编写的[响应处理程序脚本](https://www.jetbrains.com/help/go/exploring-http-syntax.html#response-handling)。您可以使用它来使用[client.assert](https://www.jetbrains.com/help/go/http-client-reference.html)方法测试HTTP请求。

### 使用响应处理程序脚本

- 在您的`.http`文件中，从请求中跳过一行，并在`> {% ... %}`中编写您的响应处理程序脚本。例如：

  ```javascript
  GET https://httpbin.org/get
  
  > {%
      client.test("Test status code", function() {
          client.assert(response.status === 200, "Response status is not 200");
      });
  %}
  ```

  

  > ​	使用GoLand以获取响应处理程序脚本的语法高亮和自动完成。


​	您还可以包含来自单独文件的测试。文件的路径可以是绝对路径，也可以是相对于您的`.http`文件的路径：

```none
GET https://httpbin.org/get

> /path/to/responseHandler.js
```



### 以JUnit XML格式保存测试报告﻿

​	HTTP Client可以以JUnit XML格式提供输出。

- 将`--report`参数添加到`ijhttp`命令中，例如：

  `./ijhttp test.http --report`


​	HTTP Client CLI将报告保存在**reports**目录下的**report.xml**文件中。