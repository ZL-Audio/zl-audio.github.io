---
title: zldsp::fft
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

### Compiler Flags

To activate SIMD, you must set the correct compilation flags. Highway will automatically detect the target architecture from these flags.

| SIMD Target | GCC/Clang                         | MSVC             |
| ----------- | --------------------------------- | ---------------- |
| SSE2        | `-march=x86-64`                   | no flag required |
| SSE4        | `-march=x86-64-v2 -mase -mpclmul` | not suported     |
| AVX2        | `-march=x86-64-v3 -maes -mpclmul` | `/arch:AVX2`     |
| NEON        | `-march=armv8-a+simd`             | `/arch:armv8.0`  |

### API

Include the relevant headers from the `/src` directory.

Both `CFFT` and `RFFT` are templated on the floating-point type (e.g., `float` or `double`) and are instantiated using the base-2 **order** of the FFT (where `size = 1 << order`).

#### Complex FFT (`CFFT`)

```cpp
#include "src/zldsp_fft_cfft.hpp"
#include <vector>
#include <complex>

// a CFFT of size 1024 (2^10) using float
constexpr size_t order = 10; 
zldsp::fft::CFFT<float> cfft(order);

std::vector<std::complex<float>> in_buffer(1 << order);
std::vector<std::complex<float>> out_buffer(1 << order);

// forward transform (AoS to AoS)
cfft.forward(in_buffer.data(), out_buffer.data());

// backward transform (AoS to AoS)
cfft.backward(out_buffer.data(), in_buffer.data());
```

#### Real FFT (`RFFT`)

```cpp
#include "src/zldsp_fft_rfft.hpp"
#include <vector>
#include <complex>

// a RFFT of size 1024 (2^10) using float
constexpr size_t order = 10;
zldsp::fft::RFFT<float> rfft(order);

std::vector<float> real_in(1 << order);
std::vector<std::complex<float>> complex_out((1 << order) / 2 + 1);
std::vector<float> sqr_mag_out((1 << order) / 2 + 1);

// forward transform (real to AoS)
rfft.forward(real_in.data(), complex_out.data());

// backward transform (AoS to real)
rfft.backward(complex_out.data(), real_in.data());

// forward transform (real to squared magnitude)
rfft.forward_sqr_mag(real_in.data(), sqr_mag_out.data())
```

#### Data Layouts (AoS/SoA)

Both `CFFT` and `RFFT` support AoS/SoA for complex numbers:

AoS stores interleaved real/imaginary values in one array:
```cpp
std::vector<std::complex<float>> out_buffer(1 << order);
```

SoA stores continuous real/imaginary values in two arrays:

```cpp
std::vector<float> out_real(1 << order);
std::vector<float> out_imag(1 << order);
```

Example using SoA:
```cpp
#include "src/zldsp_fft_cfft.hpp"
#include <vector>
#include <complex>

// a CFFT of size 1024 (2^10) using float
constexpr size_t order = 10; 
zldsp::fft::CFFT<float> cfft(order);

std::vector<std::complex<float>> in_buffer(1 << order);
std::vector<float> out_real(1 << order);
std::vector<float> out_imag(1 << order);

// forward transform (AoS to SoA)
cfft.forward(in_buffer.data(), {out_real.data(), out_imag.data()});

// backward transform (SoA to AoS)
cfft.backward({out_real.data(), out_imag.data()}, in_buffer.data());
```


## Reference

- Van Loan, Charles. Computational frameworks for the fast Fourier transform. Society for Industrial and Applied Mathematics, 1992.
- [Notes on FFTs: for implementers](https://fgiesen.wordpress.com/2023/03/19/notes-on-ffts-for-implementers/)
- [OTFFT documentation](http://wwwa.pikara.ne.jp/okojisan/otfft-en/stockham1.html)