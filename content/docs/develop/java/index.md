---
title: "安装配置 Java"
linkTitle: "Java"
weight: 35
date: 2025-04-06
description: >
  安装设置 jdk
---

## 安装 sdkman

### 安装 unzip

下载地址： https://sourceforge.net/projects/gnuwin32/files/zip/3.0/zip-3.0-bin.zip/download

解压下载的 zip-3.0-bin.zip 文件后，将 bin 目录下所有的文件都复制到 windows/system32 目录下。

> 备注：https://sourceforge.net/projects/gnuwin32/files/ 这里可以下载到很多支持 MinGW 环境的软件。

### 安装 sdkman

执行：

```bash
curl -s "https://get.sdkman.io" | bash
```

如果报错看错误信息提示，如果发现没有任何成功或者错误的信息就结束，然后 sdkman 也没能安装完成，就应该时过程中出错了。

可以先访问 https://get.sdkman.io 这个地址，将内容复制下来，在本地保存为 sdkman.sh。然后执行：

```bash
bash ./sdkman.sh
```

就可以看到日志信息。

> 备注： sdkman 安装时，需要访问 github，经常会因为墙而访问失败。注意设置好梯子。

## 安装 jdk

安装常用的四个 jdk 版本：

 ```bash
sdk install java 21.0.6-zulu
sdk install java 17.0.14-zulu
sdk install java 11.0.26-zulu 
sdk install java 8.0.442-zulu
 ```

 ## 安装 maven

 最简单的办法就是直接用 sdkman 安装：

 ```bash
sdk install maven
 ```

 输出为：

 ```bash
Downloading: maven 3.9.9

In progress...

############################################################################################################# 100.0%

Installing: maven 3.9.9
Done installing!


Setting maven 3.9.9 as default.
 ```

检查版本：

```bash
mvn --version
Apache Maven 3.9.9 (8e8579a9e76f7d015ee5ec7bfcdc97d260186937)
Maven home: C:\Users\sky\.sdkman\candidates\maven\current
Java version: 17.0.14, vendor: Azul Systems, Inc., runtime: C:\Users\sky\.sdkman\candidates\java\current
Default locale: zh_CN, platform encoding: GBK
OS name: "windows 11", version: "10.0", arch: "amd64", family: "windows"
```



