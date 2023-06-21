+++
title = "运行/调试配置"
weight = 10
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Run/debug configurations﻿ 运行/调试配置

https://www.jetbrains.com/help/go/run-debug-configuration.html#config-folders

Last modified: 04 May 2023

最后修改：2023年5月4日

Configure: Run | Edit Configurations

GoLand uses run/debug configurations to run, debug, and test your code. Each configuration is a named set of startup properties that define what to execute and what parameters and environment should be used.

​	GoLand使用运行/调试配置来运行、调试和测试您的代码。每个配置都是一组命名的启动属性，用于定义要执行的内容、使用的参数和环境。

There are two types of run/debug configurations:

​	有两种类型的运行/调试配置：

 

- Temporary — created every time you run or debug functions or tests.
- Permanent — created explicitly from a template or by saving a temporary configuration. Permanent configurations remain as part of your project until you remove them.
- 临时配置 —— 每次运行或调试函数或测试时都会创建。
- 永久配置 —— 通过从模板创建或保存临时配置来显式创建。永久配置将作为项目的一部分存在，直到您将其删除。

So whenever you run/debug or test your code, GoLand either uses an existing permanent run/debug configuration or creates a new temporary one.

​	因此，每当您运行/调试或测试代码时，GoLand要么使用现有的永久运行/调试配置，要么创建一个新的临时配置。

Permanent configurations have opaque icons while the icons of temporary configurations are semi-transparent.

​	永久配置具有不透明的图标，而临时配置的图标是半透明的。

The maximum number of temporary configurations is 5. The older ones are automatically deleted when new ones are added. If necessary, you can increase this limit in Settings | Advanced Settings | IDE | Temporary configurations limit.

​	临时配置的最大数量为5。当添加新配置时，旧的配置将自动删除。如果需要，您可以在"设置" | "高级设置" | "IDE" | "临时配置限制"中增加此限制。

![Permanent and temporary configurations have different icons](index_img/go_rdconfigslist_temporary.png)

## 创建永久运行/调试配置 Create permanent run/debug configurations﻿

GoLand provides the following ways to create a permanent run/debug configuration:

​	GoLand提供以下方法来创建永久运行/调试配置：

 

- [Save a temporary run/debug configuration as permanent](https://www.jetbrains.com/help/go/run-debug-configuration.html#save-as-permanent).
- [Create from a template](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly) or copy an existing configuration.
- [将临时运行/调试配置另存为永久配置](https://www.jetbrains.com/help/go/run-debug-configuration.html#save-as-permanent)。
- [从模板创建](https://www.jetbrains.com/help/go/run-debug-configuration.html#createExplicitly)或复制现有配置。

### 将临时配置另存为永久配置 Save a temporary configuration as permanent﻿

- Select a temporary configuration in the run/debug configuration switcher and then click Save Configuration.

- 在运行/调试配置切换器中选择临时配置，然后点击"保存配置"。

  ![Save a temporary run configuration](index_img/go_save_temporary.png)

- Alternatively, select a temporary configuration in the Run/debug configurations dialog and click 或者，在"运行/调试配置"对话框中选择临时配置，然后在工具栏上点击![Save](index_img/app.actions.menu-saveall.svg) on the toolbar.

GoLand provides run/debug configuration [templates](https://www.jetbrains.com/help/go/run-debug-configuration.html#templates) for different languages, tools, and frameworks. The list of available templates varies depending on the installed and enabled [plugins](https://www.jetbrains.com/help/go/managing-plugins.html).

​	GoLand为不同的语言、工具和框架提供运行/调试配置[模板](https://www.jetbrains.com/help/go/run-debug-configuration.html#templates)。可用模板的列表取决于安装和启用的[插件](https://www.jetbrains.com/help/go/managing-plugins.html)。

### 从模板创建运行/调试配置 Create a run/debug configuration from a template﻿

1. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.

2. 从主菜单中选择运行 | 编辑配置。或者按Alt+Shift+F10，然后按0。

3. In the Run/Debug Configuration dialog, click 在"运行/调试配置"对话框中，点击工具栏上的![App general add](index_img/app.general.add.svg) on the toolbar or press Alt+Insert. The list shows the run/debug configuration templates. Select Go build.或按Alt+Insert。列表中显示运行/调试配置模板。选择"Go build"。

4. Specify the run/debug configuration name in the Name field. This name will be shown in the list of the available run/debug configurations.

5. 在"名称"字段中指定运行/调试配置的名称。此名称将显示在可用的运行/调试配置列表中。

6. On the Configuration tab, you can set the following options:

7. 在"配置"选项卡上，您可以设置以下选项：

   - Run kind: a building scope for your application. File and Package scopes work similarly in tests and compilation/running configurations (in terms of the scope they cover).

   - 运行类型：应用程序的构建范围。文件和包范围在测试和编译/运行配置中的工作方式类似（就其覆盖的范围而言）。

     - Directory: build an application in the specified directory as a package, without processing any subdirectories.

     - 目录：在指定的目录中将应用程序作为包进行构建，而不处理任何子目录。

       For test configurations, GoLand runs all the tests in the specified directory and all its subdirectories.

       对于测试配置，GoLand会运行指定目录及其所有子目录中的所有测试。

     - File: build an application from files specified in the Files field. To pass multiple file paths, use the vertical bar (`|`) as a delimiter. This configuration is automatically selected when you run your program from scratch files.

     - 文件：从在"文件"字段中指定的文件构建应用程序。要传递多个文件路径，请使用竖线(`|`)作为分隔符。当您从头开始运行程序时，会自动选择此配置。

     - Package: build a single package with all its dependencies. Specify a full import path to the package that you want to build in the Package path field (for example, `github.com/gorilla/mux`). This configuration is automatically selected when you run the `main` function or a separate test by using the Run Application icon ( 包：构建一个带有所有依赖项的单个包。在"包路径"字段中指定要构建的包的完整导入路径（例如，`github.com/gorilla/mux`）。当您使用gutter中的运行应用程序图标（![the Run button](index_img/app.actions.execute.svg)) in the gutter.）运行"main"函数或单独的测试时，会自动选择此配置。

   - Package path: a full import path of the package that you want to compile (for example, `github.com/gorilla/mux`). This field is available only when you select the Package run kind.

   - 包路径：要编译的包的完整导入路径（例如，`github.com/gorilla/mux`）。仅当选择"包"运行类型时，此字段可用。

     You can press Ctrl+Space to see a list of available packages.

     您可以按Ctrl+Space键查看可用包的列表。

     ![Autocompletion for the Package path field](index_img/go_package_path_list_of_packages.png)

   - Output directory: a path to a directory where you want to output the executable file.

   - 输出目录：要输出可执行文件的路径。

   - Run after build: execute the application after the build.

   - 构建后运行：在构建后执行应用程序。

   - Redirect input from: a file to read the input from.

   - 重定向输入自：从文件中读取输入。

   - Working directory: a directory that is used for the built application. If you have any code that creates relative files or directories, they will be relative to this directory.

   - 工作目录：用于构建应用程序的目录。如果您有任何创建相对文件或目录的代码，它们将相对于此目录。

   - Environment: environment variables for your application.

   - 环境：应用程序的环境变量。

     To edit environment variables, click the Browse button at the end of the field. In the Environment Variables dialog, click the Add button and add the environment variables that you need.

     要编辑环境变量，请点击字段末尾的"浏览"按钮。在"环境变量"对话框中，点击"添加"按钮并添加所需的环境变量。

     ![Add an environment variable](index_img/go_add_environment_variable.png)

   - Go tool arguments: arguments for the go tool (for example, `-o`). Also, you can use macros in this field.

   - Go工具参数：go工具的参数（例如，`-o`）。您还可以在此字段中使用宏。

   - Use all custom build tags: all tags that are applied during the build. Tags are listed in settings Ctrl+Alt+S under Go | Build Tags & Vendoring.

   - 使用所有自定义构建标签：在构建过程中应用的所有标签。标签在设置（Ctrl+Alt+S）下的Go | 构建标签和供应商中列出。

   - Program arguments: arguments for the built application. Also, you can use macros in this field.

   - 程序参数：构建应用程序的参数。您也可以在此字段中使用宏。

   - Run with sudo: run the application with elevated privileges.

   - 使用sudo运行：以提升的权限运行应用程序。

   - Module: name of the current module.

   - 模块：当前模块的名称。

   - Before launch: add tasks that you want to launch before the launch of the selected run/debug configuration. To add a task click the Add button Alt+Insert and select the tool that you want to add.

   - 在启动前：添加要在选择的运行/调试配置启动之前启动的任务。点击"添加"按钮（Alt+Insert），然后选择要添加的工具。

   - Store as project file: Enable this option to save your configuration as a project file and share it with team members through [VCS](https://www.jetbrains.com/help/go/version-control-integration.html).

   - 存储为项目文件：启用此选项将运行/调试配置保存为项目文件，并通过[VCS](https://www.jetbrains.com/help/go/version-control-integration.html)与团队成员共享。

8. In the Before launch section, define whether you want to perform any specific actions before launching the application, for example, launch an [external tool](https://www.jetbrains.com/help/go/configuring-third-party-tools.html) or another build configuration before run. To skip the build stage, remove Build from the Before launch list .

9. 在"启动前"部分，定义在启动应用程序之前是否要执行任何特定操作，例如，在运行之前启动[外部工具](https://www.jetbrains.com/help/go/configuring-third-party-tools.html)或另一个构建配置。要跳过构建阶段，请从"启动前"列表中删除"构建"。

10. Apply the changes and close the dialog.

11. 应用更改并关闭对话框。

### 测试和基准测试的模板 Templates for tests and benchmarks﻿

Templates for Go tests work the same way as templates for Go applications (Go Build). But instead of selecting Go Build, you should select Go Test.

Go测试的模板与Go应用程序的模板（Go构建）相同。但是，您应该选择"Go测试"而不是"Go构建"。

### 用于测试的运行/调试配置模板 Run/debug configuration templates for tests﻿

1. Navigate to Run | Edit Configurations.

2. 导航到Run | Edit Configurations。

3. In the Run/Debug Configurations dialog, click Add New Configuration Alt+Insert and select Go Test.

4. 在Run/Debug Configurations对话框中，点击"添加新配置"（Alt+Insert），然后选择"Go测试"。

5. From the Test kind list, select the scope from which you want to run tests:

6. 在"测试类型"列表中，选择要运行测试的范围：

   - Directory: to run all the tests in the specified directory. In the Directory field, specify a path to a directory that includes an application file and a test file (for example, **applicationFolder/** with **main.go** and **main_test.go**).

   - 目录：运行指定目录中的所有测试。在"目录"字段中，指定包括应用程序文件和测试文件的目录的路径（例如，**applicationFolder/**，其中包括**main.go**和**main_test.go**）。

   - Package: to run all the tests that belong to a package. In the Package path field, select a path to the package with tests that you want to run (for example, `github.com/rcrowley/go-metrics`).

   - 包：运行属于某个包的所有测试。在"包路径"字段中，选择要运行测试的包的路径（例如，`github.com/rcrowley/go-metrics`）。

     To enable package tests, open setting by pressing Ctrl+Alt+S, navigate to Go | Go modules, and select the Enable Go modules integration checkbox.

     要启用包测试，请按Ctrl+Alt+S打开设置，导航到Go | Go模块，然后选中"启用Go模块集成"复选框。

   - File: to run all tests from a testing file. In the Files field, type a path to a testing file.

   - 文件：运行测试文件中的所有测试。在"文件"字段中输入测试文件的路径。

     Ensure that the Files field does not include other paths.
     
     确保"文件"字段不包含其他路径。

7. (Optional) Also, you can specify the following settings:

8. （可选）您还可以指定以下设置：

   - Pattern: a regular expression that defines what tests to run. GoLand will run only those tests, examples, and fuzz tests that match the regular expression. For tests, the regular expression is split by unbracketed slash (/) characters into a sequence of regular expressions, and each part of a test's identifier must match the corresponding element in the sequence, if any.

   - 模式：定义要运行的测试的正则表达式。GoLand将仅运行与正则表达式匹配的测试、示例和模糊测试。对于测试，正则表达式通过未加括号的斜杠（/）字符分隔为一系列正则表达式，如果有的话，测试标识符的每个部分必须与序列中的相应元素匹配。

   - Working directory: a directory that is used for the built application. If you have any code that creates relative files or directories, they will be relative to this directory.

   - 工作目录：用于构建应用程序的目录。如果您的代码中有创建相对文件或目录的代码，它们将相对于此目录。

   - Output directory: directory that stores your test results if any.

   - 输出目录：存储测试结果的目录（如果有）。

   - Run after build: execute a test after the build.

   - 构建后运行：构建后执行测试。

   - Redirect input from: a path to the file that will to take program input instead of the console.

   - 重定向输入自：用于读取程序输入的文件路径。

   - Working directory: directory that is used for the built application. If you have any code that creates relative files or directories, they will be relative to this directory.

   - 工作目录：用于构建应用程序的目录。如果您的代码中有创建相对文件或目录的代码，它们将相对于此目录。

   - Environment: environment variables that you need to run the test.

   - 环境：运行测试所需的环境变量。

     To edit environment variables, click the Browse button at the end of the field. In the Environment Variables dialog, click the Add button and add the environment variables that you need.

     要编辑环境变量，请点击字段末尾的"浏览"按钮。在"环境变量"对话框中，点击"添加"按钮，然后添加所需的环境变量。

     ![Add an environment variable](index_img/go_add_environment_variable.png)

   - Go tool arguments: arguments for the go tool (for example, `-tags`).

   - Go工具参数：go工具的参数（例如，`-tags`）。

   - Use all custom build tags: all tags that are applied during the build. Tags are listed in settings Ctrl+Alt+S under Go | Build Tags & Vendoring.

   - 使用所有自定义构建标签：构建过程中使用的所有标签。标签在设置（Ctrl+Alt+S）下的Go | 构建标签和供应商中列出。

   - Program arguments: arguments for the test.

   - 程序参数：测试的参数。

   - Run with sudo: grant sudo privileges to the test.

   - 使用sudo运行：授予测试sudo权限。

   - Before launch: Activate tool window: add tasks that you want to launch before the launch of the selected run/debug configuration. To add a task, click the Add button Alt+Insert and select the tool that you want to add.

   - 在启动前：激活工具窗口：添加要在选择的运行/调试配置启动之前启动的任务。点击"添加"按钮（Alt+Insert），然后选择要添加的工具。

9. 点击 Apply.

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_create_test_for_package.png](index_img/go_create_test_for_package.animated.gif)

## 共享运行/调试配置 Share run/debug configurations﻿

If you are working in a team, you might want to share your run/debug configurations so that your teammates could run the application using the same configuration or enable them to remotely attach to the process you are running.

如果您在团队中工作，可能希望共享您的运行/调试配置，以便您的团队成员可以使用相同的配置运行应用程序，或者使他们能够远程连接到您正在运行的进程。

For these purposes, GoLand provides a mechanism to store your run/debug configurations as project files and share them through VCS. The same mechanism can also be used when you want to send your configuration as a file to someone else. This saves a lot of time as run/debug configurations sometimes get sophisticated, and keeping them in sync manually would be tedious and error-prone.

为此，GoLand提供了一种机制，可以将运行/调试配置存储为项目文件，并通过VCS进行共享。当您想将配置作为文件发送给其他人时，也可以使用相同的机制。这样可以节省很多时间，因为运行/调试配置有时会变得复杂，手动保持它们的同步将很繁琐且容易出错。

1. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.

2. 从主菜单中选择"运行" | "编辑配置"。或者按Alt+Shift+F10，然后按0。

3. Select the run/debug configuration you want to share, enable the Store as project file option, and specify the location where the configuration file will be stored.

4. 选择要共享的运行/调试配置，启用"存储为项目文件"选项，并指定配置文件的存储位置。

   If compatibility with GoLand 2019.3 and earlier is required, store the file in the default location.

   如果需要与GoLand 2019.3及更早版本兼容，将文件存储在默认位置。

   ![Store as project file box](index_img/go_rdconfigs_share.png)

5. (Optional) If the **.idea** directory is added to VCS ignored files, the **.idea/runConfigurations** subfolder will be ignored, too. If you use Git for your project, you can share **.idea/runConfigurations** only and leave **.idea** ignored by modifying **.gitignore** as follows:

6. （可选）如果已将**.idea**目录添加到VCS的忽略文件中，则**.idea/runConfigurations**子文件夹也将被忽略。如果您使用的是git作为VCS，您可以按照以下步骤进行操作：

   ```none
   /.idea/*
   !/.idea/runConfigurations
   ```

   



> Turning on the Store as project file option does not submit anything to the VCS for you. For run/debug configurations to make their way to a shared repository, you have to check them in like other versioned files.
>
> ​	启用"存储为项目文件"选项不会自动提交到版本控制系统（VCS）。为了使运行/调试配置进入共享的存储库，您需要像其他版本化文件一样将它们进行提交。
>
> To learn how to import run/debug configurations from VCS, refer to the [Version control](https://www.jetbrains.com/help/go/version-control-integration.html) section.
>
> ​	要了解如何从VCS导入运行/调试配置，请参考[版本控制](https://www.jetbrains.com/help/go/version-control-integration.html)部分。

## 运行/调试配置模板 Run/debug configuration templates﻿

All run/debug configurations are based on templates, which implement the startup logic, define the list of parameters and their default values. The [list of available templates](https://www.jetbrains.com/help/go/list-of-run-debug-configurations.html) is predefined in the installation and can only be extended via [plugins](https://www.jetbrains.com/help/go/managing-plugins.html). However, you can edit default parameter values in each template to streamline the setup of new run/debug configurations.

​	所有运行/调试配置都基于模板，模板实现了启动逻辑，定义了参数列表及其默认值。[可用模板列表](https://www.jetbrains.com/help/go/list-of-run-debug-configurations.html)在安装过程中预定义，并且只能通过[插件](https://www.jetbrains.com/help/go/managing-plugins.html)进行扩展。但是，您可以编辑每个模板中的默认参数值，以简化新运行/调试配置的设置。


> Changing the default values of a template does not affect already existing run/debug configurations.
>
> ​	更改模板的默认值不会影响已存在的运行/调试配置。

### 配置模板的默认值 Configure the default values for a template﻿

1. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.

2. In the left-hand pane of the run/debug configuration dialog, click Edit configuration templates….

3. In the Run/Debug Configuration Templates dialog that opens, select a configuration type.

4. Specify the desired default parameters and click OK to save the template.

5. 从主菜单中选择Run | Edit Configurations。或者按Alt+Shift+F10，然后按0。

6. 在运行/调试配置对话框的左侧窗格中，点击Edit configuration templates…。

7. 在打开的Run/Debug Configuration Templates对话框中，选择配置类型。

8. 指定所需的默认参数，并点击OK 保存模板。

   ![Changing Run/debug templates](index_img/go_change_run_debug_defaults.png)

## 运行/调试配置文件夹 Run/debug configuration folders﻿

When there are many run/debug configurations of the same type, you can group them in folders so they become easier to distinguish visually.

当存在多个相同类型的运行/调试配置时，您可以将它们分组到文件夹中，以便更容易在视觉上区分。

Once grouped, the run/debug configurations appear in the list under the corresponding folders.

一旦分组，运行/调试配置将显示在相应文件夹下的列表中。

### 创建运行/调试配置文件夹 Create a folder for run/debug configurations﻿

1. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.
2. 从主菜单中选择"运行" | "编辑配置"。或者按Alt+Shift+F10，然后按0。
3. In the Run/Debug Configurations dialog, select a configuration type and click 在"运行/调试配置"对话框中，选择配置类型，并点击工具栏上的![the New Folder icon](index_img/app.actions.newFolder.svg) on the toolbar. A new empty folder for the selected type is created.。将创建一个新的空文件夹。
4. Specify the folder name in the text field to the right or accept the default name.
5. 在右侧的文本字段中指定文件夹名称，或接受默认名称。
6. Select the desired run/debug configurations and move them under the target folder.
7. 选择所需的运行/调试配置，并将它们移动到目标文件夹下。
8. Apply the changes. If a folder is empty, it will not be saved.
9. 应用更改。如果文件夹为空，则不会保存该文件夹。

When you no longer need a folder, you can delete it Delete. The run/debug configurations grouped under this folder will be moved under the root of the corresponding run/debug configuration type.

​	当您不再需要一个文件夹时，可以删除它。分组在该文件夹下的运行/调试配置将移动到相应运行/调试配置类型的根目录下。