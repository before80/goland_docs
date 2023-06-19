+++
title = "HTTP Response handling API reference"
weight = 10
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# HTTP Response handling API reference﻿

https://www.jetbrains.com/help/go/http-response-handling-api-reference.html

Last modified: 21 April 2023

HTTP Response handler scripts are written in JavaScript ES6, with coding assistance and documentation handled by the bundled `HTTP Response Handler` library. The library exposes two objects to be used for composing response handler scripts:

- [client](https://www.jetbrains.com/help/go/http-client-reference.html) stores the session metadata, which can be modified inside the script. The `client`'s state is preserved until you close GoLand.
- [response](https://www.jetbrains.com/help/go/http-response-reference.html) holds information about the received response: its content type, status, response body, and so on.