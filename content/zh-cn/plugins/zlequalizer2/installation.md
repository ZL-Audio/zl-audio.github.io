---
title: 安装说明
description: 如何安装 ZL Equalizer 2
weight: 1
---

## 简介视频

{{< youtube "bC-mBDumzvU" >}}

## 安装

您可以在[GitHub发布页](https://github.com/ZL-Audio/ZLEqualizer/releases/latest)下载安装器或者使用下面的下载链接。请下载与您的操作系统和架构对应的安装器。

| 操作系统        | x86-64<br>Intel 芯片<br>AMD 芯片（大多数）                                                                                                            | ARM64<br>Apple M 芯片<br>Qualcomm 芯片                                                                                                           |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **macOS**   | [ZL.Equalizer.2-1.0.3-macOS-x86.dmg](https://github.com/ZL-Audio/ZLEqualizer/releases/download/1.0.3/ZL.Equalizer.2-1.0.3-macOS-x86.dmg)     | [ZL.Equalizer.2-1.0.3-macOS-arm.dmg](https://github.com/ZL-Audio/ZLEqualizer/releases/download/1.0.3/ZL.Equalizer.2-1.0.3-macOS-arm.dmg)     |
| **Windows** | [ZL.Equalizer.2-1.0.3-Windows-x86.exe](https://github.com/ZL-Audio/ZLEqualizer/releases/download/1.0.3/ZL.Equalizer.2-1.0.3-Windows-x86.exe) | [ZL.Equalizer.2-1.0.3-Windows-arm.exe](https://github.com/ZL-Audio/ZLEqualizer/releases/download/1.0.3/ZL.Equalizer.2-1.0.3-Windows-arm.exe) |
| **Linux**   | [ZL.Equalizer.2-1.0.3-Linux-x86.zip](https://github.com/ZL-Audio/ZLEqualizer/releases/download/1.0.3/ZL.Equalizer.2-1.0.3-Linux-x86.zip)     | [ZL.Equalizer.2-1.0.3-Linux-arm.zip](https://github.com/ZL-Audio/ZLEqualizer/releases/download/1.0.3/ZL.Equalizer.2-1.0.3-Linux-arm.zip)     |

更多信息请阅读帮助中的[插件安装](../../help/plugin_installation)页面。

ZL Equalizer 是**自由开源**的软件。除了 [ZL Audio 标志](https://github.com/ZL-Audio/ZLEqualizer/blob/main/assets/zlaudio.svg) 和 [ZL Equalizer 标志](https://github.com/ZL-Audio/ZLEqualizer/blob/main/assets/logo.svg)，ZL Equalizer 按照 [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html) 进行许可。您可以在 https://github.com/ZL-Audio/ZLEqualizer 或者 https://gitee.com/ZL-Audio/ZLEqualizer 获得源码。

以下提醒来自 [由 源译识 翻译的 AGPLv3](https://atomgit.com/translation/Contransus) 第九项条款。

**您无需为了接收或运行本程序副本而接受本许可证。仅是因为使用点对点传输接收副本而发生的被覆盖作品的辅助传播，您也无需接受本许可证。然而，除了本许可证以外，没有任何其他文件授权您传播或修改任何被覆盖作品。如果您不接受本许可证，这些行为（传播和修改）即构成版权侵权。因此，如果您修改或传播被覆盖作品，就表示您接受了本许可证。**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## 更新日志

### 1.0.3

修复与改进

- 修复 插件在未获得 UI 预设文件夹权限时的崩溃问题
- 修复 低频/高频搁架 通过双击添加时的错误增益

### 1.0.2

修复与改进

- 提高 均衡匹配 稳定性

### 1.0.1

与 ZL Equalizer 0.6.2 相比：

新功能

- 增加 更多侧链滤波器控制（滤波器类型和滤波器斜率）
- 增加 右键点击面板
- 增加 浮动窗口更多控制选项
- 增加 更多快捷键
- 增加 界面缩放 控制
- 增加 均衡匹配 绘图控制

修复

- 修复 错误的八度音符显示
- 修复 错误的监听显示
- 修复 中/侧模式下不正确的并行处理

改进

- 改进  匹配相位 和 混合相位 的性能
- 改进 处理性能
- 改进 动态处理
- 改进 FFT 分析仪显示
- 改进 均衡匹配 的拟合速度

其他更改

- 当采样率 > 44.1 kHz 时，提高了滤波器频率的最大值
- 从动态参数中移除了 `RMS` (均方根) 和 `Smooth` (平滑)
- 移除了 `Zero Latency` (零延迟) 选项，因为动态处理不再需要额外的 1 ms 延迟
- 移除了 `High Quality` (高质量) 选项，因为动态处理现在始终保持高质量
- 移除了 均衡匹配 的 `Weight` (权重) 和 拟合算法 控制
- 支持 VST3 参数上下文菜单
    - 在支持此功能的宿主中，如果您右键单击某些滑块，将会弹出一个原生的参数菜单。
- 支持 VST3/AAX 参数索引
    - 在支持此功能的宿主中，宿主可以将屏幕位置映射到参数，例如 Cubase 的 "AI Knob"。