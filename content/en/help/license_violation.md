---
title: License Violation Records
linkTitle: License Violation Records
weight: 3
---

Here are some records for developers who uses ZL Audio plugin source code but violates AGPLv3 license.

Please notice: I have already given them a 30-day notice but they fail to comply the license or cease distributions.

## Case 1

Plugin: Semedo EQ (version 3.1)

ZL Audio Plugin: ZL Equalizer 2 (version 1.1.0)

### Analysis

Here is the [video](https://youtu.be/XuBGNZEBGRk) and the corresponding timeline:

00:00 ~ Installer Semedo EQ (version 3.1) and ZL Equalizer 2 (version 1.1.0)

02:28 ~ Add a 96 dB/oct Low Pass filter at 20 kHz, Q = 0.71

- Result: two plugins show identical (distorted) Freq Response and Phase Response
- Notice: ZL Equalizer 2 uses a special de-cramping method, especially for high-order filters. There is no way two plugins use the identical de-cramping method, without using the same source code.

03:35 ~ Add a 12 dB/oct Peak filter at 2.81 kHz, Gain = +11.3 dB, Q = 1.0 and turns on Static Gain Compensation

- Result: two plugins show identical Freq Response and Phase Response
- Notice: ZL Equalizer 2 uses a special way (with lots of specific constants) to calculate Static Gain Compensation. There is no way two plugins show the same gain compensation, without using the same source code.

04:20 ~ Add a 12 dB/oct High Pass filter at 20 Hz, Q = 0.71 and turns on Zero Phase/Linear Phase. Later change the High Pass to 36 dB/oct

- Result: two plugins show identical Freq Response and Phase Response
- Notice: ZL Equalizer 2 uses a special way to smooth low frequency phase shift. There is no way two plugins show the same non-zero phase response at low frequency area, without using the same source code.

### Conclusion

Semedo EQ (version 3.1) heavily uses the source code of ZL Equalizer 2 (version 1.1.0). 
