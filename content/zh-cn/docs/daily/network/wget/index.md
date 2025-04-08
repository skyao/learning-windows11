---
title: "wget"
linkTitle: "wget"
weight: 60
date: 2021-08-26
description: >
  wget 下载软件
---

主要是为了在 cmd ，bash/zsh 下使用，保持和 linux 一致的使用习惯。

GNU 版本的 wget 下载地址为：

https://eternallybored.org/misc/wget/

下载最新的 64 位版本，可以选 zip 或者 exe 格式。

将得到的 wget.exe 文件放到任何一个 path 列出的路径下即可，比如最常见的 `c:/WINDOWS/system32` 。

打开 cmd 或者 bash/zsh，检验一下：

```bash
$ wget --version
GNU Wget 1.21.4 built on mingw32.

+cares +digest +gpgme +https +ipv6 +iri +large-file +metalink -nls
+ntlm +opie +psl +ssl/openssl
......
```

下载一个文件测试一下：

```bash
wget https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt
```