---
title: 用户手册
description: 如何使用 ZL Compressor
weight: 2
---

<img src="/images/zlcompressor/dark_crop.jpg" style="width:750px; max-width: 100%; height: auto" />

-----

## 关于

ZL Compressor 是一款动态范围压缩器，其主要特性有：

- **直观可视化**：实时 峰值/RMS 显示；硬件加速渲染
- **极低 CPU 占用**：高效的 前瞻 和 最高八倍过采样
- **多样压缩设置**：四种压缩风格和更多压缩参数；压缩后削波器
- **高级侧链控制**：八频段参数均衡器；立体声模式和链接控制

## 顶部面板

-----

<p float="left">
<img src="/images/zlcompressor/zlaudio.svg" width="20pt" />
<img src="/images/zlcompressor/logo.svg" width="20pt" />
</p>

双击该标志将打开[外观设置面板](#外观设置面板)。

-----

**削波（Clipper）**

控制削波器的相对驱动量。

___

**过采样（Oversample）**

共有四种过采样选项：

  - `OFF` (关闭)：无过采样。无额外延迟。
  - `2x` (2 倍)：2 倍过采样。64 个采样点的延迟（在 48 kHz 采样率下约 1.3 毫秒）。
  - `4x` (4 倍)：4 倍过采样。72 个采样点的延迟（在 48 kHz 采样率下约 1.5 毫秒）。
  - `8x` (8 倍)：8 倍过采样。76 个采样点的延迟（在 48 kHz 采样率下约 1.6 毫秒）。

更改此参数时，您可能会听到咔嗒声/爆音。请**不要**对此参数进行自动化控制。

-----

**前瞻（Lookahead）**

控制主链信号的延迟。在支持插件延迟补偿的情况下（几乎所有 DAW 都支持），这可以被理解为侧链信号的前瞻时间。

更改此参数时，您可能会听到咔嗒声/爆音。请**不要**对此参数进行自动化控制。

-----


<p float="left">
  <img src="/images/zlcompressor/delta.svg" width="20pt"/>
</p>

- 按下：输出差值信号（未压缩主链信号 和 压缩后主链信号 的 差值）

___

<p float="left">
  <img src="/images/zlcompressor/bypass.svg" width="20pt"/>
</p>

- 释放：旁通插件

> 警告：如果你开启差值信号并旁通插件，插件会输出静音。

___

## 左侧面板

-----

<p float="left">
<img src="/images/zlcompressor/dline_rms.svg" width="20pt">
</p>

  - 按下：打开 [累积分析器](#累积分析器)
  - 弹起：关闭 [累积分析器](#累积分析器)

-----

<p float="left">
<img src="/images/zlcompressor/dline_computersvg" width="20pt"/>
</p>

  - 按下：打开 [压缩计算曲线](#压缩计算曲线)
  - 弹起：关闭 [压缩计算曲线](#压缩计算曲线)

-----

<p float="left">
<img src="/images/zlcompressor/dline_eq.svg" width="20pt"/>
</p>

  - 按下：打开[侧链均衡器](#侧链均衡器)
  - 弹起：关闭[侧链均衡器](#侧链均衡器)

-----

<p float="left">
<img src="/images/zlcompressor/dline_link.svg" width="20pt"/>
</p>

  - 按下：打开[侧链面板](#侧链面板)
  - 弹起：关闭[侧链面板](#侧链面板)

-----

## 中央面板

中央面板由一个幅值分析器、一个累积分析器和一个压缩计算曲线组成。

### 幅值分析器

幅值分析器占据了整个中央面板。它显示三条曲线：

  - 输入曲线：主链输入信号的幅值。
  - 输出曲线：主链输出信号的幅值。
  - 压缩曲线：压缩的幅值。

在左下角，您可以选择分析器的时间窗口长度（`6 s`, `9 s`, `12 s`, 和 `18 s`）。为确保视觉流畅，`6 s` 和 `9 s` 设置在 60 Hz 或更高的刷新率下表现最佳。

在右下角，您可以选择幅值类型为 峰值（`Peak`）或 均方根（`RMS`），并选择分析器的最小分贝值（`-9`, `-18`, `-36`, `-54`, 和 `-72`）。

当您把鼠标放在幅值分析器上方，您可以通过 鼠标滚轮 调整阈值并通过 Ctrl/Command + 鼠标滚轮 调整比率。

### 累积分析器

左侧的累积分析器显示输入主链信号和输出主链信号的累积均方根值。您可以双击以重置此分析器。

### 压缩计算曲线

计算机显示屏显示用于计算增益缩减值的曲线。

## 底部面板

-----

**膝宽（Knee）**

控制压缩计算曲线的膝宽。更大的膝宽使未压缩状态和压缩状态之间的过渡更平滑。

-----

**弯曲（Curve）**

控制压缩状态下的非线性行为。

-----

**阈值（Threshold）**

-----

**比率（Ratio）**

-----

**压缩风格**

  - `Clean`：前馈设计，具有指数衰减的启动/释放阶段，提供透明、精确的动态控制。
  - `Classic`：后馈设计，具有指数衰减的启动/释放阶段，提供平滑、粘合的动态控制。
  - `Optical`：前馈设计，具有线性衰减的启动/释放，提供平滑、精确的动态控制。
  - `Vocal`：后馈设计，具有线性衰减的启动/释放，提供柔和、粘合的动态控制。

-----

**抽吸（Pump）**

控制启动阶段的行为。较大的 `Pump` 值会使启动更激进，从而引入抽吸效应。

-----

**平滑（Smooth）**

控制释放阶段的行为。较大的 `Smooth` 值会使释放阶段的开始变得更慢。

-----

**启动时间（Attack）**

-----

**释放时间（Release）**


___

<p float="left">
  <img src="/images/zlcompressor/dline_r.svg" width="20pt"/>
</p>

- 按下：打开 RMS 压缩
- 释放：关闭 RMS 压缩

RMS 压缩响应短时响度并且让瞬态通过，从而提供更透明、自然的压缩效果。

___

<p float="left">
  <img src="/images/zlcompressor/right_arrow.svg" width="20pt"/>
</p>

- 按下：打开 [RMS 面板](#rms-面板)
- 释放：关闭 [RMS 面板](#rms-面板)

-----

**范围（Range）**

控制压缩的范围。实际值受 **湿信号** 参数的影响。

-----

**保持（Hold）**

控制压缩保持的最短窗口长度。在此期间，压缩可以对新的峰值做出反应，但不能释放。

-----

**补偿增益（Makeup）**

控制压缩后的补偿增益。实际值受 **湿信号** 参数的影响。

-----

<p float="left">
  <img src="/images/zlcompressor/dline_l.svg" width="20pt"/>
</p>

- 按下：当你按下按钮，插件开始测量输入信号与输出信号的整体响度
- 释放：当你释放按钮，插件更新**补偿增益**为两响度值的差
- 在测量期间，你不可以更改**补偿增益**和**湿信号**

___

**湿信号（Wet）**

控制湿信号的百分比。

-----

## 侧链面板

-----

<p float="left">
<img src="/images/zlcompressor/midside.svg" width="20pt"/>
</p>

将立体声模式设置为 中/侧。中/侧与彼此相互链接。

例如，如果中信号压缩为 -5 dB，侧信号压缩为 -1 dB，并且链接为 20%，则最终压缩为：
- 中信号压缩：(-5) * 0.8 + (-1) * 0.2 = -4.2 dB
- 侧信号压缩：(-1) * 0.8 + (-5) * 0.2 = -1.8 dB

<p float="left">
<img src="/images/zlcompressor/leftright.svg" width="20pt"/>
</p>

将立体声模式设置为 左/右。左/右与彼此相互链接。


<p float="left">
  <img src="/images/zlcompressor/midside_max.svg" width="20pt"/>
</p>

将立体声模式设置为 中/侧 最大。中/侧与两者中较大的链接，从而较大的压缩数值不会因为链接而减小。

例如，如果中信号压缩为 -5 dB，侧信号压缩为 -1 dB，并且链接为 20%，则最终压缩为：
- 中信号压缩：-5 dB
- 侧信号压缩：(-1) * 0.8 + (-5) * 0.2 = -1.8 dB

<p float="left">
  <img src="/images/zlcompressor/leftright_max.svg" width="20pt"/>
</p>

将立体声模式设置为 左/右。左/右与两者中较大的链接。

-----

<p float="left">
<img src="/images/zlcompressor/shuffle.svg" width="20pt"/>
</p>

  - 按下：交换侧链立体声模式。
      - 如果立体声模式是 左/右，侧链将来自 右/左。
      - 如果立体声模式是 中/侧，侧链将来自 侧/中。

-----

**链接（Link）**

控制两个立体声通道的链接。

___

**立体声湿信号**

控制每个立体声通道的湿信号百分比。实际值受 **湿信号** 参数的影响。

-----

**增益（Gain）**

控制侧链信号的增益。

-----

<p float="left">
<img src="/images/zlcompressor/external-side.svg" width="20pt"/>
</p>

  - 按下：使用外部侧链信号。
  - 弹起：使用内部侧链信号。

-----

<p float="left">
<img src="/images/zlcompressor/solo.svg" width="20pt"/>
</p>

  - 按下：监听侧链信号。

-----

## 侧链均衡器

侧链均衡器允许您直观地对侧链信号进行均衡。它有一个频谱图，您可以在其中添加和操作滤波器频段。

**添加频段**

当您双击频谱图时，如果至少有一个频段处于关闭状态，将会根据相应的频率/增益打开一个频段：

  - 频率 < 20Hz：添加一个高通滤波器。
  - 20Hz <= 频率 < 50Hz：添加一个低架滤波器。
  - 50Hz <= 频率 < 5000Hz：添加一个峰值滤波器。
  - 5000Hz <= 频率 < 15000Hz：添加一个高架滤波器。
  - 15000Hz <= 频率：添加一个低通滤波器。

**拖动频段**

当一个频段不处于关闭状态时，一个可拖动的按钮会出现在相应的频率/增益位置。您可以通过 拖动按钮 来调整频率和增益、用 鼠标滚轮 调整 Q 值或者用 Ctrl/Command + 鼠标滚轮 调整滤波器斜率。

当您通过单击按钮选择频段时：

  - 按钮附近会出现一个额外的控制窗口，通过它可以快速旁通/关闭所选频段、选择滤波器类型和调整滤波器斜率。
  - 频率/增益值会出现在左上角，通过它可以查看/编辑所选频段的频率/增益值。

**监听频段**

您可以 监听一个频段通过双击其可拖动的按钮 或 退出监听通过单击频谱图。监听也会在 均衡器被关闭 或 插件窗口被关闭 时自动退出。

**右键菜单**

当您鼠标右键单击滤波器按钮，您可以通过出现的右键菜单 反转当前滤波器增益 或 复制/粘贴滤波器（可以跨插件）。

## RMS 面板


___

**RMS 长度（Length）**

控制 RMS 窗口长度（以毫秒为单位）

___

**RMS 速度（Speed）**

控制 RMS 压缩 启动/释放 的 相对比例

___

**RMS 混合（Mix）**

控制 RMS 压缩 的 混合比例

___

## 外观设置面板

外观设置面板控制频谱图颜色、滑块操作等设置。下面将按照从上至下的顺序介绍。

#### 颜色（Colour）

您可以通过单击左侧色块来调整颜色，通过拖动右侧滑块来改变透明度。

**文字颜色（Text Colour）**

**背景颜色（Background Colour）**

为了良好的显示效果，请将文字/背景设置为对比度高的颜色。

**阴影颜色（Shadow Colour）**

**发光颜色（Glow Colour）**

**输入信号颜色（Pre Colour）**

**输出信号颜色（Post Colour）**

**压缩信号颜色（Reduction Colour）**

**压缩计算颜色（Computer Colour）**

**网格线颜色（Grid Colour）**

**Colour Map 1**

- 单个滤波器曲线的色彩搭配。

**Colour Map 2**

- 立体/左/右/中/侧声道曲线的色彩搭配。

**导入（Import Colours）**

- 导入颜色设置（`.xml` 文件）

**导出（Export Colours）**

- 导出颜色设置（`.xml` 文件）

#### 控制（Control）

**鼠标滚轮敏感度（Wheel Sensitivity）**

- Rough：未按下 Shift 时鼠标滚轮的敏感度
- Fine：按下 Shift 时鼠标滚轮的敏感度
- 反转：按下 Shift 时是否反转鼠标滚轮方向

**鼠标拖拽敏感度（Drag Sensitivity）**

- Rough：未按下 Shift 时鼠标拖拽的敏感度
- Fine：按下 Shift 时鼠标拖拽的敏感度

**旋钮操作方式（Rotary Slider Style）**

- `Circular`：鼠标旋转控制旋钮
- `Horizontal`：鼠标水平滑动控制旋钮
- `Vertical`：鼠标竖直滑动控制旋钮
- `Horiz + Vert`：鼠标水平/竖直滑动控制旋钮
- Distance：将旋钮从最小值拖动至最大值鼠标需要移动的相对距离。不对 Circular 方式生效。

**旋钮/滑块双击（Slider Double Click）**

- 返回默认值（`Return Default`）: 双击返回默认值; Ctrl/Command + 双击打开数值编辑器。
- 打开数值编辑器（`Open Editor`）: 双击打开数值编辑器; Ctrl/Command + 双击返回默认值。

**导入（Import Controls）**

- 导入控制设置（`.xml` 文件）

**导出（Export Controls）**

- 导出控制设置（`.xml` 文件）

#### 其他（Other）

**刷新率（Refresh Rate）**

为了更好的分析器显示，请将该值设置为您显示器刷新率的几分之一。例如：

- 如果您显示器刷新率为 120 Hz，您可以设置为 120 Hz、60 Hz 或 30 Hz。不要设置为 90 Hz。
- 如果您显示器刷新率为 90 Hz，您可以设置为 90 Hz 或 30 Hz。不要设置为 60 Hz。

**频谱图设置**

- Tilt：控制（额外的）频谱图倾斜斜率
- Speed：控制（额外的）频谱图衰减速度

**曲线粗细度**

控制幅值分析器曲线粗细度

**提示（Tooltip）**

选择提示语言。会在插件窗口重新打开后生效。

**UI Scaling (界面缩放)**

选择字体大小模式。

- `Scale (缩放)`: 字体大小随窗口大小缩放。控制相对比例。
- `Static (静态)`: 字体大小固定。控制实际字体大小。

#### 底部按钮

___

<p float="left">
  <img src="/images/zlcompressor/save.svg" width="18pt"/>
</p>
- 保存当前外观设置。

___

<p float="left">
  <img src="/images/zlcompressor/reset_settings.svg" width="18pt"/>
</p>

- 载入部分默认设置。

___

<p float="left">
  <img src="/images/zlcompressor/close.svg" width="18pt"/>
</p>

- 舍弃所有未保存设置并关闭外观设置面板。

___


## 快捷键

一般来说，按下 Shift 可以进行精细调整，按下 Ctrl/Command 可以进行特殊调整。如果按下 Shift 后鼠标滚轮的方向发生反转，可以再次设置反转以进行纠正。

- 当用 鼠标拖拽/鼠标滚轮调整 旋钮/滑块，按下 Shift 可以进行精细调整
- 当用 鼠标拖拽频段按钮时，按下 Shift 可以进行精细拖拽
- 当用 鼠标拖拽频段按钮时，使用 Ctrl/Command + 鼠标左键 可以固定频率，使用 Ctrl/Command + 鼠标右键 可以固定增益