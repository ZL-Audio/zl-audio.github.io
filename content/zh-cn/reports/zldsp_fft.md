---
title: zldsp::fft
date: 2026-08-04
author: zsliu98
tags:
  - FFT
  - spectrum
weight: 10
---

`zldsp::fft` 是一个基于 [Google Highway](https://github.com/google/highway) 构建的 header-only C++ FFT 库。`zldsp::fft` 遵循 Apache-2.0 开源许可证。你可以在 [GitHub](https://github.com/ZL-Audio/zldsp_fft) 获取源代码。`zldsp::fft` 支持 SSE2/SSE4/AVX2/NEON SIMD target，并对复数同时支持 AoS/SoA 布局。

## 使用

1. C++ Standard: C++20 或更高版本
2. Google Highway: 项目中必须包含并链接 Google Highway。本库的头文件需要解析以下 include：
```cpp
#include <hwy/aligned_allocator.h>
#include <hwy/highway.h>
```

#### 编译参数

要启用 SIMD，必须设置正确的编译 flag。Highway 会根据这些 flag 自动检测目标架构。

| SIMD Target | GCC/Clang                         | MSVC             |
| ----------- | --------------------------------- | ---------------- |
| SSE2        | `-march=x86-64`                   | no flag required |
| SSE4        | `-march=x86-64-v2 -mase -mpclmul` | not supported    |
| AVX2        | `-march=x86-64-v3 -maes -mpclmul` | `/arch:AVX2`     |
| NEON        | `-march=armv8-a+simd`             | `/arch:armv8.0`  |

#### API

包含 `/src` 目录下的相关头文件即可。

`CFFT` 与 `RFFT` 都以浮点类型（如 `float` 或 `double`）作为模板参数，并使用以 2 为底的 FFT **order** 进行实例化（其中 `size = 1 << order`）。

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

#### 数据布局 (AoS/SoA)

`CFFT` 和 `RFFT` 均支持复数的 AoS/SoA：

AoS 将 real/imaginary 值交错存储在一个数组中：
```cpp
std::vector<std::complex<float>> out_buffer(1 << order);
```

SoA 将 real/imaginary 值分别连续存储在两个数组中：

```cpp
std::vector<float> out_real(1 << order);
std::vector<float> out_imag(1 << order);
```

使用 SoA 的示例：
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

## 基准测试

这里是一些基准测试结果。基准测试代码可在 [GitHub](https://github.com/ZL-Audio/zldsp_fft_develop) 获取。已尽可能正确配置其他对比库。所有库均使用 LLVM/Clang 或 Apple-Clang 构建。[Google Benchmark](https://github.com/google/benchmark/tree/main) 用于性能测试。

包含的库如下（受各自的许可约束）：

- `IPP`: [Intel® Integrated Performance Primitives](https://www.intel.com/content/www/us/en/developer/tools/oneapi/ipp.html)
- `vDSP`: [Apple vDSP](https://developer.apple.com/documentation/accelerate/vdsp)
- `ArmPL`: [Arm Performance Libraries](https://developer.arm.com/tools-and-software/arm-performance-libraries)
- `FFTW3`: [FFTW 3.3.10 Mirror](https://github.com/zsliu98/fftw3-mirror/tree/14eea039281b8c5bd83a20314afb402538fd986c) 支持 NEON，取 `FFTW_MEASURE` 和 `FFTW_ESTIMATE` 中的较好者
- `KFR`: [KFR 7.0.0](https://github.com/kfrlib/kfr/tree/main)
- `PFFFT`: [PFFFT 1.1.0](https://github.com/marton78/pffft)
- `zldsp`: [zldsp::fft](https://github.com/ZL-Audio/zldsp_fft)

下方展示的是 order 5 到 order 25 的 Real FFT benchmark 结果。

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

## 设计

#### 低阶

对于低阶（`0 <= order <= 5`），`zldsp_fft` 使用专门定制的 CFFT 核。因此每个变换大小都具有固定实现，不使用通用的循环或分发，以便在可行的情况下尽可能将数据保存在 SIMD 寄存器中。

#### 中阶

对于中阶（`6 <= order <= switch_order - 1`），`zldsp_fft` 采用 out-of-place Stockham DIT 设计。其调度如下：

- even order 以 Radix-4 开始，后续均为 Radix-4 级
- odd order 以 Radix-8 开始，后续均为 Radix-4 级

中间数据使用对 SIMD 友好的 AoSoA 布局。第一级/最后一级会与所请求的 AoS 或 SoA 输入/输出格式转换进行融合。

#### 高阶

对于高阶（`switch_order <= order`），`zldsp_fft` 采用 Cooley–Tukey & Stockham 混合设计。它使用 Radix-4 Cooley–Tukey DIF 级将变换拆分为大小大致可容纳在 L1 缓存内的 micro CFFT。随后，每个 micro CFFT 通过中阶 Stockham DIT 设计完成。得到的矩阵使用可复用的 terminal buffer 和 SIMD 寄存器转置置于自然序。

#### 切换阈值阶数

中阶 与 高阶 之间的分界基于检测到的 L1 和 L2 缓存大小推导得出。实现会估算适合其工作集的最大变换阶数，并选取：

`switch_order = max(maximum_L1_order + 4, maximum_L2_order)`

## 参考

- Van Loan, Charles. Computational frameworks for the fast Fourier transform. Society for Industrial and Applied Mathematics, 1992.
- [Notes on FFTs: for implementers](https://fgiesen.wordpress.com/2023/03/19/notes-on-ffts-for-implementers/)
- [OTFFT documentation](http://wwwa.pikara.ne.jp/okojisan/otfft-en/stockham1.html)
