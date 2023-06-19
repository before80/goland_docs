+++
title = "HTTP Client crypto API reference"
weight = 20
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# HTTP Client crypto API reference﻿

https://www.jetbrains.com/help/go/http-client-crypto-api-reference.html#hmac_methods

Last modified: 21 December 2022

The `crypto` object provides access to HTTP Client Crypto API, which lets you use cryptographic hash functions and HMAC to generate HTTP signatures. You can then use these signatures as variables in pre-request scripts to sign your HTTP requests.

The `crypto` accepts a method that can be either one of the hash functions (`sha1`, `sha256`, `sha512`, `md5`), or [hmac](https://www.jetbrains.com/help/go/http-client-crypto-api-reference.html#hmac_methods).

## Hash methods﻿

| Method                | Parameters                                                   | Description                                                |
| --------------------- | ------------------------------------------------------------ | ---------------------------------------------------------- |
| `updateWithText`      | `textInput` (string)`encoding` (string): the encoding of `textInput`. Default is `UTF8`. | Updates a string to be transformed to a hash.              |
| `updateWithHex`       | `hexInput` (string)                                          | Updates a hexadecimal string to be transformed to a hash.  |
| `updateWithBase64`    | `base64Input` (string)`urlSafe` (boolean): enter `true` if the string is encoded using the URL-safe variant of Base64. | Updates a Base64 string to be transformed to a hash.       |
| `digest().toHex()`    | —                                                            | Generates a hash and convert it to the hexadecimal format. |
| `digest().toBase64()` | `urlSafe` (boolean): enter `true` if you want to use the URL-safe variant of Base64 | Generates a hash and convert it to the Base64 format.      |

## HMAC methods﻿

The `crypto.hmac` object enables you to use HMAC to sign HTTP requests. It has access to all [hash methods](https://www.jetbrains.com/help/go/http-client-crypto-api-reference.html#hash_methods) to generate hashes but also has methods to get the secret part of the token.

| Method             | Parameters                                                   | Description                                    |
| ------------------ | ------------------------------------------------------------ | ---------------------------------------------- |
| `withTextSecret`   | `textSecret` (string)`encoding` (string): the encoding of `textSecret`. Default is `UTF8`. | Puts the secret key to be used in HMAC.        |
| `withHexSecret`    | `hexSecret` (string)                                         | Puts the secret key in the hexadecimal format. |
| `withBase64Secret` | `base64Input` (string)`urlSafe` (boolean): enter `true` if the string is encoded using the URL-safe variant of Base64. | Puts the secret key in the Base64 format.      |

Example:

```http
< {%
    const signature = crypto.hmac.sha256()
        .withTextSecret(request.environment.get("secret"))
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

{
"prop": "value"
}
```