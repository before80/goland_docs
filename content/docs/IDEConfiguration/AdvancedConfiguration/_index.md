+++
title = "高级配置"
weight = 60
date = 2023-06-17T19:06:58+08:00
description = ""
isCJKLanguage = true
draft = false
+++
# Advanced configuration﻿

Last modified: 04 August 2022

Besides the standard options available the IDE settings, GoLand enables you to perform low-level configuration of the underlying platform and the Java runtime.

> ### 
>
> 
>
> This may lead to unexpected problems and make your GoLand installation inoperable if you are not sure what you are doing. Contact [JetBrains Support](https://intellij-support.jetbrains.com/hc/en-us) for instructions regarding the options and values that might help you with whatever issue you are trying to solve.

## JVM options﻿

GoLand runs on the Java Virtual Machine (JVM), which has various options that control its performance. The default options used to run GoLand are specified in the IDE installation directory:



Windows

macOS

Linux





**<IDE_HOME>\bin\goland64.exe.vmoptions**

> ### 
>
> 
>
> Do not change JVM options in the default file, because it is replaced when GoLand is updated. Moreover, in case of macOS, editing this file violates the application signature.

### Configure JVM options﻿

Do one of the following to create a copy of the default file with JVM options in the [configuration directory](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory) that will override the original file:

- From the main menu, select Help | Edit Custom VM Options.
- If you do not have any project open, on the Welcome screen, click Configure and then Edit Custom VM Options.
- If you cannot start GoLand, manually copy the default file with JVM options to the GoLand [configuration directory](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory).

If you do not have write access to the GoLand configuration directory, you can add the `GOLAND_VM_OPTIONS` environment variable to specify the location of the file with your preferred JVM options. This file will override both the original default file and the copy located in the GoLand configuration directory.

> ### 
>
> 
>
> If you are using the Toolbox App, it manages the installation and configuration directory and lets you configure JVM options for every IDE instance. Open the Toolbox App, click ![The screw nut icon](index_img/toolbox_settings_screw_icon.png) next to the relevant IDE instance, and select Settings.

### Locate the JVM options file﻿

If you are not sure where GoLand is getting its JVM options, check the following:

1. The location specified by the `GOLAND_VM_OPTIONS` environment variable. If the specified file exists, it will override all other JVM options files.
2. If the Toolbox App manages your current GoLand instance, open the Toolbox App, click ![The screw nut icon](index_img/toolbox_settings_screw_icon.png) next to the relevant IDE instance, and select Settings. Under Configuration, find Java Virtual Machine options and click Edit.
3. If you are running a standalone GoLand instance, check the [configuration directory](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory).
4. If there are no JVM options files defined in the previous locations, GoLand will use the [default JVM options file](https://www.jetbrains.com/help/go/tuning-the-ide.html#default-jvm-options). Do not modify it. Use it only to check what are the default options that GoLand uses.

### Common options﻿

The default values of the JVM options should be optimal in most cases. The following are the most commonly modified ones:

| Option         | Description                                                  |
| -------------- | ------------------------------------------------------------ |
| `-Xmx`         | Limits the maximum memory heap size that the JVM can allocate for running GoLand. The default value depends on the platform. If you are experiencing slowdowns, you may want to increase this value, for example, to set the value to 2048 megabytes, change this option to `-Xmx2048m`.For more information, see [Increase the memory heap of the IDE](https://www.jetbrains.com/help/go/increasing-memory-heap.html). |
| `-Xms`         | Specifies the initial memory allocated by the JVM for running GoLand. The default value depends on the platform. It is usually set to about half of the maximum allowed memory ([-Xmx](https://www.jetbrains.com/help/go/tuning-the-ide.html#xmx)), for example, `-Xms1024m`. |
| `-XX:NewRatio` | Specifies the ratio between the size of the young and old generation of the heap. In most cases, a ratio between 2 and 4 is recommended. This will set the size of the young generation to be 1/2 to 1/4 of the old generation correspondingly, which is good when you are often working on one project and only a few files at a time. However, if you are constantly opening new files and switching between several projects, you may need to increase the young generation. In this case, try setting `-XX:NewRatio=1`, which will make the young generation as large as the old generation, allowing objects to remain in the young generation for longer. |

For more information about the available JVM options, see the [java](https://docs.oracle.com/en/java/javase/11/tools/java.html) command reference.

## Platform properties﻿

GoLand enables you to customize various platform-specific properties, such as the path to user-installed plugins and the maximum supported file size. The default properties used to run GoLand are specified in the IDE installation directory:



Windows

macOS

Linux





**<IDE_HOME>\bin\idea.properties**

> ### 
>
> 
>
> Do not change platform properties in the default file, because it is replaced when GoLand is updated. Moreover, in case of macOS, editing this file violates the application signature.

### Configure platform properties:﻿

Do one of the following to create an empty **idea.properties** file in the [configuration directory](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory) that will override the values from the original file:

- From the main menu, select Help | Edit Custom Properties.
- If you do not have any project open, on the Welcome screen, click Configure and then select Edit Custom Properties.
- If you cannot start GoLand, manually create an empty **idea.properties** file in the GoLand [configuration directory](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#config-directory).

If you do not have write access to the GoLand configuration directory, you can add the `GOLAND_PROPERTIES` environment variable to specify the location of the **idea.properties** file. The properties in this file will override the corresponding properties in both the original default file and the one located in the GoLand configuration directory.

### Common properties﻿

Users often change the location of the [default IDE directories](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html). For more information, see [Change the location of IDE directories](https://www.jetbrains.com/help/go/directories-used-by-the-ide-to-store-settings-caches-plugins-and-logs.html#change-ide-dirs).

Limits that can affect performance:

| Property                         | Description                                                  |
| -------------------------------- | ------------------------------------------------------------ |
| `idea.max.content.load.filesize` | Maximum size of files (in kilobytes) that GoLand is able to open. Working with large files can affect editor performance and increase memory consumption. The default value is `20000`. |
| `idea.max.intellisense.filesize` | Maximum size of files (in kilobytes) for which GoLand provides coding assistance. Coding assistance for large files can affect editor performance and increase memory consumption. The default value is `2500`. |
| `idea.cycle.buffer`              | Maximum size of the console cyclic buffer (in kilobytes). If the console output size exceeds this value, the oldest lines are deleted. To disable the cyclic buffer, set `idea.cycle.buffer.size=disabled`. |
| `idea.max.vcs.loaded.size.kb`    | Maximum size (in kilobytes) that GoLand loads for showing past file contents when [comparing changes](https://www.jetbrains.com/help/go/comparing-files-and-folders.html). The default value is `20480`. |

GoLand provides a number of other properties that define interaction with the environment (window managers, launchers, the file system, and so on). Most of them act like hidden settings (in the sense that they are not evidently exposed), which you may need to enable or disable in certain cases. Change these properties only if advised by [JetBrains Support](https://intellij-support.jetbrains.com/hc/en-us).