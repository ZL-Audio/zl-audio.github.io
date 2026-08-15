---
title: 安装说明
description: 如何安装 ZL Spectrum Equalizer
weight: 1
---
## 简介视频

{{< youtube "qp_mmVIGBcc" >}}

## 安装

您可以在[GitHub发布页](https://github.com/ZL-Audio/ZLSpectrumEqualizer/releases/latest)下载安装器或者使用下面的下载链接。请下载与您的芯片/架构对应的安装器。

{{< installers repo="ZL-Audio/ZLSpectrumEqualizer" plugin="ZL.Spectrum.Equalizer" version="0.0.3" >}}

ZL Spectrum Equalizer 是**自由开源**的软件。除了 [ZL Audio 标志](https://github.com/ZL-Audio/ZLSpectrumEqualizer/blob/main/assets/zlaudio.svg) 和 [ZL Spectrum Equalizer 标志](https://github.com/ZL-Audio/ZLSpectrumEqualizer/blob/main/assets/logo.svg)，ZL Spectrum Equalizer 按照 [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html) 进行许可。您可以在 https://github.com/ZL-Audio/ZLSpectrumEqualizer 或者 https://gitee.com/ZL-Audio/ZLSpectrumEqualizer 获得源码。

以下提醒来自 [由 源译识 翻译的 AGPLv3 协议](https://atomgit.com/translation/Contransus) 第九项条款。

**您无需为了接收或运行本程序副本而接受本许可证。仅是因为使用点对点传输接收副本而发生的被覆盖作品的辅助传播，您也无需接受本许可证。然而，除了本许可证以外，没有任何其他文件授权您传播或修改任何被覆盖作品。如果您不接受本许可证，这些行为（传播和修改）即构成版权侵权。因此，如果您修改或传播被覆盖作品，就表示您接受了本许可证。**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## Nightly Release

可在[此处](https://github.com/ZL-Audio/ZLNightlyRelease/releases/tag/ZLSpectrumEqualizer)获取。Nightly 版本包含新功能和修复，这些内容在正式发布前可能会发生变动。不建议用于关键的生产混音工作。如果您有具体的错误报告或功能请求，可以在[此处](https://github.com/ZL-Audio/ZLSpectrumEqualizer/issues)提交 issue。

## 更新日志

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
