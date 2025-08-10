---
title: Installation
description: How to install ZL Compressor
weight: 1
---

## Introduction Video

{{< youtube "WDxXEAfy4rg" >}}

## Installation

You may download the installer at the [GitHub release page](https://github.com/ZL-Audio/ZLCompressor/releases/latest) or use the direct download link below. Please download the installer that matches your OS & architecture:

- macOS Intel-chip or macOS Apple-M-chip with **Rosetta Mode**:  [ZL.Compressor-0.2.0-macOS-x86.dmg](https://github.com/ZL-Audio/ZLCompressor/releases/download/0.2.0/ZL.Compressor-0.2.0-macOS-x86.dmg)
- macOS Apple-M-chip: [ZL.Compressor-0.2.0-macOS-arm.dmg](https://github.com/ZL-Audio/ZLCompressor/releases/download/0.2.0/ZL.Compressor-0.2.0-macOS-arm.dmg)
- Windows x86-64 architecture: [ZL.Compressor-0.2.0-Windows-x86.exe](https://github.com/ZL-Audio/ZLCompressor/releases/download/0.2.0/ZL.Compressor-0.2.0-Windows-x86.exe)
- Windows ARM64 architecture: [ZL.Compressor-0.2.0-Windows-arm.exe](https://github.com/ZL-Audio/ZLCompressor/releases/download/0.2.0/ZL.Compressor-0.2.0-Windows-arm.exe)
- Linux x86-64 architecture: [ZL.Compressor-0.2.0-Linux-x86.zip](https://github.com/ZL-Audio/ZLCompressor/releases/download/0.2.0/ZL.Compressor-0.2.0-Linux-x86.zip)
- Linux ARM64 architecture: [ZL.Compressor-0.2.0-Linux-arm.zip](https://github.com/ZL-Audio/ZLCompressor/releases/download/0.2.0/ZL.Compressor-0.2.0-Linux-arm.zip)

For more information, please refer to the [Plugin Installation](../../help/plugin_installation) page.

ZL Compressor is Free and Open-source. ZL Compressor is licensed under [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html), except for the [logo of ZL Audio](https://github.com/ZL-Audio/ZLCompressor/blob/main/assets/zlaudio.svg) and the [logo of ZL Compressor](https://github.com/ZL-Audio/ZLCompressor/blob/main/assets/logo.svg). You can obtain the corresponding source code at https://github.com/ZL-Audio/ZLCompressor or https://gitee.com/ZL-Audio/ZLCompressor.

AGPLv3 Section 9 *Acceptance Not Required for Having Copies*:

**You are not required to accept this License in order to receive or run a copy of the Program. Ancillary propagation of a covered work occurring solely as a consequence of using peer-to-peer transmission to receive a copy likewise does not require acceptance. However, nothing other than this License grants you permission to propagate or modify any covered work. These actions infringe copyright if you do not accept this License. Therefore, by modifying or propagating a covered work, you indicate your acceptance of this License to do so.**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## Changelog

### 0.2.0

New Features

- add tooltips
- add side-chain filter solo (double-click on the dragger)
- add soft clipper

Bug fixes and Improvements

- fix potential overflow in `Vocal` style
- improve stability

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