---
title: Manual
description: How to use ZL Compressor
weight: 2
---

<img src="/images/zlcompressor/dark_crop.jpg" style="width:750px; max-width: 100%; height: auto" />

___

## About

ZL Compressor is a dynamic range compressor with the following key features:

- **Versatile Compression Styles:** Sculpt your sound with three distinct compression architectures. The **Clean** style engages a modern **VCA feed-forward** design, delivering surgical and transparent gain reduction. Switch to **Classic** to harness the aggressive, colorful character of a vintage **FET feedback** design. For smooth, effortless leveling with a touch of warmth, the **Optical** mode emulates the program-dependent characteristics of light-sensitive resistors.

- **Comprehensive Side-chain Control:** Utilize the full **8-band equalizer** to make the compressor react to specific frequencies. The **stereo mode** and adjustable **stereo link** provides control over how the compressor responds to stereo material. With an integrated **lookahead** function, you can ensure that even the fastest transients are caught with surgical precision.

- **Uncompromising Performance:** With up to **8 times over-sampling**, ZL Compressor virtually eliminates aliasing artifacts, ensuring a clean and pure sound even under heavy gain reduction. The highly efficient compression algorithm has been optimized for low CPU usage, allowing you to run multiple instances in your projects without sacrificing performance.

- **Intuitive and Insightful Interface:** The large, accurate **Peak/RMS analyzer** gives you a clear visual representation of your audio's dynamics, while the **interactive spectrum analyzer** allows you to control your side-chain EQ in real-time. This combination of visual feedback and precise control empowers you to make better mixing decisions, faster.

## Top Panel

___

<p float="left">
  <img src="/images/zlcompressor/zlaudio.svg" width="44pt" />
  <img src="/images/zlcompressor/logo.svg" width="20pt" />
</p>

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

The cumulative analyzer on the left shows the cumulative RMS values of the input main-chain signal and the output main-chain signal.

### Computer Display

## Bottom Panel

## Side-chain Panel

## Side-chain Equalizer

