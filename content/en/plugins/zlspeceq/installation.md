---
title: Installation
description: How to install ZL Spectrum Equalizer
weight: 1
---
## Introduction Video

{{< youtube "qp_mmVIGBcc" >}}

## Installation

You may download the installer at the [GitHub release page](https://github.com/ZL-Audio/ZLSpectrumEqualizer/releases/latest) or use the direct download link below. Please download the installer that matches your chip/architecture:

{{< installers repo="ZL-Audio/ZLSpectrumEqualizer" plugin="ZL.Spectrum.Equalizer" version="0.0.3" >}}

ZL Spectrum Equalizer is Free and Open-source. ZL Spectrum Equalizer is licensed under [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html), except for the [logo of ZL Audio](https://github.com/ZL-Audio/ZLSpectrumEqualizer/blob/main/assets/zlaudio.svg) and the [logo of ZL Spectrum Equalizer](https://github.com/ZL-Audio/ZLSpectrumEqualizer/blob/main/assets/logo.svg). You can obtain the corresponding source code at https://github.com/ZL-Audio/ZLSpectrumEqualizer or https://gitee.com/ZL-Audio/ZLSpectrumEqualizer.

AGPLv3 Section 9 *Acceptance Not Required for Having Copies*:

**You are not required to accept this License in order to receive or run a copy of the Program. Ancillary propagation of a covered work occurring solely as a consequence of using peer-to-peer transmission to receive a copy likewise does not require acceptance. However, nothing other than this License grants you permission to propagate or modify any covered work. These actions infringe copyright if you do not accept this License. Therefore, by modifying or propagating a covered work, you indicate your acceptance of this License to do so.**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## Nightly Release

Available at [here](https://github.com/ZL-Audio/ZLNightlyRelease/releases/tag/ZLSpectrumEqualizer). Nightly releases contain new features and fixes that may change before the formal release. Not recommended for critical production work. If you have specific bug reports or feature requests, you can open an issue [here](https://github.com/ZL-Audio/ZLSpectrumEqualizer/issues).

## Changelog

### 0.0.3

Bug fixes

- fix unresponsive Linux UI
- fix incorrect static gain compensation when stereo mode changes
- fix external side-chain button may not get updated display
- fix dynamic curve display beyond Nyquist
- fix potential race condition for FFT collision colour
- fix potential redundant value notification of sliders/buttons/comboboxes
- fix potential lagging caused by UI resizing

New Features

- add built-in preset manager (very early stage)

Other Changes

- adjust UI setting panel
  - remove import/export functions
  - add reveal folder button
- adjust combobox UI

### 0.0.2

BREAKING CHANGES

- fix the `Relative` dynamic mode
- use separate sensitivity controls for sliders/draggers

New Features

- add dynamic delta (per band)

Bug fixes

- fix slider value editor display

Improvements

- improve DSP performance (slightly)

### 0.0.1

First version.