---
title: "clash-for-windows"
linkTitle: "clash-for-windows "
weight: 90
date: 2025-03-16
description: >
  clash 的 windows 客户端
---

## 下载

https://github.com/Z-Siqi/Clash-for-Windows_Chinese/

下载最新版本，选择安装文件，如 Clash.for.Windows.Setup.0.20.39_Opt-3.exe

## 安装

双击安装文件，按照提示安装。

## 配置

启动 clash-for-windows，选择 "配置"，找到默认的配置文件 config.yaml，点击编辑，增加如下内容：

```yaml
proxies:
  - name: "xxx"
    type: ss
    server:  46.xxx.xx.xx    # 服务器公网 IP
    port: 8388               # 在 config.json 里设置的 server_port
    cipher: aes-128-gcm      # 与服务端一致
    password: 1234xxxx       # 与服务端一致
```

## 使用

以浏览器 SwitchyOmega 插件为例，新建一个代理服务器，取名 local-clash，设置为：

- 代理协议： socks5
- 代理服务器：127.0.0.1
- 代理端口： 7890

然后设置浏览器使用 local-clash 代理。

## 支持简单规则

如果需要支持简单规则，避免全部访问都走代理，可以修改 config.yaml 文件，增加如下内容：

```json
# 你已有的节点
proxies:
  - name: "My-SS-Server"
    type: ss
    server: your-server-ip
    port: 8388
    cipher: aes-128-gcm
    password: STRONG_PASSWORD
proxy-groups:
  - name: "Proxy"
    type: select
    proxies:
      - "y-SS-Server"
      - "DIRECT"
rules:
  - DOMAIN-SUFFIX,cn,DIRECT
  - DOMAIN-SUFFIX,baidu.com,DIRECT
  - DOMAIN-SUFFIX,qq.com,DIRECT
  - DOMAIN-SUFFIX,bilibili.com,DIRECT
  - GEOIP,CN,DIRECT
  - MATCH,Proxy
```




