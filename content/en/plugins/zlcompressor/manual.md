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

Work in progress.

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

The delay of the main-chain signal. When PDC is supported (in almost all DAWs), it can be interpreted as the lookahead time of the side-chain signal.

You may hear clicks/pops when you change this parameter. Please **DO NOT** automate this parameter.

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

- `Clean`: feedforward design with exponential decayed attack/release stages, which offers transparent, precise dynamic control.
- `Classic`: feedback design with exponential decayed attack/release stages, which offers smooth, glued dynamic control
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

**Range**

Controls the gain reduction range. The actual value is affected by the **Wet**.

___

**Hold**

Controls the minimum amount of time where gain reduction is prevented from decreasing. During this time, compression can react to new peaks but cannot release.

___

**Makeup**

Controls the makeup gain that is applied after the compression. The actual value is affected by the **Wet**.

___

**Wet**

Controls the percent of wet signal.

___
## Side-chain Panel

___

<p float="left">
  <img src="/images/zlcompressor/midside.svg" width="20pt"/>
</p>

Set the stereo mode to Mid/Side.


<p float="left">
  <img src="/images/zlcompressor/leftright.svg" width="20pt"/>
</p>

Set the stereo mode to Left/Right.

___

<p float="left">
  <img src="/images/zlcompressor/shuffle.svg" width="20pt"/>
</p>

- Press: swap the side-chain stereo mode
	- if the stereo mode is Left/Right, the side-chain is from Right/Left
	- if the stereo mode is Mid/Side, the side-chain is from Side/Mid

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

When a frequency band is not in the off state, a draggable button appears at the corresponding frequency/gain position. You can adjust the frequency and gain by dragging the button, and adjust the Q value with your mouse wheel.

When you select the frequency band via clicking the button:

- an additional control window will appear near the button, through which you can quickly bypass/close the selected band, choose the filter type, and adjust the filter slope.
- the frequency/gain values will appear at the top-left corner, through which you can view/edit the frequency/gain values of the selected band