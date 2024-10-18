




---
title: 安装说明
description: 如何安装 ZL Equalizer
weight: 1
---

KVR Audio 2024 读者之选 提名已经开始！如果您喜欢这个插件，请在[投票页](http://www.kvraudio.com/readers-choice-awards/2024/?utm_source=kvr_all_kvr_admins_mailing&utm_medium=email&utm_campaign=2024-09-30-ad-8124&utm_content=voting%20page)提名或投票。万分感谢！

## 简介视频

{{< youtube "bC-mBDumzvU" >}}

## 安装

前往[此链接](https://github.com/ZL-Audio/ZLEqualizer/releases/latest)下载对应您操作系统的安装器：
- 后缀名为`.dmg`：macOS 系统安装器（包含 `VST3`、`AU` 和 `AAX`）。
- 后缀名为`.exe`：Windows 系统安装器（包含 `VST3`、`LV2` 和 `AAX`）。
- 后缀名为`.zip`：Linux 系统安装器（包含 `VST3` 和 `LV2`）。

更多信息请阅读帮助中的[插件安装](../../help/plugin_installation)页面。

ZL Equalizer 按照 [GPLv3](https://www.gnu.org/licenses/gpl-3.0.en.html) 进行许可。

以下提醒来自 [由 源译识 翻译的 GPLv3](https://atomgit.com/translation/Contransus) 第九项条款。

**您无需为了接收或运行本程序副本而接受本许可证。仅是因为使用点对点传输接收副本而发生的被覆盖作品的辅助传播，您也无需接受本许可证。然而，除了本许可证以外，没有任何其他文件授权您传播或修改任何被覆盖作品。如果您不接受本许可证，这些行为（传播和修改）即构成版权侵权。因此，如果您修改或传播被覆盖作品，就表示您接受了本许可证。**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## 更新日志

### 0.4.2

- 增加并改变 滑块数值输入快捷键
  - Ctrl/Command + 鼠标双击 打开数值编辑器
- 更正 调整`Scale`时错误的曲线显示
- 更正 macOS 兼容性问题（现在插件应当兼容 macOS 10.13 及以上版本）
- 提高 混合相位模式的频移连续性

### 0.4.1

- 更正 一些测试代码

### 0.4.0

- 增加 平行 滤波器结构
- 增加 匹配相位 滤波器结构
- 增加 混合相位 滤波器结构
- 增加 线性相位 滤波器结构
- 增加并改变 快捷键
  - 按下 Shift 精细拖拽按钮
  - 按下 Shift 精细调整旋钮（之前为 Ctrl/Command）
  - Ctrl/Command + 鼠标双击 添加动态频段
  - Ctrl/Command + 鼠标双击频段按钮 开启/关闭动态该频段动态功能
- 改变 实际滤波器曲线 为 理想滤波器曲线
- 改变 默认 FFT 为 12 阶，以提高低频精细度
- 增加 相位反转 按钮并改变 输出设置 面板布局
- 增加 窗口大小调整的自由度
- 提高 信号处理 和 图形界面 的稳定性
- 提高 信号处理 和 图形界面 的性能
