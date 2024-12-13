---
title: Installation
description: How to install ZL Equalizer
weight: 1
---

## Introduction Video

{{< youtube "bC-mBDumzvU" >}}

## Installation

Visit [this link](https://github.com/ZL-Audio/ZLEqualizer/releases/latest) and download the installer that matches your OS:

- If the file has a `.dmg` extension, it is for macOS (in `VST3`, `AU` & `AAX`).
- If the file has a `.exe` extension, it is for Windows (in `VST3`, `LV2` & `AAX`).
- If the file has a `.zip` extension, it is for Linux (in `VST3` & `LV2`).

For more information, please refer to the [Plugin Installation](../../help/plugin_installation) page.

ZL Equalizer is licensed under [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html).

AGPLv3 Section 9 *Acceptance Not Required for Having Copies*:

**You are not required to accept this License in order to receive or run a copy of the Program. Ancillary propagation of a covered work occurring solely as a consequence of using peer-to-peer transmission to receive a copy likewise does not require acceptance. However, nothing other than this License grants you permission to propagate or modify any covered work. These actions infringe copyright if you do not accept this License. Therefore, by modifying or propagating a covered work, you indicate your acceptance of this License to do so.**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## Changelog

### 0.5.0 (upcoming)

- add UI setting import/export
- improve GUI performance

### 0.4.5

- fix nlopt library linking issue in version 0.4.4
- fix incorrect licenses in installers (licenses have been changed to AGPLv3)
- improve DSP stability

### 0.4.4

- fix uninitialized static gain compensation in some edge cases
- fix data race in some edge cases

### 0.4.3

- change the top panel layout (move global bypass and sgc buttons outside)
- change the UI setting panel layout
- add the resizing to default size function to UI button
- add default pass filter order & slider double-clicking to the UI setting panel
- add colour maps to the UI setting panel
- add fft resolution to the UI setting panel
- fix incorrect latency when the samplerate changes after loading the plugin
- fix combobox displays in `Standalone`
- improve `matched phase` `mixed phase` under high samplerates
- improve spectrum display accuracy in the high-end

### 0.4.2

- add & change slider value editor shortcuts
  - open value editor with Ctrl/Command + mouse double-clicking for ALL sliders
- fix incorrect curve display when adjusting `Scale`
- fix macOS compatibility issue (now it should support macOS 10.13 and above)
- improve `mixed phase` phase shift continuity

### 0.4.1

- fix some debug code

### 0.4.0

- add parallel filter structure
- add match-phase filter structure
- add mixed-phase filter structure
- add linear-phase filter structure
- add & change shortcuts
  - fine-adjust dragger with Shift
  - find-adjust slider with Shift (changed from Ctrl/Command)
  - add a dynamic filter with Ctrl/Command + mouse double-clicking
  - turn on/off dynamic with Ctrl/Command + mouse double-clicking on the dragger
- change real curves to ideal curves
- change default FFT order to 12 to increase low-frequency details
- add phase-flip button and change the `Output` panel layout
- add more freedom to the plugin window size
- improve DSP & GUI stability
- improve DSP & GUI performance
