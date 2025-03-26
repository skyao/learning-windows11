---
title: "nginx"
linkTitle: "nginx"
weight: 70
date: 2021-08-26
description: >
  nginx http server
---

在必要时开启 http server 。

## 下载

https://nginx.org/en/download.html

下载最新的 Stable version，如 nginx-1.26.3：

https://nginx.org/download/nginx-1.26.3.zip

## 安装

解压缩到 c:\data\soft\nginx 目录下。

## 配置

修改配置文件 `conf\nginx.conf`, 端口从默认的 80 修改为 8088，root 目录从默认的 nginx 安装目录下的 html 目录修改为自己的目录，开启目录浏览功能：

```properties
server {
  listen 80,
  location / {
    root C:\Users\sky\data\shared;
    autoindex on;
    autoindex_exact_size off;
    autoindex_localtime on;
  }
}
```

## 启动

打开 cmd ，cd 到 nginx 安装目录，执行命令：

```bash
start nginx
```

容许 nginx 通过防火墙。

修改配置之后，执行 

```bash
nginx -s reload
```

重新装载配置文件。

## 访问

通过浏览器访问：

https://localhost:8088

http://192.168.3.227:8088/

新建一个 data 目录，新建一个 a.txt 文件，在浏览器中访问：

http://192.168.3.227:8088/data/

检查目录浏览开启成功。

## 开机启动

下载 windows server wrap：

https://github.com/winsw/winsw/releases

下载 x64 版本 WinSW-x64.exe，重命名为 nginx-service.exe，放到 nginx 安装目录下。

新建一个 nginx-service.xml 文件，内容如下：

```xml
<service>
<id>nginx</id>
<name>Nginx (powered by WinSW)</name>
<description>nginx http server</description>
<executable>C:\data\soft\nginx\nginx.exe</executable>
<stopexecutable>C:\data\soft\nginx\nginx.exe</stopexecutable>
<stoparguments>-s stop</stoparguments>
<startmode>Automatic</startmode>
</service>
```

然后打开 cmd ，cd 到 nginx 安装目录，执行命令：

```bash
C:\data\soft\nginx>nginx-service.exe install
```

输出为：

```bash
2025-03-26 17:45:30,768 INFO  - Installing service 'Nginx (powered by WinSW) (nginx)'...
2025-03-26 17:45:30,838 INFO  - Service 'Nginx (powered by WinSW) (nginx)' was installed successfully.
```

打开 计算机管理 -》 服务，可以看到 nginx 的服务，启动类型为自动。

重启，然后打开浏览器检验 nginx 是否自动启动成功。

