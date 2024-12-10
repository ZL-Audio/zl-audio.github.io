---
title: 安装说明
description: 如何安装 ZL Equalizer
weight: 1
---

## 简介视频

{{< youtube "bC-mBDumzvU" >}}

## 安装

前往[此链接](https://github.com/ZL-Audio/ZLEqualizer/releases/latest)下载对应您操作系统的安装器：
- 后缀名为`.dmg`：macOS 系统安装器（包含 `VST3`、`AU` 和 `AAX`）。
- 后缀名为`.exe`：Windows 系统安装器（包含 `VST3`、`LV2` 和 `AAX`）。
- 后缀名为`.zip`：Linux 系统安装器（包含 `VST3` 和 `LV2`）。

更多信息请阅读帮助中的[插件安装](../../help/plugin_installation)页面。

ZL Equalizer 按照 [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html) 进行许可。

以下提醒来自 [由 源译识 翻译的 AGPLv3](https://atomgit.com/translation/Contransus) 第九项条款。

**您无需为了接收或运行本程序副本而接受本许可证。仅是因为使用点对点传输接收副本而发生的被覆盖作品的辅助传播，您也无需接受本许可证。然而，除了本许可证以外，没有任何其他文件授权您传播或修改任何被覆盖作品。如果您不接受本许可证，这些行为（传播和修改）即构成版权侵权。因此，如果您修改或传播被覆盖作品，就表示您接受了本许可证。**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## 更新日志

### 0.5.0（即将到来）

- 增加 UI 设置导入/导出

### 0.4.5

- 更正 0.4.4 版本中 nlopt 库的链接问题（该问题导致 Linux 和 macOS 插件无法加载）
- 更正 安装器中错误的许可（许可已经变更为 AGPLv3）
- 提高 信号处理的稳定性

### 0.4.4

- 更正 少数情况下未初始化的静态增益补偿
- 更正 少数情况下可能的数据争用

### 0.4.3

- 改变 上方面板 布局（将 插件旁路 和 静态增益补偿 按钮移至外部）
- 改版 外观设置面板 布局
- 增加 UI 按钮的改变至默认窗口大小功能
- 增加 默认 高通/低通滤波器斜率 和 旋钮双击 到 外观设置面板
- 增加 色彩搭配 到 外观设置面板
- 增加 FFT 分辨率 到 外观设置面板
- 更正 在加载插件后采样率改变导致的错误延时
- 更正 `Standalone`中无法打开弹出菜单的问题
- 提高 高采样率下 匹配相位 和 混合相位 的效果
- 提高 频谱分析高频精确度

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
