+++
title = "运行目标"
weight = 50
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Run targets﻿ 运行目标

https://www.jetbrains.com/help/go/run-targets.html

Last modified: 03 April 2023

上次修改日期：2023年4月3日

You can run your code in another environment such as cloud or a Docker container directly from GoLand.

​	您可以直接从GoLand中在另一个环境（如云端或Docker容器）中运行代码。

For certain [run/debug configurations](https://www.jetbrains.com/help/go/run-debug-configuration.html), you can run your code in another environment such as cloud or a [Docker](https://www.jetbrains.com/help/go/docker.html) container directly from GoLand.

​	对于某些[运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html)，您可以直接从GoLand中在另一个环境（如云端或[Docker](https://www.jetbrains.com/help/go/docker.html)容器）中运行代码。

This feature allows you to instantly test the changes against the real environment the app is intended for. This ensures that there will be no incompatibilities when moving to production, which is especially important when working on code that heavily depends on the environment.

​	这个功能允许您立即对变更进行测试，以确保应用程序在实际环境中运行时没有不兼容性。这在处理严重依赖于环境的代码时尤为重要。

Running the app directly in such environment also spares you the extra actions normally required to deploy and run the app every time something changes.

​	直接在这样的环境中运行应用程序还可以省去部署和运行应用程序所需的额外操作，每次有变更时都要执行这些操作。

The environment that is used for running the app is referred to as target. For GoLand to run code on a target, the target has to define a language runtime, which represents something on the target that can be used by a run/debug configuration to run code.

​	用于运行应用程序的环境称为目标。为了让GoLand在目标上运行代码，目标必须定义一种语言运行时，该运行时代表目标上可以被运行/调试配置用于运行代码的内容。

In order to run your code on a target, all you need is to define the target execution environment in the [run/debug configuration](https://www.jetbrains.com/help/go/run-debug-configuration.html) that you would normally use for local run. After you have done that, launching the app on a target is no different than launching it locally.

​	为了在目标上运行您的代码，您只需要在您通常用于本地运行的[运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html)中定义目标执行环境。完成这一步后，将应用程序在目标上启动与在本地启动没有任何区别。

You can run several configurations on the same target. It is possible to set a project-wide default run target.

​	您可以在同一个目标上运行多个配置。还可以设置项目范围的默认运行目标。

### 设置项目的默认目标 Set a default target for a project﻿

1. Click Run | Manage Targets.

2. From the Project default target list, select a target that you want to use for your project.

3. 点击Run | Manage Targets。

4. 从Project default target列表中选择要在项目中使用的目标。

   ![Set a default target for a project](RunTargets_img/go_set_a_default_target_for_a_project.png)

## 支持的运行/调试配置类型 Supported run/debug configuration types﻿

The following [run/debug configurations](https://www.jetbrains.com/help/go/run-debug-configuration.html) can run on a remote target:

​	以下[运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html)可以在远程目标上运行： 

- Go Build
- Go Test

## 创建运行/调试配置 Create a run/debug configuration﻿

1. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.

2. 从主菜单中选择Run | Edit Configurations。或者，按下Alt+Shift+F10，然后按0。

3. In the [Run/Debug Configuration](https://www.jetbrains.com/help/go/run-debug-configuration.html) dialog, click the Add button  在[运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html)对话框中，点击工具栏上的添加按钮![the Add button](RunTargets_img/app.general.add.svg) on the toolbar or press Alt+Insert. ，或者按下Alt+Insert。

4. Select one of the [supported](https://www.jetbrains.com/help/go/run-targets.html#supported-rcs) run/debug configuration types.

5. 选择其中一种[支持的](https://www.jetbrains.com/help/go/run-targets.html#supported-rcs)运行/调试配置类型。

6. If you have already defined the target, select it from the Run on menu. Otherwise, click Manage targets… to add a new target. For instructions on configuring a particular target type, refer to the following procedures:

7. 如果您已经定义了目标，请从"Run on"菜单中选择它。否则，点击"Manage targets…"添加新的目标。有关配置特定目标类型的说明，请参考以下操作：

   - [SSH](https://www.jetbrains.com/help/go/run-targets.html#ssh)
   - [Docker](https://www.jetbrains.com/help/go/run-targets.html#docker)
   - [WSL](https://www.jetbrains.com/help/go/run-targets.html#wsl)

   ![Create a run/debug configuration](RunTargets_img/go_run_targets_create_a_run_debug_configuration.png)


You can also configure a run target in a run/debug configuration template, so the next time you create a new configuration of that type, its parameters already have the desired values. For more information, refer to [Configure the default values for a template](https://www.jetbrains.com/help/go/run-debug-configuration.html#change-template).

​	您还可以在运行/调试配置模板中配置运行目标，这样下次创建该类型的新配置时，其参数已经具有所需的值。更多信息，请参考[配置模板的默认值](https://www.jetbrains.com/help/go/run-debug-configuration.html#change-template)。

## 运行 Run﻿

Procedure for running the app on a remote target is the same as for running it locally:

​	在远程目标上运行应用程序的过程与在本地运行应用程序的过程相同： 

1. Select the run/debug configuration on the main toolbar.
2. 在主工具栏上选择运行/调试配置。
3. 点击![The Run button](RunTargets_img/app.actions.execute.svg) or press Shift+F10. 或按下Shift+F10。

GoLand builds the artifacts and then copies them to the target. After that, it runs the app on the target using the specified configuration.

​	GoLand构建构件，然后将其复制到目标上。然后，它使用指定的配置在目标上运行应用程序。

## 目标类型 Target types﻿

A target describes the configuration of the environment in which the application will run.

​	目标描述了应用程序将运行的环境的配置。

When you create a remote target, GoLand automatically detects the configuration available in the remote environment. If required, you can manually configure additional configuration.

​	创建远程目标时，GoLand会自动检测远程环境中可用的配置。如果需要，您可以手动配置其他配置。

### SSH﻿


> FTP/SFTP/WebDAV connectivity plugin is required.
>
> ​	需要FTP/SFTP/WebDAV连接插件。

1. Select if you want to use an existing SSH configuration or create a new one:

2. 选择是否要使用现有的SSH配置或创建新的配置：

   

   Existing

   New

   

   

   Select an existing SSH configuration from the SSH list, then click Next. For instructions on how to configure an SSH configuration, refer to [Create SSH configurations](https://www.jetbrains.com/help/go/create-ssh-configurations.html).

   从SSH列表中选择一个现有的SSH配置，然后点击下一步。有关如何配置SSH配置的说明，请参考[创建SSH配置](https://www.jetbrains.com/help/go/create-ssh-configurations.html)。

3. Wait for the SSH server introspection to complete. During this step, GoLand tries to identify the language configuration available in the environment. Click Next.

4. 等待SSH服务器检查完成。在此步骤中，GoLand会尝试识别环境中可用的语言配置。点击下一步。

   ![Introspection of the SSH server](RunTargets_img/go_run_targets_ssh_introspection.png)

5. Configure the following properties:

6. 配置以下属性：

   - Use rsync: toggle this option to use [rsync](https://rsync.samba.org/) for file transfer. This is recommended as it will generally speed up copying files.
   - 使用rsync：切换此选项以使用[rsync](https://rsync.samba.org/)进行文件传输。这是推荐的，因为它通常可以加快文件复制的速度。
   - Project path on target: the path on the server that will be used for storing the project files.
   - 目标上的项目路径：服务器上用于存储项目文件的路径。

7. Add language configuration settings. For each configuration, specify its version and path on the server. The configured settings then appear in the Build and run section of the run/debug configuration when you select this environment as the target.

8. 添加语言配置设置。对于每个配置，请指定其版本和服务器上的路径。配置的设置将在选择此环境作为目标时显示在运行/调试配置的构建和运行部分。

   The following configuration settings are available:

   可用的配置设置如下：

   - Go Executable: the path to the Go executable (for example, **/usr/local/go/bin/go**)

   - Go可执行文件：Go可执行文件的路径（例如，**/usr/local/go/bin/go**）

   - GOPATH: the path that defines the root of your workspace. A root directory must contain **bin**, **pkg**, and **src** subdirectories. (for example, **/home/goprojects**)

   - GOPATH：定义工作空间根目录的路径。根目录必须包含**bin**、**pkg**和**src**子目录。（例如，**/home/goprojects**）

   - Version: a version number of your Go SDK (for example, `go1.15.8 linux/amd64`). GoLand detects this information automatically by running `go version`.

   - 版本：您的Go SDK版本号（例如，`go1.15.8 linux/amd64`）。GoLand通过运行`go version`自动检测此信息。

   - Additional settings: a group of settings that allow you to set directories for source code files and executables.

   - 附加设置：一组设置，允许您设置源代码文件和可执行文件的目录。

     To run on a target, GoLand needs to upload to a target the following entities: source code files, files from a working directory, compiled binaries, and delve. If you do not specify paths in Additional Settings, the IDE will create random directories to store previously-mentioned files. See the following screenshot with randomly-generated directories for source files and executables.

     要在目标上运行，GoLand需要上传以下实体：源代码文件、工作目录中的文件、编译的二进制文件和delve。如果您在附加设置中不指定路径，IDE将创建随机目录来存储上述文件。以下是用于源文件和可执行文件的随机生成目录的屏幕截图。

     ![randomly-generated directories](RunTargets_img/go_randomly_generated_directories.png)

     You can specify the following options:
     
     您可以指定以下选项： 
     
     - Project sources directory: a directory on a target where source code files are uploaded.
     - Compiled executables directory: a directory on a target that is used to store executables that your code produces.
     - 项目源目录：上传源代码文件的目标上的目录。
     - 编译的可执行文件目录：用于存储代码生成的可执行文件的目标上的目录。

   ![Go Run Targets Ssh Runtime](RunTargets_img/go_run_targets_ssh_runtime.png)

### Docker﻿


> Docker plugin is required.
>
> 需要Docker插件。

1. Select or configure a Docker server as described in [Enable Docker support.](https://www.jetbrains.com/help/go/docker.html#connect_to_docker)

2. 按照[启用Docker支持](https://www.jetbrains.com/help/go/docker.html#connect_to_docker)中的说明选择或配置Docker服务器。

3. For Windows and macOS – make sure Docker has access to all the folders used in the workflow, for example, the project folder, **.maven**, and so on. For details, refer to [official Docker documentation](https://docs.docker.com/desktop/).

4. 对于Windows和macOS，确保Docker可以访问工作流程中使用的所有文件夹，例如项目文件夹、**.maven**等。有关详细信息，请参考[官方Docker文档](https://docs.docker.com/desktop/)。

5. Select if you want to build an image locally or pull it from Docker registry.

6. 选择是否要在本地构建镜像还是从Docker注册表中拉取镜像。

   

   Build

   Pull

   

   

   - Dockerfile: the Dockerfile that will be used for building the image.
   - Dockerfile：用于构建镜像的Dockerfile。
   - Context folder: a folder whose contents will be accessible by the Docker daemon during the build to be later used in the image filesystem.
   - 上下文文件夹：在构建期间Docker守护程序可以访问其内容的文件夹，以供稍后在镜像文件系统中使用。
   - Rebuild image automatically every time before running code: when this option is set, the image will be rebuilt every time the code is run. Otherwise, GoLand will use the already existing image (if any).
   - 在运行代码之前自动重新构建镜像：当设置了此选项时，每次运行代码时都会重新构建镜像。否则，GoLand将使用已存在的镜像（如果有）。

   Additionally, you can specify the following:

   此外，您可以指定以下内容：

   - Image tag: specify the name and tag for the built image. Similar to using the `-t` option with `docker build`.

   - 镜像标签：为构建的镜像指定名称和标签。类似于使用`docker build`的`-t`选项。

   - Build options: specify arbitrary options for the `docker build` command.

   - 构建选项：为`docker build`命令指定任意选项。

   - Build args: [override the default build-time variables](https://docs.docker.com/engine/reference/commandline/build/#set-build-time-variables-build-arg). Similar to using the `--build-arg` option with `docker build`.

   - 构建参数：[覆盖默认的构建时变量](https://docs.docker.com/engine/reference/commandline/build/#set-build-time-variables-build-arg)。类似于使用`docker build`的`--build-arg`选项。

   - Run options: specify arbitrary options for the `docker run` command.

   - 运行选项：为`docker run`命令指定任意选项。

     > Not all `docker run` options are supported. If you would like to request support for some option, leave a comment in [IDEA-181088](https://youtrack.jetbrains.com/issue/IDEA-181088).
     >
     > ​	并不是所有`docker run`选项都受支持。如果您希望请求对某些选项的支持，请在[IDEA-181088](https://youtrack.jetbrains.com/issue/IDEA-181088)中留下评论。
     

   ![run targets docker build image](RunTargets_img/go_run_targets_docker_build_image.png)

7. Wait for the container introspection to complete. During this step, GoLand tries to identify the language configuration available in the environment. Click Next.

8. 等待容器检查完成。在此步骤中，GoLand会尝试识别环境中可用的语言配置。点击下一步。

9. Configure Go settings.

10. 配置Go设置。

   The following configuration settings are available:

   可用的配置设置如下：

   - Project path on target: the path on the server that will be used for storing the project files.

   - 目标上的项目路径：服务器上用于存储项目文件的路径。

   - Go Executable: the path to the Go executable (for example, **/usr/local/go/bin/go**)

   - Go可执行文件：Go可执行文件的路径（例如，**/usr/local/go/bin/go**）

   - GOPATH: the path that defines the root of your workspace. A root directory must contain **bin**, **pkg**, and **src** subdirectories. (for example, **/home/goprojects**)

   - GOPATH：定义工作空间根目录的路径。根目录必须包含**bin**、**pkg**和**src**子目录。（例如，**/home/goprojects**）

   - Version: a version number of your Go SDK (for example, `go1.15.8 linux/amd64`). GoLand detects this information automatically by running `go version`.

   - 版本：您的Go SDK版本号（例如，`go1.15.8 linux/amd64`）。GoLand通过运行`go version`自动检测此信息。

   - Additional settings: a group of settings that allow you to set directories for source code files and executables.

   - 附加设置：一组设置，允许您设置源代码文件和可执行文件的目录。

     To run on a target, GoLand needs to upload to a target the following entities: source code files, files from a working directory, compiled binaries, and delve. If you do not specify paths in Additional Settings, the IDE will create random directories to store previously-mentioned files. See the following screenshot with randomly-generated directories for source files and executables.

     要在目标上运行，GoLand需要上传以下实体：源代码文件、工作目录中的文件、编译的二进制文件和delve。如果您在附加设置中不指定路径，IDE将创建随机目录来存储上述文件。以下是用于源文件和可执行文件的随机生成目录的屏幕截图。

     ![randomly-generated directories](RunTargets_img/go_randomly_generated_directories.png)

     You can specify the following options:
     
     您可以指定以下选项： 
     
     - Project sources directory: a directory on a target where source code files are uploaded.
     - 项目源目录：在目标上用于上传源代码文件的目录。
     - Compiled executables directory: a directory on a target that is used to store executables that your code produces.
     - 编译的可执行文件目录：用于存储您的代码生成的可执行文件的目录。

   ![The final step of the Docker target](RunTargets_img/go_run_targets_docker_final_step.png)

### Docker Compose﻿



You can use a single Docker Compose service as a run target.

​	您可以将单个Docker Compose服务用作运行目标。


> Docker plugin is required.
>
> 需要Docker插件。

1. Select or configure a Docker server as described in [Enable Docker support.](https://www.jetbrains.com/help/go/docker.html#connect_to_docker)

2. 按照[启用Docker支持](https://www.jetbrains.com/help/go/docker.html#connect_to_docker)中的说明选择或配置Docker服务器。

3. For Windows and macOS – make sure Docker has access to all the folders used in the workflow, for example, the project folder. For details, refer to [official Docker documentation](https://docs.docker.com/desktop/).

4. 对于Windows和macOS，请确保Docker可以访问工作流程中使用的所有文件夹，例如项目文件夹。有关详细信息，请参考[官方Docker文档](https://docs.docker.com/desktop/)。

5. Specify the Docker Compose configuration files, select the necessary service, and provide any additional environment variables. Click Next.

6. 指定Docker Compose配置文件，选择所需的服务，并提供任何其他环境变量。点击下一步。

7. Wait for the Docker Compose service introspection to complete. During this step, GoLand tries to identify the language configuration available in the environment. Click Next.

8. 等待Docker Compose服务检查完成。在此步骤中，GoLand会尝试识别环境中可用的语言配置。点击下一步。

9. Configure Go settings.

10. 配置Go设置。

   The following configuration settings are available:

   可用的配置设置如下：

   - Project path on target: the path on the server that will be used for storing the project files.

   - 目标上的项目路径：服务器上用于存储项目文件的路径。

   - Go Executable: the path to the Go executable (for example, **/usr/local/go/bin/go**)

   - Go可执行文件：Go可执行文件的路径（例如，**/usr/local/go/bin/go**）

   - GOPATH: the path that defines the root of your workspace. A root directory must contain **bin**, **pkg**, and **src** subdirectories. (for example, **/home/goprojects**)

   - GOPATH：定义工作空间根目录的路径。根目录必须包含**bin**、**pkg**和**src**子目录。（例如，**/home/goprojects**）

   - Version: a version number of your Go SDK (for example, `go1.15.8 linux/amd64`). GoLand detects this information automatically by running `go version`.

   - 版本：您的Go SDK版本号（例如，`go1.15.8 linux/amd64`）。GoLand通过运行`go version`自动检测此信息。

   - Additional settings: a group of settings that allow you to set directories for source code files and executables.

   - 附加设置：一组设置，允许您设置源代码文件和可执行文件的目录。

     To run on a target, GoLand needs to upload to a target the following entities: source code files, files from a working directory, compiled binaries, and delve. If you do not specify paths in Additional Settings, the IDE will create random directories to store previously-mentioned files. See the following screenshot with randomly-generated directories for source files and executables.

     要在目标上运行，GoLand需要上传以下实体：源代码文件、工作目录中的文件、编译的二进制文件和delve。如果您在附加设置中不指定路径，IDE将创建随机目录来存储上述文件。以下是用于源文件和可执行文件的随机生成目录的屏幕截图。

     ![randomly-generated directories](RunTargets_img/go_randomly_generated_directories.png)

     You can specify the following options:
     
     您可以指定以下选项： 
     
     - Project sources directory: a directory on a target where source code files are uploaded.
     - 项目源目录：在目标上用于上传源代码文件的目录。
     - Compiled executables directory: a directory on a target that is used to store executables that your code produces.
     - 编译的可执行文件目录：用于存储您的代码生成的可执行文件的目录。

   ![The final step of the Docker target](RunTargets_img/go_run_targets_docker_final_step.png)

### WSL﻿

1. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.

2. 从主菜单中选择Run | Edit Configurations。或者按下Alt+Shift+F10，然后按0。

3. In the [Run/Debug Configuration](https://www.jetbrains.com/help/go/run-debug-configuration.html) dialog, click 在[运行/调试配置](https://www.jetbrains.com/help/go/run-debug-configuration.html)对话框中，点击工具栏上的![the Add button](RunTargets_img/app.general.add.svg) on the toolbar or press Alt+Insert. ，或按下Alt+Insert。

4. From the Add New Configuration window, select the run/debug configuration that you want to create for running a target. It can be Go Build or Go Test.

5. 从新建配置窗口中，选择要为运行目标创建的运行/调试配置类型，可以选择Go Build或Go Test。

6. From the Run on menu, under the New targets section, select WSL to add a WSL target.

7. 在运行目标菜单中，在新目标部分下，选择WSL以添加WSL目标。

   ![select wsl from run on list](RunTargets_img/go_select_wsl_from_run_on_list.png)

8. In the New Target wizard, select your Linux distribution from the Linux distribution list. If the distribution was detected automatically and the introspection passed, click Next.

9. 在新目标向导中，从Linux分发列表中选择您的Linux分发。如果分发被自动检测并通过内省，点击下一步。

   ![introspection of wsl target](RunTargets_img/go_introspection_of_wsl_target.png)

10. Check that the Go runtime configuration for WSL was detected correctly and click Finish.

11. 检查WSL的Go运行时配置是否正确检测，并点击完成。

    Alternatively, type your own settings.

    或者，自己输入设置。

    - Go Executable: the path to the Go executable (for example, **/usr/local/go/bin/go**)

    - Go可执行文件：Go可执行文件的路径（例如，**/usr/local/go/bin/go**）

    - GOPATH: the path that defines the root of your workspace. A root directory must contain **bin**, **pkg**, and **src** subdirectories. (for example, **/home/goprojects**)

    - GOPATH：定义工作空间根目录的路径。根目录必须包含**bin**、**pkg**和**src**子目录。（例如，**/home/goprojects**）

    - Version: a version number of your Go SDK (for example, `go1.15.8 linux/amd64`). GoLand detects this information automatically by running `go version`.

    - 版本：您的Go SDK版本号（例如，`go1.15.8 linux/amd64`）。GoLand通过运行`go version`自动检测此信息。

    - Additional settings: a group of settings that allow you to set directories for source code files and executables.

    - 附加设置：一组设置，允许您设置源代码文件和可执行文件的目录。

      To run on a target, GoLand needs to upload to a target the following entities: source code files, files from a working directory, compiled binaries, and delve. If you do not specify paths in Additional Settings, the IDE will create random directories to store previously-mentioned files. See the following screenshot with randomly-generated directories for source files and executables.

      要在目标上运行，GoLand需要上传以下实体：源代码文件、工作目录中的文件、编译的二进制文件和delve。如果您在附加设置中不指定路径，IDE将创建随机目录来存储上述文件。以下是用于源文件和可执行文件的随机生成目录的屏幕截图。

      ![randomly-generated directories](RunTargets_img/go_randomly_generated_directories.png)

      You can specify the following options:
      
      您可以指定以下选项： 
      
      - Project sources directory: a directory on a target where source code files are uploaded.
      - Compiled executables directory: a directory on a target that is used to store executables that your code produces.
      - 项目源目录：在目标上用于上传源代码文件的目录。
      - 编译的可执行文件目录：用于存储您的代码生成的可执行文件的目录。

    ![check Go runtime configuration for WSL](RunTargets_img/go_check_go_runtime_configuration_for_wsl.png)

12. From the main menu, click Run and select the necessary run configuration or press (Shift+F10) to run your code and check the output in the Run tool window.

13. 从主菜单中点击Run，并选择所需的运行配置，或按下(Shift+F10)来运行您的代码，并在运行工具窗口中检查输出。

    ![Run tool window: WSL output](RunTargets_img/go_wsl_change_target_to_wsl.png)