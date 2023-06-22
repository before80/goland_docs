+++
title = "运行"
linkTitle = "运行"
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
[menu.main]
    weight = 10
+++
# Running﻿

https://www.jetbrains.com/help/go/running-applications.html#split_tabs_in_the_run_tool_window

Last modified: 25 April 2023

​	当你运行、调试或测试你的代码时，GoLand 会创建一个临时的运行和调试配置。这个配置包括了你想要执行操作的所有细节，通常情况下，一个临时的配置就足以运行或调试你的代码。你可以使用这个临时的配置运行你的程序一次或者保存它以备将来使用。  

​	根据你的需要，你可以编辑现有的配置或者创建新的配置。要了解有关编辑配置的更多信息，请参见[运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html)。 


> ​	如果在[运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configurations-dialog.html)中启用了在运行之前启动工具的选项，GoLand 会运行这些工具，在成功运行后再运行你的应用程序。否则，程序会立即启动。  

### 创建运行/调试配置 

1. 按以下任意一种方式打开运行/调试配置对话框：  

   - 从主菜单中选择 Run | Edit Configurations。 
   - 在[导航栏](https://www.jetbrains.com/help/go/guided-tour-around-the-user-interface.html#navigation-bar)（View | Appearance | Navigation Bar）中选择 Edit Configurations。  
   - 按 `Alt+Shift+F10`，然后按 `0`。

2. 在[运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configurations-dialog.html) 对话框中，单击工具栏上的**Add New Configuration**图标（![the Add New Configuration icon](index_img/app.general.add.svg)），或按`Alt+Insert`。列表显示了默认的运行/调试配置。选择所需的配置类型（例如，Go build)。

   在右侧面板中显示出所选配置类型的默认设置。 

   - 运行类型（Run kind）：应用程序的构建范围。在测试和编译/运行配置中，文件（File）和软件包（Package）范围的工作方式类似（就其覆盖范围而言）。 

     - 目录（Directory）：在指定的目录中构建应用程序作为一个包，而不处理任何子目录。 

       对于测试配置，GoLand 运行指定目录及其所有子目录中的所有测试。

     - 文件（File）：从指定 Files 字段中的文件中构建应用程序。要传递多个文件路径，请使用竖线（`|`）作为分隔符。当你从头开始运行程序时，这个配置会被自动选择。 

     - 软件包（Package）：构建一个包及其所有依赖项。在软件包路径（Package path）字段中指定要构建的包的完整导入路径（例如，`github.com/gorilla/mux`）。当你使用 沟槽中的 Run 图标（![the Run button](index_img/app.actions.execute.svg))运行`main`函数或单独的测试时，这个配置也会被自动选择。 

   - 软件包路径（Package path）：要编译的软件包的完整导入路径（例如，`github.com/gorilla/mux`）。只有在选择**软件包运行类型**时才可用。 

     ​     您可以按`Ctrl+Space`查看可用软件包列表。  

     

     ![Autocompletion for the Package path field](index_img/go_package_path_list_of_packages.png)

   - 输出目录（Output directory）：可执行文件的目录。 

   - 编译后运行（Run after build）：在构建后运行该应用程序。

   - 工作目录（Working directory）：用于构建应用程序的目录。如果有任何创建相对文件或目录的代码，则它们将相对于此目录。 

   - 环境（Environment）：应用程序的环境变量。 

     ​     要编辑环境变量，请单击字段末尾的 Browse 按钮。在**环境变量**对话框中，单击**Add**按钮并添加所需的环境变量。  

     ![Add an environment variable](index_img/go_add_environment_variable.png)

   - Go 工具实参（Go tool arguments）：go 工具的实参（例如，`-o`）。此字段中也可以使用宏。

   - 使用所有自定义构建标记（Use all custom build tags）：应用于该构建的所有标记。在设置（`Ctrl+Alt+S`）下，**Go | Build Tags & Vendoring**中列出了这些标记。 

   - 程序实参（Program arguments）：该构建应用程序的实参。此字段中也可以使用宏。 

   - 使用 sudo 运行（Run with sudo）：为该应用程序授予sudo权限。 

   - 模块（Module）：当前模块的名称。 

   - 在启动之前（Before launch）：添加你想要在选定的运行/调试配置启动之前启动的任务。要添加任务，请单击 Add 按钮`Alt+Insert`并选择要添加的工具。 

   - 存储为项目文件（Store as project file）：启用此选项以将你的配置保存为项目文件，并通过[VCS](https://www.jetbrains.com/help/go/version-control-integration.html)与团队成员共享。 

3. **应用**更改并关闭对话框。

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_run_configuration_settings.png](index_img/go_run_configuration_settings.animated.gif)


### ﻿使用左边沟槽中的图标

​	在编辑器左边的沟槽中，点击**Run Application**图标 ![the Run Application icon](index_img/app.actions.execute_dark.svg)，然后选择 `Run <method_name> in <file_name>`即可运行应用程序。  

![Using the icon in the left gutter](index_img/go_run_application_using_gutter_icon.png)



### 使用内容上下文

​	你也可以右键单击编辑器中的文件或方法，然后选择`Run <method_name> in <file_name> Ctrl+Shift+F10` 来运行应用程序。  

![Using the context menu](index_img/go_run_application_context_menu.png)



### 重新运行应用程序

​	如果在[运行](https://www.jetbrains.com/help/go/run-tool-window.html)窗口中仍然打开了一个应用程序的选项卡，您可以重新运行该应用程序。程序将以初始设置重新运行。 

1. 在运行窗口中，选择所需应用程序所在的选项卡。
2. 在工具栏中，单击重新运行按钮 ![Rerun console](index_img/rerunConsole.png)，或按下Ctrl+F5。
3. 在通知对话框中，单击Stop and rerun。

![Rerun an application](index_img/go_rerun_application.png)


> ​	如果你希望重新运行应用程序，但不失去正在编辑的标签页的焦点，请按Shift+F10。  

### 停止应用程序

- 要停止应用程序，请点击工具栏上的Stop 按钮 ![App actions suspend](index_img/app.actions.suspend.svg) 或按Ctrl+F2。你也可以在运行工具窗口中单击Stop 按钮。  

  ![Stop an application](index_img/go_stop_application.png)


### 查看正在运行的应用程序

- 你可以选择Run | Show Running List查看当前正在运行的应用程序列表。如果没有应用程序处于活动状态，则这个命令是灰色的。  

  ![View running applications](index_img/go_show_running_list.png)


### 拆分运行工具窗口中的选项卡

- 如果你有多个配置同时运行并且需要查看所有这些运行的结果，你可以通过将选项卡拖放到运行工具窗口内部的突出显示区域来拆分窗口。要取消拆分窗口，请右键单击顶部窗格并从上下文菜单中选择取消拆分（Unsplit ）。

  ![https://resources.jetbrains.com/help/img/idea/2023.1/go_split_tabs_in_the_run_tool_window.png](_index_img/go_split_tabs_in_the_run_tool_window.animated.gif)
