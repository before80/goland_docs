+++
title = "Response handling examples"
weight = 40
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Response handling examples﻿

https://www.jetbrains.com/help/go/http-response-handling-examples.html#stream_scripting

Last modified: 21 April 2023

In this topic, we'll examine a couple of HTTP response handling examples. To try examples yourself, explore the auth-requests and test-responses [requests collections](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#open-requests-collection).

## Checking response headers, body, and content type﻿

In this example, we'll create several tests to verify the following:

- The request is executed successfully, that is, the response status is 200.
- Headers are received within the response body.
- The response's content type is application/json.

To create a test, we call the `test` method of the [client](https://www.jetbrains.com/help/go/http-client-reference.html) object. Inside the test, we can assert a specific condition by calling the `assert` method of the `client` object and refer to various properties of the [response](https://www.jetbrains.com/help/go/http-response-reference.html) object to validate them.

```javascript
### Check response status, headers, and content-type
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



## Use global variables﻿

In this example, we'll capture a value from the received response into a [global variable](https://www.jetbrains.com/help/go/http-client-reference.html#global-variables-storage-reference), which can be then used in subsequent requests.

The first request involves a response handler script, which saves an authentication token from the received response body into the `auth_token` variable under [client.global](https://www.jetbrains.com/help/go/http-client-reference.html#global-variables-storage-reference). To achieve this, we use the `client.global.set(VariableName, VariableValue)` construction. As the `VariableValue` argument, we use the value of the `json.token` field from the [response body](https://www.jetbrains.com/help/go/http-response-reference.html#response-properties) returned by the server (by `httpbin.org` in our example). This value is then assigned to the `"auth_token"` variable.

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




> Due to the [httpbin POST implementation](http://httpbin.org/#/HTTP_Methods/post_post), we use `response.body.json.token` to retrieve the token. Depending on the actual web service you are interacting with, the response structure may differ, and you may need to use a different construction, for example, `response.body.token`.

After the request is executed, the `auth_token` variable can be accessed from both subsequent requests as `{{auth_token}}` and response handler scripts by means of the `client.global.get("auth_token")` construction.

```http
//Accessing a variable
GET https://httpbin.org/headers
Authorization: Bearer {{auth_token}}
```



To obtain a value from a response header, use the `valueOf` method of the [headers](https://www.jetbrains.com/help/go/http-response-reference.html#headers-reference) object. If several headers with the same name are received (which is a common case for the Set-Cookie header), use the `valuesOf` method instead. This will return an array of all response header values.

```shell
POST https://httpbin.org/cookies

//Saving a cookie from the first Set-Cookie header
> {%
    client.global.set("my_cookie", response.headers.valuesOf("Set-Cookie")[0]);
%}
```



## Process each line of an event stream﻿

If you subscribe to an event stream, a server will automatically send events to your client when new data becomes available. This data can be in the form of Server-Sent Events or newline-delimited JSON (NDJSON). In GoLand, you can use the HTTP Client [response.body.onEachLine](https://www.jetbrains.com/help/go/http-response-reference.html#linestreamresponse_reference) method to call a function on each line of this event stream.

Suppose you have a server that regularly sends information on the gold price. In this example, let's write a response handler script, which does the following:

1. Takes each chunk of data (JSON object) received from the server and logs the price value. When you run the request, you can view the logged info in the Response Handler tab of the Services tool window.
2. Stops processing the received data when the number of events exceeds 10. Note that this does not unsubscribe you from the event stream – you'll keep receiving events as long as the HTTP connection is open (check the Console tab of the Services tool window).
3. Tests the obtained chunks of data: if the price is less than 45, the test fails. You can view the test results in the Tests tab of the Services tool window.

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