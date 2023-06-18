+++
title = "Trusted root certificates"
weight = 40
date = 2023-06-17T19:06:58+08:00
description = ""
isCJKLanguage = true
draft = false
+++
# Trusted root certificates﻿

https://www.jetbrains.com/help/go/ssl-certificates.html#manual_configuration

Last modified: 08 March 2023

Trusted certificates establish a chain of trust that verifies other certificates signed by the trusted roots — for example, to establish a secure connection to a web server.

GoLand gets the list of trusted root certificates from the system trust store and its storage is customizable from [GoLand settings](https://www.jetbrains.com/help/go/settings-tools-server-certificates.html).

If the enterprise environment in which you are working uses custom certificates, GoLand trusts such certificates by default. No additional configuration is required.

Upon the certificate checking, GoLand also checks the system trust stores for Windows, macOS, and Linux.

## How it works under the hood﻿



Linux

macOS

Windows





Under Linux, all certificates in `.crt` (PEM) format from the following locations are imported:

- `/etc/ssl/certs/*`
- `/etc/pki/tls/certs/*`
- `/system/etc/security/cacerts/*`
- `/etc/ssl/certs/ca-certificates.crt`
- `/etc/pki/tls/certs/ca-bundle.crt`
- `/etc/ssl/ca-bundle.pem`
- `/etc/pki/tls/cacert.pem`
- `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem`
- `/etc/ssl/cert.pem`

For more information, check the [JetBrains Linux Trusted Certificates](https://github.com/JetBrains/jvm-native-trusted-roots/blob/trunk/src/main/java/org/jetbrains/nativecerts/linux/LinuxTrustedCertificatesUtil.java) library.

## Logs and diagnostics﻿

In case you've encountered a problem with certificates, you can quickly troubleshoot it by enabling the following debug categories:

- `org.jetbrains.nativecerts`
- `#com.intellij.util.net.ssl`

### Collect additional logs in GoLand﻿

1. From the main menu, select Help | Diagnostic Tools | Debug Log Settings.

2. In the dialog that opens, add the [debug categories](https://www.jetbrains.com/help/go/ssl-certificates.html#debug_categories) and click OK to save the changes.

   ![Custom Debug Log Configuration](TrustedRootCertificates_img/custom_debug_log_config.png)

3. Reproduce the issue.

4. From the main menu, select Help | Collect Logs and Diagnostic Data to collect logs.

   Send the logs to our [support](https://www.jetbrains.com/support/) along with the problem detailed description and a scenario to reproduce it.

   > ### 
   >
   > 
   >
   > Note that logs might contain private user information.

### Locate the IDE log files﻿

- From the main menu, select Help | Show logs in Finder. This menu item depends on the OS you are using. For example, for Windows, it would be Show logs in Explorer.

  The log file is named **idea.log** and is rotated based on the file size. When attaching logs to your problem report, it's recommended that you archive (**.zip**) and send several latest log files (`idea.log`, `idea.log.1`, `idea.log.2`, `idea.log.3`).

  You can also use the Collect Logs and Diagnostic Data option to generate the **.zip** file with all the log files (including the build logs and the automatic thread dumps).

## Certificates manual installation﻿

If you use a proxy server that decrypts all TLS traffic like `mitmproxy` or `fiddler`, you may import its self-signed certificate to the system so all applications on the local machine will trust it (including GoLand). However, this is potentially insecure since you can impersonate any Website with a private key from that certificate.

> ### 
>
> 
>
> You can also add the certificates as described in the [Server Certificates](https://www.jetbrains.com/help/go/settings-tools-server-certificates.html) section. However, keep in mind that it works only for the particular IDE, not for other IDEs or for the whole operating system.

After you've generated the certificate, use one of the following procedures to add it to the trust store:



Linux

macOS

Windows





### Install root certificate﻿

1. Generate the certificate in the `.crt` (PEM) format.

2. Add the certificate to the one of the [listed directories](https://www.jetbrains.com/help/go/ssl-certificates.html#linux_directories).

   For example, you can use `/etc/ssl/certs/` or `/etc/pki/tls/certs/`.