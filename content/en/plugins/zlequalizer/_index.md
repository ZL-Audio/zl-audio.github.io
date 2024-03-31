---
title: ZL Equalizer
description: 16-band minimum-phase dynamic digital equalizer
weight: 1
---

<img src="/images/zlequalizer/dark_crop.png" width="99%" />

___


## About

ZL Equalizer is a minimum-phase equalizer plugin with the following key features:

- **Multiple Filter Settings:** Supports 16 frequency bands, 8 filter types, 5 stereo modes, and 7 variable slopes.
- **High-Quality Sound:** With 64-bit floating-point processing and de-cramping technique, outstanding performance is ensured in both low-end and high-end.
- **Adjustable Dynamics:** Adjustable threshold, attack, release, and side-chain frequency, etc.
- **Carefully Designed Interface:** Interactive spectrum graph, smart collision detection, and smooth animations.

## Installation

Visit [this link](https://github.com/ZL-Audio/ZLEqualizer/releases) and download the installer which matches your OS:

- If the file has a `.dmg` extension, it is for macOS (in VST3 & AU).
- If the file has a `.exe` extension, it is for Windows (in VST3).
- If the file has a `.zip` extension, it is for Linux (in VST3). On Linux, you have to move the `*.vst3` file manually to the correct folder, e.g., `~/.vst3`.

Please note that all installers **have not been notarized**. You should decide whether to trust the installers from the provided link. Alternatively, you can build the plugin from the project source code.

> On macOS, the plugin requires Metal support.
>
> On Windows, the plugin requires Direct2D support.
>
> On Linux, the plugin **DOES NOT HAVE** hardware acceleration, which may lead to UI freezing.

ZL Equalizer is licensed under [GPLv3](https://www.gnu.org/licenses/gpl-3.0.en.html).

GPLv3 Section 9 *Acceptance Not Required for Having Copies*:

**You are not required to accept this License in order to receive or run a copy of the Program. Ancillary propagation of a covered work occurring solely as a consequence of using peer-to-peer transmission to receive a copy likewise does not require acceptance. However, nothing other than this License grants you permission to propagate or modify any covered work. These actions infringe copyright if you do not accept this License. Therefore, by modifying or propagating a covered work, you indicate your acceptance of this License to do so.**

## User Interface

The user interface consists of a top panel, a main panel, and a bottom panel.

### Common Components

#### Button

Click the button to switch between the "pressed" and "released" states.

#### Rotary/Horizontal/Vertical Slider

Values can be adjusted by dragging/clicking with the mouse or scrolling the mouse wheel.

### Top Panel

___

<p float="left">
  <img src="/images/zlequalizer/zlaudio.svg" width="5.5%" />
  <img src="/images/zlequalizer/logo.svg" width="2.5%" />
</p>

Double-clicking the icon toggles between dark and light color modes.

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


**Auto Gain Compensation (AGC)**

- OFF: turn off AGC
- ON: turn on AGC
- You can also click on the label on the left to switch options


> AGC calculates the difference between the loudness of the main-chain signal before/after filters and applies corresponding gain. Therefore, **AGC will affect the dynamic of the main-chain signal**.
> 
> When AGC is on, output main-chain singal will pass through a hard clipper at 0 dB.

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


### Bottom Panel

The bottom panel controls the parameters of the currently selected frequency band. Components will be introduced in the order from left to right, and from top to bottom.

#### Left Panel
___
<p float="left">
  <img src="/images/zlequalizer/fad-powerswitch.svg" width="2.5%"/>
</p>

- Press: [bypass](#states-of-bands) the selected band。
- Release: [turn on](#states-of-bands) the selected band。

___

<p float="left">
  <img src="/images/zlequalizer/fad-solo.svg" width="2.5%"/>
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

When the [dynamic](#dynamic-and-threshold-learning) feature is enabled, you can adjust the gain of the base filter by dragging/clicking with the left mouse button. To adjust the gain of the target filter, use the right mouse button for dragging/clicking.

___

**Bandwidth (Q)**

When the [dynamic](#dynamic-and-threshold-learning) feature is enabled, you can adjust the Q value of the base filter by dragging/clicking with the left mouse button. For adjusting the Q value of the target filter, use the right mouse button for dragging/clicking.

___

**Band Selection**


You can select the band by using the left arrows and right arrows.

___

<p float="left">
  <img src="/images/zlequalizer/fad-modsine.svg" width="2.5%"/>
</p>

- Press: turn on the [dynamic](#dynamic-and-threshold-learning) effect for the selected frequency band.
- Release: turn off the [dynamic](#dynamic-and-threshold-learning) effect for the selected frequency band.

___

<p float="left">
  <img src="/images/zlequalizer/fad-preset-a.svg" width="2.5%"/>
</p>

- Press: enables [dynamic threshold learning](#dynamic-and-threshold-learning) for the selected frequency band.
- Release: disables [dynamic threshold learning](#dynamic-and-threshold-learning) for the selected frequency band and applies the learned threshold.

___

<p float="left">
  <img src="/images/zlequalizer/xmark.svg" width="2%"/>
</p>

- Click: [turns off](#states-of-bands) the selected frequency band and resets all parameters to default values.

#### Right Panel

___
<p float="left">
  <img src="/images/zlequalizer/fad-powerswitch.svg" width="2.5%"/>
</p>

- Press: bypass the [dynamic](#dynamic-and-threshold-learning) effect for the selected frequency band.
- Release: cancel the bypass.

___

<p float="left">
  <img src="/images/zlequalizer/fad-solo.svg" width="2.5%"/>
</p>

- Press: solo the side-chain audio of the selected band。
- Release: stop the solo。

___

<p float="left">
  <img src="/images/zlequalizer/right-to-bracket-solid.svg" width="2.5%"/>
</p>

- Press: set the [dynamic](#dynamic-and-threshold-learning) threshold to the relative mode.
- Release: set the [dynamic](#dynamic-and-threshold-learning) threshold to the absolute mode.

___

<p float="left">
  <img src="/images/zlequalizer/fad-side.svg" width="2.5%"/>
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


#### Multi-band Selection

You can use your mouse to drag and select multiple frequency bands simultaneously on the spectrum graph. After that, you can click on the spectrum graph (outside the button area) to cancel the selection.

When multiple frequency bands are selected, adjusting the frequency, gain, or bandwidth of one frequency band will also affect the corresponding parameters of the other selected frequency bands.

### Decibel Scale

You can choose the maximum decibel for the decibel scale. After that, the maximum gain of filters (when you drag buttons) is limited to that range.

## Appendix

### Automation

**DO NOT activate automation on any parameters** (except bypass, dynamic bypass, and output gain). Automation may make the plugin crash.

### States of Bands

The frequency band can be in one of the following states:

- Off: By default, all frequency bands are closed, not affecting the spectrum graph, the overall response curve, or the audio signal.
- Bypassed: The response curve is displayed on the spectrum graph without affecting the overall response curve or the audio signal.
- On: The response curve is displayed on the spectrum graph and affects both the overall response curve and the audio signal.

### Dynamic and Threshold Learning

The dynamic effect calculates the instantaneous loudness of the side-chain (filtered by the bandpass filter) at a constant rate (not less than 1000 times per second) and adjusts the filter state as follows:

- When side-chain instantaneous loudness <= (threshold - knee width), the filter is in the base filter state.
- When side-chain instantaneous loudness >= (threshold + knee width), the filter is in the target filter state.
- When (threshold - knee width) < side-chain instantaneous loudness < (threshold + knee width), the filter parameters will be a mix of the baseline filter parameters and the target filter parameters with a proportion. And the filter state will be re-calculated. The closer the side-chain instantaneous loudness is to (threshold - knee width), the closer the filter state is to the baseline filter, and vice versa.

When threshold learning is on, the plugin collects the side-chain's instantaneous loudness. When threshold learning is turned off, the plugin sets the threshold to the median of the side-chain instantaneous loudness values and sets the knee width to half of the difference between the 95th and 5th percentiles.

The threshold calculation is in the absolute mode by default. When the relative mode is activated, the dynamic effect will calculate the difference between the instantaneous loudness of the side-chain (filtered by the bandpass filter) and the overall instantaneous loudness of the side-chain. The threshold learning will work in the same mode.


## Acknowledgment

Thank [JUCE](https://github.com/juce-framework/JUCE) framework and [JUCE Forum](https://forum.juce.com/)。

Thank Martin Vicanek and Nigel Redmon for sharing the filter parameter calculation method and filter cascade method.

Thank all plugin users for their support, feedback, and suggestions.

Feel free to leave feedback or suggestions at [here](https://github.com/ZL-Audio/ZLEqualizer/discussions).

## Disclaimer

This disclaimer comes from section 15 and section 16 of [GPLv3 License](https://www.gnu.org/licenses/gpl-3.0.en.html).

**THERE IS NO WARRANTY FOR THE PROGRAM, TO THE EXTENT PERMITTED BY APPLICABLE LAW. EXCEPT WHEN OTHERWISE STATED IN WRITING THE COPYRIGHT HOLDERS AND/OR OTHER PARTIES PROVIDE THE PROGRAM “AS IS” WITHOUT WARRANTY OF ANY KIND, EITHER EXPRESSED OR IMPLIED, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE. THE ENTIRE RISK AS TO THE QUALITY AND PERFORMANCE OF THE PROGRAM IS WITH YOU. SHOULD THE PROGRAM PROVE DEFECTIVE, YOU ASSUME THE COST OF ALL NECESSARY SERVICING, REPAIR OR CORRECTION.**

**IN NO EVENT UNLESS REQUIRED BY APPLICABLE LAW OR AGREED TO IN WRITING WILL ANY COPYRIGHT HOLDER, OR ANY OTHER PARTY WHO MODIFIES AND/OR CONVEYS THE PROGRAM AS PERMITTED ABOVE, BE LIABLE TO YOU FOR DAMAGES, INCLUDING ANY GENERAL, SPECIAL, INCIDENTAL OR CONSEQUENTIAL DAMAGES ARISING OUT OF THE USE OR INABILITY TO USE THE PROGRAM (INCLUDING BUT NOT LIMITED TO LOSS OF DATA OR DATA BEING RENDERED INACCURATE OR LOSSES SUSTAINED BY YOU OR THIRD PARTIES OR A FAILURE OF THE PROGRAM TO OPERATE WITH ANY OTHER PROGRAMS), EVEN IF SUCH HOLDER OR OTHER PARTY HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGES.**