+++
title = "Exploring the HTTP request syntax"
weight = 10
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Exploring the HTTP request syntax﻿

https://www.jetbrains.com/help/go/exploring-http-syntax.html#response-redirect

Last modified: 21 April 2023

This section describes the HTTP request format. For details on sending HTTP requests and viewing HTTP responses, see [HTTP Client](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html).

To compose an HTTP request in the GoLand code editor, use the following general syntax:

```http
Method Request-URI HTTP-Version
Header-field: Header-value

Request-Body
```



### Use comments in HTTP requests﻿

- Within a request, start any line with `//` or `#` to make it a comment line.

  ```shell
  // A basic request
  GET http://example.com/a/
  ```

  

### Set names for HTTP requests﻿

To quickly find your request in [run/debug configurations](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#http-request-run-debug-configurations), [Search Everywhere](https://www.jetbrains.com/help/go/searching-everywhere.html), and [Run Anything](https://www.jetbrains.com/help/go/running-anything.html#send_http_requests), you can give it a name.

- Type a name above the request next to `###`, `# @name`, or `# @name =`.

![Enter the HTTP request name](ExploringTheHTTPRequestSyntax_img/http_request_name.png)

If a request does not have a name, GoLand will use its position in the request file, such as `#1`, as the request name. If a request file contains multiple requests with the same name, GoLand will append the request position number to each of the names. This will make each request name unique so that you can easily find the needed one in the Services tool window, run/debug configurations, and so on.

![HTTP requests in Services tool window](ExploringTheHTTPRequestSyntax_img/http_request_same_names.png)

### Use short form for GET requests﻿

- For GET requests, you can omit the request method and only specify the URI.

  ```shell
  // A basic request
  http://example.com/a/
  ```

  

### Compose several requests in a single file﻿

1. Mark the end of a request by typing the `###` separator below it.

   ```shell
   // A basic request
   http://example.com/a/
   
   ###
   ```

   

2. Compose another request below the separator.

   ```shell
   // A basic request
   http://example.com/a/
   
   ###
   
   // A second request using the GET method
   http://example.com:8080/api/html/get?id=123&value=content
   ```

   

### Break long requests into several lines﻿

- Indent all query string lines but the first one.

  ```http
  // Using line breaks with indent
  GET http://example.com:8080
      /api
      /html
      /get
      ?id=123
      &value=content
  ```

  

  > ### 
  >
  > 
  >
  > The indent size for the URL parts is configured in Settings | Editor | Code Style | HTTP Request | Tabs and Indents | URL parts indent.

- If the URL is too long because of the query string, you can use the dedicated context action to put each query parameter on a new line. Place the caret on the query string part, press Alt+Enter, and select Put query parameters on separate lines.

  #### Before

  ```http
  GET http://example.com:8080/api/get/html?firstname=John&lastname=Doe&planet=Tatooine&town=Freetown
  ```

  

  #### After

  ```http
  GET http://example.com:8080/api/get/html?
      firstname=John&
      lastname=Doe&
      planet=Tatooine&
      town=Freetown
  ```

  

  > ### 
  >
  > 
  >
  > You can enforce the consistent wrapping of query parameters using the HTTP Client code style in Settings | Editor | Code Style | HTTP Request | Wrapping and Braces | Query parameters wrap.

### Access a web service with authentication﻿

- Depending on the web service you are accessing, provide the [basic](https://en.wikipedia.org/wiki/Basic_access_authentication) or [digest](https://en.wikipedia.org/wiki/Digest_access_authentication) Authorization header.

  ```http
  // Basic authentication
  GET http://example.com
  Authorization: Basic username password
  
  ###
  
  // Digest authentication
  GET http://example.com
  Authorization: Digest username password
  ```

  


> Similarly to other HTTP request elements, the provided `username` and `password` can be parameterized by means of [environment variables](https://www.jetbrains.com/help/go/exploring-http-syntax.html#using_request_vars).

### Provide the request message body﻿

Inside the request, prepend the request body with a blank line and do one of the following:

- Type the request body in place:

  ```shell
  // The request body is provided in place
  POST http://example.com:8080/api/html/post HTTP/1.1
  Content-Type: application/json
  Cookie: key=first-value
  
  { "key" : "value", "list": [1, 2, 3] }
  ```

  

  If you set the Content-Type header field value to one of the languages supported by GoLand, then the corresponding language fragment will be [auto-injected](https://www.jetbrains.com/help/go/using-language-injections.html) into the HTTP request message body. If Content-Type is not specified, you can inject a language fragment manually.

- To read the request body from a file, type the `<` symbol followed by the path to the file.

  ```shell
  // The request body is read from a file
  POST http://example.com:8080/api/html/post
  Content-Type: application/json
  
  < ./input.json
  ```

  

### Use multipart/form-data content type﻿

- Set the request's Content-Type to multipart/form-data. To send a file as part of the multipart/form-data message, include the `filename` parameter in the Content-Disposition header.

  ```shell
  POST http://example.com/api/upload HTTP/1.1
  Content-Type: multipart/form-data; boundary=boundary
  
  --boundary
  Content-Disposition: form-data; name="first"; filename="input.txt"
  
  // The 'input.txt' file will be uploaded
  < ./input.txt
  
  --boundary
  Content-Disposition: form-data; name="second"; filename="input-second.txt"
  
  // A temporary 'input-second.txt' file with the 'Text' content will be created and uploaded
  Text
  --boundary
  Content-Disposition: form-data; name="third";
  
  // The 'input.txt' file contents will be sent as plain text.
  < ./input.txt --boundary--
  ```

  

  > ### 
  >
  > 
  >
  > To speed up creating a multipart/form-data request, use the mptr [live template](https://www.jetbrains.com/help/go/using-live-templates.html).

### Disable following redirects﻿

When an HTTP request is redirected (a 3xx status code is received), the redirected page response is returned. In the Services tool window, you can view the redirected page response as well as all redirections that happened during the request.

You may want to disable following redirects. In this case, the actual redirect response header (such as 301 or 302) is returned.

- Before the request, add a comment line with the `@no-redirect` tag.

  ```shell
  // @no-redirect
  example.com/status/301
  ```

  

If you already have a redirected request, you can click Disable next to the `Redirections` list in the Services tool window. This will add the `@no-redirect` tag to the initial request.

![HTTP response with redirections](ExploringTheHTTPRequestSyntax_img/http_response_redirect.png)

### Disable saving requests to requests history﻿

If necessary, you can prevent saving a request to the [requests history](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#requests_history). This can be helpful in case a request contains some sensitive data, and you don't want to log it.

- Before the request, add a comment line with the `@no-log` tag.

  ```http
  // @no-log
  GET example.com/api
  ```

  

### Disable saving received cookies to the cookies jar﻿

If necessary, you can prevent saving the received cookie [to the cookies jar](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#manage_cookies). This way you will avoid removing the unwanted cookies from the **http-client.cookies** file manually.

- Before the request, add a comment line with the `@no-cookie-jar` tag.

  ```http
  // @no-cookie-jar
  GET example.com/api
  ```

  

## Use variables﻿

When composing an HTTP request, you can parametrize its elements by using variables. A variable can hold the values for the request's host, port, and path, query parameter or value, header value, or arbitrary values used inside the request body or in an external file.

### Provide a variable inside the request﻿

- Enclose the variable in double curly braces as `{{variable}}`.

The variable's name may only contain letters, digits, the underscore symbols `_`, or the hyphen symbols `-`. The variables' values can be any of the following:

- Provided explicitly per environment by means of the [environment variables](https://www.jetbrains.com/help/go/exploring-http-syntax.html#environment-variables)
- Generated dynamically by means of the predefined [dynamic variables](https://www.jetbrains.com/help/go/exploring-http-syntax.html#dynamic-variables)
- Defined programmatically in [response handler scripts](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#using-response-handler-scripts) by means of the `client.global.set` method or [right before the request](https://www.jetbrains.com/help/go/exploring-http-syntax.html#per_request_variables) by means of the `request.variables.set` method.

### Environment variables﻿

Environment variables let you store a set of environment definitions inside your project. For example, instead of providing a hostname in your request explicitly, you can create the `{{host}}` variable in different environments: a local hostname in the development environment and a public hostname in the production environment. You can then use the Run with list on the top of the current .http file editor to select an environment:

- No Environment: if this option is selected, no environment will be used when you run requests in the current file. Select it if your request does not contain any variables.
- Environment name (such as production or development): the selected environment will be used for all requests in the current file, and you won't need to select it when you click ![The Run button](ExploringTheHTTPRequestSyntax_img/app.actions.execute.svg). This can be helpful if you want to run multiple requests with the same environment and don't want to select it each time you run a request.
- <Select Environment Before Run>: with this option selected, you'll have to choose an environment each time you click ![The Run button](ExploringTheHTTPRequestSyntax_img/app.actions.execute.svg). This can be convenient if you often switch environments and want to explicitly select them for each run to make sure you execute requests with the needed environments.

![Run request: select environment](ExploringTheHTTPRequestSyntax_img/run_request_in_env.png)

The selected environment will be used as the default one when [Viewing a structure](https://www.jetbrains.com/help/go/viewing-structure-of-a-source-file.html) of the request, [opening the request in the browser](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#open_in_browser), [executing the request](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#execute_request_procedure), and [creating a run/debug configuration](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#http-request-run-debug-configurations) for it.

### Define environment variables﻿

Environment variables are defined in the environment files.

1. On top of the request's editor panel, in the Run with list, select where you want to add an environment:

   - Select Add Environment to Public File… if you want the environment to be public. This will add the environment to the **http-client.env.json** file. This file can contain common variables such as host name, port, or query parameters, and is meant to be distributed together with your project.
   - Select Add Environment to Private File… if you want the environment to be private. This will add the environment to the **http-client.private.env.json** file. This file might include passwords, tokens, certificates, and other sensitive information. The values of variables that are specified in the **http-client.private.env.json** file override the values in the public environment file.

   > ### 
   >
   > 
   >
   > If necessary, you can create these files manually.

2. Populate the created files with the desired variables.

   The following sample **http-client.env.json** environment file defines two environments: development and production. The additional **http-client.private.env.json** file holds the sensitive authorization data.

   

   http-client.env.json

   http-client.private.env.json

   

   

   ```json
   {
       "development": {
           "host": "localhost",
           "id-value": 12345,
           "username": "",
           "password": "",
           "my-var": "my-dev-value"
       },
   
       "production": {
           "host": "example.com",
           "id-value": 6789,
           "username": "",
           "password": "",
           "my-var": "my-prod-value"
       }
   }
   ```

   

   The example HTTP request is as follows:

   ```http
   GET http://{{host}}/api/json/get?id={{id-value}}
   Authorization: Basic {{username}} {{password}}
   Content-Type: application/json
   
   {
       "key": "{{my-var}}"
   }
   ```

   

   Before you execute the request, GoLand lets you choose an execution environment using the Run with list on top of the request's editor panel.

   Depending on your choice, the resulting request will be one of the following:

   

   development

   production

   

   

   ```http
   GET http://localhost/api/json/get?id=12345
   Authorization: Basic dev-user dev-password
   Content-Type: application/json
   
   {
       "key": "my-dev-value"
   }
   ```

   

If a variable is unresolved when executing a request, GoLand displays a notification letting you quickly create, update, or choose a different execution environment.

![Unresolved Variable in HTTP request notification](ExploringTheHTTPRequestSyntax_img/ps_http_client_unresolved_var.png)


> If you use Git in IDEA, the **http-client.private.env.json** file is not tracked by Git. However, it is not added to the **.gitignore** file. If you commit your changes using third-party tools or via a terminal, you may need to manually add **http-client.private.env.json** to **.gitignore** to avoid sharing confidential information: Right-click the file and select Git | Add to .gitignore.

### Per-request variables﻿

You can use the `request.variables.set(variableName, variableValue)` method to set values of variables used in HTTP requests. Write it in a pre-request script wrapped in `{% ... %}` above your HTTP request. For example:

```http
< {%
    request.variables.set("firstname", "John")
%}
GET http://example.org/{{firstname}}
```



Variables defined in a pre-request script are available only within a single request that follows the script.

To quickly insert the variable, use the Initialize variable context action:

![https://resources.jetbrains.com/help/img/idea/2023.1/http_create_pre_request_variable.png](ExploringTheHTTPRequestSyntax_img/http_create_pre_request_variable.animated.gif)

In pre-request scripts, you can also use [HTTP Client Crypto API](https://www.jetbrains.com/help/go/http-client-crypto-api-reference.html) to generate HTTP signatures based on cryptographic hash functions, such as SHA-1, SHA-256, SHA-512, MD5, and pass them as variable to your requests. For example:

```http
< {%
    const signature = crypto.hmac.sha256()
        .withTextSecret(request.environment.get("secret")) // get variable from http-client.private.env.json
        .updateWithText(request.body.tryGetSubstituted())
        .digest().toHex();
    request.variables.set("signature", signature)

    const hash = crypto.sha256()
        .updateWithText(request.body.tryGetSubstituted())
        .digest().toHex();
    request.variables.set("hash", hash)
%}
POST https://httpbin.org/post
X-My-Signature: {{signature}}
X-My-Hash: {{hash}}
Content-Type: application/json
```



### Dynamic variables﻿

Dynamic variables generate a value each time you run a request. Their names start with `$`:

- `$uuid` or `$random.uuid`: generates a universally unique identifier (UUID-v4)
- `$timestamp`: generates the current UNIX timestamp
- `$isoTimestamp`: generates the current timestamp in ISO-8601 format for the UTC timezone.
- `$randomInt`: generates a random integer between 0 and 1000.
- `$random.integer(from, to)`: generates a random integer between `from` (inclusive) and `to` (exclusive), for example random.integer(100, 500). If you provide no parameters, it generates a random integer between 0 and 1000.
- `$random.float(from, to)`: generates a random floating point number between `from` (inclusive) and `to` (exclusive), for example random.float(10.5, 20.3). If you provide no parameters, it generates a random float between 0 and 1000.
- `$random.alphabetic(length)`: generates a sequence of uppercase and lowercase letters of length `length` (must be greater than 0).
- `$random.alphanumeric(length)`: generates a sequence of uppercase and lowercase letters, digits, and underscores of length `length` (must be greater than 0).
- `$random.hexadecimal(length)`: generates a random hexadecimal string of length `length` (must be greater than 0).
- `$random.email`: generates a random email address.
- `$exampleServer`: is replaced with the GoLand built-in web server, which can be accessed using HTTP Client only. The variable is used in GraphQL and WebSocket [examples](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#open-requests-collection).

For example:

```http
GET http://localhost/api/get?id={{$uuid}}
```



## Handle the response﻿

You can handle the response using JavaScript. Type the `>` character after the request and specify the path and name of the JavaScript file or put the response handler script code wrapped in `{% ... %}`.

```http
GET https://httpbin.org/get

> /path/to/responseHandler.js
```



```http
GET https://httpbin.org/get

> {%
    client.global.set("my_cookie", response.headers.valuesOf("Set-Cookie")[0]);
%}
```



For more information, see [HTTP Response handling API reference](https://www.jetbrains.com/help/go/http-response-handling-api-reference.html).

## Redirect the response﻿

You can redirect a response to a file. Use `>>` to create a new file with a suffix if it already exists and `>>!` to rewrite the file if it exists. You can specify an absolute path or relative to the current HTTP Request file. You can also use variables in paths, including environment variables and the following predefined variables:

- `{{$projectRoot}}` points to the project root directory
- `{{$historyFolder}}` points to **.idea/httpRequests/**

The following example HTTP request creates **myFile.json** in **myFolder** next to the HTTP Request file and redirects the response to it. If the file already exists, it creates **myFile-1.json**.

```http
POST https://httpbin.org/post
Content-Type: application/json

{
  "id": 999,
  "value": "content"
}

>> myFolder/myFile.json
```



The following example HTTP request creates **myFile.json** in **.idea/httpRequests/**. If the file already exists, it overwrites the file. It also [handles the response](https://www.jetbrains.com/help/go/exploring-http-syntax.html#response-handling) with the **handler.js** script that resides in the project root.

```http
POST https://httpbin.org/post
Content-Type: application/json

{
  "id": 999,
  "value": "content"
}

> {{$projectRoot}}/handler.js

>>! {{$historyFolder}}/myFile.json
```




> For Windows, specify paths with the backslash `\`.