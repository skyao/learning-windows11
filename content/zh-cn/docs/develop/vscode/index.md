---
title: "安装配置VS Code"
linkTitle: "VS Code"
weight: 60
date: 2021-08-26
description: >
  安装VS Code
---

## 下载

https://code.visualstudio.com/download#

选择 windows 11 x64 版本下载。

## 安装

安装路径设置为 `d:/sky/work/soft/vscode` 。

安装完成后打开 vscode，设置为固定在任务栏上。

## 初始化配置

### 主题

启动后，在 Get Started 界面，“choose the look you want"中选择 “Brower Color themes”，然后选择 “solarized dark”，这是个人最喜欢的一个配色。

### 配置 git 插件

打开 git 仓库的项目后，vs code 报错说找不到 git，需要打开 vscode 的 settings，搜索 `git.path` ，按照提示在 settings.json 文件中加入 `git.path` 的设置，指向我们安装的 git：

```json
{
    "workbench.colorTheme": "Solarized Dark",
    "git.path": "D:\\sky\\work\\soft\\git\\bin\\git.exe"
}
```


