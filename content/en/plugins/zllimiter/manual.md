---
title: Manual
description: How to use ZL Limiter
weight: 2
---

<img src="/images/zllimiter/dark_crop.jpg" style="width:750px; max-width: 100%; height: auto" />

## About

ZL Limiter is a limiter plugin with the following key features:

- **Pristine Precision**: True Peak limiting and oversampling up to 32x help control inter-sample peaks and reduce aliasing.
- **Transient Control**: Protect and shape transients with adjustable lookahead, adaptive recovery, and flexible attack and release settings.
- **Stereo Integrity**: Preserve spatial width with customizable channel delta control.
- **Intuitive Workflow**: A carefully designed interface featuring a real-time scrolling waveform display and comprehensive loudness metering.

## Top Panel

___

<p float="left">
  <img src="/images/pcommon/zlaudio.svg" width="20pt" />
  <img src="/images/zllimiter/logo.svg" width="20pt" />
</p>

You can open the [UI Setting Panel](#ui-setting-panel) by clicking the logo.

___

<p float="left">
  <img src="/images/pcommon/collections_bookmark.svg" width="20pt"/>
</p>

You can open the [Preset Manager Panel](#preset-manager-panel) by clicking the icon.

___

**`Analyzer`**

You can open the [Analyzer Setting Panel](#analyzer-setting-panel) by clicking the text.

___

**`Ceiling`**

Adjusts the maximum output ceiling level.

___

**`Oversample`**

Selects the oversampling rate to reduce aliasing and inter-sample peaks, up to `32x`.

- `Off` is recommended for peak protection
- `4x` is recommended as the setting for fine-tuning and exporting/rendering
- `8x`, `16x`, `32x` are recommended if you can hear artifacts at `4x`

Oversampling adds a low-pass filter around the Nyquist frequency. As a result, you may observe gain reduction even if the signal peak is below the ceiling.

Higher oversampling rates increase CPU use. If playback crackles or drops out, try a lower rate or a larger audio buffer in your host.

___

<p float="left">
  <img src="/images/zllimiter/dline_tp.svg" width="20pt"/>
</p>

Toggles True Peak limiting to prevent inter-sample clipping. See details at [True Peak Limiting](#true-peak-limiting).

___


<p float="left">
  <img src="/images/pcommon/delta.svg" width="20pt"/>
</p>

Toggles delta audition. This helps you hear what the gain reduction removes from the signal.

___

<p float="left">
  <img src="/images/pcommon/bypass.svg" width="20pt"/>
</p>

Toggles plugin bypass.

___


## Analyzer Setting Panel

___

**Peak Mode**

Selects peak detection mode for the analyzer.

- `Peak`
- `True Peak`

___

**Scrolling Mode**

Selects the waveform scrolling mode.

- `Sync`
- `Slow`
- `Roll`

___

`Pre`

Toggles display of the input magnitude curve.

___

`Post`

Toggles display of the output magnitude curve.

___

`Delta`

Toggles display of the limiter gain reduction curve.

___

**Analyzer Time Duration**

Selects the time duration displayed in the analyzer window.

___

**Analyzer Min DB**

Selects the minimum decibel floor for the analyzer display.

___

<p float="left">
  <img src="/images/zllimiter/dline_meter.svg" width="20pt"/>
</p>

Toggles visibility of the level meter panel.

___

<p float="left">
  <img src="/images/zllimiter/dline_123.svg" width="20pt"/>
</p>

Toggles visibility of the [Value Panel](#value-panel).

___

## Center Panel

#### Input Gain Slider

The input gain slider is a vertical slider on the left edge of the center panel.

Adjusts the level entering the limiter.

A combobox below lets you choose the input-output gain linking mode:

- `Input`: Adjusts `Input Gain` without corresponding output compensation
- `Linked`: For positive `Input Gain`, applies an equal amount of attenuation after the limiter

#### Magnitude Analyzer

The magnitude analyzer occupies the whole center panel. It shows three curves:

- the pre curve: magnitude of the input main-chain signal
- the post curve: magnitude of the output main-chain signal
- the reduction curve: magnitude of the gain reduction

## Bottom Panel

___

**`Lookahead`**

Adjusts the lookahead time for the main envelope to anticipate transients. See details at [Main Limiting](#main-limiting).

___

**`Recovery`**

Adjusts the adaptive recovery time for the main envelope. See details at [Main Limiting](#main-limiting).

___

**`Attack`**

Adjusts the attack time of the sustained support envelope. See details at [Support Envelope](#support-envelope).

___

**`Release`**

Adjusts the release time of the sustained support envelope. See details at [Support Envelope](#support-envelope).

___

**`Stereo Delta`**

Adjusts the maximum allowed gain reduction difference between channels. See details at [Stereo Linking](#stereo-linking).

___

## Value Panel

The value panel displays loudness and numeric readouts.

- When the host supplies transport information, measurements pause when playback stops and reset when playback resumes
- Closing or hiding the whole editor interrupts measurement; opening or showing it again resets the meters

| Controls                                                | Result                                                             |
| ------------------------------------------------------- | ------------------------------------------------------------------ |
| Double-click the **True Peak** row                      | Resets its held peak                                               |
| Double-click **Correlation**                            | Resets its correlation statistics                                  |
| Double-click the **LUFS-M, LUFS-S, LRA, or LUFS-I** row | Resets all loudness statistics and the loudness histogram together |
| Double-click the vertical **level meter**               | Resets its held maximum reduction and output peak                  |

___

**`True Peak`**

Displays the maximum held True Peak level.

___

**`Correlation`**

Displays current (left) and average (right) stereo phase correlation.

___

**`LUFS-M`**

Displays current (left) and maximum (right) momentary loudness (over a 400 ms window).

___

**`LUFS-S`**

Displays current (left) and maximum (right) short-term loudness (over a 3-second window).

___

**`LRA`**

Displays the loudness range. Brackets indicate a provisional measurement.

___

**`LUFS-I`**

Displays the integrated loudness for the current measurement period.

___

## UI Setting Panel

The UI setting panel controls analyzer colors, slider operations, etc. Components will be introduced in order from top to bottom.

#### Color

You can adjust the color by clicking on the left color block and change the transparency by dragging the right slider.

**`Text Color`**

**`Background Color`**

For better accessibility, please set Text/Background to colors with high contrast.

**`Shadow Color`**

**`Glow Color`**

**`Pre Color`**

**`Post Color`**

**`Reduction Color`**

**`Grid Color`**

**`Color Map 1`**

**`Color Map 2`**

#### Control

**`Wheel Sensitivity`**

- `Rough`: mouse-wheel sensitivity when `Shift` is not pressed
- `Fine`: mouse-wheel sensitivity when `Shift` is pressed
- `Menu`: mouse-wheel sensitivity when changing menu selections
- `Reverse`: whether to reverse the direction of the mouse wheel when `Shift` is pressed

**`Slider Sensitivity`**

- `Rough`: mouse-drag sensitivity when `Shift` is not pressed
- `Fine`: mouse-drag sensitivity when `Shift` is pressed

**`Rotary Slider Style`**

- `Circular`: A rotary control that you move by dragging the mouse in a circular motion, like a knob
- `Horizontal`: A rotary control that you move by dragging the mouse left-to-right
- `Vertical`: A rotary control that you move by dragging the mouse up-and-down
- `Horiz + Vert`: A rotary control that you move by dragging the mouse up-and-down or left-to-right
- `Distance`: the relative distance that the mouse has to move to drag the slider across the full extent of its range. It does not apply to the Circular style.

**`Slider Double Click`**

- `Return Default`: when you double-click the slider, it returns to the default value; when you double-click the slider with Ctrl/Command, it opens the value editor.
- `Open Editor`: when you double-click the slider, it opens the value editor; when you double-click the slider with Ctrl/Command, it returns to the default value.

___

#### Other

**`Refresh Rate`**

Set this to 1/n of your monitor refresh rate. For example,
- If your monitor refresh rate is 120 Hz, set it to 120 Hz, 60 Hz (1/2), or 30 Hz (1/4). DO NOT set it to 90 Hz.
- If your monitor refresh rate is 90 Hz, set it to 90 Hz or 30 Hz (1/3). DO NOT set it to 60 Hz.

**`Combobox Alignment`**

- `Left`: combobox items are left-aligned
- `Center`: combobox items are center-aligned
- `Right`: combobox items are right-aligned

**`Curve Thickness`**

Adjust the thickness of the magnitude curve.

**`Tooltip`**

Choose the tooltip language. It will take effect when the plugin window is reopened.

**`UI Scaling`**

Choose the font size mode.

- `Scale`: the font size scales with the window size. Controls the relative ratio.
- `Static`: the font size is fixed. Controls the actual font size.

**`Window Size Fix`**

Choose whether to turn on Window Size Fix.

- `Off`: plugin window size adjustments will be stored
- `On`: plugin window size adjustments will NOT be stored; instead, the window will open at its current size each time the plugin is opened. The size can still be changed, but the changes will not be stored.

___

## Preset Manager Panel

The preset manager lets you save, organize, and delete presets.

___

**`Search Presets`**

Enter a preset name and search.

___

**`New Group`**

Enter a new group name and press `Enter` to save it.

___

**`New Preset`**

Enter a new preset name and press `Enter` to save it.

___

<p float="left">
  <img src="/images/pcommon/trash.svg" width="20pt"/>
</p>

- Press: delete the selected preset group (along with all presets in the group) or the selected preset

___

<p float="left">
  <img src="/images/pcommon/folder_open.svg" width="20pt"/>
</p>

- Press: reveal the preset folder

___

## UI Controls

Generally, you can enable fine adjustment with `Shift` and enable special adjustment with `Ctrl/Command`. If the direction of the mouse wheel is reversed when `Shift` is pressed, you can reverse it again (in the UI Setting Panel) to put it back to normal.

**Sliders**

- You can enable fine adjustment with `Shift` when using the mouse to drag / the mouse wheel to adjust sliders.
- You can use the left/right mouse button to control the first/second value when there are two values on the slider.

**Combobox**

- You can use the mouse wheel to change the selected item.

**Window Size**

- You can drag the resize handle at the bottom-right corner to adjust the plugin window size.
- Recommended way to set Window Size:
	1. Set **Window Size Fix** to `OFF` and press the store button.
	2. Adjust the plugin window to the size you prefer.
	3. Close the plugin window.
	4. Reopen the plugin window.
	5. Set **Window Size Fix** to `ON` and press the store button.
	6. Close the plugin window.
	7. Then, the plugin will open with the window size set in Step 2 every time.

## Peak Limiting

ZL Limiter utilizes a dual-envelope architecture consisting of a primary peak envelope, a secondary support envelope, variable stereo linking, and optional True Peak limiting.

#### Main Limiting

The main stage attenuates individual transient peaks. When oversampling is enabled, this stage also suppresses inter-sample peaks.

**`Lookahead`** sets the analysis time prior to peak arrival. Higher values lengthen the lookahead window, initiating gain reduction earlier for smoother attenuation. Lower values shorten the lookahead window, delaying gain reduction until peak arrival to preserve transient punch.

**`Recovery`** sets the minimum return time to unity gain following an isolated peak. The release rate automatically slows during heavy or continuous limiting to minimize distortion. Higher values lengthen the recovery time for cleaner, more transparent limiting. Lower values shorten the recovery time to maximize loudness between transients.

#### Support Envelope

The support envelope stabilizes macro loudness and dense peak sequences. By maintaining attenuation across closely spaced transients, it prevents rapid gain fluctuations and shares dynamic reduction with the main stage for cleaner overall processing.

**`Attack`** sets the onset time required for sustained gain reduction to engage. Higher values lengthen the attack time, allowing initial transients to pass solely to the main stage and engaging support only during sustained loudness. Lower values shorten the attack time, applying sustained gain reduction immediately upon encountering high signal levels.

> Individual peaks remain governed by the main limiting envelope regardless of the support **`Attack`** setting.

**`Release`** sets the return time for sustained gain reduction to reach unity once signal levels decrease. Higher values lengthen the release time, providing a gradual return to unity gain. Lower values shorten the release time, restoring signal levels more rapidly following loud passages.

> Use **`Recovery`** to control gain restoration following discrete transients, and use **`Release`** to govern sustained attenuation across dense, continuous program material.

#### Stereo Linking

**`Stereo Delta`** sets the maximum allowable gain reduction difference between the left and right channels. At `0 dB`, channels are fully linked to preserve stereo balance. Higher values permit greater channel independence, increasing apparent loudness at the expense of potential shifts in the stereo image.

#### True Peak Limiting

When enabled, an output stage suppresses inter-sample peaks that may cause clipping during digital-to-analog conversion or lossy encoding. This stage also catches reconstructed peaks introduced when downsampling to the project sample rate.

True Peak limiting remains active when oversampling is set to `Off` and also stays independent of the visual peak metering modes.