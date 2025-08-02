---
title: Installation
description: How to install ZL Compressor
weight: 1
---

<!-- ## Introduction Video

{{< youtube "bC-mBDumzvU" >}} -->

## Installation

Visit [this link](https://github.com/ZL-Audio/ZLCompressor/releases/latest) and download the installer that matches your OS:

- If the file has a `.dmg` extension, it is for macOS (in `VST3` & `AU`).
- If the file has a `.exe` extension, it is for Windows (in `VST3` & `LV2`).
- If the file has a `.zip` extension, it is for Linux (in `VST3` & `LV2`).

For more information, please refer to the [Plugin Installation](../../help/plugin_installation) page.

ZL Compressor is Free and Open-source. ZL Compressor is licensed under [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html), except for the [logo of ZL Audio](https://github.com/ZL-Audio/ZLCompressor/blob/main/assets/zlaudio.svg) and the [logo of ZL Compressor](https://github.com/ZL-Audio/ZLCompressor/blob/main/assets/logo.svg). 

AGPLv3 Section 9 *Acceptance Not Required for Having Copies*:

**You are not required to accept this License in order to receive or run a copy of the Program. Ancillary propagation of a covered work occurring solely as a consequence of using peer-to-peer transmission to receive a copy likewise does not require acceptance. However, nothing other than this License grants you permission to propagate or modify any covered work. These actions infringe copyright if you do not accept this License. Therefore, by modifying or propagating a covered work, you indicate your acceptance of this License to do so.**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## Changelog

### 0.1.2

New Features

- add UI setting panel
- add two stereo modes (see #20)
- add filter slope mouse wheel control (+ command/ctrl)
- add filter invert/copy/paste right click panel
- add threshold/ratio mousewheel control (on the analyzer)

Bug fixes and Improvements

- fix side wet slider width
- fix analyzer shaking when bypassed/paused
- improve slider mousewheel behaviour (see #21)
- improve FFT analyzer display

Others

- add Windows ARM64 release

### 0.1.1

New Features

- add compression style `Vocal`
- add RMS release and RMS parameters
- add loudness match

Bug fixes and Improvements

- fix delayed magnitude analyzer
- fix incorrect cumulative RMS display
- improve resizable corner dragger