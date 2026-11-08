---
title: Installation
description: How to install ZL Spectrum Equalizer
weight: 1
---
## Introduction Video

{{< youtube "qp_mmVIGBcc" >}}

## Installation

{{% include file="download-intro" repo="ZL-Audio/ZLSpectrumEqualizer" %}}

{{< installers repo="ZL-Audio/ZLSpectrumEqualizer" plugin="ZL.Spectrum.Equalizer" version="0.1.1" >}}

{{% include file="plugin-license" repo="ZL-Audio/ZLSpectrumEqualizer" plugin="ZL Spectrum Equalizer" %}}

AGPLv3 Section 9 *Acceptance Not Required for Having Copies*:

{{% include "agpl-acceptance" %}}

{{% include "vst3" %}}

## Nightly Release

{{% include file="nightly-release" repo="ZL-Audio/ZLSpectrumEqualizer" %}}

## Changelog

### 0.1.1

Bug fixes

- fix Linux combobox & text editor interaction issue

New Features

- add customized combobox alignment
- add customized FFT quality

Other Changes

- change the default FFT quality to `Normal` to prevent lags

### 0.1.0

BREAKING CHANGES

- fix incorrect fresh rate reported by internal refresh handler
    - you may notice the FFT analyzer decays in a different speed after the fix
    - you may need to re-adjust FFT `Speed` in UI settings

Bug fixes

- fix preset folder permission issue on macOS
- fix floating window position when dynamic is ON
- fix solo shortcuts regarding right-click

New Features

- add `Flat Gain` filter type
- add gain adjustment during solo
    - to fix the gain as zero, press `Ctrl/Command` during right-click dragging
- add FFT decibel scale maximum selection

Other Changes

- change filter close button to trash icon
- improve FFT analyzer precision

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