---
title: Installation
description: How to install ZL Equalizer 2
weight: 1
---

## Introduction Video

{{< youtube "bC-mBDumzvU" >}}

## Installation

You may download the installer at the [GitHub release page](https://github.com/ZL-Audio/ZLEqualizer/releases/latest) or use the direct download link below. Please download the installer that matches your OS & architecture:

| Operating System | x86-64<br>Intel Chip<br>AMD Chip (mostly)                                                                                                    | ARM64<br>Apple M Chip<br>Qualcomm Chip                                                                                                       |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **macOS**        | [ZL.Equalizer.2-1.0.0-macOS-x86.dmg](https://github.com/ZL-Audio/ZLEqualizer/releases/download/1.0.0/ZL.Equalizer.2-1.0.0-macOS-x86.dmg)     | [ZL.Equalizer.2-1.0.0-macOS-arm.dmg](https://github.com/ZL-Audio/ZLEqualizer/releases/download/1.0.0/ZL.Equalizer.2-1.0.0-macOS-arm.dmg)     |
| **Windows**      | [ZL.Equalizer.2-1.0.0-Windows-x86.exe](https://github.com/ZL-Audio/ZLEqualizer/releases/download/1.0.0/ZL.Equalizer.2-1.0.0-Windows-x86.exe) | [ZL.Equalizer.2-1.0.0-Windows-arm.exe](https://github.com/ZL-Audio/ZLEqualizer/releases/download/1.0.0/ZL.Equalizer.2-1.0.0-Windows-arm.exe) |
| **Linux**        | [ZL.Equalizer.2-1.0.0-Linux-x86.zip](https://github.com/ZL-Audio/ZLEqualizer/releases/download/1.0.0/ZL.Equalizer.2-1.0.0-Linux-x86.zip)     | [ZL.Equalizer.2-1.0.0-Linux-arm.zip](https://github.com/ZL-Audio/ZLEqualizer/releases/download/1.0.0/ZL.Equalizer.2-1.0.0-Linux-arm.zip)     |

For more information, please refer to the [Plugin Installation](../../help/plugin_installation) page.

ZL Equalizer is Free and Open-source. ZL Equalizer is licensed under [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html), except for the [logo of ZL Audio](https://github.com/ZL-Audio/ZLEqualizer/blob/main/assets/zlaudio.svg) and the [logo of ZL Equalizer](https://github.com/ZL-Audio/ZLEqualizer/blob/main/assets/logo.svg). You can obtain the corresponding source code at https://github.com/ZL-Audio/ZLEqualizer or https://gitee.com/ZL-Audio/ZLEqualizer.

AGPLv3 Section 9 *Acceptance Not Required for Having Copies*:

**You are not required to accept this License in order to receive or run a copy of the Program. Ancillary propagation of a covered work occurring solely as a consequence of using peer-to-peer transmission to receive a copy likewise does not require acceptance. However, nothing other than this License grants you permission to propagate or modify any covered work. These actions infringe copyright if you do not accept this License. Therefore, by modifying or propagating a covered work, you indicate your acceptance of this License to do so.**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## Changelog

### 1.0.1

Will be released this week. EQ Match and AAX are back :)

Compared with ZL Equalizer 0.6.2:

New Features

- add more side-chain filters controls (filter type & filer slope)
- add right-click panel
- add more controls to the floating window
- add more shortcuts
- add UI scaling control
- add EQ Match drawing control

Bug fixes

- fix wrong octave notes
- fix incorrect solo display
- fix incorrect parallel processing in mid/side

Improvements

- improve `Matched Phase` and `Mixed Phase` performance
- improve general DSP performance
- improve dynamic processing
- improve FFT analyzer display
- improve EQ Match fitting speed

Other Changes

- increase frequency maximum value when the sample rate > 44.1 kHz
- remove `RMS` & `Smooth` from dynamic parameters
- remove `Zero Latency` as dynamic won't require extra 1ms latency
- remove `High Quality` as dynamic always stays in high quality
- remove EQ Match `Weight` & fitting algorithm control