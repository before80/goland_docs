+++
title = "Work offline"
weight = 60
date = 2023-06-14T17:20:58+08:00
description = ""
isCJKLanguage = true
draft = false
+++
# Work offline﻿

https://www.jetbrains.com/help/go/working-offline.html#usage-stats

Last modified: 22 March 2023

A lot of features in GoLand require access to the Internet. If you are working offline (for example, in an isolated environment), there are some aspects that you should keep in mind.

### Access documentation offline﻿

- If you don't have internet access to view the online help, you can use the [GoLand Help](https://plugins.jetbrains.com/plugin/10490-goland-help) plugin, which serves the help pages via the built-in web server for offline use.

> The offline help plugin is updated when a new major version is released. Changes that are added to online help during the release cycle may not be available in the offline help.

## Updates﻿

By default, GoLand is configured to check for updates automatically and notify you when a new version is available. Updates are usually patch-based: they are applied to the existing installation and only require you to restart the IDE. However, sometimes patch updates are not available, and a new version of GoLand must be installed.

If GoLand does not have HTTP access outside your local network, it will not be able to check for updates and apply patches. In this case, you have to download new versions of the IDE and install them manually as described in [Standalone installation](https://www.jetbrains.com/help/go/installation-guide.html#standalone).

> Without internet access, you can't install GoLand using the [Toolbox App](https://www.jetbrains.com/help/go/installation-guide.html#toolbox) and [snaps](https://www.jetbrains.com/help/go/installation-guide.html#snap).

For more information, see [Update GoLand](https://www.jetbrains.com/help/go/update.html).

## Plugins﻿

Usually, plugins are installed from the [JetBrains Plugin Repository](https://plugins.jetbrains.com/). However, you can set up a [custom plugin repository](https://www.jetbrains.com/help/go/managing-plugins.html#repos) in your local network and configure GoLand to use it for installing and updating plugins.

Alternatively, you can download and manually [install plugins from disk](https://www.jetbrains.com/help/go/managing-plugins.html#install_plugin_from_disk).

## License activation﻿

You can evaluate GoLand for up to 30 days. After that, buy and register a license to continue using the product.

If GoLand does not have HTTP access outside your local network, you will not be able to use the [JetBrains Account](https://account.jetbrains.com/login) for signing in. However, you can generate an offline activation code that will be valid during your subscription term.

If your organization has at least 50 active subscriptions or licenses of JetBrains products, you can use the [Floating License Server](https://www.jetbrains.com/help/license_server) to activate GoLand instances within your company network. Keep in mind that the License Server itself requires internet access for connecting to the JetBrains Account.

For more information, see [Register GoLand](https://www.jetbrains.com/help/go/register.html).

## Code inspections﻿

Some code inspections verify external resources. For example, the Non-existent web resource inspection highlights dead links. If you don't have internet access, these inspections will not work and dead links will not be highlighted.

For more information, see [Code inspections](https://www.jetbrains.com/help/go/code-inspection.html).

## Version control systems﻿

Most likely, your source code is under some sort of version control system (VCS). If a remote repository is not in your local network, and there is no internet access, GoLand will not be able to communicate with the VCS. For example, if you are using Git, you will be able to commit your changes but won’t be able to push them to the remote repository or pull updates from it.

For more information about VCS integration, see [Version control](https://www.jetbrains.com/help/go/version-control-integration.html).

## Tasks and issue trackers﻿

You can set up a connection with an issue tracker to work with tasks and bugs assigned to you directly from GoLand. For example, you can connect to [YouTrack](http://www.jetbrains.com/youtrack/), [Jira](http://www.atlassian.com/software/jira/), [GitHub](http://github.com/), and so on.

If the issue tracker server is not in your local network, and there is no internet access, GoLand will not be able to sync your issues. In this case, you will be able to work only with local tasks that you create yourself.

## Usage statistics﻿

When you run GoLand for the first time, you are prompted whether to send anonymous data on the features and plugins you use, your hardware and software configuration, file types, number of files per project, and so on. This does not include any personal or sensitive data, such as parts of your source code or file names. This information is collected in accordance with the [JetBrains Privacy Policy](https://www.jetbrains.com/company/privacy.html) and is used to help improve the products and overall experience.

Even if you enable anonymous usage statistics, it will not be sent if there is no HTTP access outside your local network. Also, you can disable this feature entirely if you agreed at first and then changed your mind later.

### Disable sending usage statistics﻿

1. In the Settings dialog (Ctrl+Alt+S), select Appearance & Behavior | System Settings | Data Sharing.
2. Clear the Send usage statistics checkbox.