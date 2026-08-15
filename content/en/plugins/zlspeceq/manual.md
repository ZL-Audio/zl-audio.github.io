---
title: Manual
description: How to use ZL Spectrum Equalizer
weight: 2
---

<img src="/images/zlspeceq/dark_crop.jpg" style="width:750px; max-width: 100%; height: auto" />

## About

ZL Spectrum Equalizer is a dynamic spectrum equalizer plugin with the following key features:

- **Unmatched Versatility**: Sculpt sound with 9 filter types, 5 stereo modes, 7 variable slopes, and up to 24 linear-phase frequency bands.
- **Spectrum Dynamics**: Experience precise frequency-domain dynamic processing that tracks and controls resonances across the spectrum, with adjustable threshold, attack, release, and knee width.
- **Powerful Engine**: Tailor behavior and latency with different spectrum resolution settings, side-chain smoothing, and frequency-dependent attack/release skewing, all powered by a high-performance FFT engine.
- **Intuitive Workflow**: Achieve fast, fluid equalization with a carefully designed interface featuring an interactive spectrum graph, smart collision detection, and smooth animations.

## Top Panel

___

<p float="left">
  <img src="/images/zlspeceq/zlaudio.svg" width="20pt" />
  <img src="/images/zlspeceq/logo.svg" width="20pt" />
</p>

You can open the [UI Setting Panel](#ui-setting-panel) by clicking the logo.

___

<p float="left">
  <img src="/images/zlspeceq/collections_bookmark.svg" width="20pt"/>
</p>

You can open the [Preset Manager Panel](#preset-manager-panel) by clicking the icon.

___

**Analyzer**

You can open the [Analyzer Setting Panel](#analyzer-setting-panel) by clicking the text.

___

**Spectrum Resolution**

Choose the spectrum processing resolution:

- `Extreme Low`: around 12 ms latency
- `Very Low`: around 23 ms latency
- `Low`: around 46 ms latency
- `Medium`: around 93 ms latency
- `High`: around 186 ms latency
- `Very High`: around 372 ms latency
- `Extreme High`: around 743 ms latency

___

<p float="left">
  <img src="/images/zlspeceq/settings.svg" width="20pt"/>
</p>

- Press: open the [Spectrum Setting Panel](#spectrum-setting-panel)

___

**Spectrum Smooth Type**

Choose the spectrum processing side-chain smooth type:

- `OCT`: Octave
- `ERB`: Equivalent Rectangular Bandwidth (smoother at low frequency)

___

**Spectrum Smooth Value**

Control the spectrum processing side-chain smooth value. See more info in [Spectrum Dynamic](#spectrum-dynamic).

___

**Output**

You can open the [Output Setting Panel](#output-setting-panel) by clicking the text. It shows the current filter gain scale & total output gain.

___

<p float="left">
  <img src="/images/zlspeceq/external-side.svg" width="20pt"/>
</p>

- Press: use the external side-chain
- Release: use the internal side-chain

___

<p float="left">
  <img src="/images/zlspeceq/bypass.svg" width="20pt"/>
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

| Icon                                                  | Filter Type  | Icon                                               | Stereo Placement |
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

#### Context Menu

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
  <img src="/images/zlspeceq/bypass.svg" width="20pt"/>
</p>

- Release: bypass the band.

---

**Band Selection**

Select the current band.

___

**Filter Type**

Choose the filter type: `Peak`, `Low Shelf`, `Low Pass`, `High Shelf`, `High Pass`, `Notch`, `Band Pass`, `Tilt Shelf` and `Flat Tilt`.

---

**Slope**

Choose the filter slope: `6 dB/oct`, `12 dB/oct`, `24 dB/oct`, `36 dB/oct`, `48 dB/oct`, `72 dB/oct`, and `96 dB/oct`. A higher slope will make the filter’s response curve change more steeply. `Peak`, `Notch`, and `Band Pass` don’t support `6 dB/oct`. `Flat Tilt` doesn't support slope setting.

---

**Stereo Modes**

Choose the stereo mode: `Stereo`, `Left`, `Right`, `Mid`, and `Side`.

___

**`FREQ`**

Control the frequency. The maximum value of the frequency is affected by the sample rate.

___

**`GAIN`**

Control the base gain and the target gain. See more info in [Spectrum Dynamic](#spectrum-dynamic).

___

**`Q`**

Control the quality factor.

___

<p float="left">
  <img src="/images/zlspeceq/dynamic.svg" width="20pt"/>
</p>

- Press: turn on the spectrum dynamic behavior of the band

___


<p float="left">
  <img src="/images/zlspeceq/close.svg" width="20pt"/>
</p>

- Click: turn off the band

___

#### Right Panel

___

<p float="left">
  <img src="/images/zlspeceq/bypass.svg" width="20pt"/>
</p>

- Release: bypass the dynamic behavior. See more info in [Spectrum Dynamic](#spectrum-dynamic).

___

<p float="left">
  <img src="/images/zlspeceq/delta.svg" width="20pt"/>
</p>

- Press: output the dynamic delta signal.

___

**Dynamic Mode**

Choose the dynamic mode. See more info in [Spectrum Dynamic](#spectrum-dynamic).

___

**`Threshold`**

See more info in [Spectrum Dynamic](#spectrum-dynamic).

___

**`Knee`**

See more info in [Spectrum Dynamic](#spectrum-dynamic).

___

**`Attack`**

See more info in [Spectrum Dynamic](#spectrum-dynamic).

___

**`Release`**

See more info in [Spectrum Dynamic](#spectrum-dynamic).

___

## Spectrum Setting Panel

___

**`Tilt`**

Control the spectrum processing side-chain tilt slope. See more info in [Spectrum Dynamic](#spectrum-dynamic).

___

**`Attack Skew`**

Control the spectrum processing side-chain attack skew. See more info in [Spectrum Dynamic](#spectrum-dynamic).

___

**`Release Skew`**

Control the spectrum processing side-chain release skew. See more info in [Spectrum Dynamic](#spectrum-dynamic).

___

**`Gate`**

Control the spectrum gate of relative loudness. See more info in [Spectrum Dynamic](#spectrum-dynamic).

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
  <img src="/images/zlspeceq/dline_s.svg" width="20pt"/>
</p>

- Press: turn on Static Gain Compensation
- Release: turn off Static Gain Compensation

> SGC estimates the amount of compensation from the filters’ parameters. SGC is **inaccurate**. However, it **will NOT affect the dynamic of the main-chain signal**.

___

<p float="left">
  <img src="/images/zlspeceq/dline_l.svg" width="20pt"/>
</p>

- Press: start to measure the integrated loudness of the input signal and the output signal
- Release: update the `Output Gain` to the difference between the two loudness values


___

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

___

**Smoothing**

- Control the smoothing value, larger value indicates more smooth spectrum
- `OCT`: smooth the spectrum in octave
- `ERB`: smooth the spectrum in ERB (Equivalent Rectangular Bandwidth)

---

<p float="left">
  <img src="/images/zlspeceq/freeze.svg" width="20pt"/>
</p>

- Press: turn on the FFT freezing feature. When you hover the mouse over the analyzer for 2 seconds, the Post/Side analyzer will be frozen until you move the mouse.

___

**FFT Analyzer Stereo Placement**

| Icon                                                      | Stereo Placement |
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

- Press: turn on the collision detection.

___

**`Strength`**

Control the collision detection strength.

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

#### Control

**Wheel Sensitivity**

- `Rough`: mouse-wheel sensitivity when `Shift` is not pressed
- `Fine`: mouse-wheel sensitivity when `Shift` is pressed
- `Menu`: mouse-wheel sensitivity when adjust combobox items
- `Reverse`: whether to reverse the direction of mouse-wheel when `Shift` is pressed

**Drag Sensitivity**

- `Rough`: mouse-drag sensitivity when `Shift` is not pressed
- `Fine`: mouse-drag sensitivity when `Shift` is pressed

**Rotary Slider Style**

- `Circular`: A rotary control that you move by dragging the mouse in a circular motion, like a knob
- `Horizontal`: A rotary control that you move by dragging the mouse left-to-right
- `Vertical`: A rotary control that you move by dragging the mouse up-and-down
- `Horiz + Vert`: A rotary control that you move by dragging the mouse up-and-down or left-to-right
- `Distance`: the relative distance that the mouse has to move to drag the slider across the full extent of its range. It does not apply to the Circular style.

**Slider Double Click**

- `Return Default`: when you double-click the slider, it returns to the default value; when you double-click the slider with Ctrl/Command, it opens the value editor.
- `Open Editor`: when you double-click the slider, it opens the value editor; when you double-click the slider with Ctrl/Command, it returns to the default value.

___

Short-cut settings for following actions:

**Enter Solo**

**Exit Solo**

**Context Menu**

**Toggle Dynamic**

**Toggle Bypass**

**Delete Band**

___

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

**`Curve dB Scale`**

- `Min`: minimum decibel scale of magnitude response curves
- `Default`: default decibel scale of magnitude response curves
- `Max`: maximum decibel scale of magnitude response curves

**`Window Size Fix`**

Choose whether to turn on Window Size Fix.

- `Off`: plugin window size adjustment will be stored
- `On`: plugin window size adjustment will NOT be stored, but open as it is currently every time the plugin is opened. The size can still be changed, but the changes will not be stored.

## Preset Manager Panel

The preset manager panel let you manage(save/group/delete) presets.

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
- Other controls can be set via [UI Setting Panel](#ui-setting-panel), such as enter/exit solo, toggle dynamic/bypass, etc

**Combobox**

- You can use the mouse wheel to change the selected item.

**Window Size**

- You can drag a dragger at the bottom-right corner to adjust plugin window size.
- Recommend way to set Windows Size
	1. Set **Window Size Fix** to `OFF` and press the store button.
	2. Adjust the plugin window to the size you prefer.
	3. Close the plugin window.
	4. Reopen the plugin window.
	5. Set **Window Size Fix** to `ON` and press the store button.
	6. Close the plugin window.
	7. Then, the plugin will be opened with the window size set in the Step 2 every time.

## Spectrum Dynamic

#### How Spectrum Dynamic Works

Unlike ZL Equalizer 2 that applies broad filter curves based on wide-band audio triggers, ZL Spectrum Equalizer operates directly in the frequency domain using Fast Fourier Transforms (FFT). Audio is split into discrete frequency bins, allowing dynamic gain adjustments to be applied independently to each bin based on the level of the corresponding side-chain bin.

#### Spectrum Resolution

The **Spectrum Resolution** setting determines the FFT frame size used for spectral analysis and dynamic processing, establishing a direct trade-off between frequency precision and latency:

- **Lower Resolutions** (`Extreme Low` to `Low`): Offer minimal processing latency (~12 ms to ~46 ms) and quick time-domain response, making them well-suited for live tracking or transient-heavy material.
- **Medium Resolution** (`Medium`): Balances time and frequency resolution (~93 ms latency) for general mixing tasks.
- **Higher Resolutions** (`High` to `Extreme High`): Provide exceptionally fine spectral resolution (~186 ms to ~743 ms latency) for exceptional low-frequency precision and surgical notch correction of narrow resonances.

In general, if you do not process the low-frequency part heavily (e.g., a high-pass below 100Hz), choose medium or lower resolutions to save processing power, reduce latency, and make dynamic processing more reactive. However, if you want heavy & precise low-frequency control, you may need to choose higher resolutions. Please watch out potential pre-ringing & CPU-spikes when you choose higher resolution.

#### Core Dynamic Behavior

When dynamic behavior is enabled for a band, each FFT bin covered by the filter curve continuously modulates its gain between two target values: **Base Gain** and **Target Gain**.

* **`Threshold`**: The trigger level for dynamic action per bin.
    * When the side-chain bin level crosses above the **Threshold**, the main-chain bin gain transitions from **Base Gain** toward **Target Gain** at a rate determined by **Attack**.
    * When the side-chain bin level falls below the **Threshold**, the main-chain bin gain recovers back toward **Base Gain** at a rate determined by **Release**.
* **`Knee`**: Controls the transition curvature around the threshold.
    * A **hard knee** (low value) acts strictly: gain modulation begins only after the side-chain bin level crosses the threshold.
    * A **soft knee** (high value) creates a gradual curve, smoothly transitioning toward the target gain as the side-chain bin level approaches the threshold for transparent, unobtrusive spectral shaping.

> **Note**: Because processing occurs independently per FFT bin, parameters like **Threshold** and **Knee** operate on individual bin levels rather than the full-band signal envelope found in conventional dynamic processors.

#### Dynamic Mode

You can change how the threshold is calculated by selecting different dynamic modes:

- **`Absolute`**: Dynamic processing uses a static threshold.
- **`Band`**: Dynamic processing uses a dynamic threshold related to band side-chain loudness.
- **`Relative`**: Dynamic processing uses a dynamic threshold related to total side-chain loudness.

#### Spectrum Processing

In addition to the per-band parameters, you can adjust the following parameters that affect the overall side-chain analysis to further customize dynamic behavior:

- **Smooth Type**: Choose the spectrum processing side-chain smooth type.
- **Smooth Value**: Control the spectrum processing side-chain smooth value. A higher value makes the dynamic processing smoother on the frequency domain.
- **`Tilt`**: Control the spectrum processing side-chain tilt slope.
- **`Attack Skew`**: Control the spectrum processing side-chain attack skew. A higher skew makes the attack faster at high frequency and slower at low frequency.
- **`Release Skew`**: Control the spectrum processing side-chain release skew. A higher skew makes the release faster at high frequency and slower at low frequency.
- **`Gate`**: Control the spectrum gate of relative loudness. Under `Band` mode, if band side-chain loudness is smaller than `Gate`, dynamic will NOT be triggered. Under `Relative` mode, if total side-chain loudness is smaller than `Gate`, dynamic will NOT be triggered.