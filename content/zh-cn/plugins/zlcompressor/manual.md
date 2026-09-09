---
title: 用户手册
description: 如何使用 ZL Compressor
weight: 2
---

<img src="/images/zlcompressor/dark_crop.jpg" style="width:750px; max-width: 100%; height: auto" />

-----

## 关于

ZL Compressor 是一款动态范围处理器，其主要特性有：

- **直观可视化**：实时 峰值/RMS 显示；硬件加速渲染
- **极低 CPU 占用**：高效的 前瞻 和 最高八倍过采样
- **多样处理设置**：四种处理风格和更多处理参数；输出削波器
- **高级侧链控制**：八频段参数均衡器；立体声模式和链接控制

## 顶部面板

___

<p float="left">
  <img src="/images/zlcompressor/zlaudio.svg" width="20pt" />
  <img src="/images/zlcompressor/logo.svg" width="20pt" />
</p>

你可以通过点击标志来打开 [界面设置面板](#界面设置面板)。

___

<p float="left">
  <img src="/images/zlspeceq/collections_bookmark.svg" width="20pt"/>
</p>

你可以通过点击图标来打开 [预设管理器面板](#预设管理器面板)。

___

**处理方向**

- `Compress`: 向下压缩
- `Inflate`: 向上压缩
- `Expand`: 向下扩展
- `Shape`: 向上扩展

当你选择 `Inflate` 和 `Shape`，削波 会被设置为 100% 从而对输出在 0 dB 软削波。你可以在此之后调整 削波 数值，但请务必注意输出电平以防止对监听设备或听力造成损害。

___

**`Clipper`（削波）**

控制削波器的相对驱动量。

___

**`Oversample`（过采样）**

共有四种过采样选项：

- `OFF` (关闭)：无过采样。无额外延迟。
- `2x` (2 倍)：2 倍过采样。64 个采样点的延迟（在 48 kHz 采样率下约 1.3 毫秒）。
- `4x` (4 倍)：4 倍过采样。72 个采样点的延迟（在 48 kHz 采样率下约 1.5 毫秒）。
- `8x` (8 倍)：8 倍过采样。76 个采样点的延迟（在 48 kHz 采样率下约 1.6 毫秒）。

更改此参数时，您可能会听到咔嗒声/爆音。请**不要**对此参数进行自动化控制。

___

**`Lookahead`（前瞻）**

控制主链信号的延迟。在支持插件延迟补偿的情况下（几乎所有 DAW 都支持），这可以被理解为侧链信号的前瞻时间。

更改此参数时，您可能会听到咔嗒声/爆音。请**不要**对此参数进行自动化控制。

___

<p float="left">
  <img src="/images/zlcompressor/delta.svg" width="20pt"/>
</p>

- 按下：输出差值信号（未压缩主链信号 和 压缩后主链信号 的 差值）

___

<p float="left">
  <img src="/images/zlcompressor/bypass.svg" width="20pt"/>
</p>

- 释放：旁路插件

> 警告：如果你开启差值信号并旁路插件，插件会输出静音。

___

## 左侧面板

___

<p float="left">
  <img src="/images/zlcompressor/dline_magnitude.svg" width="20pt"/>
</p>

- 按下：打开 [分析仪设置面板](#分析仪设置面板)
- 释放：关闭 [分析仪设置面板](#分析仪设置面板)

___

<p float="left">
  <img src="/images/zlcompressor/dline_rms.svg" width="20pt"/>
</p>

- 按下：打开 [累积分析仪](#累积分析仪)
- 释放：关闭 [累积分析仪](#累积分析仪)

___

<p float="left">
  <img src="/images/zlcompressor/dline_computer.svg" width="20pt"/>
</p>

- 按下：打开 [压缩计算曲线](#压缩计算曲线)
- 释放：关闭 [压缩计算曲线](#压缩计算曲线)

___

<p float="left">
  <img src="/images/zlcompressor/dline_eq.svg" width="20pt"/>
</p>

- 按下：打开侧链均衡器
- 释放：关闭侧链均衡器

___

<p float="left">
  <img src="/images/zlcompressor/dline_link.svg" width="20pt"/>
</p>

- 按下：打开侧链面板
- 释放：关闭侧链面板

___

<p float="left">
  <img src="/images/zlcompressor/dline_meter.svg" width="20pt"/>
</p>

- 按下：打开电平表面板
- 释放：关闭电平表面板

___

## 中央面板

中央面板由一个幅值分析仪、一个累积分析仪和一个压缩计算曲线组成。

### 幅值分析仪

幅值分析仪占据了整个中央面板。它显示三条曲线：

- 输入曲线：主链输入信号的幅值。
- 输出曲线：主链输出信号的幅值。
- 压缩曲线：压缩的幅值。

在左下角，您可以选择分析仪的时间窗口长度（`6 s`, `9 s`, `12 s`, 和 `18 s`）。为确保视觉流畅，`6 s` 和 `9 s` 设置在 60 Hz 或更高的刷新率下表现最佳。

在右下角，您可以选择幅值类型为 峰值（`Peak`）或 均方根（`RMS`），并选择分析仪的最小分贝值（`-9`, `-18`, `-36`, `-54`, 和 `-72`）。

当您把鼠标放在幅值分析仪上方，您可以通过 鼠标滚轮 调整阈值并通过 Ctrl/Command + 鼠标滚轮 调整比率。

### 累积分析仪

左侧的累积分析仪显示输入主链信号和输出主链信号的累积均方根值。您可以双击以重置此分析仪。

### 压缩计算曲线

计算机显示屏显示用于计算增益缩减值的曲线。

## 底部面板

___

**`Knee`（拐点）**

控制压缩计算曲线的拐点宽度。更大的拐点使未压缩状态和压缩状态之间的过渡更平滑。

___

**`Curve`（弯曲）**

控制压缩状态下的非线性行为。在 `Compress` 和 `Shape` 下可用。

___

**`Floor`（底限）**

控制恢复为未压缩状态的底限值。在 `Inflate` 和 `Expand` 下可用。

___

**`Threshold`（阈值）**

___

**`Ratio`（比率）**

___

**压缩风格**

- `Clean`：前馈设计，具有指数衰减的启动/释放阶段，提供透明、精确的动态控制。
- `Classic`：后馈设计，具有指数衰减的启动/释放阶段，提供平滑、粘合的动态控制。
- `Optical`：前馈设计，具有线性衰减的启动/释放，提供平滑、精确的动态控制。
- `Vocal`：后馈设计，具有线性衰减的启动/释放，提供柔和、粘合的动态控制。

`Optical` 和 `Vocal` 在 `Inflate` 和 `Expand` 方向下不可用。

___

**`Pump`（抽吸）**

控制启动阶段的行为。较大的 `Pump` 值会使启动更激进，从而引入抽吸效应。

___

**`Smooth`（平滑）**

控制释放阶段的行为。较大的 `Smooth` 值会使释放阶段的开始变得更慢。

___

**`Attack`（启动时间）**

___

**`Release`（释放时间）**

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

___

**`Range`（范围）**

控制压缩范围。实际值受 **`Wet`** 参数的影响。

___

**`Hold`（保持）**

控制压缩保持的最短时间。在此期间，压缩可以对新的峰值做出反应，但不能释放。

___

**`Makeup`（补偿增益）**

控制压缩后的补偿增益。实际值受 **`Wet`** 参数的影响。

___

<p float="left">
  <img src="/images/zlcompressor/dline_l.svg" width="20pt"/>
</p>

- 按下：当你按下按钮，插件开始测量输入信号与输出信号的整体响度
- 释放：当你释放按钮，插件将 **`Makeup`** 更新为两个响度值的差
- 在测量期间，你无法更改 **`Makeup`** 和 **`Wet`**

___

**`Wet`（湿信号）**

控制湿信号的百分比。

___

## 侧链面板

___

<p float="left">
  <img src="/images/zlcompressor/midside.svg" width="20pt"/>
</p>

将立体声模式设置为 中/侧。中/侧与彼此相互链接。

例如，如果中信号压缩为 -5 dB，侧信号压缩为 -1 dB，并且链接为 20%，则最终压缩为：
- 中信号压缩：(-5) * 0.8 + (-1) * 0.2 = -4.2 dB
- 侧信号压缩：(-1) * 0.8 + (-5) * 0.2 = -1.8 dB

___

<p float="left">
  <img src="/images/zlcompressor/leftright.svg" width="20pt"/>
</p>

将立体声模式设置为 左/右。左/右与彼此相互链接。

___

<p float="left">
  <img src="/images/zlcompressor/midside_max.svg" width="20pt"/>
</p>

将立体声模式设置为 中/侧 最大。中/侧与两者中较大的链接，从而较大的压缩数值不会因为链接而减小。

例如，如果中信号压缩为 -5 dB，侧信号压缩为 -1 dB，并且链接为 20%，则最终压缩为：
- 中信号压缩：-5 dB
- 侧信号压缩：(-1) * 0.8 + (-5) * 0.2 = -1.8 dB

___

<p float="left">
  <img src="/images/zlcompressor/leftright_max.svg" width="20pt"/>
</p>

将立体声模式设置为 左/右 最大。左/右与两者中较大的链接。

___

<p float="left">
  <img src="/images/zlcompressor/shuffle.svg" width="20pt"/>
</p>

- 按下：交换侧链立体声模式。
    - 如果立体声模式是 左/右，侧链将来自 右/左。
    - 如果立体声模式是 中/侧，侧链将来自 侧/中。

___

**`Link`（链接）**

控制两个立体声通道的链接。

___

**`Stereo Wet`（立体声湿信号）**

控制每个立体声通道的湿信号百分比。实际值受 **`Wet`** 参数的影响。

___

**`Gain`（增益）**

控制侧链信号的增益。

___

<p float="left">
  <img src="/images/zlcompressor/external-side.svg" width="20pt"/>
</p>

- 按下：使用外部侧链信号
- 释放：使用内部侧链信号

___

<p float="left">
  <img src="/images/zlcompressor/solo.svg" width="20pt"/>
</p>

- 按下：监听侧链信号

___

<p float="left">
  <img src="/images/zlcompressor/bypass.svg" width="20pt"/>
</p>

- 释放：旁路侧链均衡器

___


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

**`RMS Length`（RMS 长度）**

控制 RMS 窗口长度（以毫秒为单位）。

___

**`RMS Speed`（RMS 速度）**

控制 RMS 压缩启动/释放的相对比例。

___

**`RMS Mix`（RMS 混合）**

控制 RMS 压缩的混合比例。

___

## 分析仪设置面板

___

**`Magnitude Type`（幅值类型）**

选择幅值测量类型：

- `Peak`：使用峰值作为幅值测量类型
- `RMS`：使用均方根（RMS）作为幅值测量类型

___

**`Magnitude Stereo`（幅值立体声）**

选择幅值测量立体声设置。

___

**`Magnitude Move Type`（幅值移动方式）**

选择幅值移动方式：

- `Sync`：显示与音频同步移动
- `Slow`：显示在慢速/快速移动之间交替
- `Roll`：显示在不移动的情况下重新写入旧内容

___

**`Pre/Post/Delta/Side`（输入/输出/差值/侧链）**

- `Pre`：显示输入幅值
- `Post`：显示输出幅值
- `Delta`：显示差值幅值
- `Side`：显示侧链幅值

___

**`Time Length`（时间窗口长度）**

选择幅值显示的时间跨度。

___

**`Decibles Range`（分贝范围）**

选择幅值显示的最大/最小分贝。

___

## 界面设置面板

界面设置面板控制分析仪颜色、滑块操作等设置。下面将按照从上至下的顺序介绍。

#### 颜色

你可以通过点击左侧色块来调整颜色，通过拖动右侧滑块来改变透明度。

**`Text Colour`（文本颜色）**

**`Background Colour`（背景颜色）**

为了更好的可读性，请将文本/背景设置为高对比度的颜色。

**`Shadow Colour`（阴影颜色）**

**`Glow Colour`（发光颜色）**

**`Pre Colour`（输入颜色）**

**`Post Colour`（输出颜色）**

**`Reduction Colour`（压缩颜色）**

**`Sidechain Colour`（侧链颜色）**

**`Computer Colour`（计算曲线颜色）**

**`Grid Colour`（网格颜色）**

**`Colour Map 1`（颜色映射 1）**

- 单个滤波器曲线的颜色映射。

**`Colour Map 2`（颜色映射 2）**

- Stereo/Left/Right/Mid/Side 曲线的颜色映射。

#### 控制

**`Wheel Sensitivity`（滚轮灵敏度）**

- `Rough`：未按下 `Shift` 时的鼠标滚轮灵敏度
- `Fine`：按下 `Shift` 时的鼠标滚轮灵敏度
- `Menu`：调节下拉框选项时的鼠标滚轮灵敏度
- `Reverse`：按下 `Shift` 时是否反转鼠标滚轮的方向

**`Drag Sensitivity`（拖拽灵敏度）**

- `Rough`：未按下 `Shift` 时的鼠标拖拽灵敏度
- `Fine`：按下 `Shift` 时的鼠标拖拽灵敏度

**`Rotary Slider Style`（旋钮滑块样式）**

- `Circular`：通过鼠标进行圆周运动来拖动的旋钮控件
- `Horizontal`：通过鼠标左右拖动的旋钮控件
- `Vertical`：通过鼠标上下拖动的旋钮控件
- `Horiz + Vert`：通过鼠标上下或左右拖动的旋钮控件
- `Distance`：鼠标在整个范围内拖动滑块所需移动的相对距离。它不适用于 `Circular` 样式。

**`Slider Double Click`（滑块双击）**

- `Return Default`：当你双击滑块时，它将返回默认值；当你按住 Ctrl/Command 双击滑块时，将打开数值编辑器。
- `Open Editor`：当你双击滑块时，它将打开数值编辑器；当你按住 Ctrl/Command 双击滑块时，将返回默认值。

___

以下操作的快捷键设置：

**`Enter Solo`（进入独奏）**

**`Exit Solo`（退出独奏）**

___

#### 其他

**`Refresh Rate`（刷新率）**

为了更好的分析仪显示效果，请将此设置为显示器刷新率的 1/n。例如：
- 如果你的显示器刷新率是 120 Hz，将其设置为 120 Hz、60 Hz（1/2）或 30 Hz（1/4）。不要设置为 90 Hz。
- 如果你的显示器刷新率是 90 Hz，将其设置为 90 Hz 或 30 Hz（1/3）。不要设置为 60 Hz。

**`FFT`（FFT 设置）**

- `Tilt`：FFT 的额外倾斜斜率
- `Speed`：FFT 的额外衰减速度

**`Curve Thickness`（曲线粗细）**

控制幅值分析仪的曲线粗细

**`Tooltip`（工具提示）**

选择工具提示语言。重新打开插件窗口时生效。

**`UI Scaling`（界面缩放）**

选择字体大小模式。

- `Scale`：字体大小随窗口大小缩放。控制相对比例。
- `Static`：字体大小固定。控制实际字体大小。

**`Window Size Fix`（窗口大小固定）**

选择是否开启窗口大小固定。

- `Off`：插件窗口大小调整将被保存
- `On`：插件窗口大小调整将不会被保存，但每次打开插件时都会保持当前的大小。窗口大小依然可以被调整，但这些调整不会被保存。

___

## 预设管理器面板

预设管理器面板让你可以管理（保存/分组/删除）预设。

___

**`Search Presets`（搜索预设）**

输入预设名称并进行搜索。

___

**`New Group`（新建分组）**

输入新分组名称并按下 `Enter` 键以保存。

___

**`New Preset`（新建预设）**

输入新预设名称并按下 `Enter` 键以保存。

___

<p float="left">
  <img src="/images/zlspeceq/trash.svg" width="20pt"/>
</p>

- 按下：删除选中的预设分组（以及该分组中的所有预设）或选中的预设

___

<p float="left">
  <img src="/images/zlspeceq/folder_open.svg" width="20pt"/>
</p>

- 按下：打开预设文件夹

___

## 界面控制

通常，你可以通过 `Shift` 开启精细调节，通过 `Ctrl/Command` 开启特殊调节。如果在按下 `Shift` 时鼠标滚轮方向被反转，你可以再次反转它（在界面设置面板中）以将其恢复正常。

- 当用 鼠标拖拽/鼠标滚轮调节 滑块时，按下 `Shift` 可以进行精细调节
- 当用 鼠标拖拽频段按钮时，按下 `Shift` 可以进行精细拖拽
- 当用 鼠标拖拽频段按钮时，使用 `Ctrl/Command` + 鼠标左键 可以固定频率，使用 `Ctrl/Command` + 鼠标右键 可以固定增益