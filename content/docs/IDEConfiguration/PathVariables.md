+++
title = "Path变量"
weight = 40
date = 2023-06-17T19:06:58+08:00
description = ""
isCJKLanguage = true
draft = false
+++
# Path variables﻿ - 路径变量

https://www.jetbrains.com/help/go/absolute-path-variables.html

Last modified: 16 January 2023

Use path variables to define absolute paths to resources that are not part of a specific project. These external resources may be located in different places on the computers of your teammates. This is why user-defined custom path variables are not stored as [project settings](https://www.jetbrains.com/help/go/configure-project-settings.html), but as [global IDE settings](https://www.jetbrains.com/help/go/configuring-project-and-ide-settings.html). Once configured, such path variables will have the same value for any project that you open with your instance of GoLand.

使用路径变量来定义资源的绝对路径，这些资源不属于特定项目。这些外部资源可能位于您团队成员计算机上的不同位置。这就是为什么用户定义的自定义路径变量不存储为[项目设置](https://www.jetbrains.com/help/go/configure-project-settings.html)，而是存储为[全局IDE设置](https://www.jetbrains.com/help/go/configuring-project-and-ide-settings.html)。一旦配置完成，这些路径变量对于您在GoLand中打开的任何项目都具有相同的值。

### 创建新的路径变量 Create a new path variable﻿

1. Press Ctrl+Alt+S to open the IDE settings and select Appearance & Behavior | Path Variables.
2. 按下Ctrl+Alt+S打开IDE设置，选择外观与行为 | 路径变量。
3. Click点击 ![the Add button](PathVariables_img/app.general.add.svg), enter the name and value of the variable, and click OK to apply the changes.，输入变量的名称和值，然后点击确定以应用更改。

You can use path variables to specify paths and command-line arguments for [external tools](https://www.jetbrains.com/help/go/configuring-third-party-tools.html) and in some [run configurations](https://www.jetbrains.com/help/go/run-debug-configuration.html). For more information, see [Built-in IDE macros](https://www.jetbrains.com/help/go/built-in-macros.html).

您可以使用路径变量来指定[外部工具](https://www.jetbrains.com/help/go/configuring-third-party-tools.html)的路径和命令行参数，以及某些[运行配置](https://www.jetbrains.com/help/go/run-debug-configuration.html)中的路径变量。有关详细信息，请参阅[内置IDE宏](https://www.jetbrains.com/help/go/built-in-macros.html)。

For example, you can define a path variable that points to the location of some data source (like a CSV file) or a third-party library that is not stored in your project. If you use this path variable in a run configuration that you share with your project, others can define the correct value for this path variable in their environment and be sure that the run configuration will work for them.

例如，您可以定义一个指向某个数据源（如CSV文件）或不存储在项目中的第三方库的路径变量。如果您在与项目共享的运行配置中使用此路径变量，其他人可以在其环境中定义此路径变量的正确值，并确保运行配置适用于他们。

Another example is defining a path variable for the [attached directory](https://www.jetbrains.com/help/go/working-with-user-files.html) that you use in your project. On another machine, the directory might be stored in a different location. To make sure your project with the attached directory can be shared and used on another machine, use path variables to define the location of attached directory.

另一个例子是为您在项目中使用的[附加目录](https://www.jetbrains.com/help/go/working-with-user-files.html)定义一个路径变量。在另一台计算机上，该目录可能存储在不同的位置。为了确保附加目录的项目可以在另一台计算机上共享和使用，使用路径变量来定义附加目录的位置。

Refer to the variable as `$var_name$` in fields and configuration files that accept path variables.

在接受路径变量的字段和配置文件中，将变量表示为`$var_name$`。

GoLand also has the following built-in path variables:

GoLand还具有以下内置路径变量：



### 忽略路径变量 Ignore path variables﻿

Whenever you open or update a project, GoLand checks for unresolved path variables. If the IDE detects any, it will ask you to define values for them. If you are not going to use files or directories with the unresolved path variables, you can add them to the list of ignored variables.

每当您打开或更新项目时，GoLand都会检查未解析的路径变量。如果IDE检测到任何未解析的路径变量，它会要求您为其定义值。如果您不打算使用具有未解析路径变量的文件或目录，您可以将其添加到忽略变量列表中。

You can also use the list of ignored variables when a program argument passed to the run/debug configuration has the same format as a path variable (for example, an environment variable).

当传递给运行/调试配置的程序参数具有与路径变量相同格式（例如，环境变量）时，您还可以使用忽略变量列表。 

1. Press Ctrl+Alt+S to open the IDE settings and select Appearance & Behavior | Path Variables.
2. 按下Ctrl+Alt+S打开IDE设置，选择外观与行为 | 路径变量。
3. Add the names that GoLand shouldn't consider to be path variables to the Ignored Variables field.
4. 将GoLand不应将其视为路径变量的名称添加到“忽略的变量”字段中。
5. Click OK to apply the changes.
6. 点击确定以应用更改。

## 示例：创建新的路径变量 Example: creating a new path variable﻿

https://www.jetbrains.com/help/go/absolute-path-variables.html#example

You may have a library that is located outside your project directory. This library is attached to your project, and the path to this library is included in the **.iml** file of your project. However, this path should not be absolute, because the location on this library may be different on your teammates' computers. In this case, you can create the `PATH_TO_LIB` variable:

您可能有一个位于项目目录之外的库。该库已附加到您的项目中，并且该库的路径包含在项目的**.iml**文件中。然而，此路径不应为绝对路径，因为此库在团队成员计算机上的位置可能不同。在这种情况下，您可以创建`PATH_TO_LIB`变量： 

1. Press Ctrl+Alt+S to open the IDE settings and select Appearance & Behavior | Path Variables.
2. 按下Ctrl+Alt+S打开IDE设置，选择外观与行为 | 路径变量。
3. Click 点击![the Add button](PathVariables_img/app.general.add.svg).
4. In the Add Variable dialog, type the `PATH_TO_LIB` variable, and its value that points to the library location on your disk.
5. 在“添加变量”对话框中，输入`PATH_TO_LIB`变量和其在磁盘上指向库位置的值。
6. Share the **.iml** file through your version control system.
7. 通过版本控制系统共享**.iml**文件。
8. After your teammates update their projects from VCS, they will change the `PATH_TO_LIB` variable value so that it points to the library location on their computers.
9. 在团队成员从版本控制系统更新其项目后，他们将更改`PATH_TO_LIB`变量的值，以使其指向其计算机上的库位置。