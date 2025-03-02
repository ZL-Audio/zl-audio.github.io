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

ZL Equalizer is Free and Open-source. ZL Equalizer is licensed under [AGPLv3](https://www.gnu.org/licenses/agpl-3.0.en.html), except for the [logo of ZL Audio](https://github.com/ZL-Audio/ZLEqualizer/blob/main/assets/zlaudio.svg) and the [logo of ZL Equalizer](https://github.com/ZL-Audio/ZLEqualizer/blob/main/assets/logo.svg). 

AGPLv3 Section 9 *Acceptance Not Required for Having Copies*:

**You are not required to accept this License in order to receive or run a copy of the Program. Ancillary propagation of a covered work occurring solely as a consequence of using peer-to-peer transmission to receive a copy likewise does not require acceptance. However, nothing other than this License grants you permission to propagate or modify any covered work. These actions infringe copyright if you do not accept this License. Therefore, by modifying or propagating a covered work, you indicate your acceptance of this License to do so.**

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## Changelog

### 0.6.0 (upcoming)

- BREAKING: use the new compressor model from ZL Compressor
	- dynamic filters will sound a bit different
	- dynamic filters (especially if under dynamic high-quality mode) become more efficient
	- dynamic filters will produce expected results under extreme knee width settings (see #156)
- BREAKING: smooth filter frequency/gain/Q changes
	- quick move/automation of frequency/gain/Q will have fewer artifacts
	- filter parameter automation will take more CPU usage cause it now changes filters per sample (see the manual)
- change the external side-chain button position to the top-right corner
	- since it is not a per-band parameter, top-right corner seems to be a better place
- change several button icons (see the manual)
	- the old ones are not intuitive enough
- add FFT db scale choice (see #147 and the manual)
- add loudness match (see #154 and the manual)
- add solo shortcuts (by right-mouse-button double-clicking with Ctrl/Command on the band button)
- add side-chain swap (see the manual)
- fix macOS standalone audio input permission request (see #146)
- fix curve db scale (see #148)
- fix multi-band selection (see #149)
- improve GUI performance
- improve DSP performance (especially for high-order filters and dynamic filters)
- improve stability

### 0.5.0

- BREAKING: change (default) dynamic link to UI setting (the parameter is now shared across all instances)
- add Equalization Match (see the manual for details)
- add UI setting import/export
- fix incorrect channel layout (see #138)
- fix incorrect solo display (see #138)
- fix double-click behaviour (see #141)
- improve solo display
- improve GUI performance (especially when you open the UI setting panel)

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
