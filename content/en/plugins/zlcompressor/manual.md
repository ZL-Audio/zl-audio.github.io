---
title: Manual
description: How to use ZL Compressor
weight: 2
---

<img src="/images/zlcompressor/dark_crop.jpg" style="width:750px; max-width: 100%; height: auto" />

___

## About

ZL Compressor is a dynamic range compressor with the following key features:

- **Four Versatile Compression Styles:** Choose from four distinct modes. **Clean** offers a transparent, modern VCA design. **Classic** delivers the character of a feedback FET compressor. **Optical** provides smooth, warm leveling inspired by light-sensitive circuits. **Vocal** is specifically tailored to enhance and control vocal tracks.
- **Advanced Side-chain Control:** Utilize the full **8-band Equalizer** to make the compressor react to specific frequencies. Fine-tune the stereo image with an adjustable **stereo link**. Catch the fastest transients with predictive **lookahead**.
- **Pristine Audio Performance:** Eliminate aliasing artifacts with up to **8x oversampling**, ensuring pure sound even at extreme settings. The CPU-efficient algorithm lets you run multiple instances without overloading your project.
- **Intuitive Visual Interface:** Instantly see your audio's dynamics on the large **Peak/RMS analyzer** and adjust the side-chain directly on the **interactive spectrum display**. This clear visual feedback helps you make better mixing decisions, faster.

## Top Panel

___

<p float="left">
  <img src="/images/zlcompressor/zlaudio.svg" width="44pt" />
  <img src="/images/zlcompressor/logo.svg" width="20pt" />
</p>

You can open the [UI setting panel](#ui-setting-panel) by double-clicking the logo.

___

**Oversample**

There are four over-sampling options:

- `OFF`: No over-sampling. No extra latency.
- `2x`: 2 times over-sampling. 64 sample latency (~ 1.3 ms under 48kHz)
- `4x`: 4 times over-sampling. 72 sample latency (~ 1.5 ms under 48kHz)
- `8x`: 8 times over-sampling. 76 sample latency (~ 1.6 ms under 48kHz)

You may hear clicks/pops when you change this parameter. Please **DO NOT** automate this parameter.

___

**Lookahead**

Controls the delay of the main-chain signal (in millisecond). If PDC is supported (in almost all DAWs), it can be interpreted as the lookahead time of the side-chain signal.

You may hear clicks/pops when you change this parameter. Please **DO NOT** automate this parameter.

___

<p float="left">
  <img src="/images/zlcompressor/change.svg" width="20pt"/>
</p>

- Press: output delta signal (the difference between the uncompressed main signal and the compressed main signal)

___

<p float="left">
  <img src="/images/zlcompressor/mode_off_on.svg" width="20pt"/>
</p>

- Release: bypass plugin

___


## Left Side Panel

___

<p float="left">
  <img src="/images/zlcompressor/rms_analyzer.svg" width="20pt"/>
</p>

- Press: open the [cumulative analyzer](#cumulative-analyzer)
- Release: close the [cumulative analyzer](#cumulative-analyzer)

___

<p float="left">
  <img src="/images/zlcompressor/computer.svg" width="20pt"/>
</p>

- Press: open the [computer display](#computer-display)
- Release: close the [computer display](#computer-display)

___

<p float="left">
  <img src="/images/zlcompressor/equalizer.svg" width="20pt"/>
</p>

- Press: open the side-chain equalizer
- Release: close the side-chain equalizer

___

<p float="left">
  <img src="/images/zlcompressor/link.svg" width="20pt"/>
</p>

- Press: open the side-chain panel
- Release: close the side-chain panel

___

## Center Panel

The center panel consists of a magnitude analyzer, a cumulative RMS analyzer and a computer display.

### Magnitude Analyzer

The magnitude analyzer occupies the whole center panel. It shows three curves:

- the pre curve: magnitude of the input main-chain signal
- the post curve: magnitude of the output main-chain signal
- the reduction curve: magnitude of the gain reduction

In the bottom-left corner, you can select the analyzer's time window length (`6 s`, `9 s`, `12 s`, and `18 s`). To ensure visual fluidity, the `6 s` and `9 s` settings perform best with a refresh rate of 60 Hz or higher.

In the bottom-right corner, you can select the magnitude type (`Peak` and `RMS`) and the minimum decibel value of the analyzer (`-9`, `-18`, `-36`, `-54`, and `-72`).

When you put the mouse above the magnitude analyzer, you can adjust the threshold via mouse wheel and adjust the ratio via Ctrl/Command + mouse wheel.
### Cumulative Analyzer

The cumulative analyzer on the left shows the cumulative RMS values of the input main-chain signal and the output main-chain signal. You can double-click to reset this analyzer.

### Computer Display

The computer display shows the curve that is used to calculate the gain reduction value.

## Bottom Panel

___

**Knee**

Controls the knee width of the gain reduction computer. A wider knee makes the transition between the uncompressed state and the compressed state smoother.

___

**Curve**

Controls the non-linearity behavior of compressed state.

___

**Threshold**

___

**Ratio**

___

**Compression Style**

- `Clean`: feedforward design with exponentially decayed attack/release stages, which offers transparent, precise dynamic control.
- `Classic`: feedback design with exponentially decayed attack/release stages, which offers smooth, glued dynamic control
- `Optical`: feedforward design with linear decayed attack/release, which offers smooth, precise dynamic control
- `Vocal`: feedback design with linear decayed attack/release, which offers gentle, buttery dynamic control

___

**Pump**

Controls the behavior of the attack stage. Larger `Pump` makes the attack more aggressive, which introduces the pumping effect.

___

**Smooth**

Controls the behavior of the release stage.  Larger `Smooth` makes the start of the release stage slower.

___

**Attack**

___

**Release**

___

<p float="left">
  <img src="/images/zlcompressor/rms.svg" width="20pt"/>
</p>

- Press: enable RMS compression
- Release: disable RMS compression

RMS compression reacts to a short-term loudness and lets peaks go through, which helps to achieve a more transparent and natural-sounding compression.

___

<p float="left">
  <img src="/images/zlcompressor/arrow_menu_open.svg" width="20pt"/>
</p>

- Press: open [RMS Panel](#rms-panel)
- Release: close [RMS Panel](#rms-panel)

___

**Range**

Controls the gain reduction range. The actual value is affected by the **Wet**.

___

**Hold**

Controls the minimum amount of time where gain reduction is prevented from decreasing. During this time, compression can react to new peaks but cannot release.

___

**Makeup**

Controls the makeup gain that is applied after the compression. The actual value is affected by the **Wet**.

___

<p float="left">
  <img src="/images/zlcompressor/learn.svg" width="20pt"/>
</p>

- Press: when you press it, it starts to measure the integrated loudness of the input signal and the output signal
- Release: when you release it, it updates the **Makeup** to the difference between two loudness values
- during the learning process, you cannot modify **Makeup** and **Wet**

___

**Wet**

Controls the percent of wet signal.

___
## Side-chain Panel

___

<p float="left">
  <img src="/images/zlcompressor/midside.svg" width="20pt"/>
</p>

Set the stereo mode to Mid/Side. Mid/Side is linked with each other.

For example, if the reduction of Mid is -5 dB, the reduction of Side is -1 dB, and the link is 20%, the final results are:
- Mid reduction: (-5) * 0.8 + (-1) * 0.2 = -4.2 dB
- Side reduction: (-1) * 0.8 + (-5) * 0.2 = -1.8 dB


<p float="left">
  <img src="/images/zlcompressor/leftright.svg" width="20pt"/>
</p>

Set the stereo mode to Left/Right. Left/Right is linked with each other.

<p float="left">
  <img src="/images/zlcompressor/midside_max.svg" width="20pt"/>
</p>

Set the stereo mode to Mid/Side Max. Mid/Side is linked with the maximum of Mid/Side. As a result, the larger reduction won't decrease.

For example, if the reduction of Mid is -5 dB, the reduction of Side is -1 dB, and the link is 20%, the final results are:
- Mid reduction: -5 dB
- Side reduction: (-1) * 0.8 + (-5) * 0.2 = -1.8 dB

<p float="left">
  <img src="/images/zlcompressor/leftright_max.svg" width="20pt"/>
</p>

Set the stereo mode to Left/Right Max. Left/Right is linked with the maximum of Left/Right.

___

<p float="left">
  <img src="/images/zlcompressor/shuffle.svg" width="20pt"/>
</p>

- Press: swap the side-chain stereo mode
	- if the stereo mode is Left/Right, the side-chain is from Right/Left
	- if the stereo mode is Mid/Side, the side-chain is from Side/Mid

___

**Link**

Controls the link between two stereo channels.

___

**Stereo Wet**

Controls the percent of wet signal for each stereo channel. The actual value is affected by the **Wet**.

___

**Gain**

Controls the gain of the side-chain signal.

___

<p float="left">
  <img src="/images/zlcompressor/external-side.svg" width="20pt"/>
</p>

- Press: use external side-chain signal
- Release: use internal side-chain signal

___

<p float="left">
  <img src="/images/zlcompressor/headphones.svg" width="20pt"/>
</p>

- Press: listen to the side-chain signal

___
## Side-chain Equalizer

The side-chain equalizer allows you to visually equalize the side-chain signal. It features a spectrum graph where you can add and manipulate filter bands.

**Add a Band**

If there is at least one frequency band in the off state when you double-click the spectrum, a frequency band will be turned on with the corresponding frequency/gain:

- Frequency < 20Hz: Adds a High Pass filter.
- 20Hz <= Frequency < 50Hz: Adds a Low Shelf filter.
- 50Hz <= Frequency < 5000Hz: Adds a Peak filter.
- 5000Hz <= Frequency < 15000Hz: Adds a High Shelf filter.
- 15000Hz <= Frequency: Adds a Low Pass filter.

**Drag a Band**

When a frequency band is not in the off state, a draggable button appears at the corresponding frequency/gain position. You can adjust the frequency and gain by dragging the button, adjust the Q value with mouse wheel, and adjust the slope with Ctrl/Command + mouse wheel.

When you select the frequency band via clicking the button:

- an additional control window will appear near the button, through which you can quickly bypass/close the selected band, choose the filter type, and adjust the filter slope.
- the frequency/gain values will appear at the top-left corner, through which you can view/edit the frequency/gain values of the selected band

**Right Click Menu**

When you right-click on a frequency band, the right-click menu will appear, through which you can invert the gain of the current band, or copy/paste filters (even across plugins).

## RMS Panel

___

**RMS Length**

Controls the RMS window length (in millisecond).

___

**RMS Speed**

Controls the relative attack/release speed of RMS compression.

___

**RMS Mix**

Controls the mix percent of RMS compression.

___


## UI Setting Panel

The UI setting panel controls analyzer colours, slider operations, etc. Components will be introduced in the order from top to bottom.

#### Colour

You can adjust the colour by clicking on the left colour block and change the transparency by dragging the right slider.

**Text Colour**

**Background Colour**

For better accessibility, please set Text/Background to colours with high contrast.

**Shadow Colour**

**Glow Colour**

**Pre Colour**

**Post Colour**

**Reduction Colour**

**Computer Colour**

**Grid Colour**

**Colour Map 1**

- The colour map of the curves of each single filter.

**Colour Map 2**

- The colour map of the curves of Stereo/Left/Right/Mid/Side.

**Import Colours**

- import colour settings (`.xml` file)

**Export Colours**

- export colour settings (`.xml` file)

#### Control

**Wheel Sensitivity**

- Rough: mouse-wheel sensitivity when Shift is not pressed
- Fine: mouse-wheel sensitivity when Shift is pressed
- Reverse: whether to reverse the direction of mouse-wheel when Shift is pressed

**Drag Sensitivity**

- Rough: mouse-drag sensitivity when Shift is not pressed
- Fine: mouse-drag sensitivity when Shift is pressed

**Rotary Slider Style**

- `Circular`: A rotary control that you move by dragging the mouse in a circular motion, like a knob
- `Horizontal`: A rotary control that you move by dragging the mouse left-to-right
- `Vertical`: A rotary control that you move by dragging the mouse up-and-down
- `Horiz + Vert`: A rotary control that you move by dragging the mouse up-and-down or left-to-right
- Distance: the relative distance that the mouse has to move to drag the slider across the full extent of its range. It does not apply to the Circular style.

**Slider Double Click**

- `Return Default`: when you double-click the slider, it returns to the default value; when you double-click the slider with Ctrl/Command, it opens the value editor.
- `Open Editor`: when you double-click the slider, it opens the value editor; when you double-click the slider with Ctrl/Command, it returns to the default value.

**Import Controls**

- import control settings (`.xml` file)

**Export Controls**

- export control settings (`.xml` file)

#### Other

**Refresh Rate**

For better analyzer display, set this as 1/n of your monitor refresh rate. For example,
- If your monitor refresh rate is 120 Hz, set it to 120 Hz, 60 Hz (1/2), or 30 (1/4) Hz. DO NOT set it to 90 Hz.
- If your monitor refresh rate is 90 Hz, set it to 90 Hz or 30 Hz (1/3). DO NOT set it to 60 Hz.


**FFT  Setting**

- Tilt: the extra tilting slope of the FFT
- Speed: the extra decay speed of the FFT

**Curve Thickness**

thickness of the magnitude analyzer

#### Bottom Buttons


___

<p float="left">
  <img src="/images/zlcompressor/save.svg" width="18pt"/>
</p>

- Save the current setting.

___

<p float="left">
  <img src="/images/zlcompressor/reset_settings.svg" width="18pt"/>
</p>

- Load the default settings of some colours.

___

<p float="left">
  <img src="/images/zlcompressor/close.svg" width="18pt"/>
</p>

- Discard all unsaved settings and close the UI setting panel.

___

## Shortcuts

Generally, you can enable fine-adjustment with Shift and enable special adjustment with Ctrl/Command. If the direction of the mouse wheel is reversed when Shift is pressed, you can reverse it again to put it back to normal.

- when using the mouse to drag / the mouse wheel to adjust sliders, you can enable fine-adjustment with Shift
- when dragging the band button, you can enable fine-dragging with Shift
- when dragging the band button, you can fix frequency with Ctrl/Command + left-click and fix gain with Ctrl/Command + right-click

