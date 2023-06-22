+++
title = "创建测试"
weight = 20
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Create tests﻿ - 创建测试

https://www.jetbrains.com/help/go/create-tests.html

Last modified: 11 January 2023

最后修改日期：2023年1月11日

​	在GoLand中创建新的测试文件的最简单方式是使用专用的快捷键，您可以从源代码中调用。在这种情况下，IDE会创建一个新的测试文件，并为该文件、包或函数生成测试代码。

### 生成测试文件

1. 在代码编辑器中，导航到Code | Generate或按下Alt+Insert键。

2. 选择要生成的测试类型，然后按Enter键。您可以为以下范围创建测试文件：

   - 空测试文件
   - 函数测试
   - 文件测试
   - 包测试

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_generate_test_file.png](CreateTests_img/go_generate_test_file.animated.gif)



## 在测试和生产代码之间导航

在GoLand中，您可以在测试类和生产代码之间进行跳转。 

- 在编辑器中，将光标放置在测试类或源代码中的测试主题处，然后按Ctrl+Shift+T（导航|测试主题或导航|测试）。

​	如果该类只有一个测试，IDE将立即导航到该测试。否则，您将被提示从弹出窗口中选择所需的测试或[创建一个新的测试](https://www.jetbrains.com/help/go/create-tests.html#create-test)。

![Jump to test](CreateTests_img/go_jump_to_test.png)