---
title: "Windows11的安装过程"
linkTitle: "安装过程"
weight: 10
date: 2021-08-26
description: >
  Windows11 的安装过程
---


## 版本选择

选了了新发布的 windows 11 LTSC 2024 版本，基于最新的 windows 11 24h2。

## 安装前准备

可以从以下地址下载 windows 11 LTSC 2024 版本：

- https://massgrave.dev/windows_ltsc_links

- https://www.xitongku.com/


我选择的是 Windows 11 Enterprise LTSC 2024 （非IoT版本），Build - 26100.1742，简体中文版。

下载得到 zh-tw_windows_11_enterprise_ltsc_2024_x64_dvd_6287d84d.iso，用 refus 制作启动U盘或者用 ventoy 之类的工具加载 iso 即可。

## 安装

安装时，在硬盘分区和选择安装盘时需要注意：

- 分别建立 200G 和 800G 的两个分区，用于 windows 系统盘和安装程序和资料，避免系统盘过大不方便备份。

安装过程中不要选择用微软账号登录，而是建立本地账号如 sky，后面进入windows之后再登录。

安装过程中会重启几次，还会进行 windows 更新操作。
