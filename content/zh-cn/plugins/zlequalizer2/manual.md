---
title: 使用手册
description: 如何使用 ZL Equalizer 2
weight: 2
---

## 教程视频

{{< youtube "VzmNqjWfE2Y" >}}

## 关于

ZL Equalizer 2 是一款动态均衡器插件，具有以下主要特性：

- **多功能性**：通过 6 种滤波器结构、10 种滤波器类型、5 种声道模式、7 种可变斜率和多达 24 个频段来塑造声音。
- **集成动态**：除了静态 EQ，更具有可调节的阈值、启动时间、释放时间和侧链滤波器，实现强大的动态均衡。
- **纯净精度**：64 位浮点处理和先进的去扭曲技术提供卓越的性能，确保从极低频到极高频都有出色的清晰度。
- **直观控制**：精心设计的界面包含交互式频谱图、智能碰撞检测和流畅的动画，使均衡处理快速而流畅。

## 顶部面板

___

<p float="left">
  <img src="/images/zlequalizer2/zlaudio.svg" width="20pt" />
  <img src="/images/zlequalizer2/logo.svg" width="20pt" />
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

<p float="left">
  <img src="/images/zlequalizer2/match.svg" width="20pt"/>
</p>

你可以通过点击图标来打开 [均衡匹配面板](#均衡匹配面板)。

___

**滤波器结构**

- `Minimum Phase`（最小相位）：[最小相位](#minimum-phase-最小相位)
- `State Variable`（状态变量）：[状态变量](#state-variable-状态变量)
- `Parallel`（并行）：[并行](#parallel-并行)
- `Matched Phase`（匹配相位）：[匹配相位](#matched-phase-匹配相位)
- `Mixed Phase`（混合相位）：[混合相位](#mixed-phase-混合相位)
- `Zero Phase`（零相位）：[零相位](#zero-phase-零相位)

___

**`Output`（输出）**

你可以通过点击文本来打开 [输出设置面板](#输出设置面板)。它显示了当前滤波器增益缩放比例和总输出增益。

___

<p float="left">
  <img src="/images/zlequalizer2/external-side.svg" width="20pt"/>
</p>

- 按下：使用外部侧链
- 释放：使用内部侧链

___

<p float="left">
  <img src="/images/zlequalizer2/bypass.svg" width="20pt"/>
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

| 图标                                                         | 滤波器类型  | 图标                                                      | 声道模式 |
| ------------------------------------------------------------ | ------------ | --------------------------------------------------------- | ---------------- |
| <img src="/images/zlequalizer2/peak.svg" width="20pt"/>      | `Peak`       | <img src="/images/zlequalizer2/stereo.svg" width="20pt"/> | `Stereo`         |
| <img src="/images/zlequalizer2/lowshelf.svg" width="20pt"/>  | `Low Shelf`  | <img src="/images/zlequalizer2/left.svg" width="20pt"/>   | `Left`           |
| <img src="/images/zlequalizer2/lowpass.svg" width="20pt"/>   | `Low Pass`   | <img src="/images/zlequalizer2/right.svg" width="20pt"/>  | `Right`          |
| <img src="/images/zlequalizer2/highshelf.svg" width="20pt"/> | `High Shelf` | <img src="/images/zlequalizer2/mid.svg" width="20pt"/>    | `Mid`            |
| <img src="/images/zlequalizer2/highpass.svg" width="20pt"/>  | `High Pass`  | <img src="/images/zlequalizer2/side.svg" width="20pt"/>   | `Side`           |
| <img src="/images/zlequalizer2/notch.svg" width="20pt"/>     | `Notch`      |                                                           |                  |
| <img src="/images/zlequalizer2/bandpass.svg" width="20pt"/>  | `Band Pass`  |                                                           |                  |
| <img src="/images/zlequalizer2/tiltshelf.svg" width="20pt"/> | `Tilt Shelf` |                                                           |                  |
| <img src="/images/zlequalizer2/flattilt.svg" width="20pt"/>  | `Flat Tilt`  |                                                           |                  |
| <img src="/images/zlequalizer2/allpass.svg" width="20pt"/>   | `All Pass`   |                                                           |                  |

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
  <img src="/images/zlequalizer2/bypass.svg" width="20pt"/>
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

调节基础增益与目标增益。更多信息请参见 [动态滤波器](#动态滤波器)。

___

**`Q`（品质因数）**

调节品质因数。

___

<p float="left">
  <img src="/images/zlequalizer2/dynamic.svg" width="20pt"/>
</p>

- 按下：开启该频段的动态行为

___


<p float="left">
  <img src="/images/zlequalizer2/close.svg" width="20pt"/>
</p>

- 点击：关闭该频段

___

#### 右侧面板

___


<p float="left">
  <img src="/images/zlequalizer2/bypass.svg" width="20pt"/>
</p>

- 释放：旁路动态行为。更多信息请参见 [动态滤波器](#动态滤波器)。

___


<p float="left">
  <img src="/images/zlequalizer2/circle_a.svg" width="20pt"/>
</p>

- 按下：开启动态学习行为。更多信息请参见 [动态滤波器](#动态滤波器)。
- 释放：关闭动态学习行为并设置 `Threshold`（阈值）和 `Knee`（拐点）

___


<p float="left">
  <img src="/images/zlequalizer2/circle_r.svg" width="20pt"/>
</p>

- 按下：开启动态相对行为。更多信息请参见 [动态滤波器](#动态滤波器)。

___


<p float="left">
  <img src="/images/zlequalizer2/shuffle.svg" width="20pt"/>
</p>

- 按下：更改侧链声道模式。按下时，如果频段处于 `Left`/`Right`/`Mid`/`Side`，侧链频段将处于 `Right`/`Left`/`Side`/`Mid`。

___

**`Threshold`（阈值）**

更多信息请参见 [动态滤波器](#动态滤波器)。

___

**`Knee`（拐点）**

更多信息请参见 [动态滤波器](#动态滤波器)。

___

**`Attack`（启动时间）**

更多信息请参见 [动态滤波器](#动态滤波器)。

___

**`Release`（释放时间）**

更多信息请参见 [动态滤波器](#动态滤波器)。

___


<p float="left">
  <img src="/images/zlequalizer2/link.svg" width="20pt"/>
</p>

- 按下：将频段与侧链频段关联。更多信息请参见 [动态滤波器](#动态滤波器)。

___

**侧链滤波器类型**

选择侧链滤波器类型：`BP (Band Pass)`、`LP (Low Pass)` 和 `HP (High Pass)`。

___

**侧链滤波器斜率**

选择侧链滤波器斜率：`6 dB/oct`、`12 dB/oct`、`24 dB/oct`、`36 dB/oct`、`48 dB/oct`、`72 dB/oct` 和 `96 dB/oct`。

___

**`FREQ`（频率）**

调节侧链滤波器频率。

___

**`Q`（品质因数）**

调节侧链滤波器品质因数。

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
  <img src="/images/zlequalizer2/dline_s.svg" width="20pt"/>
</p>

- 按下：开启静态增益补偿（SGC）
- 释放：关闭静态增益补偿（SGC）

> SGC 会根据滤波器的参数来估算补偿量。SGC **不够精确**。不过，它**不会影响主链信号的动态**。

___

<p float="left">
  <img src="/images/zlequalizer2/dline_l.svg" width="20pt"/>
</p>

- 按下：开始测量输入信号与输出信号的整体响度
- 释放：关闭 AGC 并将 `Output Gain`（输出增益）更新为两响度值之差

___

<p float="left">
  <img src="/images/zlequalizer2/dline_a.svg" width="20pt"/>
</p>

- 按下：开启自动增益补偿（AGC）
- 释放：关闭自动增益补偿（AGC）

> AGC 计算滤波器前后主链信号的响度差异，并应用相应的增益。因此，**AGC 会影响主链信号的动态**。
> 
> 当 AGC 开启时，输出的主链信号将通过一个 0 dB 的硬削波器。

___

<p float="left">
  <img src="/images/zlequalizer2/phase.svg" width="20pt"/>
</p>

- 按下：翻转输出信号的相位

___

**`Lookahead`（前瞻）**

调节侧链信号的前瞻时间。

> **警告：** **请勿自动化** `Lookahead`（前瞻）参数。

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
  <img src="/images/zlequalizer2/freeze.svg" width="20pt"/>
</p>

- 按下：开启 FFT 冻结功能。将鼠标悬停在分析仪上 2 秒钟，输出/侧链分析仪将会被冻结，直到你移动鼠标。

___

**FFT 分析仪声道模式**

| 图标                                                      | 声道模式 |
| --------------------------------------------------------- | ---------------- |
| <img src="/images/zlequalizer2/stereo.svg" width="20pt"/> | `Stereo`         |
| <img src="/images/zlequalizer2/left.svg" width="20pt"/>   | `Left`           |
| <img src="/images/zlequalizer2/right.svg" width="20pt"/>  | `Right`          |
| <img src="/images/zlequalizer2/mid.svg" width="20pt"/>    | `Mid`            |
| <img src="/images/zlequalizer2/side.svg" width="20pt"/>   | `Side`           |

___

<p float="left">
  <img src="/images/zlequalizer2/collision.svg" width="20pt"/>
</p>

- 按下：开启碰撞检测。

___

**`Strength`（强度）**

调节碰撞检测强度。

___

## 均衡匹配面板

> **警告**：均衡匹配面板打开后，**请勿**更改插件的采样率（例如更改工程采样率或为该插件开启 DAW 过采样）。**否则该插件可能会导致 DAW 崩溃**。

#### 均衡匹配步骤

1. 打开均衡匹配面板。它将分析源信号和目标信号。
2. 选择目标信号。源信号必须为主链输入。你可以从侧链输入、平直曲线或预设中选择目标信号。
3. 等待差值曲线趋于稳定。然后通过 `Shift`（垂直偏移）、`Smooth`（平滑度）和 `Slope`（斜率）调节差值曲线。如果需要，你也可以绘制差值曲线。
4. 开始拟合。拟合过程将在数秒内完成。之后你可以调整频段数量。

#### 均衡匹配分析仪

当均衡匹配面板处于显示状态时，分析仪会显示三条曲线：

- **源曲线**：源信号的平均频谱。
- **目标曲线**：目标信号的平均频谱。
- **差值曲线**：源信号与目标信号之间的差值。

当启用差值曲线绘制时，你可以：

- 按住鼠标左键拖动以绘制差值曲线
- 按住鼠标右键拖动以重置差值曲线
- 按住 Shift + 鼠标左键拖动以将差值曲线归零
- 双击鼠标左键以重置整条差值曲线

#### 均衡匹配控制

___

<p float="left">
  <img src="/images/zlequalizer2/save.svg" width="20pt"/>
</p>

- 点击：将目标曲线保存为预设文件

___

<p float="left">
  <img src="/images/zlequalizer2/draw.svg" width="20pt"/>
</p>

- 按下：启用差值曲线绘制

___

**目标信号**

选择目标信号：

- `Side`：将目标曲线设为侧链信号的平均频谱
- `Preset`：从预设文件中加载目标曲线
- `Flat`：将目标曲线设为平直曲线
- `Balanced`：将目标曲线设为均衡曲线
- `Natural`：将目标曲线设为自然曲线

___

**`Shift`（垂直偏移）**

调节差值曲线的垂直偏移。

___

**`Scale`（缩放）**

调节差值曲线的缩放。

___

**`Slope`（斜率）**

调节差值曲线的（额外）斜率。

___

**`Limit`（限制）**

选择差值曲线的限制（在拟合时应用）。

___

<p float="left">
  <img src="/images/zlequalizer2/start.svg" width="20pt"/>
</p>

- 点击：开始拟合过程。

> **警告：** 一旦点击此按钮，**所有**频段将被删除并设置为拟合后的参数。

___

**频段数量**

调节用于拟合的频段数量。你可以在拟合完成后调节它。

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
- `On`：插件窗口大小调整将不会被保存

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
- 可以双击按钮以进入/退出独奏状态。
- 可以按住 `Ctrl/Command` 双击以开启/关闭动态行为。

**下拉框**

- 可以使用鼠标滚轮来更改选择项。

**窗口大小**

- 可以拖动右下角的拖拽点来调整插件窗口大小。

## 滤波器结构

#### `Minimum Phase`（最小相位）

这是**标准、经典的数字 EQ 声音**。它是最常见的滤波器类型。

* **最适用于：** 常规 EQ 任务。
* **优点：** 平缓的 6 dB 和 12 dB/oct 斜率引起的相位偏移非常小，可以安全地与原始信号混合（相位抵消风险低）。
* **缺点：** 对频率或增益进行激进的自动化有时可能会导致可听见的咔哒声或不稳定。

#### `State Variable`（状态变量）

这种滤波器类型常用于**合成器滤波器和分频器**。

* **最适用于：** 创意效果和高强度自动化。
* **优点：** 即使在快速、复杂的自动化下也极其稳定。
* **缺点：** CPU 占用稍高。对频率或增益进行激进的自动化有时可能会导致可听见的咔哒声或不稳定。

#### `Parallel`（并行）

此模式改变了滤波器协同工作的方式。**搁架**（<= 12 dB/oct）和**峰值**（<= 24 dB/oct）滤波器被并行处理。

* **最适用于：** 高效的动态 EQ 处理与自然的声音。
* **优点：** 提供不同的特性，并且在处理动态任务时 CPU 效率更高。
* **缺点：** 并行处理意味着最终的 EQ 曲线**看起来会与**显示器上显示的曲线不同。

#### `Matched Phase`（匹配相位）

此模式在 `Minimum Phase`（最小相位）滤波器的基础上增加了一个特殊处理，以**模拟模拟原型的幅度与相位响应**。

* **最适用于：** 获得**模拟**的相位和幅度响应。
* **延迟：** 增加约 11 ms 延迟。
* **缺点：** 动态滤波器保持在 `Minimum Phase`（最小相位）模式。

> **警告：** **请勿在此模式下自动化**滤波器参数。

#### `Mixed Phase`（混合相位）

此模式在 `Minimum Phase`（最小相位）滤波器的基础上增加了一个特殊处理，以**模拟模拟原型的幅度响应**并清理高频相位。

* **最适用于：** 获得**模拟**的幅度响应，同时消除高频（5 kHz 以上）的相位偏移。
* **延迟：** 增加约 21 ms 延迟。
* **缺点：** 动态滤波器保持在 `Minimum Phase`（最小相位）模式。

> **警告：** **请勿在此模式下自动化**滤波器参数。

#### `Zero Phase`（零相位）

此模式提供**几乎为零的相位响应**。

* **最适用于：** 需要严格保持相位关系的精细母带处理任务。
* **优点：** 对于中高频（200 Hz 以上）完全没有相位失真。
* **缺点：** 增加约 171 ms 的**极高延迟**。可能会导致可听见的前振铃。动态滤波器保持在 `Minimum Phase`（最小相位）模式。

> **警告：** **请勿在此模式下自动化**滤波器参数。


## 动态滤波器

#### 动态滤波器如何工作

动态滤波器会自动为你调高或调低某个频段的增益，但仅在特定频率变得过响或过静时才会触发。

#### 核心动态行为

当开启动态模式时，滤波器会监听特定的频率范围，即经过侧链滤波器过滤后的侧链信号。相关设置决定了它何时反应以及反应多快。

* `Threshold`（阈值）：这是触发电平。
    * 当信号音量超过 `Threshold`（阈值）时，滤波器开始向**目标增益**变化。反应速度由 `Attack`（启动时间）控制。
    * 当信号音量低于 `Threshold`（阈值）时，滤波器开始向**基础增益**恢复。恢复速度由 `Release`（释放时间）控制。
* `Knee`（拐点）：控制当信号接近 `Threshold`（阈值）时滤波器的反应平滑度。
    * 硬拐点（低值）就像开关：滤波器保持在**基础增益**，直到信号准确穿过 `Threshold`（阈值）。
    * 软拐点（高值）就像调光器：当信号接近 `Threshold`（阈值）时，滤波器*平缓地*向**目标增益**过渡，从而产生更渐进、更透明的效果。

请牢记，`Threshold`（阈值）和 `Knee`（拐点）的定义与传统压缩器不同。

#### 动态学习

完美设置 `Threshold`（阈值）和 `Knee`（拐点）可能比较困难，尤其是当轨道的音量发生变化时。

当你开启 **Dynamic Learning**（动态学习）时，插件会为你完成这项工作。它会**持续分析输入信号**，并实时自动设置 `Threshold`（阈值）和 `Knee`（拐点）。这使动态处理能够持续适应信号。

#### 动态相对

此模式完全改变了滤波器的监听内容。

* **普通模式**由绝对音量触发：过滤后的侧链绝对音量是否足够大？
* **相对模式**由相对音量触发：过滤后的侧链是否比整个侧链更响？
