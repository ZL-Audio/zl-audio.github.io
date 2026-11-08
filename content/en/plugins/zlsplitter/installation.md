---
title: Installation
description: How to install ZL Splitter
weight: 1
---

## Introduction Video

{{< youtube "-RVm9mbbQtA" >}}

## Installation

{{% include file="download-intro" repo="ZL-Audio/ZLSplitter" platform="os" %}}

{{< installers repo="ZL-Audio/ZLSplitter" plugin="ZL.Splitter" version="0.4.0" >}}

{{% include "installation-help" %}}

{{% include file="plugin-license" repo="ZL-Audio/ZLSplitter" plugin="ZL Splitter" %}}

AGPLv3 Section 9 *Acceptance Not Required for Having Copies*:

{{% include "agpl-acceptance" %}}

{{% include "vst3" %}}

## Nightly Release

{{% include file="nightly-release" repo="ZL-Audio/ZLSplitter" intro="Available" %}}

## Changelog

### 0.4.0

Breaking Changes

- Low/High splitter `SVF` changes to `IIR` and the filters are now de-cramped
- Low/High splitter `FIR` changes to the de-cramping method proposed by Yuriy Ivantsov
- several FFT analyzer settings are removed

Bug Fixes

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
