---
title: 安装说明
description: 如何安装 ZL Splitter
weight: 1
---

## 简介视频

{{< youtube "-RVm9mbbQtA" >}}

## 安装

您可以在[GitHub发布页](https://github.com/ZL-Audio/ZLSplitter/releases/latest)下载安装器或者使用下面的下载链接。请下载与您的芯片/架构对应的安装器。

{{< installers repo="ZL-Audio/ZLSplitter" plugin="ZL.Splitter" version="0.4.0" >}}

更多信息请阅读帮助中的[插件安装](../../help/plugin_installation)页面。

ZL Splitter 是**自由开源**的软件。除了 [ZL Audio 标志](https://github.com/ZL-Audio/ZLSplitter/blob/main/assets/zlaudio.svg) 和 [ZL Splitter 标志](https://github.com/ZL-Audio/ZLSplitter/blob/main/assets/logo.svg)，ZL Splitter 按照 [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html) 进行许可。您可以在 https://github.com/ZL-Audio/ZLSplitter 或者 https://gitee.com/ZL-Audio/ZLSplitter 获得源码。

以下提醒来自 [由 源译识 翻译的 AGPLv3](https://atomgit.com/translation/Contransus) 第九项条款。

**您无需为了接收或运行本程序副本而接受本许可证。仅是因为使用点对点传输接收副本而发生的被覆盖作品的辅助传播，您也无需接受本许可证。然而，除了本许可证以外，没有任何其他文件授权您传播或修改任何被覆盖作品。如果您不接受本许可证，这些行为（传播和修改）即构成版权侵权。因此，如果您修改或传播被覆盖作品，就表示您接受了本许可证。**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## Nightly Release

可在[此处](https://github.com/ZL-Audio/ZLNightlyRelease/releases/tag/ZLSplitter)获取。Nightly 版本包含新功能和修复，这些内容在正式发布前可能会发生变动。不建议用于关键的生产混音工作。如果您有具体的错误报告或功能请求，可以在[此处](https://github.com/ZL-Audio/ZLSplitter/issues)提交 issue。

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
