---
title: 使用手册
description: 如何使用 ZL Spectrum Equalizer
weight: 2
---

<img src="/images/zlspeceq/dark_crop.jpg" style="width:750px; max-width: 100%; height: auto" />

## 关于

ZL Spectrum Equalizer 是一款动态频谱均衡器插件，具有以下主要特性：

- **多功能性**：通过 9 种滤波器类型、5 种声道模式、7 种可变斜率，以及多达 24 个线性相位频段来塑造声音。
- **频谱动态**：体验精确的频域动态处理，追踪并控制整个频谱的谐振，具有可调节的阈值、启动时间、释放时间和拐点宽度。
- **强大引擎**：通过不同的频谱分辨率设置、侧链平滑，以及随频率变化的启动/释放偏置来定制行为和延迟，所有这些均由高性能的 FFT 引擎提供支持。
- **直观控制**：通过精心设计的界面（包含交互式频谱图、智能碰撞检测和流畅的动画）实现快速、流畅的均衡处理。

## 顶部面板

___

<p float="left">
  <img src="/images/zlspeceq/zlaudio.svg" width="20pt" />
  <img src="/images/zlspeceq/logo.svg" width="20pt" />
</p>

你可以通过点击标志来打开 [界面设置面板](#界面设置面板)。

___

<p float="left">
  <img src="/images/zlspeceq/collections_bookmark.svg" width="20pt"/>
</p>

你可以通过点击图标来打开 [预设管理器面板](#预设管理器面板)。

___

**`Analyzer`（分析仪）**

你可以通过点击文本来打开 [分析仪设置面板](#分析仪设置面板)。

___

**频谱分辨率**

选择频谱处理分辨率：

- `Extreme Low`：约 12 ms 延迟
- `Very Low`：约 23 ms 延迟
- `Low`：约 46 ms 延迟
- `Medium`：约 93 ms 延迟
- `High`：约 186 ms 延迟
- `Very High`：约 372 ms 延迟
- `Extreme High`：约 743 ms 延迟

___

<p float="left">
  <img src="/images/zlspeceq/settings.svg" width="20pt"/>
</p>

- 按下：打开 [频谱设置面板](#频谱设置面板)

___

**频谱平滑类型**

选择频谱处理侧链平滑类型：

- `OCT`：倍频程
- `ERB`：等效矩形带宽（在低频处更平滑）

___

**频谱平滑值**

调节频谱处理侧链平滑值。更多信息请参见 [频谱动态](#频谱动态)。

___

**`Output`（输出）**

你可以通过点击文本来打开 [输出设置面板](#输出设置面板)。它显示了当前滤波器增益缩放比例和总输出增益。

___

<p float="left">
  <img src="/images/zlspeceq/external-side.svg" width="20pt"/>
</p>

- 按下：使用外部侧链
- 释放：使用内部侧链

___

<p float="left">
  <img src="/images/zlspeceq/bypass.svg" width="20pt"/>
</p>

- 释放：旁路插件

___

## 中央面板

中央面板包括频谱分析仪、滤波器响应曲线、滤波器按钮、悬浮窗口以及分贝刻度。

#### 频谱分析仪

频谱分析仪显示输入/输出/侧链信号的频谱以及碰撞区域（可选）。你可以通过 [分析仪设置面板](#分析仪设置面板) 来控制它。

#### 滤波器响应曲线

滤波器响应曲线显示了每个单独频段的幅度响应以及每个声道模式的幅度响应。

#### 滤波器按钮

滤波器按钮附着在滤波器响应曲线上。你可以拖动它们来更改滤波器参数。更多信息请参见 [界面控制](#界面控制)。

当你在频谱上双击（按下或不按下 `Ctrl/Command` 键）时，会在相应位置添加一个带滤波器按钮的频段（开启或不开启动态行为）。

#### 悬浮窗口

悬浮窗口附着在所选频段的滤波器按钮上。你可以通过该窗口控制某些滤波器参数。

| 图标                                                  | 滤波器类型  | 图标                                               | 声道模式 |
| ----------------------------------------------------- | ------------ | -------------------------------------------------- | ---------------- |
| <img src="/images/zlspeceq/peak.svg" width="20pt"/>      | `Peak`       | <img src="/images/zlspeceq/stereo.svg" width="20pt"/> | `Stereo`         |
| <img src="/images/zlspeceq/lowshelf.svg" width="20pt"/>  | `Low Shelf`  | <img src="/images/zlspeceq/left.svg" width="20pt"/>   | `Left`           |
| <img src="/images/zlspeceq/lowpass.svg" width="20pt"/>   | `Low Pass`   | <img src="/images/zlspeceq/right.svg" width="20pt"/>  | `Right`          |
| <img src="/images/zlspeceq/highshelf.svg" width="20pt"/> | `High Shelf` | <img src="/images/zlspeceq/mid.svg" width="20pt"/>    | `Mid`            |
| <img src="/images/zlspeceq/highpass.svg" width="20pt"/>  | `High Pass`  | <img src="/images/zlspeceq/side.svg" width="20pt"/>   | `Side`           |
| <img src="/images/zlspeceq/notch.svg" width="20pt"/>     | `Notch`      |                                                    |                  |
| <img src="/images/zlspeceq/bandpass.svg" width="20pt"/>  | `Band Pass`  |                                                    |                  |
| <img src="/images/zlspeceq/tiltshelf.svg" width="20pt"/> | `Tilt Shelf` |                                                    |                  |
| <img src="/images/zlspeceq/flattilt.svg" width="20pt"/>  | `Flat Tilt`  |                                                    |                  |

#### 右键菜单

___

**`Invert Gain`（反转增益）**

- 点击：反转所选频段的增益

___

**`Split L/R`（拆分左右声道）**

- 点击：将所选频段设置为 `Left` 并添加一个参数相同但在 `Right` 的频段

___

**`Split M/S`（拆分中侧声道）**

- 点击：将所选频段设置为 `Mid` 并添加一个参数相同但在 `Side` 的频段

___

**`Copy`（复制）**

- 点击：将所有选定频段的滤波器参数复制到剪贴板

___

**`Paste`（粘贴）**

- 点击：从剪贴板获取滤波器参数并创建这些频段

___

#### 分贝刻度

你可以选择幅度响应曲线的分贝刻度（通过右上角的下拉框），以及频谱分析仪的分贝刻度（通过右下角的下拉框）。

## 底部面板

#### 左侧面板

___

<p float="left">
  <img src="/images/zlspeceq/bypass.svg" width="20pt"/>
</p>

- 释放：旁路该频段。

---

**频段选择**

选择当前频段。

___

**滤波器类型**

选择滤波器类型：`Peak`、`Low Shelf`、`Low Pass`、`High Shelf`、`High Pass`、`Notch`、`Band Pass`、`Tilt Shelf` 和 `Flat Tilt`。

---

**斜率**

选择滤波器斜率：`6 dB/oct`、`12 dB/oct`、`24 dB/oct`、`36 dB/oct`、`48 dB/oct`、`72 dB/oct` 和 `96 dB/oct`。较高的斜率会让滤波器的响应曲线变化更陡峭。`Peak`、`Notch` 和 `Band Pass` 不支持 `6 dB/oct`。`Flat Tilt` 不支持斜率设置。

---

**声道模式**

选择声道模式：`Stereo`、`Left`、`Right`、`Mid` 和 `Side`。

___

**`FREQ`（频率）**

调节频率。频率的最大值受采样率影响。

___

**`GAIN`（增益）**

调节基础增益与目标增益。更多信息请参见 [频谱动态](#频谱动态)。

___

**`Q`（品质因数）**

调节品质因数。

___

<p float="left">
  <img src="/images/zlspeceq/dynamic.svg" width="20pt"/>
</p>

- 按下：开启该频段的频谱动态行为

___


<p float="left">
  <img src="/images/zlspeceq/close.svg" width="20pt"/>
</p>

- 点击：关闭该频段

___

#### 右侧面板

___

<p float="left">
  <img src="/images/zlspeceq/bypass.svg" width="20pt"/>
</p>

- 释放：旁路动态行为。更多信息请参见 [频谱动态](#频谱动态)。

___

<p float="left">
  <img src="/images/zlspeceq/delta.svg" width="20pt"/>
</p>

- 按下：输出动态差值信号。

___

**动态模式**

选择动态模式。更多信息请参见 [频谱动态](#频谱动态)。

___

**`Threshold`（阈值）**

更多信息请参见 [频谱动态](#频谱动态)。

___

**`Knee`（拐点）**

更多信息请参见 [频谱动态](#频谱动态)。

___

**`Attack`（启动时间）**

更多信息请参见 [频谱动态](#频谱动态)。

___

**`Release`（释放时间）**

更多信息请参见 [频谱动态](#频谱动态)。

___

## 频谱设置面板

___

**`Tilt`（倾斜斜率）**

调节频谱处理侧链倾斜斜率。更多信息请参见 [频谱动态](#频谱动态)。

___

**`Attack Skew`（启动偏置）**

调节频谱处理侧链启动偏置。更多信息请参见 [频谱动态](#频谱动态)。

___

**`Release Skew`（释放偏置）**

调节频谱处理侧链释放偏置。更多信息请参见 [频谱动态](#频谱动态)。

___

**`Gate`（门限）**

调节相对响度的频谱门限。更多信息请参见 [频谱动态](#频谱动态)。

___

## 输出设置面板

___

**`GAIN`（增益）**

调节额外输出增益。

___

**`SCALE`（缩放）**

调节所有滤波器的基础增益与目标增益缩放比例。

___

<p float="left">
  <img src="/images/zlspeceq/dline_s.svg" width="20pt"/>
</p>

- 按下：开启静态增益补偿（SGC）
- 释放：关闭静态增益补偿（SGC）

> SGC 会根据滤波器的参数来估算补偿量。SGC **不够精确**。不过，它**不会影响主链信号的动态**。

___

<p float="left">
  <img src="/images/zlspeceq/dline_l.svg" width="20pt"/>
</p>

- 按下：开始测量输入信号与输出信号的整体响度
- 释放：将 `Output Gain`（输出增益）更新为两响度值之差


___

## 分析仪设置面板

___

**`Pre/Post/Side`（输入/输出/侧链分析仪）**

- 按下：开启输入/输出/侧链分析仪
- 释放：关闭输入/输出/侧链分析仪

___

**衰减速度**

___

**斜率**

- 影响频谱显示（不影响实际信号）
- `0 dB/oct`：无倾斜，白噪声显示为水平线
- `3 dB/oct`：粉红噪声显示为水平线
- `4.5 dB/oct`：默认值，能更好地代表感知响度

___

**平滑**

- 调节平滑值，值越大表示频谱越平滑
- `OCT`：以倍频程平滑频谱
- `ERB`：以 ERB（等效矩形带宽）平滑频谱

---

<p float="left">
  <img src="/images/zlspeceq/freeze.svg" width="20pt"/>
</p>

- 按下：开启 FFT 冻结功能。将鼠标悬停在分析仪上 2 秒钟，输出/侧链分析仪将会被冻结，直到你移动鼠标。

___

**FFT 分析仪声道模式**

| 图标                                                      | 声道模式 |
| --------------------------------------------------------- | ---------------- |
| <img src="/images/zlspeceq/stereo.svg" width="20pt"/> | `Stereo`         |
| <img src="/images/zlspeceq/left.svg" width="20pt"/>   | `Left`           |
| <img src="/images/zlspeceq/right.svg" width="20pt"/>  | `Right`          |
| <img src="/images/zlspeceq/mid.svg" width="20pt"/>    | `Mid`            |
| <img src="/images/zlspeceq/side.svg" width="20pt"/>   | `Side`           |

___

<p float="left">
  <img src="/images/zlspeceq/collision.svg" width="20pt"/>
</p>

- 按下：开启碰撞检测。

___

**`Strength`（强度）**

调节碰撞检测强度。

___

## 界面设置面板

界面设置面板用于控制分析仪颜色、滑块操作等。组件将从上到下依次介绍。

#### 颜色

你可以通过点击左侧的色块来调整颜色，并通过拖动右侧的滑块来更改透明度。

**`Text Color`（文本颜色）**

**`Background Color`（背景颜色）**

为了更好的无障碍体验，请将文本/背景设置为对比度高的颜色。

**`Shadow Color`（阴影颜色）**

**`Glow Color`（发光颜色）**

**`Pre Color`（输入颜色）**

**`Post Color`（输出颜色）**

**`Side Color`（侧链颜色）**

**`Collision Color`（碰撞颜色）**

**`Grid Color`（网格颜色）**

**`Color Map 1`（颜色映射 1）**

- 每个单独滤波器曲线的颜色映射。

**`Color Map 2`（颜色映射 2）**

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

**`Context Menu`（右键菜单）**

**`Toggle Dynamic`（切换动态处理）**

**`Toggle Bypass`（切换旁路）**

**`Delete Band`（删除频段）**

___

#### 其他

**`Refresh Rate`（刷新率）**

通常来说，30 Hz 对于均衡器插件来说已经足够。

为了更好的分析仪显示效果，请将此设置为显示器刷新率的 1/n。例如，
- 如果你的显示器刷新率是 120 Hz，将其设置为 120 Hz、60 Hz（1/2）或 30 Hz（1/4）。不要设置为 90 Hz。
- 如果你的显示器刷新率是 90 Hz，将其设置为 90 Hz 或 30 Hz（1/3）。不要设置为 60 Hz。

**`FFT`（FFT 设置）**

- `Tilt`：FFT 的额外倾斜斜率
- `Speed`：FFT 的额外衰减速度

**`Curve Thickness`（曲线粗细）**

控制每个频段和每个声道模式的曲线粗细。

**`Tooltip`（工具提示）**

选择工具提示语言。重新打开插件窗口时生效。

**`UI Scaling`（界面缩放）**

选择字体大小模式。

- `Scale`：字体大小随窗口大小缩放。控制相对比例。
- `Static`：字体大小固定。控制实际字体大小。

**`Curve dB Scale`（曲线 dB 刻度）**

- `Min`：幅度响应曲线的最小分贝刻度
- `Default`：幅度响应曲线的默认分贝刻度
- `Max`：幅度响应曲线的最大分贝刻度

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

**滑块**

- 在使用鼠标拖动或鼠标滚轮调节滑块时，可以通过 `Shift` 开启精细调节。
- 当滑块上有两个值时，可以使用鼠标左/右键来控制第一个/第二个值。

**滤波器按钮**

- 可以拖动按钮来改变频率/增益值。
- 可以使用鼠标滚轮来改变 Q 值。
- 可以使用鼠标滚轮 + `Ctrl/Command` 改变斜率。
- 可以通过 `Shift` 开启精细拖动调节。
- 可以在固定频率的情况下，按下鼠标左键 + `Ctrl/Command` 拖动。
- 可以在固定增益的情况下，按下鼠标右键 + `Ctrl/Command` 拖动。
- 其他控制可以通过 [界面设置面板](#界面设置面板) 设置，比如进入/退出独奏，切换动态/旁路等。

**下拉框**

- 可以使用鼠标滚轮来更改选择项。

**窗口大小**

- 可以拖动右下角的拖拽点来调整插件窗口大小。
- 推荐的设置窗口大小的方法：
	1. 将 **`Window Size Fix`（窗口大小固定）** 设置为 `OFF` 并按下保存按钮。
	2. 调整插件窗口至你偏好的大小。
	3. 关闭插件窗口。
	4. 重新打开插件窗口。
	5. 将 **`Window Size Fix`（窗口大小固定）** 设置为 `ON` 并按下保存按钮。
	6. 关闭插件窗口。
	7. 之后，每次打开插件时，它都会以第 2 步中设置的窗口大小显示。

## 频谱动态

#### 频谱动态如何工作

不同于基于宽带音频触发器应用宽滤波器曲线的 ZL Equalizer 2，ZL Spectrum Equalizer 使用快速傅里叶变换（FFT）直接在频域中操作。音频被分割成离散的频率仓，从而允许根据相应侧链仓的电平，独立地对每个仓应用动态增益调节。

#### 频谱分辨率

**频谱分辨率** 设置决定了用于频谱分析和动态处理的 FFT 帧大小，这在频率精度和延迟之间建立了直接的权衡：

- **较低分辨率**（`Extreme Low` 至 `Low`）：提供最小的处理延迟（约 12 ms 至 46 ms）和快速的时域响应，使其非常适合现场跟踪或瞬态密集的素材。
- **中等分辨率**（`Medium`）：平衡了时间和频率分辨率（约 93 ms 延迟），适用于一般的混音任务。
- **较高分辨率**（`High` 至 `Extreme High`）：提供极其精细的频谱分辨率（约 186 ms 至 743 ms 延迟），以实现卓越的低频精度和对外科手术般的窄频谐振进行陷波校正。

通常情况下，如果你不大量处理低频部分（例如在 100Hz 以下进行高通处理），请选择中等或较低的分辨率以节省处理能力、减少延迟并使动态处理更具响应性。然而，如果你需要对低频进行重度且精确的控制，你可能需要选择较高的分辨率。在选择高分辨率时，请注意潜在的前振铃和 CPU 占用尖峰。

#### 核心动态行为

当频段开启了动态行为时，滤波器曲线覆盖的每个 FFT 仓将在两个目标值之间连续调制其增益：**基础增益** 和 **目标增益**。

* **`Threshold`（阈值）**：每个仓进行动态操作的触发电平。
    * 当侧链仓电平上升穿过 **`Threshold`（阈值）** 时，主链仓增益将以由 **`Attack`（启动时间）** 决定的速率，从 **基础增益** 向 **目标增益** 过渡。
    * 当侧链仓电平下降低于 **`Threshold`（阈值）** 时，主链仓增益将以由 **`Release`（释放时间）** 决定的速率，向 **基础增益** 恢复。
* **`Knee`（拐点）**：控制阈值周围的过渡曲率。
    * **硬拐点**（低值）执行严格的动作：只有在侧链仓电平穿过阈值后，增益调制才会开始。
    * **软拐点**（高值）创建渐进的曲线，当侧链仓电平接近阈值时平滑地向目标增益过渡，实现透明的、不突兀的频谱塑造。

> **注意**：由于处理是独立对每个 FFT 仓进行的，因此诸如 `Threshold`（阈值） 和 `Knee`（拐点） 之类的参数是对单独仓的电平进行操作的，而不是像传统动态处理器那样对全频段信号包络进行操作。

#### 动态模式

你可以通过选择不同的动态模式来改变阈值的计算方式：

- **`Absolute`（绝对模式）**：动态处理使用静态阈值。
- **`Band`（频段模式）**：动态处理使用与该频段侧链响度相关的动态阈值。
- **`Relative`（相对模式）**：动态处理使用与总侧链响度相关的动态阈值。

#### 频谱处理

除了各个频段上的参数，你还可以调整以下影响整体侧链分析的参数，以进一步定制动态行为：

- **平滑类型**：选择频谱处理侧链平滑类型。
- **平滑值**：调节频谱处理侧链平滑值。更高的值会让动态处理在频域上更平滑。
- **`Tilt`（倾斜斜率）**：调节频谱处理侧链倾斜斜率。
- **`Attack Skew`（启动偏置）**：调节频谱处理侧链启动偏置。偏置值越高，高频部分的启动越快，低频部分的启动越慢。
- **`Release Skew`（释放偏置）**：调节频谱处理侧链释放偏置。偏置值越高，高频部分的释放越快，低频部分的释放越慢。
- **`Gate`（门限）**：调节相对响度的频谱门限。在 `Band` 模式下，如果该频段的侧链响度小于 `Gate`，则不会触发动态处理。在 `Relative` 模式下，如果总侧链响度小于 `Gate`，则不会触发动态处理。
