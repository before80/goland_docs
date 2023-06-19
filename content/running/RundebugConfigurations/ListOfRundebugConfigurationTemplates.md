+++
title = "List of run/debug configuration templates"
weight = 20
date = 2023-06-19T11:20:58+08:00
type = "docs"
description = ""
isCJKLanguage = true
draft = false
+++
# List of run/debug configuration templates﻿

https://www.jetbrains.com/help/go/list-of-run-debug-configurations.html

Last modified: 06 March 2023

This page lists [run/debug configuration](https://www.jetbrains.com/help/go/run-debug-configuration.html) templates available in GoLand. For detailed instructions on how to use them in your project, refer to the related how-to pages.


> Whether a run/debug configuration is available in your IDE may depend on which [plugins](https://www.jetbrains.com/help/go/managing-plugins.html) are installed and enabled.

| Name                                                         | Use it to                                                    | Required plugins                |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------- |
| [Compound](https://www.jetbrains.com/help/go/run-debug-multiple.html#compound-configs) | Run several run/debug configurations in parallel. This is useful, for example, if you want to launch various automated tests or client-server apps. The controls for each configuration will be available in a separate tab in the Run or Debug tool window. |                                 |
| [Database script](https://www.jetbrains.com/help/go/run-debug-configuration-database-script.html) | Run your database scripts against created data sources.      | Database                        |
| [Dockerfile](https://www.jetbrains.com/help/go/dockerfile-run-configuration.html) | Created automatically when you [run a container from a Dockerfile](https://www.jetbrains.com/help/go/docker-containers.html#run_image_dockerfile). This configuration builds an image from the Dockerfile, and then derives a container from this image. | Docker                          |
| [Docker Image](https://www.jetbrains.com/help/go/docker-image-run-configuration.html) | Created automatically when you [run a container from an existing image](https://www.jetbrains.com/help/go/docker-containers.html#run_image). You can run it from a locally existing Docker image that you either [pulled](https://www.jetbrains.com/help/go/docker-images.html#pull-image) or [built](https://www.jetbrains.com/help/go/docker-images.html#build-image) previously. | Docker                          |
| [Docker Compose](https://www.jetbrains.com/help/go/docker-compose-run-configuration.html) | Created automatically when you [run a multi-container Docker application](https://www.jetbrains.com/help/go/docker-compose.html) from a [Docker Compose file](https://docs.docker.com/compose/overview/). | Docker                          |
| [Go Build](https://www.jetbrains.com/help/go/go-build.html)  | Run and debug your Go applications.                          | Go                              |
| [Go Remote](https://www.jetbrains.com/help/go/go-remote.html) | Debug Go applications on a remote server.                    | Go                              |
| [Go Test](https://www.jetbrains.com/help/go/go-test.html)    | Run and debug your Go tests.                                 | Go                              |
| [Grunt.js](https://www.jetbrains.com/help/go/run-debug-configuration-grunt.html) | Run and debug Grunt.js tasks.                                |                                 |
| [Gulp.js](https://www.jetbrains.com/help/go/run-debug-configuration-gulp-js.html) | Run and debug Gulp.js tasks.                                 |                                 |
| [HTTP Request](https://www.jetbrains.com/help/go/http-client-in-product-code-editor.html#http-request-run-debug-configurations) | Execute HTTP Requests directly in the GoLand either individually or as part of a compound run/debug configuration. | HTTP Client                     |
| [JavaScript Debug](https://www.jetbrains.com/help/go/run-debug-configuration-javascript-debug.html) | Debug JavaScript in applications running on the built-in or on an external web server and to debug Dart web applications. | JavaScript Debugger             |
| [Jest](https://www.jetbrains.com/help/go/run-debug-configuration-jest.html) | Run and debug [Jest](https://facebook.github.io/jest/) tests. |                                 |
| [NPM](https://www.jetbrains.com/help/go/run-debug-configuration-npm.html) | Run and debug [npm](https://docs.npmjs.com/misc/scripts) and [Yarn](https://yarnpkg.com/en/) scripts locally, that is when GoLand itself starts Node.js installed on your computer and initiates script execution. |                                 |
| [Protractor](https://www.jetbrains.com/help/go/run-debug-configuration-protractor.html) | Run and debug AngularJS unit tests using the Protractor test runner. |                                 |
| [React Native](https://www.jetbrains.com/help/go/run-debug-configuration-react-native.html) | Run and debug [React Native](http://www.reactnative.com/) applications. |                                 |
| [Shell Script](https://www.jetbrains.com/help/go/run-debug-configuration-shell-script.html) | Run [shell scripts](https://www.jetbrains.com/help/go/shell-scripts.html). | Shell Script                    |
| [tSQLt Test](https://www.jetbrains.com/help/go/tsqlt-test.html) | Run tests for stored procedures, functions, views, and triggers of Microsoft SQL Server. | Database (Microsoft SQL Server) |
| [utPLSQL Test](https://www.jetbrains.com/help/go/utplsql-test.html) | Run tests for packages, functions, procedures, triggers, views, and other objects that can be used in PL/SQL. | Database (Oracle)               |