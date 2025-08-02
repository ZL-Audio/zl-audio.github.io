---
title: 安装说明
description: 如何安装 ZL Compressor
weight: 1
---

## 安装

前往[此链接](https://github.com/ZL-Audio/ZLEqualizer/releases/latest)下载对应您操作系统的安装器：
- 后缀名为`.dmg`：macOS 系统安装器（包含 `VST3` 和 `AU`）。
- 后缀名为`.exe`：Windows 系统安装器（包含 `VST3` 和 `LV2`）。
- 后缀名为`.zip`：Linux 系统安装器（包含 `VST3` 和 `LV2`）。

更多信息请阅读帮助中的[插件安装](../../help/plugin_installation)页面。

ZL Compressor 是**自由开源**的软件。除了 [ZL Audio 标志](https://github.com/ZL-Audio/ZLCompressor/blob/main/assets/zlaudio.svg) 和 [ZL Compressor 标志](https://github.com/ZL-Audio/ZLCompressor/blob/main/assets/logo.svg)，ZL Compressor 按照 [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html) 进行许可。

以下提醒来自 [由 源译识 翻译的 AGPLv3](https://atomgit.com/translation/Contransus) 第九项条款。

**您无需为了接收或运行本程序副本而接受本许可证。仅是因为使用点对点传输接收副本而发生的被覆盖作品的辅助传播，您也无需接受本许可证。然而，除了本许可证以外，没有任何其他文件授权您传播或修改任何被覆盖作品。如果您不接受本许可证，这些行为（传播和修改）即构成版权侵权。因此，如果您修改或传播被覆盖作品，就表示您接受了本许可证。**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## 更新日志

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