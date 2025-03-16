---
title: "微软Edge浏览器"
linkTitle: "Edge"
weight: 10
date: 2021-08-26
description: >
  目前我的主力浏览器
---

windows 11 自带微软Edge浏览器，无需安装，但是需要稍微设置一下。

## 定制首页

默认情况下打开的页面上显示了太多的乱七八糟的内容，需要定制一下。

打开页面设置：

- 快速链接：关闭
- 网站导航：关闭
- 显示信息提要：关闭
- 背景： 关闭
- 显示天气：关闭

但 bing 的搜索还是不够喜欢，默认还是继续用 google 吧。因此修改 edge 启动时默认打开 google 页面。

打开设置 -> 开始、主页和新建标签页 -> Microsoft Edge 启动时，设置为：打开一下页面，然后添加页面 https://www.google.com/

## 设置默认搜索引擎

默认使用 bing 作为搜索引擎，我喜欢换成 google。

打开设置 -> 隐私、搜索和服务 -> 地址栏和搜索（在最下面倒数第二个），设置为：

- 地址栏中使用的搜索引擎：google
- 新标签页上的搜索使用搜索框或地址栏：搜索栏

## 登录并同步数据

用微软账号登录，方便同步书签和扩展等数据。

发现 edge 登录之后，windows 账号也有信息了，下一次登录windows时会出现该账号的头像。

## 设置扩展插件

### 1password

需要登录。

### SwitchOmega

思路：增加 auto switch 场景，指向虚拟场景 fanqiang，再根据实际需要增加具体的 proxy，然后以后就只要修改虚拟场景 fanqiang 的指向就好了。

设置 proxy 为 socket5, 代理服务器为 192.168.2.1, 代理端口为 7891。

不经过的地址列表为:

```bash
127.0.0.1
::1
localhost
192.168.0.0/16
```

增加 auto switch，设置规则格式为 AutoProxy ，规则列表网址为：

https://raw.githubusercontent.com/gfwlist/gfwlist/master/gfwlist.txt

### save to pocket

登录即可。

### 沉浸式翻译

无需操作。


