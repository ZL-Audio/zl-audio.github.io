---
title: 安装说明
description: 如何安装 ZL Spectrum Equalizer
weight: 1
---
## 简介视频

{{< youtube "qp_mmVIGBcc" >}}

## 安装

{{% include file="download-intro" repo="ZL-Audio/ZLSpectrumEqualizer" %}}

{{< installers repo="ZL-Audio/ZLSpectrumEqualizer" plugin="ZL.Spectrum.Equalizer" version="0.1.1" >}}

{{% include file="plugin-license" repo="ZL-Audio/ZLSpectrumEqualizer" plugin="ZL Spectrum Equalizer" %}}

以下提醒来自 [由 源译识 翻译的 AGPLv3 协议](https://atomgit.com/translation/Contransus) 第九项条款。

{{% include "agpl-acceptance" %}}

{{% include "vst3" %}}

## Nightly Release

{{% include file="nightly-release" repo="ZL-Audio/ZLSpectrumEqualizer" %}}

## 更新日志

### 0.1.1

修复

- 修复 Linux 下下拉框与文本编辑器的交互问题

新功能

- 增加 自定义下拉框对齐方式
- 增加 自定义 FFT 质量

其他更改

- 将默认 FFT 质量更改为 `Normal` 以防止卡顿

### 0.1.0

破坏性更改

- 修复内部刷新处理器报告的不正确刷新率
  - 修复后您可能会注意到 FFT 分析仪以不同的速度衰减
  - 您可能需要在界面设置中重新调整 FFT `Speed`（衰减速度）

修复

- 修复 macOS 上的预设文件夹权限问题
- 修复 动态开启时浮动窗口的位置
- 修复 与右键单击相关的独奏快捷键

新功能

- 增加 `Flat Gain` 滤波器类型
- 增加 独奏时的增益调整
  - 如需将增益固定为零，请在右键拖动时按住 `Ctrl/Command`
- 增加 FFT 分贝刻度最大值选择

其他更改

- 将滤波器关闭按钮更改为垃圾桶图标
- 改进 FFT 分析仪精度

### 0.0.3

修复

- 修复 Linux 下用户界面无响应的问题
- 修复 声道模式改变时不正确的静态增益补偿
- 修复 外部侧链按钮可能无法更新显示的问题
- 修复 超过奈奎斯特频率的动态曲线显示
- 修复 FFT 碰撞颜色潜在的数据争用问题
- 修复 滑块/按钮/下拉框潜在的冗余数值通知
- 修复 调整界面大小可能导致的潜在卡顿

新功能

- 增加 内置预设管理器（非常早期阶段）

其他更改

- 调整 界面设置面板
  - 移除 导入/导出功能
  - 增加 打开文件夹按钮
- 调整 下拉框界面

### 0.0.2

破坏性更改

- 修复 `Relative`（相对）动态模式
- 为滑块/拖拽使用独立的灵敏度控制

新功能

- 增加 动态差值（每个频段）

修复

- 修复 滑块数值编辑器的显示

改进

- 改进 信号处理性能（略微）

### 0.0.1

第一个版本。
