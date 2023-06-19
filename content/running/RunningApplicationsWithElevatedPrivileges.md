+++
title = "Running applications with elevated privileges"
weight = 30
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Running applications with elevated privileges﻿

https://www.jetbrains.com/help/go/debug-as-root.html#elevation

Last modified: 16 January 2023


> Before running or debugging the application with elevated privileges, ensure that this application is not malicious.

Elevated privileges are roles or permissions for some accounts in your operating system that grant the ability to do more than a standard user. A standard user here means someone that has no administrative privileges in any capacity.

In different operating systems, accounts with elevated privileges can be a root user, a superuser, an administrator, a user with sudo privileges. This user account is usually used for administrative purposes, and typically has the highest access rights on the system. This means it can read and write any files on the system, perform operations as any user, or change system configuration.

## Configure authorization time﻿

If do not want to authorize each time you run or debug an application with elevated privileges, you can configure the amount of time the authorization is kept. This is similar to how the `sudo` command-line program works by default.

When you run or debug with elevated privileges for the first time, you will be prompted to choose whether to authorize every time or grant authorization for the configured period. You will always be able to change this [in the settings](https://www.jetbrains.com/help/go/debug-as-root.html#authorize-settings).

![Authorization preferences dialog](RunningApplicationsWithElevatedPrivileges_img/go_debug_as_root_dialog.png)



Note that GoLand will not have access to any passwords - the authorization is carried out via a system dialog. After the configured time runs out, the already running processes with root privileges will continue to run, but no new elevated process will be able to start until you authorize that again.

### Set the authorization period in the settings﻿

You can also configure the time the authorization is kept in the settings.

1. Go to Settings | Appearance & Behavior | System Settings | Process Elevation.

2. Set the Keep 'sudo' authorization for (Keep UAC authorization for) checkbox and specify the value. The default is 15 minutes.

   ![Authorization time settings](RunningApplicationsWithElevatedPrivileges_img/go_debug_as_root_settings.png)