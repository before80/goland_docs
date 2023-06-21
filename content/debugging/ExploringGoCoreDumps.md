+++
title = "探索Go核心转储文件"
weight = 50
date = 2023-06-20T10:40:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Exploring Go core dumps﻿ 探索Go核心转储文件

https://www.jetbrains.com/help/go/exploring-go-core-dumps.html

Last modified: 16 January 2023

最近修改：2023年1月16日

Sometimes when you debug a program, you need to examine the code execution flow and understand the current state of a program. Go core dump is a file that contains the memory dump of running processes and their status during the life of a program. You can debug core dumps when the program finished its execution or while it is still running.

​	有时在调试程序时，您需要检查代码的执行流程并了解程序的当前状态。Go核心转储文件是一个包含正在运行的进程的内存转储和它们在程序生命周期中的状态的文件。您可以在程序执行完成后或仍在运行时调试核心转储文件。


> You can create Go core dump files only on Linux machines. But you can view the dump files on any operating system that supports GoLand.
>
> ​	您只能在Linux机器上创建Go核心转储文件。但您可以在任何支持GoLand的操作系统上查看转储文件。

### 在Linux上创建Go核心转储文件 Create a Go core dump file on Linux﻿

1. Open a terminal in the directory with the file .

2. 在文件所在的目录中打开终端。

3. Set the `ulimit` parameter to `unlimited`: `ulimit -c unlimited`.

4. 将`ulimit`参数设置为`unlimited`：`ulimit -c unlimited`。

5. Build the program by running `go build .` in the terminal. The `build` command creates a binary file in the current project folder (for example, **awesomeProject**).

6. 在终端中运行`go build .`来构建程序。`build`命令会在当前项目文件夹（例如**awesomeProject**）中创建一个二进制文件。

7. To create a core dump file, run `GOTRACEBACK=crash ./<binary_file_name>` (for example, `GOTRACEBACK=crash ./awesomeProject`). This command creates a **core** file in the current project folder.

8. 要创建核心转储文件，请运行`GOTRACEBACK=crash ./<binary_file_name>`（例如`GOTRACEBACK=crash ./awesomeProject`）。此命令会在当前项目文件夹中创建一个**core**文件。

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_create_go_core_dump.png](ExploringGoCoreDumps_img/go_create_go_core_dump.animated.gif)

### 查看转储日志 View the dump log﻿

1. 转到 Run | Open Core Dump.

2. In the Executable field, specify a path to the binary file (for example, **awesomeProject**).

3. 在“可执行文件”字段中，指定二进制文件的路径（例如**awesomeProject**）。

4. In the Core Dump field, specify a path to the `core` file (for example, **core**).

5. 在“核心转储”字段中，指定`core`文件的路径（例如**core**）。

6. Click OK. In the Debug tool window, select a frame that you want to inspect.

7. 单击“确定”。在调试工具窗口中，选择要检查的帧。

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_open_go_core_dump.png](ExploringGoCoreDumps_img/go_open_go_core_dump.animated.gif)

### 在GoLand中查看Go核心转储文件 View the Go core dump in GoLand﻿

1. Open or create the Go Build configuration for the Go file.

2. 打开或创建Go文件的Go构建配置。

3. In the Environment field, click the folder (在“环境”字段中，单击文件夹图标（![The folder icon](ExploringGoCoreDumps_img/app.nodes.folder.svg)).)。

4. In the Environment Variables dialog, click the Add icon (在“环境变量”对话框中，单击添加图标（![The Add icon](ExploringGoCoreDumps_img/app.general.add.svg)).)。

5. Click the Name field and type `GOTRACEBACK`.

6. 单击“名称”字段，输入`GOTRACEBACK`。

7. Click the Value field and type `crash`.

8. 单击“值”字段，输入`crash`。

9. Save all changes and click OK.

10. 保存所有更改，单击“确定”。

11. Run the programShift+F10. The output for the program is displayed in the debugger window.

12. 运行程序（按下Shift+F10）。程序的输出将显示在调试器窗口中。

    ![https://resources.jetbrains.com/help/img/idea/2023.1/go_gotraceback_crash.png](ExploringGoCoreDumps_img/go_gotraceback_crash.animated.gif)
