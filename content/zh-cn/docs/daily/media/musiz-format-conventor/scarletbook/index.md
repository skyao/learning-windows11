---
title: "scarletbook"
linkTitle: "scarletbook"
weight: 10
date: 2021-01-18
description: >
  将 ISO 格式的 SACD 转为 DSD/DFF 文件
---

## 介绍

scarletbook 可以把 ISO 格式的 SACD 文件解压成 DSD/DFF 文件。

## 使用

### 注册 dll

首先要注册 DecoderComp.dll。

以管理员身份运行cmd，然后输入：

```bash
regsvr32 scarletbook/DecoderComp.dll
```

注意：必须以管理员身份运行，否则注册会失败。

### 转换

注册完成后将需要解压的音乐镜像 ISO 文件放入 scarletbook 文件夹。

如果想转成 DSD 格式：

- 双击 `Extract DSD Stereo Files.bat` 则可解压出 ISO 内的二声道文件为 DSD 格式

如果想转成 DSF 格式：

- 双击 `Extract DSF Stereo Files.bat` 则可解压出 ISO 内的二声道文件为 DSF 格式
- 双击 `Extract DSF Multichannel Files.bat` 则可解压出 ISO 内的多声道文件为 DSF 格式

如果想转成 DST 格式：

- 双击 `Extract DST Stereo Files.bat` 则可解压出 ISO 内的二声道文件为 DST 格式
- 双击 `Extract DST Multichannel Files.bat` 则可解压出 ISO 内的多声道文件为 DST 格式

### 附录：格式说明

DSD、DSF、DST格式‌是音频处理中常用的几种格式，它们各有其特点和用途。

DSD 文件后缀包括 DFF 与 DSF，它们实际上是同一种文件格式的两种叫法，分别对应飞利浦与索尼。这些文件格式特性为无压缩存储，专为双声道音频设计。

对于多声道音频，因文件体积过大，通常会进行压缩处理，此时便形成了DST文件格式。

DFF、DSF 与 DST 文件格式均隶属于 DSD 技术，其源码输出保持一致。

- DSD 格式
‌
  DSD（Direct Stream Digital）‌是一种高解析度的音频编码方式，由 Sony 和 Philips 在1996年共同开发。
  
  DSD采用1bit比特流取样，采样率为2.8224MHz，是CD采样率（44.1kHz）的64倍。
  
  DSD直接将模拟音乐信号波形以脉冲方式转变为数字信号，能够以接近四倍于CD的空间储存音乐，提供更为优秀的声音效果‌

- DSF 格式

  ‌DSF（Digital Stream Format）‌是 Sony 提出的一种将 DSD 数据封装后的格式。
  
  DSF 格式对标签信息（tag）支持友好，适合管理和识别音频文件‌

  > 备注：为了方便通过 tag 来整理音乐，我通常会选择将 sacd 转为 dsf 格式。

- DST 格式

  ‌DST（Digital Stream Transfer）‌是一种对 DSD 数据进行无损压缩的编码格式。
  
  通过压缩减少存储空间，但不会影响音质。播放时需要解压，可能会增加运算量，导致播放卡顿‌

### 附录：格式支持

- 海贝音乐：完备的 DSD 支持：云盘直播，无损解码，原生输出。支持格式包括：DSF、DFF、ISO（含DST压缩）

- hifiman 901: TODO：忘了这个老机器支持什么格式了

## 参考文档

- https://www.audioapp.cn/thread-99165-1-1.html
- https://invitacongpe.hashnode.dev/scarletbook-sacd-extractor-patched