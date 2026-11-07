---
title: Installation
description: How to install ZL Splitter
weight: 1
---

## Introduction Video

{{< youtube "-RVm9mbbQtA" >}}

## Installation

You may download the installer at the [GitHub release page](https://github.com/ZL-Audio/ZLSplitter/releases/latest) or use the direct download link below. Please download the installer that matches your OS & architecture:

{{< installers repo="ZL-Audio/ZLSplitter" plugin="ZL.Splitter" version="0.4.0" >}}

For more information, please refer to the [Plugin Installation](../../help/plugin_installation) page.

ZL Splitter is Free and Open-source. ZL Splitter is licensed under [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html), except for the [logo of ZL Audio](https://github.com/ZL-Audio/ZLSplitter/blob/main/assets/zlaudio.svg) and the [logo of ZL Splitter](https://github.com/ZL-Audio/ZLSplitter/blob/main/assets/logo.svg). You can obtain the corresponding source code at https://github.com/ZL-Audio/ZLSplitter or https://gitee.com/ZL-Audio/ZLSplitter.

AGPLv3 Section 9 *Acceptance Not Required for Having Copies*:

**You are not required to accept this License in order to receive or run a copy of the Program. Ancillary propagation of a covered work occurring solely as a consequence of using peer-to-peer transmission to receive a copy likewise does not require acceptance. However, nothing other than this License grants you permission to propagate or modify any covered work. These actions infringe copyright if you do not accept this License. Therefore, by modifying or propagating a covered work, you indicate your acceptance of this License to do so.**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## Nightly Release

Available [here](https://github.com/ZL-Audio/ZLNightlyRelease/releases/tag/ZLSplitter). Nightly releases contain new features and fixes that may change before the formal release. Not recommended for critical production work. If you have specific bug reports or feature requests, you can open an issue [here](https://github.com/ZL-Audio/ZLSplitter/issues).

## Changelog

### 0.4.0

Breaking Changes

- Low/High splitter `SVF` changes to `IIR` and the filters are now de-cramped
- Low/High splitter `FIR` changes to the de-cramping method proposed by Yuriy Ivantsov
- several FFT analyzer settings are removed

Bug fixes and Improvements

- fix old audio replaying when switching split modes
- fix bypass delay continuity and latency updates when changing the Low/High `FIR` crossover frequency
- fix processing of the highest frequency bins in the Transient/Steady split
- fix magnitude and wave display history and scaling

New Features

- add built-in preset manager
- add host parameter context menus on right-click in supported hosts
- add `OCT` and `ERB` FFT analyzer smoothing modes
- add `Sync`, `Slow`, and `Roll` magnitude analyzer display modes

Improvements

- improve splitter performance (especially for Low/High splitter `FIR` and Transient/Steady splitter)
- improve analyzer performance

### 0.3.0

New Features

- add wave display panel
- add more analyzer settings

Bug fixes and Improvements

- improve FFT analyzer display
- improve magnitude analyzer display

### 0.2.1

Bug fixes and Improvements

- fix plugin crashes when it does not have UI preset folder permission

### 0.2.0

New Features

- add tooltips
- add fft analyzer
- add magnitude analyzer
- add bypass
- add more options to UI setting panel

Bug fixes and Improvements

- improve performance

Others

- add Windows ARM64 release
