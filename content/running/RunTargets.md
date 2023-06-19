+++
title = "Run targets"
weight = 50
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Run targets﻿

https://www.jetbrains.com/help/go/run-targets.html#wsl

Last modified: 03 April 2023

You can run your code in another environment such as cloud or a Docker container directly from GoLand.

For certain [run/debug configurations](https://www.jetbrains.com/help/go/run-debug-configuration.html), you can run your code in another environment such as cloud or a [Docker](https://www.jetbrains.com/help/go/docker.html) container directly from GoLand.

This feature allows you to instantly test the changes against the real environment the app is intended for. This ensures that there will be no incompatibilities when moving to production, which is especially important when working on code that heavily depends on the environment.

Running the app directly in such environment also spares you the extra actions normally required to deploy and run the app every time something changes.

The environment that is used for running the app is referred to as target. For GoLand to run code on a target, the target has to define a language runtime, which represents something on the target that can be used by a run/debug configuration to run code.

In order to run your code on a target, all you need is to define the target execution environment in the [run/debug configuration](https://www.jetbrains.com/help/go/run-debug-configuration.html) that you would normally use for local run. After you have done that, launching the app on a target is no different than launching it locally.

You can run several configurations on the same target. It is possible to set a project-wide default run target.

### Set a default target for a project﻿

1. Click Run | Manage Targets.

2. From the Project default target list, select a target that you want to use for your project.

   ![Set a default target for a project](RunTargets_img/go_set_a_default_target_for_a_project.png)

## Supported run/debug configuration types﻿

The following [run/debug configurations](https://www.jetbrains.com/help/go/run-debug-configuration.html) can run on a remote target:

- Go Build
- Go Test

## Create a run/debug configuration﻿

1. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.

2. In the [Run/Debug Configuration](https://www.jetbrains.com/help/go/run-debug-configuration.html) dialog, click the Add button ![the Add button](RunTargets_img/app.general.add.svg) on the toolbar or press Alt+Insert.

3. Select one of the [supported](https://www.jetbrains.com/help/go/run-targets.html#supported-rcs) run/debug configuration types.

4. If you have already defined the target, select it from the Run on menu. Otherwise, click Manage targets… to add a new target. For instructions on configuring a particular target type, refer to the following procedures:

   - [SSH](https://www.jetbrains.com/help/go/run-targets.html#ssh)
   - [Docker](https://www.jetbrains.com/help/go/run-targets.html#docker)
   - [WSL](https://www.jetbrains.com/help/go/run-targets.html#wsl)

   ![Create a run/debug configuration](RunTargets_img/go_run_targets_create_a_run_debug_configuration.png)

You can also configure a run target in a run/debug configuration template, so the next time you create a new configuration of that type, its parameters already have the desired values. For more information, refer to [Configure the default values for a template](https://www.jetbrains.com/help/go/run-debug-configuration.html#change-template).

## Run﻿

Procedure for running the app on a remote target is the same as for running it locally:

1. Select the run/debug configuration on the main toolbar.
2. Click ![The Run button](RunTargets_img/app.actions.execute.svg) or press Shift+F10.

GoLand builds the artifacts and then copies them to the target. After that, it runs the app on the target using the specified configuration.

## Target types﻿

A target describes the configuration of the environment in which the application will run.

When you create a remote target, GoLand automatically detects the configuration available in the remote environment. If required, you can manually configure additional configuration.

### SSH﻿




> FTP/SFTP/WebDAV connectivity plugin is required.

1. Select if you want to use an existing SSH configuration or create a new one:

   

   Existing

   New

   

   

   Select an existing SSH configuration from the SSH list, then click Next. For instructions on how to configure an SSH configuration, refer to [Create SSH configurations](https://www.jetbrains.com/help/go/create-ssh-configurations.html).

2. Wait for the SSH server introspection to complete. During this step, GoLand tries to identify the language configuration available in the environment. Click Next.

   ![Introspection of the SSH server](RunTargets_img/go_run_targets_ssh_introspection.png)

3. Configure the following properties:

   - Use rsync: toggle this option to use [rsync](https://rsync.samba.org/) for file transfer. This is recommended as it will generally speed up copying files.
   - Project path on target: the path on the server that will be used for storing the project files.

4. Add language configuration settings. For each configuration, specify its version and path on the server. The configured settings then appear in the Build and run section of the run/debug configuration when you select this environment as the target.

   The following configuration settings are available:

   - Go Executable: the path to the Go executable (for example, **/usr/local/go/bin/go**)

   - GOPATH: the path that defines the root of your workspace. A root directory must contain **bin**, **pkg**, and **src** subdirectories. (for example, **/home/goprojects**)

   - Version: a version number of your Go SDK (for example, `go1.15.8 linux/amd64`). GoLand detects this information automatically by running `go version`.

   - Additional settings: a group of settings that allow you to set directories for source code files and executables.

     To run on a target, GoLand needs to upload to a target the following entities: source code files, files from a working directory, compiled binaries, and delve. If you do not specify paths in Additional Settings, the IDE will create random directories to store previously-mentioned files. See the following screenshot with randomly-generated directories for source files and executables.

     ![randomly-generated directories](RunTargets_img/go_randomly_generated_directories.png)

     You can specify the following options:

     - Project sources directory: a directory on a target where source code files are uploaded.
     - Compiled executables directory: a directory on a target that is used to store executables that your code produces.

   ![Go Run Targets Ssh Runtime](RunTargets_img/go_run_targets_ssh_runtime.png)

### Docker﻿




> Docker plugin is required.

1. Select or configure a Docker server as described in [Enable Docker support.](https://www.jetbrains.com/help/go/docker.html#connect_to_docker)

2. For Windows and macOS – make sure Docker has access to all the folders used in the workflow, for example, the project folder, **.maven**, and so on. For details, refer to [official Docker documentation](https://docs.docker.com/desktop/).

3. Select if you want to build an image locally or pull it from Docker registry.

   

   Build

   Pull

   

   

   - Dockerfile: the Dockerfile that will be used for building the image.
   - Context folder: a folder whose contents will be accessible by the Docker daemon during the build to be later used in the image filesystem.
   - Rebuild image automatically every time before running code: when this option is set, the image will be rebuilt every time the code is run. Otherwise, GoLand will use the already existing image (if any).

   Additionally, you can specify the following:

   - Image tag: specify the name and tag for the built image. Similar to using the `-t` option with `docker build`.

   - Build options: specify arbitrary options for the `docker build` command.

   - Build args: [override the default build-time variables](https://docs.docker.com/engine/reference/commandline/build/#set-build-time-variables-build-arg). Similar to using the `--build-arg` option with `docker build`.

   - Run options: specify arbitrary options for the `docker run` command.

     > ### 
     >
     > 
     >
     > Not all `docker run` options are supported. If you would like to request support for some option, leave a comment in [IDEA-181088](https://youtrack.jetbrains.com/issue/IDEA-181088).

   ![run targets docker build image](RunTargets_img/go_run_targets_docker_build_image.png)

4. Wait for the container introspection to complete. During this step, GoLand tries to identify the language configuration available in the environment. Click Next.

5. Configure Go settings.

   The following configuration settings are available:

   - Project path on target: the path on the server that will be used for storing the project files.

   - Go Executable: the path to the Go executable (for example, **/usr/local/go/bin/go**)

   - GOPATH: the path that defines the root of your workspace. A root directory must contain **bin**, **pkg**, and **src** subdirectories. (for example, **/home/goprojects**)

   - Version: a version number of your Go SDK (for example, `go1.15.8 linux/amd64`). GoLand detects this information automatically by running `go version`.

   - Additional settings: a group of settings that allow you to set directories for source code files and executables.

     To run on a target, GoLand needs to upload to a target the following entities: source code files, files from a working directory, compiled binaries, and delve. If you do not specify paths in Additional Settings, the IDE will create random directories to store previously-mentioned files. See the following screenshot with randomly-generated directories for source files and executables.

     ![randomly-generated directories](RunTargets_img/go_randomly_generated_directories.png)

     You can specify the following options:

     - Project sources directory: a directory on a target where source code files are uploaded.
     - Compiled executables directory: a directory on a target that is used to store executables that your code produces.

   ![The final step of the Docker target](RunTargets_img/go_run_targets_docker_final_step.png)

### Docker Compose﻿



You can use a single Docker Compose service as a run target.


> Docker plugin is required.

1. Select or configure a Docker server as described in [Enable Docker support.](https://www.jetbrains.com/help/go/docker.html#connect_to_docker)

2. For Windows and macOS – make sure Docker has access to all the folders used in the workflow, for example, the project folder. For details, refer to [official Docker documentation](https://docs.docker.com/desktop/).

3. Specify the Docker Compose configuration files, select the necessary service, and provide any additional environment variables. Click Next.

4. Wait for the Docker Compose service introspection to complete. During this step, GoLand tries to identify the language configuration available in the environment. Click Next.

5. Configure Go settings.

   The following configuration settings are available:

   - Project path on target: the path on the server that will be used for storing the project files.

   - Go Executable: the path to the Go executable (for example, **/usr/local/go/bin/go**)

   - GOPATH: the path that defines the root of your workspace. A root directory must contain **bin**, **pkg**, and **src** subdirectories. (for example, **/home/goprojects**)

   - Version: a version number of your Go SDK (for example, `go1.15.8 linux/amd64`). GoLand detects this information automatically by running `go version`.

   - Additional settings: a group of settings that allow you to set directories for source code files and executables.

     To run on a target, GoLand needs to upload to a target the following entities: source code files, files from a working directory, compiled binaries, and delve. If you do not specify paths in Additional Settings, the IDE will create random directories to store previously-mentioned files. See the following screenshot with randomly-generated directories for source files and executables.

     ![randomly-generated directories](RunTargets_img/go_randomly_generated_directories.png)

     You can specify the following options:

     - Project sources directory: a directory on a target where source code files are uploaded.
     - Compiled executables directory: a directory on a target that is used to store executables that your code produces.

   ![The final step of the Docker target](RunTargets_img/go_run_targets_docker_final_step.png)

### WSL﻿



1. From the main menu, select Run | Edit Configurations. Alternatively, press Alt+Shift+F10, then 0.

2. In the [Run/Debug Configuration](https://www.jetbrains.com/help/go/run-debug-configuration.html) dialog, click ![the Add button](RunTargets_img/app.general.add.svg) on the toolbar or press Alt+Insert.

3. From the Add New Configuration window, select the run/debug configuration that you want to create for running a target. It can be Go Build or Go Test.

4. From the Run on menu, under the New targets section, select WSL to add a WSL target.

   ![select wsl from run on list](RunTargets_img/go_select_wsl_from_run_on_list.png)

5. In the New Target wizard, select your Linux distribution from the Linux distribution list. If the distribution was detected automatically and the introspection passed, click Next.

   ![introspection of wsl target](RunTargets_img/go_introspection_of_wsl_target.png)

6. Check that the Go runtime configuration for WSL was detected correctly and click Finish.

   Alternatively, type your own settings.

   - Go Executable: the path to the Go executable (for example, **/usr/local/go/bin/go**)

   - GOPATH: the path that defines the root of your workspace. A root directory must contain **bin**, **pkg**, and **src** subdirectories. (for example, **/home/goprojects**)

   - Version: a version number of your Go SDK (for example, `go1.15.8 linux/amd64`). GoLand detects this information automatically by running `go version`.

   - Additional settings: a group of settings that allow you to set directories for source code files and executables.

     To run on a target, GoLand needs to upload to a target the following entities: source code files, files from a working directory, compiled binaries, and delve. If you do not specify paths in Additional Settings, the IDE will create random directories to store previously-mentioned files. See the following screenshot with randomly-generated directories for source files and executables.

     ![randomly-generated directories](RunTargets_img/go_randomly_generated_directories.png)

     You can specify the following options:

     - Project sources directory: a directory on a target where source code files are uploaded.
     - Compiled executables directory: a directory on a target that is used to store executables that your code produces.

   ![check Go runtime configuration for WSL](RunTargets_img/go_check_go_runtime_configuration_for_wsl.png)

7. From the main menu, click Run and select the necessary run configuration or press (Shift+F10) to run your code and check the output in the Run tool window.

   ![Run tool window: WSL output](RunTargets_img/go_wsl_change_target_to_wsl.png)