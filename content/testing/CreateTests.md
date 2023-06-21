+++
title = "创建测试"
weight = 20
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# Create tests﻿ 创建测试

https://www.jetbrains.com/help/go/create-tests.html

Last modified: 11 January 2023

最后修改日期：2023年1月11日

The simplest way of creating a new test file in GoLand is by using a dedicated shortcut that you can invoke from your source code. In this case, the IDE creates a new test file and generates test code for this file, package, or function.

​	在GoLand中创建新的测试文件的最简单方式是使用专用的快捷键，您可以从源代码中调用。在这种情况下，IDE会创建一个新的测试文件，并为该文件、包或函数生成测试代码。

### 生成测试文件 Generate test files﻿

1. In the code editor, navigate to Code | Generate or press Alt+Insert.

2. 在代码编辑器中，导航到“代码”|“生成”或按下Alt+Insert键。

3. Select what kind of a test you want to generate and press Enter. You can create test files for the following scopes:

4. 选择要生成的测试类型，然后按Enter键。您可以为以下范围创建测试文件：

   - Empty test file
   - Test for function
   - Tests for file
   - Tests for package
   - 空测试文件
   - 函数测试
   - 文件测试
   - 包测试

   ![https://resources.jetbrains.com/help/img/idea/2023.1/go_generate_test_file.png](CreateTests_img/go_generate_test_file.animated.gif)


## 在测试和生产代码之间导航 Navigate between tests and production code﻿

In GoLand, you can jump between test classes and production code.

在GoLand中，您可以在测试类和生产代码之间进行跳转。 

- In the editor, place the caret at the test class or at the test subject in the source code and press Ctrl+Shift+T (Navigate | Test Subject or Navigate | Test).
- 在编辑器中，将光标放置在测试类或源代码中的测试主题处，然后按Ctrl+Shift+T（导航|测试主题或导航|测试）。

If there's only one test for this class, the IDE will navigate you to it right away. Otherwise, you will be prompted to select the necessary test from a popup or [create a new test](https://www.jetbrains.com/help/go/create-tests.html#create-test).

​	如果该类只有一个测试，IDE将立即导航到该测试。否则，您将被提示从弹出窗口中选择所需的测试或[创建一个新的测试](https://www.jetbrains.com/help/go/create-tests.html#create-test)。

![Jump to test](CreateTests_img/go_jump_to_test.png)