---
title: High-performance FFT Library zldsp::fft
date: 2026-08-04
author: zsliu98
tags:
  - FFT
  - spectrum
weight: 10
---

`zldsp::fft` is a header-only C++ Fast Fourier Transform (FFT) library built with [Google Highway](https://github.com/google/highway). `zldsp::fft` is licensed under Apache-2.0 license. You can obtain the source code at [GitHub](https://github.com/ZL-Audio/zldsp_fft). `zldsp::fft` supports SSE2/SSE4/AVX2/NEON SIMD targets and both AoS/SoA layouts for complex numbers.

## Usage

1. C++ Standard: C++20 or higher
2. Google Highway: You must include and link Google Highway in your project. The headers in this library expect the following includes to be resolvable:
```cpp
#include <hwy/aligned_allocator.h>
#include <hwy/highway.h>
```

### Static Dispatch

```cmake
target_compile_definitions(my_static_target PRIVATE HWY_COMPILE_ONLY_STATIC)
```

Use the compiler's architecture option to select an SSE, AVX2, or NEON static
target.

| SIMD Target | GCC/Clang                         | MSVC             |
| ----------- | --------------------------------- | ---------------- |
| SSE2        | `-march=x86-64`                   | no flag required |
| SSE4        | `-march=x86-64-v2 -maes -mpclmul` | not supported    |
| AVX2        | `-march=x86-64-v3 -maes -mpclmul` | `/arch:AVX2`     |
| NEON        | `-march=armv8-a+simd`             | `/arch:armv8.0`  |

See [`static_dispatch_caller`](https://github.com/ZL-Audio/zldsp_fft_develop/tree/main/examples/static_dispatch_caller.cpp) for CFFT and RFFT static dispatch examples with AoS and SoA layouts.

### Caller-owned Dynamic Dispatch

For example, an x86 application can enable only SSE2 and AVX2:

```cmake
target_compile_definitions(my_dynamic_target PRIVATE "HWY_DISABLED_TARGETS=~(HWY_SSE2|HWY_AVX2)")
```

Compile this target for the oldest supported baseline (for example, `-march=x86-64` for SSE2).

See [`wrapper`](https://github.com/ZL-Audio/zldsp_fft_develop/tree/main/examples/dynamic_dispatch_wrapper.cpp), its [`interface`](https://github.com/ZL-Audio/zldsp_fft_develop/tree/main/examples/dynamic_dispatch_wrapper.hpp), and [`dynamic_dispatch_caller`](https://github.com/ZL-Audio/zldsp_fft_develop/tree/main/examples/dynamic_dispatch_caller.cpp) for CFFT and RFFT dynamic dispatch examples with AoS and SoA layouts.

## Benchmark

Here are some benchmarks results. The benchmark code is available at [GitHub](https://github.com/ZL-Audio/zldsp_fft_develop). I have tried my best to configure other libraries correctly. All libraries are built with LLVM/Clang or Apple-Clang. [Google Benchmark](https://github.com/google/benchmark/tree/main) is used for benchmark.

Included libraries are (they are subjected to their own licenses):

- `IPP`: [Intel® Integrated Performance Primitives](https://www.intel.com/content/www/us/en/developer/tools/oneapi/ipp.html)
- `vDSP`: [Apple vDSP](https://developer.apple.com/documentation/accelerate/vdsp)
- `ArmPL`: [Arm Performance Libraries](https://developer.arm.com/tools-and-software/arm-performance-libraries)
- `FFTW3`: [FFTW 3.3.10 Mirror](https://github.com/zsliu98/fftw3-mirror/tree/14eea039281b8c5bd83a20314afb402538fd986c) with NEON support, take the better one from `FFTW_MEASURE` and `FFTW_ESTIMATE`
- `KFR`: [KFR 7.1.0](https://github.com/kfrlib/kfr/tree/main)
- `PFFFT`: [PFFFT 1.1.0](https://github.com/marton78/pffft)
- `zldsp`: [zldsp::fft](https://github.com/ZL-Audio/zldsp_fft)

The benchmarks shown below are Real FFT benchmarks from order 5 to order 25.

#### Apple M4 Pro 14-core (local)

<div style="display: flex; gap: 20px; justify-content: center;">
  <figure style="text-align: center; margin: 0;">
    <figcaption style="font-weight: bold; margin-bottom: 8px;">NEON float32</figcaption>
    <img src="/reports/2026-08-04/m4pro_rfft_f32.svg" alt="Plot 1" style="width: 100%; max-width: 400px;">
  </figure>
  <figure style="text-align: center; margin: 0;">
    <figcaption style="font-weight: bold; margin-bottom: 8px;">NEON float64</figcaption>
    <img src="/reports/2026-08-04/m4pro_rfft_f64.svg" alt="Plot 2" style="width: 100%; max-width: 400px;">
  </figure>
</div>

#### Intel Core i7-8850H (local)

<div style="display: flex; gap: 20px; justify-content: center;">
  <figure style="text-align: center; margin: 0;">
    <figcaption style="font-weight: bold; margin-bottom: 8px;">AVX2 float32</figcaption>
    <img src="/reports/2026-08-04/8850_rfft_avx2_f32.svg" alt="Plot 1" style="width: 100%; max-width: 400px;">
  </figure>
  <figure style="text-align: center; margin: 0;">
    <figcaption style="font-weight: bold; margin-bottom: 8px;">AVX2 float64</figcaption>
    <img src="/reports/2026-08-04/8850_rfft_avx2_f64.svg" alt="Plot 2" style="width: 100%; max-width: 400px;">
  </figure>
</div>

#### AMD EPYC 7763 (GitHub Actions runner images)

<div style="display: flex; gap: 20px; justify-content: center;">
  <figure style="text-align: center; margin: 0;">
    <figcaption style="font-weight: bold; margin-bottom: 8px;">AVX2 float32</figcaption>
    <img src="/reports/2026-08-04/7763_rfft_avx2_f32.svg" alt="Plot 1" style="width: 100%; max-width: 400px;">
  </figure>
  <figure style="text-align: center; margin: 0;">
    <figcaption style="font-weight: bold; margin-bottom: 8px;">AVX2 float64</figcaption>
    <img src="/reports/2026-08-04/7763_rfft_avx2_f64.svg" alt="Plot 2" style="width: 100%; max-width: 400px;">
  </figure>
</div>

#### AMD AMD EPYC 9V74 (GitHub Actions runner images)

<div style="display: flex; gap: 20px; justify-content: center;">
  <figure style="text-align: center; margin: 0;">
    <figcaption style="font-weight: bold; margin-bottom: 8px;">AVX2 float32</figcaption>
    <img src="/reports/2026-08-04/9v74_rfft_avx2_f32.svg" alt="Plot 1" style="width: 100%; max-width: 400px;">
  </figure>
  <figure style="text-align: center; margin: 0;">
    <figcaption style="font-weight: bold; margin-bottom: 8px;">AVX2 float64</figcaption>
    <img src="/reports/2026-08-04/9v74_rfft_avx2_f64.svg" alt="Plot 2" style="width: 100%; max-width: 400px;">
  </figure>
</div>

#### Ampere Altra Q80-30 (Oracle Cloud VM)

<div style="display: flex; gap: 20px; justify-content: center;">
  <figure style="text-align: center; margin: 0;">
    <figcaption style="font-weight: bold; margin-bottom: 8px;">NEON float32</figcaption>
    <img src="/reports/2026-08-04/q80_30_rfft_f32.svg" alt="Plot 1" style="width: 100%; max-width: 400px;">
  </figure>
  <figure style="text-align: center; margin: 0;">
    <figcaption style="font-weight: bold; margin-bottom: 8px;">NEON float64</figcaption>
    <img src="/reports/2026-08-04/q80_30_rfft_f64.svg" alt="Plot 2" style="width: 100%; max-width: 400px;">
  </figure>
</div>

## Design

#### Low Order

For low orders, `0 <= order <= 5`, `zldsp_fft` uses specialized CFFT kernels. Each transform size therefore has a fixed implementation without general stage iteration or stage dispatch to keep values in SIMD registers where practical.

#### Medium Order

For medium orders, `6 <= order <= switch_order - 1`, `zldsp_fft` uses out-of-place Stockham DIT design. It is scheduled as follows:

- an even order begins with Radix-4 and following by Radix-4 stages
- an odd order begins with Radix-8 and following by Radix-4 stages

Intermediate data uses an SIMD-friendly AoSoA layout. The first/final stage is fused with conversion from/to the requested AoS or SoA input/output.

#### High Order

For high orders, `switch_order <= order`, `zldsp_fft` uses a hybrid Cooley–Tukey & Stockham design. It uses Radix-4 Cooley–Tukey DIF macro stages to split the transform into micro CFFTs sized to fit approximately within L1 cache. Then, each micro CFFT is completed with the medium-order Stockham DIT design. The resulting matrix is placed in natural order using a reusable terminal buffer and SIMD register-transpose tiles.

#### Switch Order

The boundary between medium and high orders is derived from the detected L1 cache size. The implementation estimates the largest transform orders that fit its working sets and selects:

`switch_order = maximum_L1_order + 4`

## Reference

- Van Loan, Charles. Computational frameworks for the fast Fourier transform. Society for Industrial and Applied Mathematics, 1992.
- [Notes on FFTs: for implementers](https://fgiesen.wordpress.com/2023/03/19/notes-on-ffts-for-implementers/)
- [OTFFT documentation](http://wwwa.pikara.ne.jp/okojisan/otfft-en/stockham1.html)