---
title: 安装说明
description: 如何安装 ZL Splitter
weight: 1
---

## 简介视频

{{< youtube "-RVm9mbbQtA" >}}

## 安装

{{% include file="download-intro" repo="ZL-Audio/ZLSplitter" %}}

{{< installers repo="ZL-Audio/ZLSplitter" plugin="ZL.Splitter" version="0.4.0" >}}

{{% include "installation-help" %}}

{{% include file="plugin-license" repo="ZL-Audio/ZLSplitter" plugin="ZL Splitter" %}}

以下提醒来自 [由 源译识 翻译的 AGPLv3](https://atomgit.com/translation/Contransus) 第九项条款。

{{% include "agpl-acceptance" %}}

{{% include "vst3" %}}

## Nightly Release

{{% include file="nightly-release" repo="ZL-Audio/ZLSplitter" %}}

## 更新日志

### 0.4.0

破坏性变更

- 低频/高频分离器由 `SVF` 改为 `IIR`，且滤波器现已去扭曲
- 低频/高频分离器 `FIR` 改为采用 Yuriy Ivantsov 提出的去扭曲方法
- 移除数项 FFT 分析仪设置

修复

- 修复切换分离模式时重新播放旧音频的问题
- 修复更改低频/高频 `FIR` 分频点时的旁通延迟连续性及延迟报告更新
- 修复瞬态/稳态分离中最高频率 bin 的处理问题
- 修复幅值与波形显示的历史记录与缩放问题

新功能

- 增加内置预设管理器
- 增加在支持的宿主中右键点击弹出宿主参数上下文菜单
- 增加 `OCT` 和 `ERB` FFT 分析仪平滑模式
- 增加 `Sync`、`Slow` 与 `Roll` 幅值分析仪显示移动模式

改进

- 提升分离器性能（特别是低频/高频 `FIR` 与瞬态/稳态分离器）
- 提升分析仪性能

### 0.3.0

新功能

- 增加 波形 分析仪
- 增加 更多 分析仪设置

修复与改进

- 优化 频谱 分析仪
- 增加 幅值 分析仪

### 0.2.1

修复与改进

- 修复 插件在未获得 UI 预设文件夹权限时的崩溃问题

### 0.2.0

新功能

- 增加 功能提示
- 增加 FFT 分析仪
- 增加 幅值 分析仪
- 增加 旁通
- 增加 更多 UI 设置

修复与改进

- 提高性能

其他

- 增加 Windows ARM64 发行
