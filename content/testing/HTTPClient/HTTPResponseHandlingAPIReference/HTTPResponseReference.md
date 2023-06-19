+++
title = "HTTP Response reference"
weight = 30
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# HTTP Response reference﻿

Last modified: 21 April 2023

## Response properties﻿

The `response` object holds the information about a received HTTP Response (response content, headers, status, and so on) and provides access to the [headers](https://www.jetbrains.com/help/go/http-response-reference.html#headers-reference) and [contentType](https://www.jetbrains.com/help/go/http-response-reference.html#content-type-reference) nested objects.

| Property                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| `body` (string \| [LineStreamResponse](https://www.jetbrains.com/help/go/http-response-reference.html#linestreamresponse_reference) \| object) | Response content, which can be a string, a LineStreamResponse object, or a JSON object. |
| `headers` ([ResponseHeaders](https://www.jetbrains.com/help/go/http-response-reference.html#headers-reference)) | The [response headers storage object](https://www.jetbrains.com/help/go/http-response-reference.html#headers-reference). |
| `status` (int)                                               | Response status, for example, 200 or 404.                    |
| `contentType` ([ContentType](https://www.jetbrains.com/help/go/http-response-reference.html#content-type-reference)) | The [contentType object](https://www.jetbrains.com/help/go/http-response-reference.html#content-type-reference), which holds the data on the Content-Type response header value. |

## Headers object﻿

The `ResponseHeaders` object is used for retrieving the data about response headers' values.

### Methods﻿

| Method   | Parameters            | Description                                                  |
| -------- | --------------------- | ------------------------------------------------------------ |
| valueOf  | `headerName` (string) | Retrieves the first value of the `headerName` response header or `null` if the `headerName` response header does not exist. |
| valuesOf | `headerName` (string) | Retrieves the array containing all values of the `headerName` response header. Returns an empty array if the `headerName` response header does not exist. |

## ContentType object﻿

The `ContentType` data object contains information from the Content-Type response header.

### Properties﻿

| Property            | Description                                                  |
| ------------------- | ------------------------------------------------------------ |
| `mimeType` (string) | The MIME type of the response, for example, text/plain, text/xml, application/json. |
| `charset` (string)  | The string representation of the response charset, for example, utf-8. |

## LineStreamResponse object﻿

The `LineStreamResponse` interface is used to process a response as a stream of lines. It implements a `onEachLine(line, unsubscribe)` method, which loops through each line in the stream, one after the other. The method takes two arguments:

### Arguments﻿

| Argument                           | Description                                                |
| ---------------------------------- | ---------------------------------------------------------- |
| `line` (a string or a JSON object) | A line (event) received as part of the stream.             |
| `unsubscribe`                      | Function to terminate execution of the `onEachLine` block. |

## Request properties﻿

The `request` object holds the information about the HTTP request and can be used both in pre-request scripts and in response handler scripts.

| Property                                                     | When used in pre-request scripts                             | When used in response handler scripts                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `body`                                                       | The request [body](https://www.jetbrains.com/help/go/exploring-http-syntax.html#provide-request-body) obtained using one of two methods:`getRaw()`: returns the request body in the raw format: If the request body contains variables, their names are displayed instead of their values.`tryGetSubstituted()`: returns the request body with all known variables replaced with their values. | The request [body](https://www.jetbrains.com/help/go/exploring-http-syntax.html#provide-request-body) as a string, for example `client.log(request.body())`. |
| `environment`                                                | Has the `get(name)` method, which retrieves a value of the [environment variable](https://www.jetbrains.com/help/go/exploring-http-syntax.html#environment-variables) identified by its `name` or returns `null` if it does not exist. |                                                              |
| `headers`                                                    | Has two methods:`all`: returns the array containing the values of all headers of the current request.`findByName(name)`: retrieves the value of the header identified by the `name` parameter. |                                                              |
| Each of the elements of the array is a request header with the following methods:`name`: the header name, such as `Content-Type`.`getRawValue`: returns the header value in the raw format: If the header contains variables, their names are displayed instead of their values.`tryGetSubstitutedValue()`: returns the header with all known variables replaced with their values. | Each of the elements of the array is a request header with the following methods:`name`: the header name, such as `Content-Type`.`value()`: the header value, such as `application/json`. |                                                              |
| `url`                                                        | The request URL obtained using one of two methods:`getRaw()`: returns the request URL in the raw format: If the URL contains variables, their names are displayed instead of their values.`tryGetSubstituted()`: returns the request URL with all known variables replaced with their values. | The request URL as a string.                                 |
| `variables`                                                  | Has the `get(name)` method, which retrieves a value of the [per-request variable](https://www.jetbrains.com/help/go/exploring-http-syntax.html#per_request_variables) identified by its `name` or returns `null` if it does not exist. |                                                              |