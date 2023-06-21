+++
title = "使用调试器附加到正在运行的Go进程"
weight = 90
date = 2023-06-20T10:40:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false

+++
# Attach to running Go processes with the debugger﻿ - 使用调试器附加到正在运行的Go进程

https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html

Last modified: 16 January 2023

最近修改：2023年1月16日

In GoLand, you can attach the debugger to a running Go process [on a local machine](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#attach-to-a-process-on-a-local-machine), [on a remote machine](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#attach-to-a-process-on-a-remote-machine), or [in the Docker container](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#attach-to-a-process-in-the-docker-container).

​	在GoLand中，您可以将调试器附加到正在运行的Go进程[在本地机器上](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#attach-to-a-process-on-a-local-machine)、[在远程机器上](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#attach-to-a-process-on-a-remote-machine)或[在Docker容器中](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#attach-to-a-process-in-the-docker-container)。

## 在本地机器上附加到进程 Attach to a process on a local machine﻿

You can debug an application that you launched from the command line. In this case, the application runs outside the IDE but on the same local machine. To debug the application, you need to open the project in the IDE and attach the debugger to the running process.

​	您可以调试从命令行启动的应用程序。在这种情况下，应用程序在IDE之外但在同一台本地机器上运行。要调试应用程序，您需要在IDE中打开项目，并将调试器附加到正在运行的进程。

For example purposes, you can use [the following Go code at github.com](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go).

​	单击运行 | 附加到进程（Ctrl+Alt+F5）。在通知窗口中，单击“Invoke 'go get gops'”链接。

### 第1步：安装gops包 Step 1. Install the gops package﻿

- Open the Terminal tool window (View | Tool Windows | Terminal) and run the following command:

- 打开终端工具窗口（查看 | 工具窗口 | 终端），运行以下命令：

  ```bash
  go get -t github.com/google/gops/
  ```

  

- Click Run | Attach to Process (Ctrl+Alt+F5). In the notification window, click the Invoke 'go get gops' link.

- 单击运行 | 附加到进程（Ctrl+Alt+F5）。在通知窗口中，单击“Invoke 'go get gops'”链接。

  ![Install the gops package](AttachToRunningGoProcessesWithTheDebugger_img/go_invoke_go_get_gops.png)

### 第2步：构建和运行应用程序 Step 2. Build and run the application﻿

1. Open the Terminal tool window (View | Tool Windows | Terminal) and run the following command depending on your Go version:

2. 打开终端工具窗口（查看 | 工具窗口 | 终端），根据您的Go版本运行以下命令：

   - Go 1.10 and later:

   - Go 1.10及更高版本：

     ```bash
     go build -gcflags="all=-N -l" -o myApp
     ```

     

   - Go 1.9 and earlier:

   - Go 1.9及更早版本：

     ```bash
     go build -gcflags="-N -l" -o myApp
     ```

     

   This command compiles the `myApp` executable and disables compiler optimizations and inlining.

   此命令编译`myApp`可执行文件并禁用编译器优化和内联。

3. Run the compiled executable (for example, `./myApp`).

4. 运行编译后的可执行文件（例如，`./myApp`）。

   ![Build the application with gcflags flags](AttachToRunningGoProcessesWithTheDebugger_img/go_build_application_with_gcflags.png)


> Do not use `-ldflags="all=-w"` or `-ldflags="-w"` flags. These flags are incompatible with debugging the application because they strip out the necessary DWARF information that is required by Delve.
>
> 不要使用`-ldflags="all=-w"`或`-ldflags="-w"`标志，因为它们与调试应用程序不兼容，会删除Delve所需的DWARF信息。


> Symbolic links or symlinks are incompatible with debugging because of incompatibility between the Go toolchain, Delve, and GoLand.
>
> ​	由于Go工具链、Delve和GoLand之间的不兼容性，符号链接（symbolic links或symlinks）与调试不兼容。

### 第3步：附加并调试正在运行的进程 Step 3. Attach to and debug the running process﻿

1. Click the gutter near the line of code to place the breakpoint. For example, in [the provided code example](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go), put the breakpoint on the line 23 (`message := fmt.Sprintf("Hello %s!", r.UserAgent())`). Read more about breakpoints in [Breakpoints](https://www.jetbrains.com/help/go/using-breakpoints.html).

2. 单击代码行附近的gutter以设置断点。例如，在[提供的代码示例](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go)中，将断点放在第23行（`message := fmt.Sprintf("Hello %s!", r.UserAgent())`）。了解有关断点的更多信息，请参阅[断点](https://www.jetbrains.com/help/go/using-breakpoints.html)。

3. Click Run | Attach to ProcessCtrl+Alt+F5.

4. 单击运行 | 附加到进程（Ctrl+Alt+F5）。

5. In the Attach with Debugger To window, select your application process and press Enter.

6. 在“使用调试器附加到”窗口中，选择您的应用程序进程并按Enter键。

7. Trigger the event at the breakpoint in your application. If you used [the provided code example](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go), open the `http://localhost:8080/` link in a browser.

8. 在应用程序的断点处触发事件。如果您使用了[提供的代码示例](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go)，在浏览器中打开`http://localhost:8080/`链接。

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_attach_to_the_running_process.png](AttachToRunningGoProcessesWithTheDebugger_img/go_attach_to_the_running_process.animated.gif)

## 在远程机器上附加到进程 Attach to a process on a remote machine﻿

You can connect to a remote computer (a host) and attach the debugger to the Go process that runs on the host. The remote debugger (Delve) must be running on the remote computer.

​	您可以连接到远程计算机（主机）并将调试器附加到在主机上运行的Go进程。远程调试器（Delve）必须在远程计算机上运行。


> Compile Delve with the same Go version, host and target as your application because there might be slight differences between the various operating systems, which could cause the debugging session not to work as expected.
>
> ​	使用与应用程序相同的Go版本、主机和目标编译Delve，因为不同操作系统之间可能存在细微差异，可能导致调试会话无法正常工作

### 第1步：在主机上构建应用程序 Step 1. Build the application on the host machine﻿

1. If you use the `$GOPATH` approach, ensure that the project is compiled with the same relative path to `$GOPATH` on host and client machines. For example, if code of your application on the host is in `$GOPATH/src/debuggingTutorial/`. Code on the client must be in the same directory (`$GOPATH/src/debuggingTutorial/`).

2. 如果您使用`$GOPATH`方法，请确保项目在主机和客户端机器上与`$GOPATH`的相对路径相同。例如，如果您在主机上的应用程序代码位于`$GOPATH/src/debuggingTutorial/`，则客户端上的代码必须位于相同的目录（`$GOPATH/src/debuggingTutorial/`）。

3. Open the Terminal tool window (View | Tool Windows | Terminal) and run the following command depending on your Go version:

4. 打开终端工具窗口（查看 | 工具窗口 | 终端），根据您的Go版本运行以下命令：

   - Go 1.10 and later:

   - Go 1.10及更高版本：

     ```bash
     go build -gcflags="all=-N -l" -o myApp
     ```

     

   - Go 1.9 and earlier:

   - Go 1.9及更早版本：

     ```bash
     go build -gcflags="-N -l" -o myApp
     ```

     

   This command compiles the `myApp` executable and disables compiler optimizations and inlining.

   此命令编译`myApp`可执行文件并禁用编译器优化和内联。

   ![Build the application with gcflags flags for remote debugging](AttachToRunningGoProcessesWithTheDebugger_img/go_build_application_with_gcflags_for_remote.png)


### 第2步：在主机上运行Delve Step 2. Run Delve on the host machine﻿

- You have two options to launch the debugger on the host machine:

- 您有两种选项来在主机机器上启动调试器：

  - The debugger runs the process for you. If you use a firewall, expose the port that is used in the configuration (for example, `2345`). You can use any port number that is not occupied. `myApp` is the name of the executable that was built on [Step 1](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#step-1-build-the-application).

  - 调试器为您运行进程。如果使用了防火墙，请暴露在配置中使用的端口（例如，`2345`）。您可以使用任何未被占用的端口号。`myApp`是在[第1步](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#step-1-build-the-application)中构建的可执行文件的名称。
  
    ```bash
    dlv --listen=:2345 --headless=true --api-version=2 exec ./myApp
    ```

    

    If you need to pass arguments to the binary as-is, add the double dash sign (`--`) to the previous command and then necessary options (for example, `-- --config=/path/to/config/file`).

    如果需要将参数原样传递给二进制文件，请在前面的命令中添加双破折号（`--`），然后添加必要的选项（例如，`-- --config=/path/to/config/file`）。
  
  - You run the process, and the debugger attaches to the running process. `<PID>` is the process identifier of your application. You can get the process identifier by using [the Attach to Process command](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#attach-to-a-process-on-a-local-machine).

  - 您运行进程，然后调试器附加到正在运行的进程。`<PID>`是您的应用程序的进程标识符。您可以使用[附加到进程命令](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#attach-to-a-process-on-a-local-machine)获取进程标识符。

    ```bash
    dlv --listen=:2345 --headless=true --api-version=2 attach <PID>
    ```
  
    
    
  
  ![Run Delve on the host machine](AttachToRunningGoProcessesWithTheDebugger_img/go_run_delve_on_the_host_machine.png)

### 第3步：在客户端机器上创建Go Remote运行/调试配置 Step 3. Create the Go Remote run/debug configuration on the client computer﻿

1. Click Edit | Run Configurations. Alternatively, click the list of run/debug configurations on the toolbar and select Edit Configurations.

2. 单击“编辑”|“运行配置”。或者，单击工具栏上的运行/调试配置列表，然后选择“编辑配置”。

3. In the Run/Debug Configurations dialog, click the Add button (在“运行/调试配置”对话框中，单击“添加”按钮（![the Add button](AttachToRunningGoProcessesWithTheDebugger_img/app.general.add.svg)) and select Go Remote.），然后选择“Go Remote”。

4. In the Host field, type the host IP address (for example, `192.168.1.33`).

5. 在“主机”字段中，输入主机的IP地址（例如，`192.168.1.33`）。

6. In the Port field, type the debugger port that you configured on [Step 2](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#step-2-run-delve-on-the-host-machine) (for example, `2345`).

7. 在“端口”字段中，输入您在[第2步](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#step-2-run-delve-on-the-host-machine)中配置的调试器端口（例如，“2345”）。

8. 单击OK.

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_create_the_remote_run_debug_configuration.png](AttachToRunningGoProcessesWithTheDebugger_img/go_create_the_remote_run_debug_configuration.animated.gif)

### 第4步：在客户端机器上开始调试过程 Step 4. Start the debugging process on the client computer﻿

1. Click the gutter near the line of code to place the breakpoint. For example, in [the provided code example](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go), put the breakpoint on the line 23 (`message := fmt.Sprintf("Hello %s!", r.UserAgent())`). Read more about breakpoints in [Breakpoints](https://www.jetbrains.com/help/go/using-breakpoints.html).

2. 单击代码行附近的gutter以设置断点。例如，在[提供的代码示例](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go)中，将断点放在第23行（`message := fmt.Sprintf("Hello %s!", r.UserAgent())`）。了解有关断点的更多信息，请参阅[断点](https://www.jetbrains.com/help/go/using-breakpoints.html)。

3. From the list of run/debug configurations on the toolbar, select [the created Go Remote configuration](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#step-3-create-the-remote-run-debug-configuration-on-the-client-computer) and click the Debug <configuration_name> button (在工具栏上的运行/调试配置列表中，选择[创建的Go Remote配置](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#step-3-create-the-remote-run-debug-configuration-on-the-client-computer)，然后单击“调试<configuration_name>”按钮（![the Debug button](AttachToRunningGoProcessesWithTheDebugger_img/app.actions.startDebugger.svg)). Alternatively, press Alt+Shift+F9 and select the created Go Remote configuration.）。或者，按下Alt+Shift+F9，然后选择创建的Go Remote配置。

4. Trigger the event at the breakpoint in your application. If you used [the provided code example](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go), open the `http://<host_address>:8080/` link in a browser.

5. 触发应用程序中的断点处的事件。如果使用了[提供的代码示例](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go)，请在浏览器中打开`http://<host_address>:8080/`链接。

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_start_the_debugging_process_on_the_client_computer.png](AttachToRunningGoProcessesWithTheDebugger_img/go_start_the_debugging_process_on_the_client_computer.animated.gif)

## 附加到Docker容器中的进程 Attach to a process in the Docker container﻿

You can attach the debugger to a Go process that runs in a Docker container. For more information about Docker, see [Docker](https://www.jetbrains.com/help/go/docker.html).

​	您可以将调试器附加到在Docker容器中运行的Go进程。有关Docker的更多信息，请参阅[Docker](https://www.jetbrains.com/help/go/docker.html)。

For example purposes, you can use [the following Dockerfile](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/Dockerfile) for [this Go application](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go). Save **Dockerfile** and **main.go** in **$GOPATH/src/debuggingTutorial**. Note that **Dockerfile** uses the **debuggingTutorial** directory. If you use a different directory for the project, change the directory name in the Dockerfile.

​	为了示例目的，您可以使用以下Dockerfile配置用于[此Go应用程序](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go)。将**Dockerfile**和**main.go**保存在**$GOPATH/src/debuggingTutorial**中。请注意，\**Dockerfile\**使用**debuggingTutorial**目录。如果您在项目中使用了不同的目录，请在Dockerfile中更改目录名。

### 第1步：创建Dockerfile配置 Step 1. Create a Dockerfile configuration﻿

1. Click Edit | Run Configurations. Alternatively, click the list of run/debug configurations on the toolbar and select Edit Configurations.

2. 单击“编辑”|“运行配置”。或者，单击工具栏上的运行/调试配置列表，然后选择“编辑配置”。

3. In the Run/Debug Configurations dialog, click the Add button (在“运行/调试配置”对话框中，单击“添加”按钮（![the Add button](AttachToRunningGoProcessesWithTheDebugger_img/app.general.add.svg)) and select Docker | Dockerfile.），然后选择“Docker”|“Dockerfile”。

4. In the Dockerfile field, click the Browse icon (在“Dockerfile”字段中，单击“浏览”图标（![the Browse icon](AttachToRunningGoProcessesWithTheDebugger_img/app.actions.menu-open.svg)) and navigate to **Dockerfile** in the file browser. If you use the example from this section, navigate to [this Dockerfile](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/Dockerfile).），然后在文件浏览器中导航到**Dockerfile**。如果您使用了本节中的示例，请导航到[此Dockerfile](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/Dockerfile)。

5. In the Container name field, type the container name (for example, `debugging-tutorial`.

6. 在“容器名称”字段中，键入容器名称（例如，`debugging-tutorial`）。

7. In the Bind ports field, click the Browse icon (在“绑定端口”字段中，单击“浏览”图标（![the Browse icon](AttachToRunningGoProcessesWithTheDebugger_img/app.actions.menu-open.svg)). Click the Add button ( ）。单击“添加”按钮（![the Add button](AttachToRunningGoProcessesWithTheDebugger_img/app.general.add.svg)). In the Host port column, type `8080`. Click the Container port column, type `8080`. Also, add the same binding for the port `40000`.)。在“主机端口”列中，键入`8080`。在“容器端口”列中，键入`8080`。还要为端口`40000`添加相同的绑定。

   ![Bind ports](AttachToRunningGoProcessesWithTheDebugger_img/go_docker_bind_ports.png)

8. In the Run options field, specify command-line options for Docker. For the provided example in Dockerfile, disable [the security profile](https://docs.docker.com/engine/security/apparmor/) and add the `SYS_PTRACE` [Linux capability](https://www.man7.org/linux/man-pages/man7/capabilities.7.html).

9. 在“运行选项”字段中，为Docker指定命令行选项。对于Dockerfile中提供的示例，请禁用[安全配置文件](https://docs.docker.com/engine/security/apparmor/)并添加`SYS_PTRACE` [Linux功能](https://www.man7.org/linux/man-pages/man7/capabilities.7.html)。

   ```dockerfile
   --security-opt="apparmor=unconfined" --cap-add=SYS_PTRACE
   ```

   

10. 单击OK.

   ![Create a Dockerfile configuration](AttachToRunningGoProcessesWithTheDebugger_img/go_create_dockerfile_configuration.png)

### 第2步：运行Dockerfile配置 Step 2. Run the Dockerfile configuration﻿

- From the list of run/debug configurations on the toolbar, select [the created Dockerfile configuration](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#step-1-create-a-dockerfile-configuration) and click the Run <configuration_name> button (从工具栏上的运行/调试配置列表中，选择[创建的Dockerfile配置](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#step-1-create-a-dockerfile-configuration)，然后单击“运行<configuration_name>”按钮（![the Run button](AttachToRunningGoProcessesWithTheDebugger_img/app.actions.execute.svg)).)。

  ![https://resources.jetbrains.com/help/img/idea/2023.1/go_run_dockerfile_configuration.png](AttachToRunningGoProcessesWithTheDebugger_img/go_run_dockerfile_configuration.animated.gif)

### 第3步：创建Go Remote运行/调试配置Step 3. Create the Go Remote run/debug configuration﻿

1. Click Edit | Run Configurations. Alternatively, click the list of run/debug configurations on the toolbar and select Edit Configurations.

2. 单击“编辑”|“运行配置”。或者，单击工具栏上的运行/调试配置列表，然后选择“编辑配置”。

3. In the Run/Debug Configurations dialog, click the Add button (在“运行/调试配置”对话框中，单击“添加”按钮（![the Add button](AttachToRunningGoProcessesWithTheDebugger_img/app.general.add.svg)) and select Go Remote.），然后选择“Go Remote”。

4. 

5. In the Host field, type the host IP address (for example, `localhost`).

6. 在“主机”字段中，键入主机IP地址（例如，`localhost`）。

7. In the Port field, type the debugger port that you configured. In the provided example, it is `40000`.

8. 在“端口”字段中，键入您配置的调试器端口。在提供的示例中，它是`40000`。

9. 单击 OK.

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_create_the_remote_run_debug_configuration_for_docker.png](AttachToRunningGoProcessesWithTheDebugger_img/go_create_the_remote_run_debug_configuration_for_docker.animated.gif)

### 第4步：开始调试过程 Step 4. Start the debugging process﻿

1. In the Services tool window (View | Tool Windows | Services), expand Docker | Containers. Ensure that the created container is running and listens to the preconfigured debugger port.

2. 在“服务”工具窗口（视图|工具窗口|服务）中，展开“Docker”|“容器”。确保创建的容器正在运行并侦听预配置的调试器端口。

3. Click the gutter near the line of code to place the breakpoint. For example, in [the provided code example](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go), put the breakpoint on the line 23 (`message := fmt.Sprintf("Hello %s!", r.UserAgent())`). Read more about breakpoints in [Breakpoints](https://www.jetbrains.com/help/go/using-breakpoints.html).

4. 单击代码行附近的gutter，将断点放置在其中。例如，在[提供的代码示例](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go)中，在第23行（`message := fmt.Sprintf("Hello %s!", r.UserAgent())`）上设置断点。有关断点的更多信息，请参阅[断点](https://www.jetbrains.com/help/go/using-breakpoints.html)。

5. From the list of run/debug configurations on the toolbar, select [the created Go Remote configuration](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#step-3-create-the-go-remote-run-debug-configuration) and click the Debug <configuration_name> button (从工具栏上的运行/调试配置列表中，选择[创建的Go Remote配置](https://www.jetbrains.com/help/go/attach-to-running-go-processes-with-debugger.html#step-3-create-the-go-remote-run-debug-configuration)，然后单击“调试<configuration_name>”按钮（![the Debug button](AttachToRunningGoProcessesWithTheDebugger_img/app.actions.startDebugger.svg)). Alternatively, press Alt+Shift+F9, select the created Go Remote configuration.）。或者，按下Alt+Shift+F9，选择创建的Go Remote配置。

6. Trigger the event at the breakpoint in your application. If you used [the provided code example](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go), open the `http://localhost:8080/` link in a browser.

7. 触发应用程序中设置的断点处的事件。如果使用了[提供的代码示例](https://github.com/apronichev/documentation-code-examples/blob/master/debuggingTutorial/main.go)，请在浏览器中打开`http://localhost:8080/`链接。

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_start_the_debugging_process_for_docker.png](AttachToRunningGoProcessesWithTheDebugger_img/go_start_the_debugging_process_for_docker.animated.gif)

## 提高生产力的技巧 Productivity tips﻿

### 终止远程进程  Terminate the remote process﻿

- You can press Ctrl+F2 to terminate the remote process during the remote debugging session. Note that you cannot reattach to the process when you terminated it.

- 在远程调试会话期间，您可以按Ctrl+F2键终止远程进程。请注意，终止进程后将无法重新附加到该进程。

  ![https://resources.jetbrains.com/help/img/idea/2023.1/go_terminate_the_remote_process.png](AttachToRunningGoProcessesWithTheDebugger_img/go_terminate_the_remote_process.animated.gif)