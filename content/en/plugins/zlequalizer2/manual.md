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
- **Pristine Precision**: 64-bit floating-point processing and advanced de-cramping technique deliver outstanding performance, ensuring exceptional clarity from the deepest lows to the highest highs.
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

**Output Panel**

You can open the [Output Setting Panel](#output-setting-panel) by clicking the text. It shows the current filter gain scale & total output gain.

___

<p float="left">
  <img src="/images/zlequalizer2/external-side.svg" width="20pt"/>
</p>

- Press: use the external side-chain
- Release: use the internal side-chain

___

<p float="left">
  <img src="/images/zlequalizer2/bypass.svg" width="20pt"/>
</p>

- Release: bypass the plugin

___

## Center Panel

## Bottom Panel

## Output Setting Panel

___

**GAIN**

Control the additional output gain.

___

**SCALE**

Control the scale of all filters' base & target gain.

___

<p float="left">
  <img src="/images/zlequalizer2/dline_s.svg" width="20pt"/>
</p>

- Press: turn on Static Gain Compensation
- Release: turn off Static Gain Compensation

> SGC estimates the amount of compensation from the filters’ parameters. SGC is **inaccurate**. However, it **will NOT affect the dynamic of the main-chain signal**.

___

<p float="left">
  <img src="/images/zlequalizer2/dline_l.svg" width="20pt"/>
</p>

- Press: start to measure the integrated loudness of the input signal and the output signal
- Release: turn AGC off and update the `Output Gain` to the difference between the two loudness values

___

<p float="left">
  <img src="/images/zlequalizer2/dline_a.svg" width="20pt"/>
</p>

- Press: turn on Auto Gain Compensation
- Release: turn off Auto Gain Compensation

> AGC calculates the difference between the loudness of the main-chain signal before/after filters and applies the corresponding gain. Therefore, **AGC will affect the dynamic of the main-chain signal**.
> 
> When AGC is on, the output main-chain signal will pass through a hard clipper at 0 dB.

___

<p float="left">
  <img src="/images/zlequalizer2/phase.svg" width="20pt"/>
</p>

- Press: flip the phase of the output signal

___

**Lookahead**

Control the lookahead of the side-chain signal.

> **Warning:** **Do not automate** `Lookahead`.

## Analyzer Setting Panel

___

**Pre/Post/Side**

- Press: turn on the Pre/Post/Side analyzer
- Release: turn off the Pre/Post/Side analyzer

___

**Decay Speed**

___

**Slope**

- affects the spectrum display (not the actual signal)
- `0 dB/oct`: no tilting, white noise displays as a horizon line
- `3 dB/oct`: pink noise displays as a horizon line
- `4.5 dB/oct`: default value, which represents perceived loudness better

---

<p float="left">
  <img src="/images/zlequalizer2/freeze.svg" width="20pt"/>
</p>

- Press: turn on the FFT freezing feature. When you hover the mouse over the analyzer for 2 seconds, the Post/Side analyzer will be frozen until you move the mouse.

___

<p float="left">
  <img src="/images/zlequalizer2/collision.svg" width="20pt"/>
</p>

- Press: turn on the collision detection.

___

**Strength**

Control the collision detection strength.

___

## EQ Match Panel

## UI Setting Panel

## UI Controls

Generally, you can enable fine-adjustment with `Shift` and enable special adjustment with `Ctrl/Command`. If the direction of the mouse wheel is reversed when `Shift` is pressed, you can reverse it again (in the UI Setting Panel) to put it back to normal.

**Sliders**

- You can enable fine-adjustment with `Shift` when using the mouse to drag / the mouse wheel to adjust sliders.
- You can use the left/right mouse button to control the first/second value when there are two values on the slider.

**Filter Buttons**

- You can drag a button to change the frequency/gain value.
- You can use the mouse wheel to change the Q value.
- You can enable fine-adjustment with `Shift` when using the mouse to drag a button.
- You can drag with the left mouse button + `Ctrl/Command` down while fixing the frequency.
- You can drag with the right mouse button + `Ctrl/Command` down while fixing the frequency.
- You can double-click the button to enter/exit the solo status.
- You can double-click with `Ctrl/Command` to turn on/off the dynamic behavior.

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

This mode changes how filters work together. **Shelf** (<= 12 dB/oct) and **Peak** (<= 24 dB/oct) filters are processed in parallel.
* **Best For:** Efficient dynamic EQ processing & Natural sounding.
* **Pros:** Offers a different character and is more CPU-efficient for dynamic tasks.
* **Cons:** The parallel processing means the final EQ curve **will look different** from the curves shown on the display.

#### Matched Phase

This mode adds a special process to the `Minimum Phase` filters to **mimic analog prototype** magnitude & phase response.
* **Best For:** Getting an **analog** phase and magnitude response.
* **Latency:** Adds about 11 ms (up to 22 ms for L/R & M/S processing).
* **Cons**: Dynamic filters stay in `Minimum Phase`.

> **Warning:** **Do not automate** filter parameters in this mode.

#### Mixed Phase

This mode adds a special process to the `Minimum Phase` filters to **mimic analog prototype** magnitude response and clean up high-end phase.
* **Best For:** Getting an **analog** magnitude response without the high-end phase shift (above 5 kHz).
* **Latency:** Adds about 21 ms (up to 43 ms for L/R & M/S processing).
* **Cons**: Dynamic filters stay in `Minimum Phase`.

> **Warning:** **Do not automate** filter parameters in this mode.

#### Zero Phase

This mode provides **almost zero phase response**.
* **Best For:** Surgical mastering tasks where preserving phase relationships is critical.
* **Pros:** No phase distortion at all for mid/high frequencies (above 200 Hz).
* **Cons:** Adds a **very high latency** of about 171 ms (up to 342 ms for L/R & M/S processing). May cause audible pre-ringing. Dynamic filters stay in `Minimum Phase`.

> **Warning:** **Do not automate** filter parameters in this mode.


## Dynamic Filter