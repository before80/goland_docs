+++
title = "Directories used by the IDE"
weight = 10
date = 2023-06-17T19:06:58+08:00
description = ""
isCJKLanguage = true
draft = false
+++
# Directories used by the IDE﻿

Last modified: 26 April 2023

By default, GoLand stores user-specific files for each IDE instance (configuration, caches, plugins, logs, and so on) in the user's home directory. However, you can change the location for storing those files, if necessary.

> ### 
>
> 
>
> The default location of the IDE directories has changed starting from GoLand version 2020.1. If you had a previous version, new installations will import configuration from the old directories. For information about the location of the default directories in previous IDE versions, see the corresponding help version, for example: https://www.jetbrains.com/help/go/2019.3/tuning-the-ide.html#default-dirs.

### Change the location of IDE directories﻿

You can move the default IDE directories, for example, if the user profile drive runs out of space or it is located on a slow disk, if the home directory is encrypted (slowing down the IDE) or is located on a network drive, if you want to create a portable installation or exclude caches from home directory backups, and so on.

1. From the main menu, select Help | Edit Custom Properties.

2. Set the property that corresponds to the necessary directory:

   | Property            | Path to                                                      |
   | ------------------- | ------------------------------------------------------------ |
   | `idea.config.path`  | [Configuration directory](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory) |
   | `idea.system.path`  | [System directory](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#system-directory) |
   | `idea.plugins.path` | [Plugins directory](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#plugins-directory) |
   | `idea.log.path`     | [Logs directory](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#logs-directory) |

   Specify paths with forward slashes **/**, including Windows paths (for example, **C:/idea/system**).

   You can insert any other properties as variables. For example, use `${user.home}` (standard Java system property) to specify paths relative to the user's home directory:

   ```plaintext
   idea.config.path=${user.home}/MyIdeaConfiguration
   ```

   

3. After you restart GoLand, it will use the new location of the corresponding directory.

### Clean up old IDE directories﻿

Every time you install a new major version of GoLand, it uses a new set of IDE directories and automatically deletes the caches and logs directories for older versions of the IDE that have not been updated in the last 180 days. The configuration and plugins directories will remain forever, unless you remove them manually.

1. From the main menu, select Help | Delete Leftover IDE Directories
2. In the Delete Leftover IDE Storage Directories dialog, select the versions of the IDE that you are not planning to use and click Delete.

## Configuration directory﻿

The GoLand configuration directory contains user-defined IDE settings, such as keymaps, color schemes, custom [VM options](https://www.jetbrains.com/help/go/tuning-the-ide.html#configure-jvm-options), [platform properties](https://www.jetbrains.com/help/go/tuning-the-ide.html#configure-platform-properties), and so on.



Windows

macOS

Linux







You can change the location of the GoLand configuration directory using the [idea.config.path](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#idea.config.path) property.

To share your personal IDE settings, copy the files from the configuration directory to the corresponding folders on another GoLand installation. Make sure that GoLand is not running to avoid erasing the copied files when you shut down the IDE. Depending on which settings you modified, the GoLand configuration directory can contain the following subfolders:

| Directory         | User settings                                                |
| ----------------- | ------------------------------------------------------------ |
| **codestyles**    | Customized [code style schemes](https://www.jetbrains.com/help/go/configuring-code-style.html) |
| **colors**        | Customized [editor color and font schemes](https://www.jetbrains.com/help/go/configuring-colors-and-fonts.html) |
| **fileTemplates** | User-defined [file templates](https://www.jetbrains.com/help/go/using-file-and-code-templates.html) |
| **filetypes**     | User-defined file types                                      |
| **inspection**    | [Code inspection profiles](https://www.jetbrains.com/help/go/code-inspection.html) |
| **keymaps**       | Customized [keyboard shortcuts](https://www.jetbrains.com/help/go/configuring-keyboard-and-mouse-shortcuts.html) |
| **options**       | Various options, for example, feature usage statistics and macros |
| **scratches**     | [Scratch files and buffers](https://www.jetbrains.com/help/go/scratches.html) |
| **settingsSync**  | IDE settings shared using [Settings Sync](https://www.jetbrains.com/help/go/sharing-your-ide-settings.html#IDE_settings_sync) |
| **templates**     | User-defined [live templates](https://www.jetbrains.com/help/go/using-live-templates.html) |
| **tools**         | Configuration files for [user-defined external tools](https://www.jetbrains.com/help/go/configuring-third-party-tools.html) |
| **shelf**         | [Shelved changes](https://www.jetbrains.com/help/go/work-on-several-features-simultaneously.html#shelve) |

## System directory﻿

The GoLand system directory contains caches and local history files.



Windows

macOS

Linux







You can change the location of the GoLand system directory using the [idea.system.path](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#idea.system.path) property.

## Plugins directory﻿

The GoLand plugins directory contains user-installed plugins.



Windows

macOS

Linux







You can change the location of the GoLand plugins directory using the [idea.plugins.path](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#idea.plugins.path) property.

> ### 
>
> 
>
> If you installed GoLand via the [Toolbox App](https://www.jetbrains.com/toolbox/app/), the plugins directory will be located in the installation directory. To find the installation directory, open the settings of the IDE instance in the Toolbox App, expand Configuration and look for the Install location field. There should be a directory that ends with **.plugins**.
>
> You can also see the location of the plugins directory in the VM options file. From the main menu, select Help | Edit Custom VM Options. For example, the option can look like this:
>
> ```plaintext
> -Didea.plugins.path=/Users/jsmith/Library/Application Support/JetBrains/Toolbox/apps/IDEA-U/ch-2/212.5080.55/IntelliJ IDEA.app.plugins
> ```

## Logs directory﻿

The GoLand logs directory contains product logs and thread dumps.



Windows

macOS

Linux







You can change the location of the GoLand logs directory using the [idea.log.path](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#idea.log.path) property.

> ### 
>
> 
>
> You can open the location of the logs directory using the corresponding Help menu action: Show Log in Explorer on Windows or Show Log in Finder on macOS.