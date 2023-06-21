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

In addition to the GoLand plugin, the HTTP Client is also available as a CLI tool. It allows you to run HTTP requests from a terminal, without the IDE, or include HTTP request testing in your CI workflow.

​	除了GoLand插件之外，HTTP Client还作为CLI工具提供。它允许您在终端中运行HTTP请求，无需使用IDE，或将HTTP请求测试包含在CI工作流中。



### 安装HTTP Client CLI - Install HTTP Client CLI﻿

You can get the HTTP Client CLI as a [Docker image](https://hub.docker.com/r/jetbrains/intellij-http-client) or as a ZIP archive.

​	您可以将HTTP Client CLI作为[Docker镜像](https://hub.docker.com/r/jetbrains/intellij-http-client)或ZIP归档文件获取。

- To get the HTTP Client CLI as a Docker image, pull the image:

- 要获取HTTP Client CLI的Docker镜像，请拉取镜像：

  `docker pull jetbrains/intellij-http-client`

- To get a ZIP archive, use cURL:

- 要获取ZIP归档文件，请使用cURL：

  `curl -f -L -o ijhttp.zip "https://jb.gg/ijhttp/latest"`

  > The ZIP distribution requires JDK 17 to be installed.
  >
  > ​	ZIP分发需要已安装JDK 17。

When the HTTP Client CLI is downloaded, you can run `./ijhttp` to get the list of available arguments. Run `./ijhttp --version` to check the version of the HTTP Client CLI.

​	当下载HTTP Client CLI后，您可以运行`./ijhttp`来获取可用参数的列表。运行`./ijhttp --version`来检查HTTP Client CLI的版本。

### 运行HTTP请求 Run HTTP request﻿

1. [Create an .http request file](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#composing-http-requests). Your file can contain multiple HTTP requests if you want to run all of them at once.

2. [创建一个`.http`请求文件](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#composing-http-requests)。如果要一次运行多个HTTP请求，您的文件可以包含多个请求。

   > Support for gRPC, WebSocket, and GraphQL requests will be added to HTTP Client CLI version 2023.2.
   >
   > ​	对于gRPC、WebSocket和GraphQL请求的支持将在HTTP Client CLI版本2023.2中添加。

3. Run HTTP Client CLI:

4. 运行HTTP Client CLI：

   {{< tabpane text=true >}}

   {{< tab header="On host machine" >}}

   Pass the file name to the `./ijhttp` command, for example:

   将文件名传递给`./ijhttp`命令，例如：

   ```
   ./ijhttp myrequest.http
   ```

   {{< /tab >}}

   {{< tab header="In Docker" >}}

   Run a container with the `.http` file:

   使用`.http`文件运行一个容器：

   ```
   docker run --rm -i -t -v $PWD:/workdir jetbrains/intellij-http-client run.http
   ```

   This command creates a bind mount between your current working directory on the host machine (`$PWD`) and the `workdir` directory in the container.

   此命令在主机机器上的当前工作目录（`$PWD`）与容器中的`workdir`目录之间创建了一个绑定挂载。

   > Note that `/workdir` is required in this command: All `.http` files will be run inside this directory in the container.
   >
   > ​	注意，在此命令中需要使用`/workdir`：所有的`.http`文件将在容器内的此目录中运行。

   {{< /tab >}}

   {{< /tabpane >}}

The command output contains information about the requests that have been sent, test statuses, and [environment variables](https://www.jetbrains.com/help/go/http-client-cli.html#environment-variables).

​	命令输出包含已发送的请求的信息、测试状态和[环境变量](https://www.jetbrains.com/help/go/http-client-cli.html#environment-variables)。

![https://resources.jetbrains.com/help/img/idea/2023.1/http_client_cli.png](HTTPClientCLI_img/http_client_cli.animated.gif)

### 更改日志级别 Change log level﻿

By default, the HTTP Client CLI outputs only the information about the requests that have been sent and the environment variables. You can change the log level by using the `-L` option.

​	默认情况下，HTTP Client CLI仅输出已发送的请求和环境变量的信息。您可以使用`-L`选项更改日志级别。 

- Use `-L HEADERS` to log information on the request and response headers.
- Or use `-L VERBOSE` to log information on the request and response headers and body.
- 使用`-L HEADERS`记录请求和响应头的信息。
- 或者使用`-L VERBOSE`记录请求和响应头以及正文的信息。

### 将响应保存到文件 Save response to file﻿

- If you want to save an HTTP response to a separate file, add `>>` or `>>!` in your `.http` file (see also [Redirect the response](https://www.jetbrains.com/help/go/exploring-http-syntax.html#response-redirect)). For example:

- 如果要将HTTP响应保存到单独的文件中，在`.http`文件中添加`>>`或`>>!`（请参阅[重定向响应](https://www.jetbrains.com/help/go/exploring-http-syntax.html#response-redirect)）。例如：

  ```none
  GET https://example.org/get
  
  >> myFolder/myFile.json
  ```

  

- If you want to save output from HTTP Client CLI, use standard terminal commands, such as `>`. For example:

- 如果要保存来自HTTP Client CLI的输出，请使用标准终端命令，如`>`。例如：

  `./ijhttp rest-api.http > yourFile.txt`

  The level of detail in the saved HTTP Client CLI output depends on the specified [log level](https://www.jetbrains.com/help/go/http-client-cli.html#change-log-level).
  
  保存的HTTP Client CLI输出中的详细程度取决于指定的[日志级别](https://www.jetbrains.com/help/go/http-client-cli.html#change-log-level)。

### 在Docker中解析localhost - Resolve localhost in Docker﻿

If you have a server running on your host machine, and you run HTTP requests in the Docker container, you may need to resolve `localhost` to the localhost of your host machine.

​	如果您的主机机器上运行着一个服务器，并且在Docker容器中运行HTTP请求，您可能需要将`localhost`解析为主机机器的本地主机。

- Use the `-D` option, for example:

- 使用`-D`选项，例如：

  `docker run --rm -i -t -v $PWD:/workdir jetbrains/intellij-http-client -D run.http`

  > If you use Docker-for-Linux 20.10.0+, you should also add the `--add-host host.docker.internal:host-gateway` option to the command:
  >
  > ​	如果使用的是Docker-for-Linux 20.10.0+，还应在命令中添加`--add-host host.docker.internal:host-gateway`选项：
  >
  > ```none
  >docker run --rm -i -t -v $PWD:/workdir --add-host host.docker.internal:host-gateway jetbrains/intellij-http-client -D run.http
  > ```
  > 
  > 

This way, requests intended for `localhost` will be sent to the localhost of your host machine.

​	这样，针对`localhost`的请求将发送到主机机器的本地主机。

### 环境变量 Environment variables﻿

Just like in the GoLand HTTP Client, you can use [environment variables](https://www.jetbrains.com/help/go/exploring-http-syntax.html#using_request_vars) in your HTTP requests. You use variables from HTTP environment files, or you can pass variable values directly in the CLI command.

​	就像在GoLand HTTP Client中一样，您可以在HTTP请求中使用[环境变量](https://www.jetbrains.com/help/go/exploring-http-syntax.html#using_request_vars)。您可以使用来自HTTP环境文件的变量，或者可以直接在CLI命令中传递变量值。

### 使用公共环境变量 Use public environment variables﻿

- Use the `--env-file` option to specify a path to the variable file and `--env` to specify the name of an environment. For example:

- 使用`--env-file`选项指定变量文件的路径，使用`--env`指定环境的名称。例如：

  `./ijhttp --env-file http-client.env.json --env dev rest-api.http`

- Alternatively, pass the variable value in the `-V` option. If you want to pass multiple variables, repeat the `-V` option:

- 或者，通过`-V`选项传递变量值。如果要传递多个变量，请重复`-V`选项：

  `ijhttp -V host=localhost:8080 -V planet=tatooine rest-api.http`

You can combine both options:

​	您可以组合两个选项：

```
./ijhttp --env-file http-client.env.json --env dev -V host=localhost:8080 rest-api.http
```

### 使用私有环境变量 Use private environment variables﻿

- Use the `--private-env-file` option to specify a path to the variable file and `--env` to specify the name of an environment. For example:

- 使用`--private-env-file`选项指定变量文件的路径，使用`--env`指定环境的名称。例如：

  `./ijhttp --private-env-file http-client.private.env.json --env dev rest-api.http`

- You can also pass the variable value in the `-P` option. If you want to pass multiple variables, repeat the `-P` option:

- 您还可以通过`-P`选项传递变量值。如果要传递多个变量，请重复`-P`选项：

  `ijhttp -P password=mypassword123 -P user=johndoe rest-api.http`

You can combine both options:

​	您可以组合两个选项：

```
./ijhttp --private-env-file http-client.private.env.json --env dev -P password=mypassword123 rest-api.http
```

### 测试请求 Test requests﻿

Just like in the HTTP Client plugin, your `.http` file may contain a [response handler script](https://www.jetbrains.com/help/go/exploring-http-syntax.html#response-handling) written in JavaScript ES6. You can use it to test HTTP requests with the [client.assert](https://www.jetbrains.com/help/go/http-client-reference.html) method.

​	就像在HTTP Client插件中一样，您的`.http`文件可以包含用JavaScript ES6编写的[响应处理程序脚本](https://www.jetbrains.com/help/go/exploring-http-syntax.html#response-handling)。您可以使用它来使用[client.assert](https://www.jetbrains.com/help/go/http-client-reference.html)方法测试HTTP请求。

### 使用响应处理程序脚本 Use response handler script﻿

- In your `.http` file, skip one line from the request and write your response handler script enclosed in `> {% ... %}`. For example:

- 在您的`.http`文件中，从请求中跳过一行，并在`> {% ... %}`中编写您的响应处理程序脚本。例如：

  ```javascript
  GET https://httpbin.org/get
  
  > {%
      client.test("Test status code", function() {
          client.assert(response.status === 200, "Response status is not 200");
      });
  %}
  ```

  

  > Use GoLand to get syntax highlighting and completion for the response handler script.
  >
  > ​	使用GoLand以获取响应处理程序脚本的语法高亮和自动完成。

You can also include a test from a separate file. The path to the file can be either absolute or relative to your `.http` file:

​	您还可以包含来自单独文件的测试。文件的路径可以是绝对路径，也可以是相对于您的`.http`文件的路径：

```none
GET https://httpbin.org/get

> /path/to/responseHandler.js
```



### 以JUnit XML格式保存测试报告 Save test report in JUnit XML format﻿

The HTTP Client can provide output in the JUnit XML format.

​	HTTP Client可以以JUnit XML格式提供输出。

- Add the `--report` argument to the `ijhttp` command, for example:

- 将`--report`参数添加到`ijhttp`命令中，例如：

  `./ijhttp test.http --report`

The HTTP Client CLI saves the report in the **report.xml** file under the **reports** directory.

​	HTTP Client CLI将报告保存在**reports**目录下的**report.xml**文件中。