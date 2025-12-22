---
title: 用户手册
description: 如何使用 ZL Equalizer 2
weight: 2
---
## Tutorial Video

{{< youtube "VzmNqjWfE2Y" >}}

## 关于

ZL Equalizer 2 是一款动态均衡器插件，具有以下主要功能：

- **多样的功能**：通过 6 种滤波器结构、8 种滤波器类型、5 种立体声模式、7 种可变斜率和多达 24 个频段来雕刻您的声音。
- **丰富的动态**：超越静态 EQ，具有可调的阈值、启动时间、释放时间和侧链滤波器，可实现强大的动态均衡。
- **纯净的精度**：64 位浮点处理和先进的去“痉挛”技术（de-cramping）提供了卓越的性能，确保了从最低的低频到最高的（高）频都有出色的清晰度。
- **直观的界面**：精心设计的界面，具有交互式频谱图、智能碰撞检测和流畅的动画，使均衡操作快速而流畅。

## 顶部面板

___

<p float="left">
  <img src="/images/zlequalizer2/zlaudio.svg" width="20pt" />
  <img src="/images/zlequalizer2/logo.svg" width="20pt" />
</p>

双击徽标可打开[用户界面设置面板](#用户界面设置)。

___

**Analyzer (分析仪)**

点击“Analyzer”文本可打开[分析仪设置面板](#分析仪设置面板)。

___

<p float="left">
  <img src="/images/zlequalizer2/match.svg" width="20pt"/>
</p>

点击图标可打开[均衡匹配面板](#均衡匹配面板)。

___

**Filter Structure (滤波器结构)**

- `Minimum Phase`: [最小相位](#最小相位-minimum-phase)
- `State Variable`: [状态变量](#状态变量-state-variable)
- `Parallel`: [并行](#并行-parallel)
- `Matched Phase`: [匹配相位](#匹配相位-matched-phase)
- `Mixed Phase`: [混合相位](#混合相位-mixed-phase)
- `Zero Phase`: [零相位](#零相位-zero-phase)

___

**Output Panel (输出面板)**

点击“Output”文本可打开[输出设置面板](#输出设置面板)。它会显示当前的滤波器增益缩放和总输出增益。

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

- 释放：旁通插件

___

## 中间面板

中间面板由频谱分析仪、滤波器响应曲线、滤波器按钮、一个浮动窗口和分贝刻度组成。

#### 频谱分析仪

频谱分析仪显示输入/输出/侧链信号的频谱和碰撞区域（可选）。您可以通过[分析仪设置面板](#分析仪设置面板)来控制它。

#### 滤波器响应曲线

滤波器响应曲线显示每个单独频段的幅度响应以及每种立体声布局的幅度响应。

#### 滤波器按钮

滤波器按钮附着在滤波器响应曲线上。您可以拖动它们来更改滤波器参数。更多信息请参见[界面控件](#界面控件)。

当您在频谱上双击（并按下 `Ctrl/Command`），将在相应位置添加一个频段（并开启动态行为），并带有一个滤波器按钮。

#### 浮动窗口

浮动窗口附着在所选频段的滤波器按钮上。您可以通过此窗口控制一些滤波器参数。

| 图标                                                           | 滤波器类型               | 图标                                                        | 立体声位置          |
| :----------------------------------------------------------- | :------------------ | :-------------------------------------------------------- | :------------- |
| <img src="/images/zlequalizer2/peak.svg" width="20pt"/>      | `峰值 (Peak)`         | <img src="/images/zlequalizer2/stereo.svg" width="20pt"/> | `立体声 (Stereo)` |
| <img src="/images/zlequalizer2/lowshelf.svg" width="20pt"/>  | `低搁架 (Low Shelf)`   | <img src="/images/zlequalizer2/left.svg" width="20pt"/>   | `左声道 (Left)`   |
| <img src="/images/zlequalizer2/lowpass.svg" width="20pt"/>   | `低通 (Low Pass)`     | <img src="/images/zlequalizer2/right.svg" width="20pt"/>  | `右声道 (Right)`  |
| <img src="/images/zlequalizer2/highshelf.svg" width="20pt"/> | `高搁架 (High Shelf)`  | <img src="/images/zlequalizer2/mid.svg" width="20pt"/>    | `中声道 (Mid)`    |
| <img src="/images/zlequalizer2/highpass.svg" width="20pt"/>  | `高通 (High Pass)`    | <img src="/images/zlequalizer2/side.svg" width="20pt"/>   | `侧声道 (Side)`   |
| <img src="/images/zlequalizer2/notch.svg" width="20pt"/>     | `带阻 (Notch)`        |                                                           |                |
| <img src="/images/zlequalizer2/bandpass.svg" width="20pt"/>  | `带通 (Band Pass)`    |                                                           |                |
| <img src="/images/zlequalizer2/tiltshelf.svg" width="20pt"/> | `倾斜搁架 (Tilt Shelf)` |                                                           |                |

#### 右键菜单

___

**Invert Gain**

- 点击：反转所选频段的增益

___

**Split L/R**

- 点击：将所选频段设置为 `Left`，并添加一个参数相同但模式为 `Right` 的频段

___

**Split M/S**

- 点击：将所选频段设置为 `Mid`，并添加一个参数相同但模式为 `Side` 的频段

___

**Copy**

- 点击：将所有选定频段的滤波器参数复制到剪贴板

___

**Paste**

- 点击：从剪贴板获取滤波器参数并创建这些频段

___

#### 分贝刻度

您可以选择幅度响应曲线的分贝刻度（通过右上方的组合框）和频谱分析仪的分贝刻度（通过右下方的组合框）。

## 底部面板

#### 左侧面板

___

<p float="left">
  <img src="/images/zlequalizer2/bypass.svg" width="20pt"/>
</p>

- 释放：旁通此频段。

---

**Band Selection (频段选择)**

选择当前频段。

___

**Filter Type (滤波器类型)**

选择滤波器类型：`峰值 (Peak)`、`低搁架 (Low Shelf)`、`低通 (Low Pass)`、`高搁架 (High Shelf)`、`高通 (High Pass)`、`带阻 (Notch)`、`带通 (Band Pass)` 和 `倾斜搁架 (Tilt Shelf)`。

---

**Slope (斜率)**

选择滤波器斜率：`6 dB/oct`、`12 dB/oct`、`24 dB/oct`、`36 dB/oct`、`48 dB/oct`、`72 dB/oct` 和 `96 dB/oct`。较高的斜率会使滤波器的响应曲线变化更陡峭。`峰值 (Peak)`、`带阻 (Notch)` 和 `带通 (Band Pass)` 不支持 `6 dB/oct`。

---

**Stereo Modes (立体声模式)**

选择立体声模式：`立体声 (Stereo)`、`左声道 (Left)`、`右声道 (Right)`、`中声道 (Mid)` 和 `侧声道 (Side)`。

___

**`FREQ` (频率)**

控制频率。频率的最大值受采样率影响。

___

**`GAIN` (增益)**

控制基础增益与目标增益。更多信息请参见[动态滤波器](#动态滤波器)。

___

**`Q` (Q 值)**

控制品质因数 (Q 值)。Q 值越大，带宽越窄。

___

<p float="left">
  <img src="/images/zlequalizer2/dynamic.svg" width="20pt"/>
</p>

- 按下：开启动态行为。

___


<p float="left">
  <img src="/images/zlequalizer2/close.svg" width="20pt"/>
</p>

- 点击：关闭此频段。

___

#### 右侧面板

___


<p float="left">
  <img src="/images/zlequalizer2/bypass.svg" width="20pt"/>
</p>

- 释放：旁通动态行为。更多信息请参见[动态滤波器](#动态滤波器)。

___


<p float="left">
  <img src="/images/zlequalizer2/circle_a.svg" width="20pt"/>
</p>

- 按下：开启动态学习行为。更多信息请参见[动态滤波器](#动态滤波器)。
- 释放：关闭动态学习行为，并设置阈值 (Threshold) 与拐点 (Knee)。

___


<p float="left">
  <img src="/images/zlequalizer2/circle_r.svg" width="20pt"/>
</p>

- 按下：开启动态相对行为。更多信息请参见[动态滤波器](#动态滤波器)。

___


<p float="left">
  <img src="/images/zlequalizer2/shuffle.svg" width="20pt"/>
</p>

- 按下：更改侧链立体声模式。按下时，如果频段处于 `Left`/`Right`/`Mid`/`Side`，侧链频段将处于 `Right`/`Left`/`Side`/`Mid`。

___

**`Threshold` (阈值)**

控制动态行为的阈值。更多信息请参见[动态滤波器](#动态滤波器)。

___

**`Knee` (拐点)**

控制动态行为的拐点宽度。更多信息请参见[动态滤波器](#动态滤波器)。

___

**`Attack` (触发时间)**

控制动态行为的触发时间。更多信息请参见[动态滤波器](#动态滤波器)。

___

**`Release` (释放时间)**

控制动态行为的释放时间。更多信息请参见[动态滤波器](#动态滤波器)。

___

<p float="left">
  <img src="/images/zlequalizer2/link.svg" width="20pt"/>
</p>

- 按下：将此频段与侧链频段关联。更多信息请参见[动态滤波器](#动态滤波器)。

___

**Side-chain Filter Type (侧链滤波器类型)**

选择侧链滤波器类型：`BP (带通)`、`LP (低通)` 和 `HP (高通)`。

___

**Side-chain Filter Slope (侧链滤波器斜率)**

选择侧链滤波器斜率：`6 dB/oct`、`12 dB/oct`、`24 dB/oct`、`36 dB/oct`、`48 dB/oct`、`72 dB/oct` 和 `96 dB/oct`。

___

**`FREQ` (频率)**

控制侧链滤波器频率。

___

**`Q` (Q 值)**

控制侧链滤波器 Q 值。

___

## 输出设置面板

___

**`GAIN` (增益)**

控制额外的输出增益。

___

**`SCALE` (缩放)**

控制所有滤波器基础增益和目标增益的缩放比例。

___

<p float="left">
  <img src="/images/zlequalizer2/dline_s.svg" width="20pt"/>
</p>

- 按下：开启静态增益补偿 (SGC)
- 释放：关闭静态增益补偿 (SGC)

> SGC 根据滤波器参数估算补偿量。SGC 是**不精确的**。但是，它**不会影响主链信号的动态**。

___

<p float="left">
  <img src="/images/zlequalizer2/dline_l.svg" width="20pt"/>
</p>

- 按下：开始测量输入信号和输出信号的整体响度
- 释放：关闭 AGC，并更新输出增益为两者响度差值

___

<p float="left">
  <img src="/images/zlequalizer2/dline_a.svg" width="20pt"/>
</p>

- 按下：开启自动增益补偿 (AGC)
- 释放：关闭自动增益补偿 (AGC)

> AGC 计算滤波器前后主链信号的响度差异，并应用相应的增益。因此，**AGC 会影响主链信号的动态**。
>
> 当 AGC 开启时，输出的主链信号将通过一个 0 dB 的硬削波器 (hard clipper)。

___

<p float="left">
  <img src="/images/zlequalizer2/phase.svg" width="20pt"/>
</p>

- 按下：翻转输出信号的相位

___

**`Lookahead` (前瞻)**

控制侧链信号的前瞻时间。

> **警告：** **请勿自动化** `Lookahead` 参数。

## 分析仪设置面板

___

**`Pre/Post/Side` (前/后/侧链)**

- 按下：开启输入/输出/侧链信号频谱分析仪
- 释放：关闭输入/输出/侧链信号频谱分析仪

___

**Decay Speed (衰减速度)**

选择频谱分析仪的衰减速度。

___

**Slope (斜率)**

- 影响频谱显示（不影响实际信号）
- `0 dB/oct`：不倾斜，白噪声显示为一条水平线
- `3 dB/oct`：粉红噪声显示为一条水平线
- `4.5 dB/oct`：默认值，能更好地代表感知响度

---

<p float="left">
  <img src="/images/zlequalizer2/freeze.svg" width="20pt"/>
</p>

- 按下：开启冻结功能。将鼠标悬停在分析仪上 2 秒钟，输出/侧链分析仪将被冻结，直到您移开鼠标。

___

**FFT 分析仪立体声位置**

| 图标                                                        | 立体声位置          |
| :-------------------------------------------------------- | :------------- |
| <img src="/images/zlequalizer2/stereo.svg" width="20pt"/> | `立体声 (Stereo)` |
| <img src="/images/zlequalizer2/left.svg" width="20pt"/>   | `左声道 (Left)`   |
| <img src="/images/zlequalizer2/right.svg" width="20pt"/>  | `右声道 (Right)`  |
| <img src="/images/zlequalizer2/mid.svg" width="20pt"/>    | `中声道 (Mid)`    |
| <img src="/images/zlequalizer2/side.svg" width="20pt"/>   | `侧声道 (Side)`   |

___

<p float="left">
  <img src="/images/zlequalizer2/collision.svg" width="20pt"/>
</p>

- 按下：开启碰撞检测。

___

**`Strength` (强度)**

控制碰撞检测的强度。

___

## 均衡匹配面板

>  **警告**：均衡匹配面板打开后**请勿**变更该插件的采样率，例如改变混音工程采样率或开启该插件的 DAW 超采样。**否则该插件可能会导致 DAW 崩溃**。

#### 均衡匹配步骤

1. 打开均衡匹配面板。它将开始分析源信号和目标信号。
2. 选择目标信号。源信号必须是主链输入。您可以从侧链输入、一条平坦的线或一个预设中选择目标信号。
3. 等待差异曲线变得稳定。然后使用 `Shift (偏移)`、`Smooth (平滑度)` 和 `Slope (斜率)` 调整差异曲线。如果需要，您也可以绘制差异曲线。
4. 开始拟合。拟合过程应在几秒钟内完成。之后，您可以调整用于拟合的频段数量。

#### 均衡匹配分析仪

当均衡匹配面板可见时，分析仪会显示三条曲线：

- **源曲线**：源信号的平均频谱。
- **目标曲线**：目标信号的平均频谱。
- **差异曲线**：源信号和目标信号之间的差异。

当启用差异曲线绘制时，您可以：

- 用鼠标左键拖动画制差异曲线
- 用鼠标右键拖动重置差异曲线
- 按住 Shift + 鼠标左键拖动将差异曲线设置为零
- 用鼠标左键双击重置整条差异曲线

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

- 按下：启用差异曲线绘制

___

**Target Signal (目标信号)**

选择目标信号：

- `Side (侧链)`：让目标曲线成为侧链信号的平均频谱
- `Flat (平坦)`：将目标曲线设置为一条平坦的线
- `Preset (预设)`：从预设文件中加载目标曲线

___

**`Shift` (偏移)**

控制差异曲线的垂直偏移。

___

**`Smooth` (平滑度)**

控制差异曲线的平滑度。

- 从 0.0 到 0.5：平滑度增加，差异曲线变得更平滑
- 从 0.5 到 1.0：平滑度增加，差异曲线按比例缩小

___

**`Slope` (斜率)**

控制差异曲线的（额外）斜率。

___

<p float="left">
  <img src="/images/zlequalizer2/start.svg" width="20pt"/>
</p>

- 点击：开始拟合过程。

> **警告：** 一旦点击此按钮，**所有**频段将被删除，然后设置为拟合后的参数。

___

**Number of Bands (频段数量)**

控制用于拟合的频段数量。您可以在拟合完成后控制此参数。

___

## 用户界面设置

用户界面设置面板控制分析仪颜色、滑块操作等。组件将按从上到下的顺序介绍。

#### Color (颜色)

您可以通过点击左侧的色块来调整颜色，并通过拖动右侧的滑块来更改透明度。

**Text Color (文本颜色)**

**Background Color (背景颜色)**

为了更好的可访问性，请将文本/背景设置为高对比度的颜色。

**Shadow Color (阴影颜色)**

**Glow Color (发光颜色)**

**Pre Color (输入颜色)**

**Post Color (输出颜色)**

**Side Color (侧链颜色)**

**Collision Color (碰撞颜色)**

**Grid Color (网格颜色)**

**Color Map 1 (色图 1)**

- 每个单独滤波器曲线的色图。

**Color Map 2 (色图 2)**

- 立体声/左声道/右声道/中声道/侧声道曲线的色图。

**Import Colors (导入颜色)**

- 导入颜色设置（`.xml` 文件）

**Export Colors (导出颜色)**

- 导出颜色设置（`.xml` 文件）

#### Control (控制)

**Wheel Sensitivity (滚轮灵敏度)**

- Rough (粗调): 未按下 `Shift` 时的鼠标滚轮灵敏度
- Fine (微调): 按下 `Shift` 时的鼠标滚轮灵S敏度
- Reverse (反转): 按下 `Shift` 时是否反转鼠标滚轮的方向

**Drag Sensitivity (拖动灵敏度)**

- Rough (粗调): 未按下 `Shift` 时的鼠标拖动灵敏度
- Fine (微调): 按下 `Shift` 时的鼠标拖动灵敏度

**Rotary Slider Style (旋转滑块样式)**

- `Circular (圆形)`: 通过环形拖动鼠标来移动的旋转控件，像旋钮一样
- `Horizontal (水平)`: 通过左右拖动鼠标来移动的旋转控件
- `Vertical (垂直)`: 通过上下拖动鼠标来移动的旋转控件
- `Horiz + Vert (水平 + 垂直)`: 通过上下或左右拖动鼠标来移动的旋转控件
- `Distance (距离)`: 鼠标拖动滑块经过其全部范围所需的相对距离。不适用于圆形样式。

**Slider Double Click (滑块双击)**

- `Return Default (返回默认值)`: 双击滑块时，返回默认值；按住 Ctrl/Command 双击滑块时，打开数值编辑器。
- `Open Editor (打开编辑器)`: 双击滑块时，打开数值编辑器；按住 Ctrl/Command 双击滑块时，返回默认值。

**Import Controls (导入控制)**

- 导入控制设置（`.xml` 文件）

**Export Controls (导出控制)**

- 导出控制设置（`.xml` 文件）

#### Other (其它)

**Refresh Rate (刷新率)**

通常，30 Hz 对于均衡器插件来说足够了。

为了获得更好的分析仪显示效果，请将其设置为显示器刷新率的 1/n。例如：
- 如果您的显示器刷新率是 120 Hz，请将其设置为 120 Hz、60 Hz (1/2) 或 30 (1/4) Hz。不要设置为 90 Hz。
- 如果您的显示器刷新率是 90 Hz，请将其设置为 90 Hz 或 30 Hz (1/3)。不要设置为 60 Hz。

**FFT Setting (FFT 设置)**

- `Tilt (倾斜)`: FFT 的额外倾斜斜率
- `Speed (速度)`: FFT 的额外衰减速度

**Curve Thickness (曲线粗细)**

控制每个频段和每种立体声模式的曲线粗细。

**Tooltip (工具提示)**

选择工具提示语言。将在插件窗口重新打开时生效。

**UI Scaling (界面缩放)**

选择字体大小模式。

- `Scale (缩放)`: 字体大小随窗口大小缩放。控制相对比例。
- `Static (静态)`: 字体大小固定。控制实际字体大小。

## 界面控件

通常，您可以使用 `Shift` 键启用微调，使用 `Ctrl/Command` 键启用特殊调整。如果按下 `Shift` 键时鼠标滚轮的方向相反，您可以在（用户界面设置面板中）再次反转它以使其恢复正常。

**Sliders (滑块)**

- 当使用鼠标拖动 / 鼠标滚轮调整滑块时，您可以使用 `Shift` 键启用微调。
- 当滑块上有两个值时，您可以使用鼠标左/右键来控制第一个/第二个值。

**Filter Buttons (滤波器按钮)**

- 您可以拖动按钮来更改频率/增益值。
- 您可以使用鼠标滚轮来更改 Q 值。
- 您可以在按下 `Ctrl/Command` 的同时使用鼠标滚轮来更改斜率。
- 当拖动按钮时，您可以使用 `Shift` 键启用微调。
- 您可以在按下 `Ctrl/Command` 的同时用鼠标左键拖动，以固定频率。
- 您可以在按下 `Ctrl/Command` 的同时用鼠标右键拖动，以固定频率。
- 您可以双击按钮进入/退出监听 (solo) 状态。
- 您可以按住 `Ctrl/Command` 双击以打开/关闭动态行为。

## 滤波器结构

#### 最小相位 (Minimum Phase)

这是**标准、经典的数字 EQ 声音**。它是最常见的滤波器类型。

- 最适用于：常规 EQ 任务。
- 优点：平缓的 6 dB 和 12 dB/oct 斜率只会引起非常小的相位偏移，使其可以安全地与原始信号混合（相位抵消的风险低）。
- 缺点：对频率或增益进行激进的自动化有时可能会导致可听见的咔哒声或不稳定。

#### 状态变量 (State Variable)

这种滤波器类型常用于**合成器滤波器和分频器**。

- 最适用于：创意效果和高强度自动化。
- 优点：即使在快速、复杂的自动化下也极其稳定。
- 缺点：会导致较大的相位偏移。**避免将此信号与原始信号**（或其他相关信号）混合，因为它很可能会导致相位抵消。

#### 并行 (Parallel)

此模式会改变滤波器协同工作的方式。**搁架 (Shelf)** (<= 12 dB/oct) 和**峰值 (Peak)** (<= 24 dB/oct) 滤波器被并行处理。
- 最适用于：高效的动态 EQ 处理和自然的声音。
- 优点：提供不同的特性，并且在处理动态任务时 CPU 效率更高。
- 缺点：并行处理意味着最终的 EQ 曲线**看起来会与**显示器上显示的曲线不同。

#### 匹配相位 (Matched Phase)

此模式在 `最小相位` 滤波器的基础上增加了一个特殊处理，以**模拟模拟原型的幅度与相位响应**。
- 最适用于：获得**模拟**的相位和幅度响应。
- 延迟：增加约 11 毫秒（对于 L/R 和 M/S 处理，最多 22 毫秒）的延迟。
- 缺点：动态滤波器保持在 `最小相位` 模式。

> **警告：** **请勿在此模式下自动化**滤波器参数。

#### 混合相位 (Mixed Phase)

此模式在 `最小相位` 滤波器的基础上增加了一个特殊处理，以**模拟模拟原型的幅度响应**并清理高频相位。
- 最适用于：获得**模拟**的幅度响应，同时消除高频（5 kHz 以上）的相位偏移。
- 延迟：增加约 21 毫秒（对于 L/R 和 M/S 处理，最多 43 毫秒）的延迟。
- 缺点：动态滤波器保持在 `最小相位` 模式。

> **警告：** **请勿在此模式下自动化**滤波器参数。

#### 零相位 (Zero Phase)

此模式提供**几乎为零的相位响应**。
- 最适用于：需要严格保持相位关系的精细母带处理任务。
- 优点：对于中/高频（200 Hz 以上）完全没有相位失真。
- 缺点：增加**非常高的延迟**，约 171 毫秒（对于 L/R 和 M/S 处理，最多 342 毫秒）。可能会导致可听见的前振铃。动态滤波器保持在 `最小相位` 模式。

> **警告：** **请勿在此模式下自动化**滤波器参数。

## 动态滤波器

#### 动态滤波器工作原理

动态滤波器会自动为您调高或调低某个频段的增益，但仅当特定频率变得太响或太安静时才会触发。

#### 核心动态行为

当开启动态模式时，滤波器会监听一个特定的频率范围，即通过侧链滤波器过滤后的侧链信号。相关设置告诉它何时反应以及反应多快。

* `Threshold (阈值)`：这是触发电平。
    * 当信号音量超过 `阈值` 时，滤波器开始向**目标增益**变化。反应速度由 `Attack (触发时间)` 控制。
    * 当信号音量低于 `阈值` 时，滤波器开始向**基础增益**变化。重置速度由 `Release (释放时间)` 控制。
* `Knee (拐点)`：这控制了当信号接近 `阈值` 时滤波器的反应平滑度。
    * 硬拐点（低数值）就像一个开关：滤波器保持在**基础增益**，直到信号精确地超过 `阈值`。
    * 软拐点（高数值）就像一个调光器：当信号接近 `阈值` 时，滤波器*平缓地*移动到**目标增益**，从而产生更渐进、更透明的效果。

请注意，`阈值` 和 `拐点` 的定义与传统压缩器不同。

#### 动态学习

完美地设置 `阈值` 和 `拐点` 可能很棘手，特别是当轨道的音量发生变化时。

当您启用**动态学习**时，插件会为您完成这项工作。它**持续分析输入信号**，并实时自动设置 `阈值` 和 `拐点`。这使动态处理能持续适应信号。

#### 动态相对

此模式完全改变了滤波器的监听内容。

* **普通模式**由绝对音量触发：即“滤波后的侧链”的绝对音量大吗？
* **相对模式**由相对音量触发：即“滤波后的侧链”是否比“整个侧链”更响？