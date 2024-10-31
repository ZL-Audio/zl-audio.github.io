---
title: Installation
description: How to install ZL Equalizer
weight: 1
---

Nominations for KVR Audio Readers' Choice Awards 2024 are currently open! If you like this plugin, please nominate/vote it at the [voting page](http://www.kvraudio.com/readers-choice-awards/2024/?utm_source=kvr_all_kvr_admins_mailing&utm_medium=email&utm_campaign=2024-09-30-ad-8124&utm_content=voting%20page). Thank you so much.

## Introduction Video

{{< youtube "bC-mBDumzvU" >}}

## Installation

Visit [this link](https://github.com/ZL-Audio/ZLEqualizer/releases/latest) and download the installer that matches your OS:

- If the file has a `.dmg` extension, it is for macOS (in `VST3`, `AU` & `AAX`).
- If the file has a `.exe` extension, it is for Windows (in `VST3`, `LV2` & `AAX`).
- If the file has a `.zip` extension, it is for Linux (in `VST3` & `LV2`).

For more information, please refer to the [Plugin Installation](../../help/plugin_installation) page.

ZL Equalizer is licensed under [GPLv3](https://www.gnu.org/licenses/gpl-3.0.en.html).

GPLv3 Section 9 *Acceptance Not Required for Having Copies*:

**You are not required to accept this License in order to receive or run a copy of the Program. Ancillary propagation of a covered work occurring solely as a consequence of using peer-to-peer transmission to receive a copy likewise does not require acceptance. However, nothing other than this License grants you permission to propagate or modify any covered work. These actions infringe copyright if you do not accept this License. Therefore, by modifying or propagating a covered work, you indicate your acceptance of this License to do so.**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## Changelog

### 0.4.3/0.5.0 upcoming

- change the top panel layout (move global bypass and sgc buttons outside)
- change the UI setting panel layout
- add the resizing to default size function to UI button
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
