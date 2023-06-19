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

5. On the Configuration tab, you can set the following options:

   - Run kind: a building scope for your application. File and Package scopes work similarly in tests and compilation/running configurations (in terms of the scope they cover).

     - Directory: build an application in the specified directory as a package, without processing any subdirectories.

       For test configurations, GoLand runs all the tests in the specified directory and all its subdirectories.

     - File: build an application from files specified in the Files field. To pass multiple file paths, use the vertical bar (`|`) as a delimiter. This configuration is automatically selected when you run your program from scratch files.

     - Package: build a single package with all its dependencies. Specify a full import path to the package that you want to build in the Package path field (for example, `github.com/gorilla/mux`). This configuration is automatically selected when you run the `main` function or a separate test by using the Run Application icon (![the Run button](index_img/app.actions.execute.svg)) in the gutter.

   - Package path: a full import path of the package that you want to compile (for example, `github.com/gorilla/mux`). This field is available only when you select the Package run kind.

     You can press Ctrl+Space to see a list of available packages.

     ![Autocompletion for the Package path field](index_img/go_package_path_list_of_packages.png)

   - Output directory: a path to a directory where you want to output the executable file.

   - Run after build: execute the application after the build.

   - Redirect input from: a file to read the input from.

   - Working directory: a directory that is used for the built application. If you have any code that creates relative files or directories, they will be relative to this directory.

   - Environment: environment variables for your application.

     To edit environment variables, click the Browse button at the end of the field. In the Environment Variables dialog, click the Add button and add the environment variables that you need.

     ![Add an environment variable](index_img/go_add_environment_variable.png)

   - Go tool arguments: arguments for the go tool (for example, `-o`). Also, you can use macros in this field.

   - Use all custom build tags: all tags that are applied during the build. Tags are listed in settings Ctrl+Alt+S under Go | Build Tags & Vendoring.

   - Program arguments: arguments for the built application. Also, you can use macros in this field.

   - Run with sudo: run the application with elevated privileges.

   - Module: name of the current module.

   - Before launch: add tasks that you want to launch before the launch of the selected run/debug configuration. To add a task click the Add button Alt+Insert and select the tool that you want to add.

   - Store as project file: Enable this option to save your configuration as a project file and share it with team members through [VCS](https://www.jetbrains.com/help/go/version-control-integration.html).

6. In the Before launch section, define whether you want to perform any specific actions before launching the application, for example, launch an [external tool](https://www.jetbrains.com/help/go/configuring-third-party-tools.html) or another build configuration before run. To skip the build stage, remove Build from the Before launch list .

7. Apply the changes and close the dialog.

### Templates for tests and benchmarks﻿

Templates for Go tests work the same way as templates for Go applications (Go Build). But instead of selecting Go Build, you should select Go Test.

### Run/debug configuration templates for tests﻿

1. Navigate to Run | Edit Configurations.

2. In the Run/Debug Configurations dialog, click Add New Configuration Alt+Insert and select Go Test.

3. From the Test kind list, select the scope from which you want to run tests:

   - Directory: to run all the tests in the specified directory. In the Directory field, specify a path to a directory that includes an application file and a test file (for example, **applicationFolder/** with **main.go** and **main_test.go**).

   - Package: to run all the tests that belong to a package. In the Package path field, select a path to the package with tests that you want to run (for example, `github.com/rcrowley/go-metrics`).

     To enable package tests, open setting by pressing Ctrl+Alt+S, navigate to Go | Go modules, and select the Enable Go modules integration checkbox.

   - File: to run all tests from a testing file. In the Files field, type a path to a testing file.

     Ensure that the Files field does not include other paths.

4. (Optional) Also, you can specify the following settings:

   - Pattern: a regular expression that defines what tests to run. GoLand will run only those tests, examples, and fuzz tests that match the regular expression. For tests, the regular expression is split by unbracketed slash (/) characters into a sequence of regular expressions, and each part of a test's identifier must match the corresponding element in the sequence, if any.

   - Working directory: a directory that is used for the built application. If you have any code that creates relative files or directories, they will be relative to this directory.

   - Output directory: directory that stores your test results if any.

   - Run after build: execute a test after the build.

   - Redirect input from: a path to the file that will to take program input instead of the console.

   - Working directory: directory that is used for the built application. If you have any code that creates relative files or directories, they will be relative to this directory.

   - Environment: environment variables that you need to run the test.

     To edit environment variables, click the Browse button at the end of the field. In the Environment Variables dialog, click the Add button and add the environment variables that you need.

     ![Add an environment variable](index_img/go_add_environment_variable.png)

   - Go tool arguments: arguments for the go tool (for example, `-tags`).

   - Use all custom build tags: all tags that are applied during the build. Tags are listed in settings Ctrl+Alt+S under Go | Build Tags & Vendoring.

   - Program arguments: arguments for the test.

   - Run with sudo: grant sudo privileges to the test.

   - Before launch: Activate tool window: add tasks that you want to launch before the launch of the selected run/debug configuration. To add a task, click the Add button Alt+Insert and select the tool that you want to add.

5. Click Apply.

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_create_test_for_package.png](index_img/go_create_test_for_package.animated.gif)

## Share run/debug configurations﻿

If you are working in a team, you might want to share your run/debug configurations so that your teammates could run the application using the same configuration or enable them to remotely attach to the process you are running.

For these purposes, GoLand provides a mechanism to store your run/debug configurations as project files and share them through VCS. The same mechanism can also be used when you want to send your configuration as a file to someone else. This saves a lot of time as run/debug configurations sometimes get sophisticated, and keeping them in sync manually would be tedious and error-prone.

1. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.

2. Select the run/debug configuration you want to share, enable the Store as project file option, and specify the location where the configuration file will be stored.

   If compatibility with GoLand 2019.3 and earlier is required, store the file in the default location.

   ![Store as project file box](index_img/go_rdconfigs_share.png)

3. (Optional) If the **.idea** directory is added to VCS ignored files, the **.idea/runConfigurations** subfolder will be ignored, too. If you use Git for your project, you can share **.idea/runConfigurations** only and leave **.idea** ignored by modifying **.gitignore** as follows:

   ```none
   /.idea/*
   !/.idea/runConfigurations
   ```

   


> Turning on the Store as project file option does not submit anything to the VCS for you. For run/debug configurations to make their way to a shared repository, you have to check them in like other versioned files.
>
> To learn how to import run/debug configurations from VCS, refer to the [Version control](https://www.jetbrains.com/help/go/version-control-integration.html) section.

## Run/debug configuration templates﻿

All run/debug configurations are based on templates, which implement the startup logic, define the list of parameters and their default values. The [list of available templates](https://www.jetbrains.com/help/go/list-of-run-debug-configurations.html) is predefined in the installation and can only be extended via [plugins](https://www.jetbrains.com/help/go/managing-plugins.html). However, you can edit default parameter values in each template to streamline the setup of new run/debug configurations.


> Changing the default values of a template does not affect already existing run/debug configurations.

### Configure the default values for a template﻿

1. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.

2. In the left-hand pane of the run/debug configuration dialog, click Edit configuration templates….

3. In the Run/Debug Configuration Templates dialog that opens, select a configuration type.

4. Specify the desired default parameters and click OK to save the template.

   ![Changing Run/debug templates](index_img/go_change_run_debug_defaults.png)

## Run/debug configuration folders﻿

When there are many run/debug configurations of the same type, you can group them in folders so they become easier to distinguish visually.

Once grouped, the run/debug configurations appear in the list under the corresponding folders.

### Create a folder for run/debug configurations﻿

1. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.
2. In the Run/Debug Configurations dialog, select a configuration type and click ![the New Folder icon](index_img/app.actions.newFolder.svg) on the toolbar. A new empty folder for the selected type is created.
3. Specify the folder name in the text field to the right or accept the default name.
4. Select the desired run/debug configurations and move them under the target folder.
5. Apply the changes. If a folder is empty, it will not be saved.

When you no longer need a folder, you can delete it Delete. The run/debug configurations grouped under this folder will be moved under the root of the corresponding run/debug configuration type.