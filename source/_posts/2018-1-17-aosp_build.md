---
layout: post
title:  "阅读Android源代码——使用Studio查看源代码"
date:  2018-1-17 10:26:08 +0800
categories: study
---

### 下载源代码

１．阅读之前，首先应该有源代码，所以先下载，下载地址建议在清华镜像 下下载，如果网速好，大概几个小时就可以。

２．打开源码目录，就像　soap目录，首先要运行　./build/envsetup.sh 文件，好安装ｍｍm 命令。

命令行：
``` bash
$:cd soap

$:source  ./build/envsetup.sh

$:sh  ./build/envsetup.sh
```
如果运行sh  ./build/envsetup.sh该命令行出现如下错误：

envsetup.sh: 1: envsetup.sh: Syntax error: "(" unexpected
则可能是系统兼容问题，运行命令行：
``` bash
sudo dpkg-reconfigure dash
```
出现选择 yes 或者是　ｎｏ，选择　no

然后重新运行sh  ./build/envsetup.sh　命令

现在就可以编译某一个模块了！


### 在Studio下看源代码

编译开发环境Ｓtudio 下的ｉｄｅ：

１运行命令：
``` bash
$ mmm development/tools/idegen/

```
生成IDE工具文件，这个命令运行时间大概７分钟,运行完将生成idegen.jar文件。成功后会有如下日志：

[ 86% 26/30] //development/tools/idegen:idegen javac [linux_glibc common] 注: 某些输入文件使用或覆盖了已过时的 API。 注: 有关详细信息, 请使用 -Xlint:deprecation 重新编译。 [100% 30/30] Install: out/host/linux-x86/framework/idegen.jar
２接着运行生成Android Studio 工程的文件命令：

```bash
$ sh ./development/tools/idegen/idegen.sh  
```
生成Android Studio配置文件,在soap目录下，生成android.iws, android.ipr, android.iml，这三个文件是Android

Studio项目的关键文件，主要就是列出项目由模块组成，依赖关系，目录结构。

然后打开Android Studio，File->Open->工程根目录android.ipr，Android会自动导入工程所有代码，进行index，大约要40分钟

等着将源代码导入Android Studio　中……
