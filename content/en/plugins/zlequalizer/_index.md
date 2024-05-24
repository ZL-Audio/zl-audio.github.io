---
title: ZL Equalizer
description: 16-band dynamic digital equalizer
weight: 1
---

<img src="/images/zlequalizer/dark_crop.png" width="99%" />

___


## About

ZL Equalizer is an equalizer plugin with the following key features:

- **Multiple Filter Settings:** Supports 16 frequency bands, 8 filter types, 5 stereo modes, 7 variable slopes and 2 filter structures.
- **High-Quality Sound:** With 64-bit floating-point processing and de-cramping technique, outstanding performance is ensured in both low-end and high-end.
- **Adjustable Dynamics:** Adjustable threshold, attack, release, and side-chain frequency, etc.
- **Carefully Designed Interface:** Interactive spectrum graph, smart collision detection, and smooth animations.

## Installation

Visit [this link](https://github.com/ZL-Audio/ZLEqualizer/releases) and download the installer which matches your OS:

- If the file has a `.tgz` extension, it is for macOS (in VST3 & AU). You need to unzip it to get the `.pkg` installer.
- If the file has a `.exe` extension, it is for Windows (in VST3 & LV2).
- If the file has a `.zip` extension, it is for Linux (in VST3 & LV2). On Linux, you have to move the `*.vst3` file manually to the correct folder, e.g., `~/.vst3`.

Please note that all installers **have not been notarized**. You should decide whether to trust the installers from the provided link. Alternatively, you can build the plugin from the project source code.

> On macOS, the plugin requires Metal support. For some unknown reason, the plugin is not compatible with macOS earlier than macOS 11. Besides that, you may refer to [Safely open apps on your Mac](https://support.apple.com/en-us/102445) if you are confused by the alert given by your OS.
>
> On Windows, the plugin requires Direct2D support. The plugin is compatible with Windows 10 and later.
>
> On Linux, the plugin **DOES NOT HAVE** hardware acceleration, which may lead to UI freezing. The plugin is compatible with Mainstream Linux distributions.

ZL Equalizer is licensed under [GPLv3](https://www.gnu.org/licenses/gpl-3.0.en.html).

GPLv3 Section 9 *Acceptance Not Required for Having Copies*:

**You are not required to accept this License in order to receive or run a copy of the Program. Ancillary propagation of a covered work occurring solely as a consequence of using peer-to-peer transmission to receive a copy likewise does not require acceptance. However, nothing other than this License grants you permission to propagate or modify any covered work. These actions infringe copyright if you do not accept this License. Therefore, by modifying or propagating a covered work, you indicate your acceptance of this License to do so.**

## User Interface

The user interface consists of a top panel, a main panel, and a bottom panel.

### Common Components

#### Button

Click the button to switch between the "pressed" and "released" states.

#### Rotary/Horizontal/Vertical Slider

Values can be adjusted by dragging/clicking with the mouse or scrolling the mouse wheel. You can enable mouse wheel fine adjustment with Ctrl/Command.

### Top Panel

___

<p float="left">
  <img src="/images/zlequalizer/zlaudio.svg" width="44pt" />
  <img src="/images/zlequalizer/logo.svg" width="20pt" />
</p>

Double-clicking the icon toggles between light, dark, and custom colour modes.

___

#### General Setting

You can open the general setting panel by clicking `General` and close it by clicking somewhere else.

The components of this setting panel are:

___

**Filter Structure**

- Minimum Phase: [Minimum Phase Filter](#filter-structure)
- State Variable: [State Variable Filter](#filter-structure)

___

**Default Dynamic Link (Dyn Link)**

- OFF: turn off the default dynamic link (for bands of which the dynamic is enabled afterward, the dynamic link will be turned off by default)
- ON: turn on the default dynamic link (for bands of which the dynamic is enabled afterward, the dynamic link will be turned on by default)
- You can also click on the label on the left to switch options

> When the dynamic link for a band is on, adjusting the frequency or Q value of the main filter will correspondingly adjust the frequency or Q value of the side-chain band-pass filter. You can control the dynamic link of each band using the [dynamic link button](#frequency-band-drag-button).

___

#### Collision Detection Setting

You can open the collision detection setting panel by clicking `Collision` and close it by clicking somewhere else.

The components of this setting panel are:

___

**Switch (DET)**

- OFF: turn off the collision detection
- ON: turn on the collision detection
- You can also click on the label on the left to switch options

___

**Detection (Strength)**

- If you increase this parameter, the detected areas will become larger and darker

___

**Detection (Scale)**

- If you increase this parameter, the detected areas will become darker

___

> Collision detection compares the main-chain signal and the side-chain signal in real-time. 
> 
> Collision detection uses an independent spectrum graph, which is not affected by `Analyzer` settings.
> 
> When collision detection is activated, the frame rate of the `Main Panel` will decrease to reduce the rendering pressure.
> 
> Collision detection may cause interface lag.

___

#### Output Setting

You can open the output detection setting panel by clicking `Output` and close it by clicking somewhere else.

The components of this setting panel are:

___

**Switch (ALL)**

- OFF: bypass the plugin
- ON: turn on the plugin
- You can also click on the label on the left to switch options

___

**Scale**

The ratio of the actual gain over the displayed gain of all 'gain type' filters (Peak, Low Shelf, High Shelf, and Tilt Shelf) (including all [base filters and target filters](#dynamic-and-threshold-learning)).

___

**Static Gain Compensation（SGC）**

- OFF: turn off SGC
- ON: turn on SGC
- You can also click on the label on the left to switch options


> SGC estimates the amount of compensation from filters' parameters. SGC is **inaccurate**. However, it **will NOT affect the dynamic of the main-chain signal**.

___

**Auto Gain Compensation (AGC)**

- OFF: turn off AGC
- ON: turn on AGC
- You can also click on the label on the left to switch options


> AGC calculates the difference between the loudness of the main-chain signal before/after filters and applies the corresponding gain. Therefore, **AGC will affect the dynamic of the main-chain signal**.
> 
> When AGC is on, the output main-chain signal will pass through a hard clipper at 0 dB.

___

**Output Gain**

___

#### Dynamic Setting

You can open the dynamic detection setting panel by clicking `Dynamic` and close it by clicking somewhere else.

The components of this setting panel are:

___

**Lookahead**

- the delay of the [main-chain](#dynamic-and-threshold-learning) signal
- when PDC is supported (hopefully in your DAW), it can be interpreted as the lookahead time of the side-chain signal

___

**RMS**

- the length of the audio when calculating the [instantaneous loudness](#dynamic-and-threshold-learning)
- the actual attack/release will increase (significantly) will RMS increases

___

**Smooth**

- the smoothness of attack/release

___

**High Quality (HQ)**

- OFF: turn off the high-quality
- ON: turn on the high-quality
- You can also click on the label on the left to switch options


> When high-quality is on, [dynamic](#dynamic-and-threshold-learning) will adjust the filter state per sample, which smooths dynamic effects and reduces artifacts. However, high-quality will **significantly increase** the processing time of [dynamic](#dynamic-and-threshold-learning).

___

#### Analyzer Setting

You can open the analyzer setting panel by clicking `Analyzer` and close it by clicking somewhere else.

The components of this setting panel are:

___

**FFT Mode**

- `Pre`, `Post`, and `Side` represents the input main-chain signal, the output main-chain signal, and the side-chain signal
- OFF: turn off the spectrum
- ON: turn on the spectrum
- FRZ: freeze the spectrum
- You can also click on the label on the left to switch options


___


**Decay Speed**

- applies to spectrums that is on (and not frozen)

___

**Slope**

- affects the spectrum display (not the actual signal)
- 0 dB/oct: no tilting, white noise displays as a horizon line
- 3 dB/oct: pink noise displays as a horizon line
- 4.5 dB/oct: default value, which represents perceived loudness better

___

#### UI setting

Under custom colour mode, You can open the [UI setting panel](#ui-setting-panel) by clicking `UI`.

___

### Bottom Panel

The bottom panel controls the parameters of the currently selected frequency band. Components will be introduced in the order from left to right, and from top to bottom.

#### Left Panel
___
<p float="left">
  <img src="/images/zlequalizer/fad-powerswitch.svg" width="20pt"/>
</p>

- Press: [bypass](#states-of-bands) the selected band。
- Release: [turn on](#states-of-bands) the selected band。

___

<p float="left">
  <img src="/images/zlequalizer/fad-solo.svg" width="20pt"/>
</p>

- Press: solo the audio affected by the selected frequency band.
- Release: stop the solo.

___

**Filter Type**


There are a total of eight filter types: Peak, Low Shelf, Low Pass, High Shelf, High Pass, Notch, Band Pass, and Tilt Shelf.

___

**Slope**

There are seven slopes: 6 dB/oct, 12 dB/oct, 24 dB/oct, 36 dB/oct, 48 dB/oct, 72 dB/oct and 96 dB/oct。
A higher slope will make the filter's response curve change more steeply. Peak, Notch, and Band Pass don't support 6 dB/oct. 

___

**Stereo Modes**

There are five stereo modes: Stereo, Left, Right, Mid, and Side.

___

**Frequency (Freq)**

___

**Gain**

When the [dynamic](#dynamic-and-threshold-learning) feature is enabled, you can adjust the gain of the base filter by dragging/clicking with the left mouse button. To adjust the gain of the target filter, use the right mouse button for dragging/clicking. To adjust the gain of the base filter and the target filter, use the mousewheel.

___

**Bandwidth (Q)**

When the [dynamic](#dynamic-and-threshold-learning) feature is enabled, you can adjust the Q value of the base filter by dragging/clicking with the left mouse button. For adjusting the Q value of the target filter, use the right mouse button for dragging/clicking. To adjust the Q values of the base filter and the target filter, use the mouse-wheel.

___

**Band Selection**


You can select the band by using the left arrows and right arrows.

___

<p float="left">
  <img src="/images/zlequalizer/fad-modsine.svg" width="20pt"/>
</p>

- Press: turn on the [dynamic](#dynamic-and-threshold-learning) effect for the selected frequency band.
- Release: turn off the [dynamic](#dynamic-and-threshold-learning) effect for the selected frequency band.

___

<p float="left">
  <img src="/images/zlequalizer/fad-preset-a.svg" width="20pt"/>
</p>

- Press: enables [dynamic threshold learning](#dynamic-and-threshold-learning) for the selected frequency band.
- Release: disables [dynamic threshold learning](#dynamic-and-threshold-learning) for the selected frequency band and applies the learned threshold.

___

<p float="left">
  <img src="/images/zlequalizer/xmark.svg" width="16pt"/>
</p>

- Click: [turns off](#states-of-bands) the selected frequency band and resets all parameters to default values.

#### Right Panel

___
<p float="left">
  <img src="/images/zlequalizer/fad-powerswitch.svg" width="20pt"/>
</p>

- Press: bypass the [dynamic](#dynamic-and-threshold-learning) effect for the selected frequency band.
- Release: cancel the bypass.

___

<p float="left">
  <img src="/images/zlequalizer/fad-solo.svg" width="20pt"/>
</p>

- Press: solo the side-chain audio of the selected band。
- Release: stop the solo。

___

<p float="left">
  <img src="/images/zlequalizer/right-to-bracket-solid.svg" width="20pt"/>
</p>

- Press: set the [dynamic](#dynamic-and-threshold-learning) threshold to the relative mode.
- Release: set the [dynamic](#dynamic-and-threshold-learning) threshold to the absolute mode.

___

<p float="left">
  <img src="/images/zlequalizer/fad-side.svg" width="20pt"/>
</p>

- Press: use external side-chain (this setting applies to all frequency bands).
- Release: use internal side-chain (this setting applies to all frequency bands).

___

**Threshold**

___

**Knee Width (Knee)**

The adjusted knee width value is within the range of 0 to 1, and the actual knee width is this value multiplied by 60 dB.

___

**Attack**

___

**Release**

___

**Side-chain Bandpass Frequency (Freq)**

Adjust the center frequency of the bandpass filter applied to the side-chain audio. When the [dynamic](#dynamic-and-threshold-learning) effect is turned on, this frequency will be automatically adjusted to fit the audio affected by the main-chain filter.

___

**Side-chain Bandpass Bandwidth (Q)**

Adjust the Q value of the bandpass filter applied to the side-chain audio. When the [dynamic](#dynamic-and-threshold-learning) effect is turned on, this Q value will be automatically adjusted to fit the audio affected by the main-chain filter.

___

### Main Panel

The main panel consists of grid lines, a spectrum graph, a single frequency band response curve, an overall response curve, and a dB scale on the right side.

#### Double-Click to Add a Frequency Band

If there is at least one frequency band in the [off](#states-of-bands) state when you double-click the spectrum, a frequency band will be turned on with the corresponding frequency/gain:

- Frequency < 20Hz: Adds a High Pass filter.
- 20Hz <= Frequency < 50Hz: Adds a Low Shelf filter.
- 50Hz <= Frequency < 5000Hz: Adds a Peak filter.
- 5000Hz <= Frequency < 15000Hz: Adds a High Shelf filter.
- 15000Hz <= Frequency: Adds a Low Pass filter.

#### Frequency Band Drag Button

When a frequency band is not in the [off](#states-of-bands) state, a draggable button appears at the corresponding frequency/gain position. You can adjust the frequency and gain by dragging the button, and adjust the Q value with your mouse wheel. You can fix the freq/gain by pressing Ctrl/Command and dragging with left/right mouse button.

When you select the frequency band, the button will be highlighted, and an additional control window will appear. Through this window, you can quickly bypass/solo the selected band and adjust the filter type.


Additionally, if the dynamic function of this frequency band is not disabled:

- A draggable diamond-shaped button will appear at the corresponding position of the target filter, allowing you to adjust the frequency and gain of the target filter by dragging this button. After selecting it, you can adjust the Q value of the target filter by scrolling the mouse wheel.
- A draggable square-shaped button will appear at the corresponding position of the side-chain bandpass filter, enabling you to adjust the frequency of the bandpass filter by dragging this button. After selecting it, you can adjust the Q value of the bandpass filter by scrolling the mouse wheel.
- A dynamic link button will appear above the side-chain band-pass filter. You can enable/disable the dynamic link of that band by clicking this button.


#### Multi-band Selection

You can use your mouse to drag and select multiple frequency bands simultaneously on the spectrum graph. After that, you can click on the spectrum graph (outside the button area) to cancel the selection.

When multiple frequency bands are selected, adjusting the frequency, gain, or bandwidth of one frequency band will also affect the corresponding parameters of the other selected frequency bands.

#### Decibel Scale

You can choose the maximum decibel for the decibel scale. After that, the maximum gain of filters (when you drag buttons) is limited to that range.

### UI Setting Panel

The UI setting panel controls spectrum colours, slider operations, etc. Components will be introduced in the order from top to bottom.

___

The following settings only apply to the custom colour mode:

You can adjust the color by clicking on the left color block and change the transparency by dragging the right slider.

**Main-Chain Input Signal Spectrum Colour (Pre Colour)**

**Main-Chain Output Signal Spectrum Colour (Post Colour)**

**Side-Chain Signal Spectrum Colour (Side Colour)**

**Grid Lines Colour (Grid Colour)**

___

The following settings apply to all three colour modes:

**Mouse-Wheel Sensitivity**

- Rough: mouse-wheel sensitivity when Ctrl/Command is not pressed
- Fine: mouse-wheel sensitivity when Ctrl/Command is pressed

**Rotary Slider Style**

- Circular: A rotary control that you move by dragging the mouse in a circular motion, like a knob
- Horizontal: A rotary control that you move by dragging the mouse left-to-right
- Vertical: A rotary control that you move by dragging the mouse up-and-down
- Horiz + Vert: A rotary control that you move by dragging the mouse up-and-down or left-to-right
- Distance: the relative distance that the mouse has to move to drag the slider across the full extent of its range. It does not apply to the Circular style.

**Refresh Rate**

- The refresh rate of the response curve(s). The higher this value, the smoother the response curve(s) when dragging the buttons or enabling dynamic, but the higher the CPU and GPU load. When the CPU or GPU load is too high, the response curve may get distorted when dragging the button.

**FFT Setting**

- Tilt: extra tilting slope of the FFT
- Speed: extra decay speed of the FFT

**Curve Thickness**

- Single: the thickness of the response curves of single bands
- Sum: the thickness of the overall response curves

___

<p float="left">
  <img src="/images/zlequalizer/save-line.svg" width="18pt"/>
</p>

- Save the current setting.

___

<p float="left">
  <img src="/images/zlequalizer/loop-left-line.svg" width="18pt"/>
</p>

- Discard all unsaved settings and load the previously saved settings.

___

<p float="left">
  <img src="/images/zlequalizer/xmark.svg" width="16pt"/>
</p>

- Discard all unsaved settings and close the UI setting panel.

___


## Appendix

### Automation

You can automate frequency, gain, Q value, dynamic threshold, knee width, attack, and release parameters. Attention:

> The modulation speed of automation is not less than 1000 times per second, but much slower than once per sample.
>
> When the plugin window is open, filter parameter modulation may cause interface lag.
>
> The plugin does not smooth modulation internally. Therefore, extremely fast modulation and modulation of other parameters may cause noise.
>
> When you modulate multiple filters, DO NOT select them on the spectrum.

### States of Bands

The frequency band can be in one of the following states:

- Off: By default, all frequency bands are closed, not affecting the spectrum graph, the overall response curve, or the audio signal.
- Bypassed: The response curve is displayed on the spectrum graph without affecting the overall response curve.
- On: The response curve is displayed on the spectrum graph and affects both the overall response curve and the audio signal.

### Dynamic and Threshold Learning

The dynamic effect calculates the instantaneous loudness of the side-chain (filtered by the bandpass filter) at a constant rate (not less than 1000 times per second) and adjusts the filter state as follows:

- When side-chain instantaneous loudness <= (threshold - knee width), the filter is in the base filter state.
- When side-chain instantaneous loudness >= (threshold + knee width), the filter is in the target filter state.
- When (threshold - knee width) < side-chain instantaneous loudness < (threshold + knee width), the filter parameters will be a mix of the baseline filter parameters and the target filter parameters with a proportion. And the filter state will be re-calculated. The closer the side-chain instantaneous loudness is to (threshold - knee width), the closer the filter state is to the baseline filter, and vice versa.

When threshold learning is on, the plugin collects the side-chain's instantaneous loudness. When threshold learning is turned off, the plugin sets the threshold to the median of the side-chain instantaneous loudness values and sets the knee width to half of the difference between the 95th and 5th percentiles.

The threshold calculation is in the absolute mode by default. When the relative mode is activated, the dynamic effect will calculate the difference between the instantaneous loudness of the side-chain (filtered by the bandpass filter) and the overall instantaneous loudness of the side-chain. The threshold learning will work in the same mode.

### Filter Structure

- Minimum Phase: The most common filter structure, also known as analog or zero delay. Low-order minimum phase filters (6 dB/oct and 12 dB/oct) cause small phase shifts. Therefore, when the signal processed by low-order minimum phase filters is mixed with the original or highly correlated signals, phase cancellation issues are almost inaudible. However, when frequency and gain are rapidly modulated, this type of filter is more likely to become unstable and produce audible artifacts.
- State Variable: This type of filter is more stable when frequency and gain are rapidly modulated. However, the phase shift caused by this type of filter is significant. It is not recommended to mix the processed signal with the original or highly correlated signals. What's more, this type of filter will also affect the phase when it is bypassed.


## Acknowledgment

Thank [JUCE](https://github.com/juce-framework/JUCE) framework and [JUCE Forum](https://forum.juce.com/)。

Thank Martin Vicanek and Nigel Redmon for sharing the filter parameter calculation method and filter cascade method.

Thank all plugin users for their support, feedback, and suggestions.

Feel free to leave feedback or suggestions at [here](https://github.com/ZL-Audio/ZLEqualizer/discussions).

## Disclaimer

This disclaimer comes from section 15 and section 16 of [GPLv3 License](https://www.gnu.org/licenses/gpl-3.0.en.html).

**THERE IS NO WARRANTY FOR THE PROGRAM, TO THE EXTENT PERMITTED BY APPLICABLE LAW. EXCEPT WHEN OTHERWISE STATED IN WRITING THE COPYRIGHT HOLDERS AND/OR OTHER PARTIES PROVIDE THE PROGRAM “AS IS” WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. THE ENTIRE RISK AS TO THE QUALITY AND PERFORMANCE OF THE PROGRAM IS WITH YOU. SHOULD THE PROGRAM PROVE DEFECTIVE, YOU ASSUME THE COST OF ALL NECESSARY SERVICING, REPAIR OR CORRECTION.**

**IN NO EVENT UNLESS REQUIRED BY APPLICABLE LAW OR AGREED TO IN WRITING WILL ANY COPYRIGHT HOLDER, OR ANY OTHER PARTY WHO MODIFIES AND/OR CONVEYS THE PROGRAM AS PERMITTED ABOVE, BE LIABLE TO YOU FOR DAMAGES, INCLUDING ANY GENERAL, SPECIAL, INCIDENTAL OR CONSEQUENTIAL DAMAGES ARISING OUT OF THE USE OR INABILITY TO USE THE PROGRAM (INCLUDING BUT NOT LIMITED TO LOSS OF DATA OR DATA BEING RENDERED INACCURATE OR LOSSES SUSTAINED BY YOU OR THIRD PARTIES OR A FAILURE OF THE PROGRAM TO OPERATE WITH ANY OTHER PROGRAMS), EVEN IF SUCH HOLDER OR OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.**