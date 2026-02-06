---
title: 安装说明
description: 如何安装 ZL Compressor
weight: 1
---
## 简介视频

{{< youtube "WDxXEAfy4rg" >}}

## 安装

您可以在[GitHub发布页](https://github.com/ZL-Audio/ZLCompressor/releases/latest)下载安装器或者使用下面的下载链接。请下载与您的操作系统和架构对应的安装器。

| 操作系统        | x86-64<br>Intel 芯片<br>AMD 芯片（大多数）                                                                                                           | ARM64<br>Apple M 芯片<br>Qualcomm 芯片                                                                                                          |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------- |
| **macOS**   | [ZL.Compressor-0.4.0-macOS-x86.dmg](https://github.com/ZL-Audio/ZLCompressor/releases/download/0.4.0/ZL.Compressor-0.4.0-macOS-x86.dmg)     | [ZL.Compressor-0.4.0-macOS-arm.dmg](https://github.com/ZL-Audio/ZLCompressor/releases/download/0.4.0/ZL.Compressor-0.4.0-macOS-arm.dmg)     |
| **Windows** | [ZL.Compressor-0.4.0-Windows-x86.msi](https://github.com/ZL-Audio/ZLCompressor/releases/download/0.4.0/ZL.Compressor-0.4.0-Windows-x86.msi) | [ZL.Compressor-0.4.0-Windows-arm.msi](https://github.com/ZL-Audio/ZLCompressor/releases/download/0.4.0/ZL.Compressor-0.4.0-Windows-arm.msi) |
| **Linux**   | [ZL.Compressor-0.4.0-Linux-x86.zip](https://github.com/ZL-Audio/ZLCompressor/releases/download/0.4.0/ZL.Compressor-0.4.0-Linux-x86.zip)     | [ZL.Compressor-0.4.0-Linux-arm.zip](https://github.com/ZL-Audio/ZLCompressor/releases/download/0.4.0/ZL.Compressor-0.4.0-Linux-arm.zip)     |


更多信息请阅读帮助中的[插件安装](../../help/plugin_installation)页面。

ZL Compressor 是**自由开源**的软件。除了 [ZL Audio 标志](https://github.com/ZL-Audio/ZLCompressor/blob/main/assets/zlaudio.svg) 和 [ZL Compressor 标志](https://github.com/ZL-Audio/ZLCompressor/blob/main/assets/logo.svg)，ZL Compressor 按照 [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html) 进行许可。您可以在 https://github.com/ZL-Audio/ZLCompressor 或者 https://gitee.com/ZL-Audio/ZLCompressor 获得源码。

以下提醒来自 [由 源译识 翻译的 AGPLv3](https://atomgit.com/translation/Contransus) 第九项条款。

**您无需为了接收或运行本程序副本而接受本许可证。仅是因为使用点对点传输接收副本而发生的被覆盖作品的辅助传播，您也无需接受本许可证。然而，除了本许可证以外，没有任何其他文件授权您传播或修改任何被覆盖作品。如果您不接受本许可证，这些行为（传播和修改）即构成版权侵权。因此，如果您修改或传播被覆盖作品，就表示您接受了本许可证。**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## 更新日志

### 0.4.0

新功能

- 增加 竖直仪表
- 增加 无限范围 按钮
- 增加 负数前瞻（即侧链延迟）

修复与改进

- 改进 用户界面布局
- 改进 幅值分析仪 显示
- 改进 频谱分析仪 显示

### 0.3.1

新功能

- 增加 `Inflat`、`Expand` 和 `Shape` 压缩方向（详见用户手册）
- 增加 幅值分析仪 立体声模式
- 增加 界面缩放 控制 和 Credit 信息

修复与改进

- 修复 插件在未获得 UI 预设文件夹权限时的崩溃问题
- 修复 错误的 RMS 显示
- 修复 接近零的参数显示问题
- 修复 从 ZL Equalizer 2 复制/粘贴 滤波器错误的问题
- 提高 DSP 性能

其他更改

- 支持 VST3 参数上下文菜单
- 更改 若干参数的范围
- 更改 部分按钮图标

## 0.2.1

新功能

- 增加频谱图冻结（鼠标悬停）
- 增加多频段框选
- 增加多频段复制/粘贴

修复与改进

- 修复 鼠标滚轮可能导致的错误 6dB 斜率
- 提高 超采样性能（大幅）

### 0.2.0

新功能

- 增加 功能提示
- 增加 侧链滤波器监听（双击频段拖拽按钮）
- 增加 软削波器

修复与改进

- 修复 压缩风格 `Vocal` 可能出现的浮点溢出
- 提高 稳定性

### 0.1.2

新功能

- 增加 外观设置 面板
- 增加 两个立体声模式（见#20）
- 增加 滤波器斜率 通过 Command/Ctrl + 鼠标滚轮调整
- 增加 滤波器 反转增益/复制/粘贴 右键面板
- 增加 阈值/比率 鼠标滚轮控制（在幅值分析器上）

修复与改进

- 修复 立体声湿信号 滑块宽度
- 修复 幅值分析器 在旁通/暂停时的抖动问题
- 改进 滑块鼠标滚轮控制（见#21）
- 改进 频谱图显示

其他

- 增加 Windows ARM64 发行

### 0.1.1

新功能

- 增加 压缩风格 `Vocal`
- 增加 RMS 压缩 及 RMS 相关参数
- 增加 响度匹配

修复与改进

- 修复 幅值分析器 延迟问题
- 修复 累积分析器 错误显示
- 改进 插件窗口大小拖拽