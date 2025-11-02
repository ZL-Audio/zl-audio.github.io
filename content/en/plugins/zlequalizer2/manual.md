---
title: Manual
description: How to use ZL Equalizer 2
weight: 2
---

<img src="/images/zlequalizer2/dark_crop.jpg" style="width:750px; max-width: 100%; height: auto" />

___

## About

ZL Equalizer 2 is a dynamic equalizer plugin with the following key features:

- **Unmatched Versatility**: Sculpt your sound with 6 filter structures, 8 filter types, 5 stereo modes, 7 variable slopes, and up to 24 frequency bands.
- **Integrated Dynamic Control**: Go beyond static EQ with adjustable threshold, attack, release, and side-chain filters for powerful dynamic equalization.
- **Pristine 64-bit Audio**: 64-bit floating-point processing and advanced de-cramping technique deliver outstanding performance, ensuring exceptional clarity from the deepest lows to the highest highs.
- **Intuitive Workflow**: A carefully designed interface with an interactive spectrum graph, smart collision detection, and smooth animations makes equalization fast and fluid.

## Top Panel

___


<p float="left">
  <img src="/images/zlequalizer2/zlaudio.svg" width="20pt" />
  <img src="/images/zlequalizer2/logo.svg" width="20pt" />
</p>

You can open the [UI Setting Panel](#ui-setting-panel) by double-clicking the logo.

___

**Analyzer**

You can open the [Analyzer Setting Panel](#analyzer-setting-panel) by clicking the text.

___

<p float="left">
  <img src="/images/zlequalizer2/match.svg" width="20pt"/>
</p>
You can open the [EQ Match Panel](#eq-match-panel) by clicking the icon.

___

**Filter Structure**

- `Minimum Phase`: [Minimum Phase](#minimum-phase)
- `State Variable`: [State Variable](#state-variable)
- `Parallel`: [Parallel](#parallel)
- `Matched Phase`: [Matched Phase](#matched-phase)
- `Mixed Phase`: [Mixed Phase](#mixed-phase)
- `Zero Phase`: [Zero Phase](#zero-phase)

___


## Center Panel

## Bottom Panel

## Output Setting Panel

## Analyzer Setting Panel

## EQ Match Panel

## UI Setting Panel

## Shortcuts

## Filter Structure

#### Minimum Phase

This is the **standard, classic digital EQ sound**. It's the most common filter type.
* **Best For:** General EQ tasks.
* **Pros:** Gentle 6 dB and 12 dB/oct slopes cause very little phase shift, making it safe to blend with your original signal (low risk of cancellation).
* **Cons:** Aggressive automation of frequency or gain can sometimes cause audible clicks or instability.
#### State Variable

This is the filter type often used in **synth filters and crossovers**.
* **Best For:** Creative effects and heavy automation.
* **Pros:** Extremely stable, even with rapid, complex automation.
* **Cons:** Causes a significant phase shift. **Avoid mixing this signal with the original** (or other correlated signals) as it will likely cause phase cancellation.

#### Parallel

This mode changes how filters work together. **Shelf** (<= 12 dB/oct) and **Peak** (<= 24 dB/oct) filters are processed in parallel**.
* **Best For:** Efficient dynamic EQ processing.
* **Pros:** Offers a different character and is more CPU-efficient for dynamic tasks.
* **Cons:** The parallel processing means the final EQ curve **will look different** from the curves shown on the display.

#### Matched Phase

This mode adds a special process to the `Minimum Phase` filters to **sound more like the analog prototype**.
* **Best For:** Getting an "analog" phase and magnitude response.
* **Latency:** Adds about 11 ms (up to 22 ms for L/R & M/S processing).
* **Warning:** **Do not automate** filter parameters in this mode.

#### Mixed Phase

This is a hybrid mode that **mimics analog magnitude but "cleans up" high-frequency phase**.
* **Best For:** Getting an "analog" magnitude response without the high-end phase shift (above 5 kHz).
* **Latency:** Adds about 21 ms (up to 43 ms for L/R & M/S processing).
* **Warning:** **Do not automate** filter parameters in this mode.

#### Zero Phase

This mode provides **almost zero phase response**.
* **Best For:** Surgical mastering tasks where preserving phase relationships is critical (e.g., on multi-miked drums).
* **Pros:** No phase distortion at all for mid/high frequencies (above 200 Hz).
* **Cons:** Adds a **very high latency** of about 171 ms (up to 342 ms for L/R & M/S processing). May cause audible pre-ringing.
* **Warning:** **Do not automate** filter parameters in this mode.

