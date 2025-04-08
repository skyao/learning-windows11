---
title: "hanewin nfs服务器"
linkTitle: "hanewin nfs"
weight: 50
date: 2021-08-26
description: >
  hanewin nfs 服务器软件
---

## 安装

### 安装路径

建议不要安装在program files目录下，找个普通路径，不需要管理员权限的

如：`C:\data\soft\nfsd`

### 注册和设置

打开 nfssrv.exe 进行注册和设置时，要以管理员身份运行。

输入注册号注册：

```properties
FBLZ3317FCE4196E
Team BLiZZARD
```

在export中设置export内容：

```bash
e:\ -public -readonly
f:\ -public -readonly
g:\ -public -readonly
h:\ -public -readonly
```

### 重启验证

安装之后重启，在管理 -》 服务中看是否有 nfs server。

查看 `C:\data\soft\nfsd` 下的 nfsd2005.log 看是否启动成功。

也可以在服务列表中停止 nfs server，然后删除 nfsd2005.log 文件，再启动 nfs server 服务，再检查 nfsd2005.log。

正常启动成功会出现下面的内容：

```bash
2020-05-24 10:43:19 --- haneWIN NFS Server 1.1.75
2020-05-24 10:43:19 nfsd   file handle cache size 24
2020-05-24 10:43:19 nfsd   client charset UTF-8
2020-05-24 10:43:19 nfsd   NTFS 2000/XP hardlinks supported

------ Exported file systems ------
21367d2e e:\          -ro -public
04ba4fb0 f:\          -ro -public
06a79256 g:\          -ro -public
0debb5d0 h:\          -ro -public
-----------------------------------

2020-05-24 10:43:19 mountd started
2020-05-24 10:43:19 nfsd   started, 4 udp threads
```  


## windows防火墙

要关闭windows防火墙，或者设置让 nfs server 通过 windows 防火墙，将  `C:\data\soft\nfsd`  下面的三个可执行文件都设置为可以穿透防火墙。

1. nfssrv.exe
2. nfsd.exe
3. pmapd.exe

## 文件中文编码

设置 server  -》 “utf-8 charracter sets”，打勾