---
title: "系统设置"
linkTitle: "系统"
weight: 90
date: 2025-03-16
description: >
  启动远程桌面连接，启动文件共享，容许ping，解决中文乱码
---

安装完成之后，为了方便使用，需要进行一些设置。

### 启动远程桌面

windows 11 默认是关闭远程桌面的，需要手动开启。

打开 "系统设置" -> "远程桌面" -> "启用远程桌面":

![](images/enable-remote-desktop.png)

另外需要开启 windows defender 防火墙的远程桌面规则。

1. 打开 windows defender 防火墙
2. 点击 “高级设置”
3. 在“入站规则”中，找到“远程桌面 (TCP-In)”，右键点击，选择“属性”
4. 在“属性”窗口中，点击“启用规则”，然后点击“确定”

![](images/remote-desktop-firewall.png)

### 启动文件共享

打开 "设置" -> "网络和internet" -> "高级网络设置" -> "高级共享设置":

![](images/file-share.png)

为一些常见的目录设置高级共享：

- `C:\Users\sky\data\shared`
- `C:\Users\sky\Downloads`

另外去掉默认的 `C:\Users\` 的共享。

### (可选)容许ping

如果发现无法 ping 到安装好的 windows 11 系统，通常是因为防火墙阻止了 ping 请求。

> 备注：如果执行了前面的 "启动文件共享" 步骤，则可以跳过此步骤。启动文件共享时，会自动开启 ping 请求的许可。

在防火墙中，容许 ping 请求的方式是：

1. 打开 windows defender 防火墙
2. 点击 “高级设置”
3. 在“入站规则”中，找到“文件和打印机共享 (回显请求 - ICMPv4-In)”，右键点击，选择“属性”
4. 在“属性”窗口中，点击“启用规则”，然后点击“确定”

![](images/ping-icmp.pgn.PNG)

### 中文乱码

如果安装时采用的是英文操作系统，然后通过安装中文语言包的方式安装的系统，则可能会出现某些文件有中文乱码的问题。通常是 unicode 的文件可以正常显示中文，非 unicode 的文件乱码。体现为新建的文件中文显示正常，打开老的文件中文显示乱码。

在 windows 10 中，可以打开 "设置" -> "时间和语言" -> "语言" -> "管理语言设置" -> "非 Unicode 程序的语言"，如果如下图所示的默认是 "英语(美国)":

![](images/win10-non-unicode-setting.png)

则需要修改为 "中文(简体，中国)"：

![](images/win10-non-unicode-setting2.png)

重新之后，再打开非 unicode 的文件，中文就能正常显示了。

在 windows 11 中，同样可以打开 "设置" -> "时间和语言" -> "语言和区域" -> "管理语言设置" -> "非 Unicode 程序的语言"，因为我直接安装的中文版所以默认是 "中文(简体，中国)" 无需更改：

![](images/win11-non-unicode-setting.png)




