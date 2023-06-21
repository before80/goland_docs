+++
title = "HTTP 客户端加密 API 参考"
weight = 20
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# HTTP Client crypto API reference﻿ - HTTP 客户端加密 API 参考

https://www.jetbrains.com/help/go/http-client-crypto-api-reference.html

Last modified: 21 December 2022

最近修改日期：2022年12月21日

The `crypto` object provides access to HTTP Client Crypto API, which lets you use cryptographic hash functions and HMAC to generate HTTP signatures. You can then use these signatures as variables in pre-request scripts to sign your HTTP requests.

​	`crypto` 对象提供了对 HTTP 客户端加密 API 的访问，允许您使用加密哈希函数和 HMAC 生成 HTTP 签名。然后，您可以在预请求脚本中使用这些签名作为变量来对您的 HTTP 请求进行签名。

The `crypto` accepts a method that can be either one of the hash functions (`sha1`, `sha256`, `sha512`, `md5`), or [hmac](https://www.jetbrains.com/help/go/http-client-crypto-api-reference.html#hmac_methods).

​	`crypto` 接受一个方法，可以是哈希函数之一（`sha1`、`sha256`、`sha512`、`md5`），或者是 [hmac](https://www.jetbrains.com/help/go/http-client-crypto-api-reference.html#hmac_methods)。

## 哈希方法 Hash methods﻿

| 方法                  | 参数                                                         | 描述                               |
| --------------------- | ------------------------------------------------------------ | ---------------------------------- |
| `updateWithText`      | `textInput`（字符串）`encoding`（字符串）：`textInput` 的编码方式。默认为 `UTF8`。 | 更新要转换为哈希的字符串。         |
| `updateWithHex`       | `hexInput`（字符串）                                         | 更新要转换为哈希的十六进制字符串。 |
| `updateWithBase64`    | `base64Input`（字符串）`urlSafe`（布尔值）：如果字符串是使用 URL 安全的 Base64 变体进行编码的，请输入 `true`。 | 更新要转换为哈希的 Base64 字符串。 |
| `digest().toHex()`    | —                                                            | 生成哈希并将其转换为十六进制格式。 |
| `digest().toBase64()` | `urlSafe`（布尔值）：如果要使用 URL 安全的 Base64 变体，请输入 `true` | 生成哈希并将其转换为 Base64 格式。 |

## HMAC 方法 HMAC methods﻿

The `crypto.hmac` object enables you to use HMAC to sign HTTP requests. It has access to all [hash methods](https://www.jetbrains.com/help/go/http-client-crypto-api-reference.html#hash_methods) to generate hashes but also has methods to get the secret part of the token.

​	`crypto.hmac` 对象使您能够使用 HMAC 对 HTTP 请求进行签名。它可以访问所有的[哈希方法](https://www.jetbrains.com/help/go/http-client-crypto-api-reference.html#hash_methods)来生成哈希，还有一些方法可以获取令牌的密钥部分。

| 方法               | 参数                                                         | 描述                         |
| ------------------ | ------------------------------------------------------------ | ---------------------------- |
| `withTextSecret`   | `textSecret`（字符串）`encoding`（字符串）：`textSecret` 的编码方式。默认为 `UTF8`。 | 设置要在 HMAC 中使用的密钥。 |
| `withHexSecret`    | `hexSecret`（字符串）                                        | 使用十六进制格式设置密钥。   |
| `withBase64Secret` | `base64Input`（字符串）`urlSafe`（布尔值）：如果字符串是使用 URL 安全的 Base64 变体进行编码的，请输入 `true`。 | 使用 Base64 格式设置密钥。   |

示例：

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