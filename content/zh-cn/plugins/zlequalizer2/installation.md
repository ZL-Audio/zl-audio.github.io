---
title: 安装说明
description: 如何安装 ZL Equalizer 2
weight: 1
---

## 简介视频

{{< youtube "bC-mBDumzvU" >}}

## 安装

您可以在[GitHub发布页](https://github.com/ZL-Audio/ZLEqualizer/releases/latest)下载安装器或者使用下面的下载链接。请下载与您的芯片/架构对应的安装器。

{{< installers repo="ZL-Audio/ZLEqualizer" plugin="ZL.Equalizer.2" version="1.3.1" >}}

更多信息请阅读帮助中的[插件安装](../../help/plugin_installation)页面。

ZL Equalizer 是**自由开源**的软件。除了 [ZL Audio 标志](https://github.com/ZL-Audio/ZLEqualizer/blob/main/assets/zlaudio.svg) 和 [ZL Equalizer 标志](https://github.com/ZL-Audio/ZLEqualizer/blob/main/assets/logo.svg)，ZL Equalizer 按照 [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html) 进行许可。您可以在 https://github.com/ZL-Audio/ZLEqualizer 或者 https://gitee.com/ZL-Audio/ZLEqualizer 获得源码。

以下提醒来自 [由 源译识 翻译的 AGPLv3 协议](https://atomgit.com/translation/Contransus) 第九项条款。

**您无需为了接收或运行本程序副本而接受本许可证。仅是因为使用点对点传输接收副本而发生的被覆盖作品的辅助传播，您也无需接受本许可证。然而，除了本许可证以外，没有任何其他文件授权您传播或修改任何被覆盖作品。如果您不接受本许可证，这些行为（传播和修改）即构成版权侵权。因此，如果您修改或传播被覆盖作品，就表示您接受了本许可证。**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## Nightly Release

可在[此处](https://github.com/ZL-Audio/ZLNightlyRelease/releases/tag/ZLEqualizer)获取。Nightly 版本包含新功能和修复，这些内容在正式发布前可能会发生变动。不建议用于关键的生产混音工作。如果您有具体的错误报告或功能请求，可以在[此处](https://github.com/ZL-Audio/ZLEqualizer/issues)提交 issue。

## 更新日志

### 1.3.1

修复

- 修复 Linux 下用户界面无响应的问题
- 修复 相对动态开启时的错误阈值
- 修复 外部侧链按钮可能无法更新显示的问题
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

### 1.3.0

破坏性更改

- 提高滤波器频率调制速度的上限
- 更改 `State Variable`（状态变量）滤波器结构（由 Yuriy Ivantsov 提出）
  - 现在 `State Variable`（状态变量）滤波器与 `Minimum Phase`（最小相位）具有相同的幅值与相位响应，但具有不同的调制/动态行为
- 更改 `Matched Phase`（匹配相位）/`Mixed Phase`（混合相位）/`Zero Phase`（零相位）引入的延迟
  - 现在无论是否使用 L/R/M/S，它们都将引入恒定的延迟
  - 响应保持不变，性能得到进一步提升
- 更改若干键盘快捷键
  - 现在您可以在 `Control`（控制）设置面板中调整不同操作的快捷键
  - 现在独奏状态的默认快捷键为 `Right Click`（右键单击）
  - 现在右键面板的默认快捷键为 `Right Click` + `Alt/Option`

修复

- 修复 级联滤波器在奈奎斯特频率处的 FIR 校正
- 修复 双精度单声道侧链可能导致的崩溃
- 修复 相对动态开启且学习关闭时的错误阈值
- 修复 重置或采样率更改后错误的 RMS 动态
- 修复 全局旁通时仍应用相位翻转的问题
- 修复 静态/动态高阶峰值不一致的问题
- 修复 均衡匹配中错误的 FFT 插值
- 修复 均衡匹配中次优的 FFT 优化过程
- 修复 滑块数值编辑器的显示

其他更改

- 放宽窗口大小比例限制
- 支持低至 10kHz 的采样率

### 1.2.2

新功能

- 增加 对截止频率超过奈奎斯特的滤波器的支持（现在在采样率 44.1/48 kHz 下，滤波器截止频率最高为 30 kHz）
- 增加 滤波器类型 `All Pass`（全通）
- 增加 分析仪平滑选项
- 增加 下拉框 鼠标滚轮控制
- 增加 滤波器响应曲线 分贝刻度值设置（参见界面设置）
- 增加 增益 和 缩放 鼠标滚轮控制
- 增加 均衡匹配 分贝限制选择
- 增加 两个均衡匹配内置目标曲线 `Balanced`（均衡）和 `Natural`（自然）

修复

- 修复 静态增益补偿 的数值显示
- 修复 错误的响度匹配结果
- 修复 均衡匹配 导致的潜在爆音
- 修复 动态 `Flat Tilt`（平坦倾斜）可能导致的崩溃

其他更改

- 允许 音高音符 通过小写字母输入

### 1.2.1

新功能

- 增加 滤波器类型 `Flat Tilt`（平坦倾斜）

修复

- 修复 未实现的 FFT 频谱冻结功能
- 修复 Windows 上碰撞检测功能

改进

- 改进 信号处理性能（略微）
- 改进 频谱仪显示

### 1.2.0

破坏性更改

- 更改滤波器去扭曲方法（由 Yuriy Ivantsov 提出）
  - 截止频率在奈奎斯特附近的滤波器响应会略有不同

修复

- 修复 动态滤波器在动态功能关闭后未能更新增益
- 修复 若干滑块的鼠标拖拽灵敏度

改进

- 改进 信号处理性能
- 改进 用户界面性能

### 1.1.1

修复

- 修复 工具提示中的语法错误
- 修复 Maschine 中外部侧链的设置问题

改进

- 改进 动态均衡效率
- 改进 用户界面性能

其他更改

- 增加 LV2 标签
- 调整某些弹出面板的背景
- 更换为 Windows MSI 安装器

### 1.1.0

破坏性更改

- 修复 错误的立体声动态处理
  - 这个修复会更正之前错误的立体声动态行为。如果在工程中使用了动态行为，请在更新前完成当前的混音工程。

新功能

- 增加 额外的动态参数：RMS `Length`（长度）、RMS `Mix`（混合）和 `Smooth`（平滑）
- 增加 FFT 分析仪立体声模式

修复与改进

- 修复 错误的并行滤波器旁通行为
- 修复 悬浮窗口重叠问题
- 修复 接近零的数值显示问题
- 修复 从 ZL Compressor 复制/粘贴滤波器错误的问题

### 1.0.3

修复与改进

- 修复 插件在未获得 UI 预设文件夹权限时的崩溃问题
- 修复 低搁架/高搁架 通过双击添加时的错误增益

### 1.0.2

修复与改进

- 提高 均衡匹配稳定性

### 1.0.1

与 ZL Equalizer 0.6.2 相比：

新功能

- 增加 更多侧链滤波器控制（滤波器类型与滤波器斜率）
- 增加 右键面板
- 增加 悬浮窗口更多控制选项
- 增加 更多快捷键
- 增加 界面缩放控制
- 增加 均衡匹配绘图控制

修复

- 修复 错误的八度音符
- 修复 错误的独奏显示
- 修复 中/侧模式下不正确的并行处理

改进

- 改进 `Matched Phase`（匹配相位）和 `Mixed Phase`（混合相位）的性能
- 改进 通用信号处理性能
- 改进 动态处理
- 改进 FFT 分析仪显示
- 改进 均衡匹配的拟合速度

其他更改

- 当采样率 > 44.1 kHz 时，提高了滤波器频率的最大值
- 从动态参数中移除了 `RMS` 与 `Smooth`
- 移除了 `Zero Latency`，因为动态处理不再需要额外的 1 ms 延迟
- 移除了 `High Quality`，因为动态处理现在始终保持高质量
- 移除了 均衡匹配的 `Weight` 与拟合算法控制
- 支持 VST3 参数上下文菜单
  - 在支持此功能的宿主中，如果您右键单击某些滑块，将会弹出一个原生的参数菜单。
- 支持 VST3/AAX 参数索引
  - 在支持此功能的宿主中，宿主可以将屏幕位置映射到参数，例如 Cubase 的 "AI Knob"。