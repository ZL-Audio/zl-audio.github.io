---
title: Manual
description: How to use ZL Equalizer 2
weight: 2
---

## Tutorial Video

{{< youtube "VzmNqjWfE2Y" >}}

## About

ZL Equalizer 2 is a dynamic equalizer plugin with the following key features:

- **Unmatched Versatility**: Sculpt your sound with 6 filter structures, 8 filter types, 5 stereo modes, 7 variable slopes, and up to 24 frequency bands.
- **Integrated Dynamic Control**: Go beyond static EQ with adjustable threshold, attack, release, and side-chain filters for powerful dynamic equalization.
- **Pristine Precision**: 64-bit floating-point processing and advanced de-cramping technique deliver outstanding performance, ensuring exceptional clarity from the deepest lows to the highest highs.
- **Intuitive Workflow**: A carefully designed interface with an interactive spectrum graph, smart collision detection, and smooth animations makes equalization fast and fluid.

## Top Panel

___

<p float="left">
  <img src="/images/zlequalizer2/zlaudio.svg" width="20pt" />
  <img src="/images/zlequalizer2/logo.svg" width="20pt" />
</p>

You can open the [UI Setting Panel](#ui-setting-panel) by double-clicking the logo.

___

**Analyzer**

You can open the [Analyzer Setting Panel](#analyzer-setting-panel) by clicking the text.

___

<p float="left">
  <img src="/images/zlequalizer2/match.svg" width="20pt"/>
</p>

You can open the [EQ Match Panel](#eq-match-panel) by clicking the icon.

___

**Filter Structure**

- `Minimum Phase`: [Minimum Phase](#minimum-phase)
- `State Variable`: [State Variable](#state-variable)
- `Parallel`: [Parallel](#parallel)
- `Matched Phase`: [Matched Phase](#matched-phase)
- `Mixed Phase`: [Mixed Phase](#mixed-phase)
- `Zero Phase`: [Zero Phase](#zero-phase)

___

**Output Panel**

You can open the [Output Setting Panel](#output-setting-panel) by clicking the text. It shows the current filter gain scale & total output gain.

___

<p float="left">
  <img src="/images/zlequalizer2/external-side.svg" width="20pt"/>
</p>

- Press: use the external side-chain
- Release: use the internal side-chain

___

<p float="left">
  <img src="/images/zlequalizer2/bypass.svg" width="20pt"/>
</p>

- Release: bypass the plugin

___

## Center Panel

The center panel consists of a spectrum analyzer, filter response curves, filter buttons, a floating window, and a decibel scale.

#### Spectrum Analyzer

The spectrum analyzer shows the spectrum of the input/output/side-chain signal and collision areas (optional). You can control it via the [Analyzer Setting Panel](#analyzer-setting-panel).

#### Filter Response Curves

The filter response curves show the magnitude response of each single band and the magnitude response of each stereo placement.

#### Filter Buttons

The filter buttons are attached to filter response curves. You can drag them to change filter parameters. See more info in [UI Controls](#ui-controls).

When you double-click (with/without `Ctrl/Command` down) on the spectrum, a band will be added at the corresponding position (with/without dynamic behavior enabled) with a filter button.

#### Floating Window

The floating window is attached to the filter button of the selected band. You can control some filter parameters through this window.

| Icon                                                         | Filter Type  | Icon                                                      | Stereo Placement |
| ------------------------------------------------------------ | ------------ | --------------------------------------------------------- | ---------------- |
| <img src="/images/zlequalizer2/peak.svg" width="20pt"/>      | `Peak`       | <img src="/images/zlequalizer2/stereo.svg" width="20pt"/> | `Stereo`         |
| <img src="/images/zlequalizer2/lowshelf.svg" width="20pt"/>  | `Low Shelf`  | <img src="/images/zlequalizer2/left.svg" width="20pt"/>   | `Left`           |
| <img src="/images/zlequalizer2/lowpass.svg" width="20pt"/>   | `Low Pass`   | <img src="/images/zlequalizer2/right.svg" width="20pt"/>  | `Right`          |
| <img src="/images/zlequalizer2/highshelf.svg" width="20pt"/> | `High Shelf` | <img src="/images/zlequalizer2/mid.svg" width="20pt"/>    | `Mid`            |
| <img src="/images/zlequalizer2/highpass.svg" width="20pt"/>  | `High Pass`  | <img src="/images/zlequalizer2/side.svg" width="20pt"/>   | `Side`           |
| <img src="/images/zlequalizer2/notch.svg" width="20pt"/>     | `Notch`      |                                                           |                  |
| <img src="/images/zlequalizer2/bandpass.svg" width="20pt"/>  | `Band Pass`  |                                                           |                  |
| <img src="/images/zlequalizer2/tiltshelf.svg" width="20pt"/> | `Tilt Shelf` |                                                           |                  |

#### Right-click Panel

___

**Invert Gain**

- Click: invert gain of the selected band

___

**Split L/R**

- Click: set selected band to `Left` and add a band with same parameters but in `Right`

___

**Split M/S**

- Click: set selected band to `Mid` and add a band with same parameters but in `Side`

___

**Copy**

- Click: copy all selected bands' filter parameters to the clipboard

___

**Paste**

- Click: get filter parameters from the clipboard and create those bands

___

#### Decibel Scale

You can choose the decibel scale of magnitude response curves (through a combobox at the top-right) and the decibel scale of the spectrum analyzer (through a combobox at the bottom-right).

## Bottom Panel

#### Left Panel

___

<p float="left">
  <img src="/images/zlequalizer2/bypass.svg" width="20pt"/>
</p>

- Release: bypass the band.

---

**Band Selection**

Select the current band.

___

**Filter Type**

Choose the filter type: `Peak`, `Low Shelf`, `Low Pass`, `High Shelf`, `High Pass`, `Notch`, `Band Pass`, and `Tilt Shelf`.

---

**Slope**

Choose the filter slope: `6 dB/oct`, `12 dB/oct`, `24 dB/oct`, `36 dB/oct`, `48 dB/oct`, `72 dB/oct`, and `96 dB/oct`. A higher slope will make the filter’s response curve change more steeply. `Peak`, `Notch`, and `Band Pass` don’t support `6 dB/oct`.

---

**Stereo Modes**

Choose the stereo mode: `Stereo`, `Left`, `Right`, `Mid`, and `Side`.

___

**`FREQ`**

Control the frequency. The maximum value of the frequency is affected by the sample rate.

___

**`GAIN`**

Control the base gain and the target gain. See more info in [Dynamic Filter](#dynamic-filter).

___

**`Q`**

Control the quality factor.

___

<p float="left">
  <img src="/images/zlequalizer2/dynamic.svg" width="20pt"/>
</p>

- Press: turn on the dynamic behavior of the band

___


<p float="left">
  <img src="/images/zlequalizer2/close.svg" width="20pt"/>
</p>

- Click: turn off the band

___

#### Right Panel

___


<p float="left">
  <img src="/images/zlequalizer2/bypass.svg" width="20pt"/>
</p>

- Release: bypass the dynamic behavior. See more info in [Dynamic Filter](#dynamic-filter).

___


<p float="left">
  <img src="/images/zlequalizer2/circle_a.svg" width="20pt"/>
</p>

- Press: turn on the dynamic learning behavior. See more info in [Dynamic Filter](#dynamic-filter).
- Release: turn off the dynamic learning behavior and set the `Threshold` and `Knee`

___


<p float="left">
  <img src="/images/zlequalizer2/circle_r.svg" width="20pt"/>
</p>

- Press: turn on the dynamic relative behavior. See more info in [Dynamic Filter](#dynamic-filter).

___


<p float="left">
  <img src="/images/zlequalizer2/shuffle.svg" width="20pt"/>
</p>

- Press: change the side-chain stereo mode. When pressed, if the band is in `Left`/`Right`/`Mid`/`Side`, the side-chain band will be in `Right`/`Left`/`Side`/`Mid`.

___

**`Threshold`**

See more info in [Dynamic Filter](#dynamic-filter).

___

**`Knee`**

See more info in [Dynamic Filter](#dynamic-filter).

___

**`Attack`**

See more info in [Dynamic Filter](#dynamic-filter).

___

**`Release`**

See more info in [Dynamic Filter](#dynamic-filter).

___


<p float="left">
  <img src="/images/zlequalizer2/link.svg" width="20pt"/>
</p>

- Press: link the band with the side-chain band. See more info in [Dynamic Filter](#dynamic-filter).

___

**Side-chain Filter Type**

Choose the side-chain filter type: `BP (Band Pass)`, `LP (Low Pass)`, and `HP (High Pass)`.

___

**Side-chain Filter Slope**

Choose the side-chain filter slope: `6 dB/oct`, `12 dB/oct`, `24 dB/oct`, `36 dB/oct`, `48 dB/oct`, `72 dB/oct`, and `96 dB/oct`.

___

**`FREQ`**

Control the side-chain filter frequency.

___

**`Q`**

Control the side-chain filter quality factor.

___

## Output Setting Panel

___

**`GAIN`**

Control the additional output gain.

___

**`SCALE`**

Control the scale of all filters' base & target gain.

___

<p float="left">
  <img src="/images/zlequalizer2/dline_s.svg" width="20pt"/>
</p>

- Press: turn on Static Gain Compensation
- Release: turn off Static Gain Compensation

> SGC estimates the amount of compensation from the filters’ parameters. SGC is **inaccurate**. However, it **will NOT affect the dynamic of the main-chain signal**.

___

<p float="left">
  <img src="/images/zlequalizer2/dline_l.svg" width="20pt"/>
</p>

- Press: start to measure the integrated loudness of the input signal and the output signal
- Release: turn AGC off and update the `Output Gain` to the difference between the two loudness values

___

<p float="left">
  <img src="/images/zlequalizer2/dline_a.svg" width="20pt"/>
</p>

- Press: turn on Auto Gain Compensation
- Release: turn off Auto Gain Compensation

> AGC calculates the difference between the loudness of the main-chain signal before/after filters and applies the corresponding gain. Therefore, **AGC will affect the dynamic of the main-chain signal**.
> 
> When AGC is on, the output main-chain signal will pass through a hard clipper at 0 dB.

___

<p float="left">
  <img src="/images/zlequalizer2/phase.svg" width="20pt"/>
</p>

- Press: flip the phase of the output signal

___

**`Lookahead`**

Control the lookahead of the side-chain signal.

> **Warning:** **Do not automate** `Lookahead`.

## Analyzer Setting Panel

___

**`Pre/Post/Side`**

- Press: turn on the Pre/Post/Side analyzer
- Release: turn off the Pre/Post/Side analyzer

___

**Decay Speed**

___

**Slope**

- affects the spectrum display (not the actual signal)
- `0 dB/oct`: no tilting, white noise displays as a horizon line
- `3 dB/oct`: pink noise displays as a horizon line
- `4.5 dB/oct`: default value, which represents perceived loudness better

---

<p float="left">
  <img src="/images/zlequalizer2/freeze.svg" width="20pt"/>
</p>

- Press: turn on the FFT freezing feature. When you hover the mouse over the analyzer for 2 seconds, the Post/Side analyzer will be frozen until you move the mouse.

___

**FFT Analyzer Stereo Placement**

| Icon                                                      | Stereo Placement |
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

- Press: turn on the collision detection.

___

**`Strength`**

Control the collision detection strength.

___

## EQ Match Panel

> **Warning**: Once the EQ Match panel is open, **DO NOT** change the plugin's sample rate (e.g., by changing the project sample rate or enabling DAW oversampling for this plugin). **Otherwise, this plugin may crash the DAW**.

#### EQ Match Steps

1. Open the EQ Match Panel. It will analyze the source signal and the target signal.
2. Choose the target signal. The source signal must be the main-chain input. You can choose the target signal from the side-chain input, a flat line, or a preset.
3. Wait till the difference curve becomes stable. Then adjust the difference curve with `Shift`, `Smooth`, and `Slope`. You can also draw the difference curve if you want.
4. Start the fitting. The fitting process should finish in several seconds. After that, you can adjust the number of bands.

#### EQ Match Analyzer

When the EQ Match Panel is visible, the analyzer displays three curves:

- **Source Curve**: the average spectrum of the source signal.
- **Target Curve**: the average spectrum of the target signal.
- **Difference Curve**: the difference between the source signal and the target signal.

When the difference curve drawing is enabled, you can:

- draw the difference curve with the left mouse button dragging
- reset the difference curve with the right mouse button dragging
- set the difference curve to zero with Shift + the left mouse button dragging
- reset the whole difference curve with the left mouse button double-clicking

#### EQ Match Control

___

<p float="left">
  <img src="/images/zlequalizer2/save.svg" width="20pt"/>
</p>

- Click: save the target curve to a preset file

___

<p float="left">
  <img src="/images/zlequalizer2/draw.svg" width="20pt"/>
</p>

- Press: enable the difference curve drawing

___

**Target Signal**

Choose the target signal:

- `Side`: let the target curve be the average spectrum of the side-chain signal
- `Flat`: set the target curve as a flat line
- `Preset`: load the target curve from a preset file

___

**`Shif`**

Control the vertical shift of the difference curve.

___

**`Smooth`**

Control the smoothness of the difference curve.

- from 0.0 to 0.5: the difference curve becomes smoother as the smoothness increases
- from 0.5 to 1.0: the difference curve scales down as the smoothness increases

___

**`Slope`**

Control the (additional) slope of the difference curve.

___

<p float="left">
  <img src="/images/zlequalizer2/start.svg" width="20pt"/>
</p>

- Click: start the fitting process.

> **Warning:** Once you click this button, **ALL** bands will be deleted and then be set to fitted parameters.

___

**Number of Bands**

Control the number of bands for fitting. You can control it after the fitting is completed.

___

## UI Setting Panel

The UI setting panel controls analyzer colors, slider operations, etc. Components will be introduced in the order from top to bottom.

#### Color

You can adjust the color by clicking on the left color block and change the transparency by dragging the right slider.

**Text Color**

**Background Color**

For better accessibility, please set Text/Background to colors with high contrast.

**Shadow Color**

**Glow Color**

**Pre Color**

**Post Color**

**Side Color**

**Collision Color**

**Grid Color**

**Color Map 1**

- The color map of the curves of each single filter.

**Color Map 2**

- The color map of the curves of Stereo/Left/Right/Mid/Side.

**Import Colors**

- Import color settings (`.xml` file)

**Export Colors**

- Export color settings (`.xml` file)

#### Control

**Wheel Sensitivity**

- Rough: mouse-wheel sensitivity when `Shift` is not pressed
- Fine: mouse-wheel sensitivity when `Shift` is pressed
- Reverse: whether to reverse the direction of mouse-wheel when `Shift` is pressed

**Drag Sensitivity**

- Rough: mouse-drag sensitivity when `Shift` is not pressed
- Fine: mouse-drag sensitivity when `Shift` is pressed

**Rotary Slider Style**

- `Circular`: A rotary control that you move by dragging the mouse in a circular motion, like a knob
- `Horizontal`: A rotary control that you move by dragging the mouse left-to-right
- `Vertical`: A rotary control that you move by dragging the mouse up-and-down
- `Horiz + Vert`: A rotary control that you move by dragging the mouse up-and-down or left-to-right
- `Distance`: the relative distance that the mouse has to move to drag the slider across the full extent of its range. It does not apply to the Circular style.

**Slider Double Click**

- `Return Default`: when you double-click the slider, it returns to the default value; when you double-click the slider with Ctrl/Command, it opens the value editor.
- `Open Editor`: when you double-click the slider, it opens the value editor; when you double-click the slider with Ctrl/Command, it returns to the default value.

**Import Controls**

- Import control settings (`.xml` file)

**Export Controls**

- Export control settings (`.xml` file)

#### Other

**Refresh Rate**

In general, 30 Hz is enough for an equalizer plugin.

For a better analyzer display, set this to 1/n of your monitor refresh rate. For example,
- If your monitor refresh rate is 120 Hz, set it to 120 Hz, 60 Hz (1/2), or 30 (1/4) Hz. DO NOT set it to 90 Hz.
- If your monitor refresh rate is 90 Hz, set it to 90 Hz or 30 Hz (1/3). DO NOT set it to 60 Hz.


**FFT  Setting**

- `Tilt`: the extra tilting slope of the FFT
- `Speed`: the extra decay speed of the FFT

**Curve Thickness**

Control the thickness of the curve of each band & each stereo mode.

**Tooltip**

Choose the tooltip language. It will take effect when the plugin window is reopened.

**UI Scaling**

Choose the font size mode.

- `Scale`: the font size scales with the window size. Control the relative ratio.
- `Static`: the font size is fixed. Control the actual font size.

## UI Controls

Generally, you can enable fine-adjustment with `Shift` and enable special adjustment with `Ctrl/Command`. If the direction of the mouse wheel is reversed when `Shift` is pressed, you can reverse it again (in the UI Setting Panel) to put it back to normal.

**Sliders**

- You can enable fine-adjustment with `Shift` when using the mouse to drag / the mouse wheel to adjust sliders.
- You can use the left/right mouse button to control the first/second value when there are two values on the slider.

**Filter Buttons**

- You can drag a button to change the frequency/gain value.
- You can use the mouse wheel to change the Q value.
- You can use the mouse wheel + `Ctrl/Command` to change the slope.
- You can enable fine-adjustment with `Shift` when using the mouse to drag a button.
- You can drag with the left mouse button + `Ctrl/Command` down while fixing the frequency.
- You can drag with the right mouse button + `Ctrl/Command` down while fixing the gain.
- You can double-click the button to enter/exit the solo status.
- You can double-click with `Ctrl/Command` to turn on/off the dynamic behavior.

## Filter Structure

#### Minimum Phase

This is the **standard, classic digital EQ sound**. It's the most common filter type.

* **Best For:** General EQ tasks.
* **Pros:** Gentle 6 dB and 12 dB/oct slopes cause very little phase shift, making it safe to blend with your original signal (low risk of cancellation).
* **Cons:** Aggressive automation of frequency or gain can sometimes cause audible clicks or instability.
#### State Variable

This is the filter type often used in **synth filters and crossovers**.

* **Best For:** Creative effects and heavy automation.
* **Pros:** Extremely stable, even with rapid, complex automation.
* **Cons:** Causes a significant phase shift. **Avoid mixing this signal with the original** (or other correlated signals) as it will likely cause phase cancellation.

#### Parallel

This mode changes how filters work together. **Shelf** (<= 12 dB/oct) and **Peak** (<= 24 dB/oct) filters are processed in parallel.

* **Best For:** Efficient dynamic EQ processing & Natural sounding.
* **Pros:** Offers a different character and is more CPU-efficient for dynamic tasks.
* **Cons:** The parallel processing means the final EQ curve **will look different** from the curves shown on the display.

#### Matched Phase

This mode adds a special process to the `Minimum Phase` filters to **mimic analog prototype** magnitude & phase response.

* **Best For:** Getting an **analog** phase and magnitude response.
* **Latency:** Adds about 11 ms (up to 22 ms for L/R & M/S processing).
* **Cons**: Dynamic filters stay in `Minimum Phase`.

> **Warning:** **Do not automate** filter parameters in this mode.

#### Mixed Phase

This mode adds a special process to the `Minimum Phase` filters to **mimic analog prototype** magnitude response and clean up high-end phase.

* **Best For:** Getting an **analog** magnitude response without the high-end phase shift (above 5 kHz).
* **Latency:** Adds about 21 ms (up to 43 ms for L/R & M/S processing).
* **Cons**: Dynamic filters stay in `Minimum Phase`.

> **Warning:** **Do not automate** filter parameters in this mode.

#### Zero Phase

This mode provides **almost zero phase response**.

* **Best For:** Surgical mastering tasks where preserving phase relationships is critical.
* **Pros:** No phase distortion at all for mid/high frequencies (above 200 Hz).
* **Cons:** Adds a **very high latency** of about 171 ms (up to 342 ms for L/R & M/S processing). May cause audible pre-ringing. Dynamic filters stay in `Minimum Phase`.

> **Warning:** **Do not automate** filter parameters in this mode.


## Dynamic Filter

#### How the Dynamic Filter Works

A dynamic filter automatically turns the gain of a band up or down for you, but only when specific frequencies get too loud or too quiet.

#### Core Dynamic Behavior

When dynamic mode is enabled, the filter listens to a specific frequency range, i.e., the side-chain signal filtered by the side-chain filter. The settings tell it when to react and how fast.

* `Threshold`: This is the trigger level.
    * When the signal's volume crosses above `Threshold`, the filter starts to change to the **target gain**. The reaction speed is controlled by `Attack`.
    * When the signal's volume falls below `Threshold`, the filter starts to change to the **base gain**. The reset speed is controlled by `Release`.
* `Knee`: This controls how smoothly the filter reacts as the signal approaches the `Threshold`.
    * A hard knee (low value) is like a switch: the filter stays at **base gain** until the signal exactly crosses the `Threshold`.
    * A soft knee (high value) is like a dimmer: the filter *gently* moves to **target gain** as the signal gets close to the `Threshold`, resulting in a more gradual and transparent effect.

Please do keep in mind that the definition of `Threshold` and `Knee` is different from traditional compressors.

#### Dynamic Learning

Setting the `Threshold` and `Knee` perfectly can be tricky, especially if the track's volume changes.

When you enable **Dynamic Learning**, the plugin does the work for you. It **continuously analyzes the incoming signal** and automatically sets the `Threshold` and `Knee` in real-time. This keeps the dynamic processing adapted to the signal.

#### Dynamic Relative

This mode completely changes what the filter listens to.

* **Normal Mode** is triggered by the absolute volume: Is the filtered side-chain loud in absolute terms?
* **Relative Mode** is triggered by the relative volume: Is the filtered side-chain louder than the whole side-chain?