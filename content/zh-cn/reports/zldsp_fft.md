---
title: 高性能 FFT 库 zldsp::fft
date: 2026-08-04
author: zsliu98
tags:
  - FFT
  - spectrum
weight: 10
---

`zldsp::fft` 是一个基于 [Google Highway](https://github.com/google/highway) 构建的 header-only C++ 快速傅里叶变换（FFT）库，采用 Apache-2.0 许可证授权。源代码可在 [GitHub](https://github.com/ZL-Audio/zldsp_fft) 获取。`zldsp::fft` 支持 SSE2/SSE4/AVX2/NEON 等 SIMD 目标架构，且复数运算同时支持 AoS 与 SoA 两种数据布局。

## 使用方法

1. C++ 标准：C++20 或更高版本
2. Google Highway：项目中必须包含并链接 Google Highway。本库头文件要求能够正确引入并解析以下包含路径：
```cpp
#include <hwy/aligned_allocator.h>
#include <hwy/highway.h>
```

#### 编译选项

要启用 SIMD 加速，必须设置正确的编译器选项。Highway 将根据这些编译标志自动检测目标架构。

| SIMD 目标架构 | GCC/Clang                         | MSVC             |
| ----------- | --------------------------------- | ---------------- |
| SSE2        | `-march=x86-64`                   | 无需额外参数      |
| SSE4        | `-march=x86-64-v2 -mase -mpclmul` | 不支持           |
| AVX2        | `-march=x86-64-v3 -maes -mpclmul` | `/arch:AVX2`     |
| NEON        | `-march=armv8-a+simd`             | `/arch:armv8.0`  |

#### API

引入 `/src` 目录下的相关头文件即可。

`CFFT` 与 `RFFT` 均以浮点类型（如 `float` 或 `double`）作为模板参数，并通过以 2 为底的 FFT 阶数 **order** 进行实例化（其中大小 `size = 1 << order`）。

#### 复数 FFT (`CFFT`)

```cpp
#include "src/zldsp_fft_cfft.hpp"
#include <vector>
#include <complex>

// 基于 float 类型的 1024 (2^10) 点 CFFT
constexpr size_t order = 10; 
zldsp::fft::CFFT<float> cfft(order);

std::vector<std::complex<float>> in_buffer(1 << order);
std::vector<std::complex<float>> out_buffer(1 << order);

// 正向变换（AoS 到 AoS）
cfft.forward(in_buffer.data(), out_buffer.data());

// 逆向变换（AoS 到 AoS）
cfft.backward(out_buffer.data(), in_buffer.data());
```

#### 实数 FFT (`RFFT`)

```cpp
#include "src/zldsp_fft_rfft.hpp"
#include <vector>
#include <complex>

// 基于 float 类型的 1024 (2^10) 点 RFFT
constexpr size_t order = 10;
zldsp::fft::RFFT<float> rfft(order);

std::vector<float> real_in(1 << order);
std::vector<std::complex<float>> complex_out((1 << order) / 2 + 1);
std::vector<float> sqr_mag_out((1 << order) / 2 + 1);

// 正向变换（实数 到 AoS）
rfft.forward(real_in.data(), complex_out.data());

// 逆向变换（AoS 到 实数）
rfft.backward(complex_out.data(), real_in.data());

// 正向变换（实数 到 幅度平方）
rfft.forward_sqr_mag(real_in.data(), sqr_mag_out.data());
```

#### 数据布局 (AoS/SoA)

`CFFT` 与 `RFFT` 的复数运算均支持 AoS 和 SoA 布局：

AoS 在单个数组中交错存储实部与虚部数值：
```cpp
std::vector<std::complex<float>> out_buffer(1 << order);
```

SoA 在两个独立的数组中分别连续存储实部与虚部数值：

```cpp
std::vector<float> out_real(1 << order);
std::vector<float> out_imag(1 << order);
```

使用 SoA 的示例：
```cpp
#include "src/zldsp_fft_cfft.hpp"
#include <vector>
#include <complex>

// 基于 float 类型的 1024 (2^10) 点 CFFT
constexpr size_t order = 10; 
zldsp::fft::CFFT<float> cfft(order);

std::vector<std::complex<float>> in_buffer(1 << order);
std::vector<float> out_real(1 << order);
std::vector<float> out_imag(1 << order);

// 正向变换（AoS 到 SoA）
cfft.forward(in_buffer.data(), {out_real.data(), out_imag.data()});

// 逆向变换（SoA 到 AoS）
cfft.backward({out_real.data(), out_imag.data()}, in_buffer.data());
```

## 基准测试

以下是部分基准测试结果，测试代码可在 [GitHub](https://github.com/ZL-Audio/zldsp_fft_develop) 获取。作者已尽最大努力确保其他对比库的配置合理准确。所有库均使用 LLVM/Clang 或 Apple-Clang 编译构建，并采用 [Google Benchmark](https://github.com/google/benchmark/tree/main) 进行基准测试。

参与对比的库如下（各库受其自身的开源许可证约束）：

- `IPP`: [Intel® Integrated Performance Primitives](https://www.intel.com/content/www/us/en/developer/tools/oneapi/ipp.html)
- `vDSP`: [Apple vDSP](https://developer.apple.com/documentation/accelerate/vdsp)
- `ArmPL`: [Arm Performance Libraries](https://developer.arm.com/tools-and-software/arm-performance-libraries)
- `FFTW3`: [FFTW 3.3.10 Mirror](https://github.com/zsliu98/fftw3-mirror/tree/14eea039281b8c5bd83a20314afb402538fd986c)（支持 NEON，取 `FFTW_MEASURE` 与 `FFTW_ESTIMATE` 中的更优结果）
- `KFR`: [KFR 7.1.0](https://github.com/kfrlib/kfr/tree/main)
- `PFFFT`: [PFFFT 1.1.0](https://github.com/marton78/pffft)
- `zldsp`: [zldsp::fft](https://github.com/ZL-Audio/zldsp_fft)

下方展示的是阶数从 order 5 到 order 25 的实数 FFT（Real FFT）基准测试结果。

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

#### AMD EPYC 9V74 (GitHub Actions runner images)

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

## 设计架构

#### 低阶（Low Order）

对于低阶（`0 <= order <= 5`），`zldsp_fft` 使用专门定制的 CFFT 内核（kernel）。因此，每种变换尺寸都具有固定的实现代码，无需通用的阶段迭代与动态分发逻辑，从而在可行的情况下尽可能将数据保留在 SIMD 寄存器中。

#### 中阶（Medium Order）

对于中阶（`6 <= order <= switch_order - 1`），`zldsp_fft` 采用非原地（out-of-place）Stockham DIT 算法设计。其计算调度流程如下：

- 偶数阶（even order）：以 Radix-4 阶段开始，后续各级均为 Radix-4 阶段
- 奇数阶（odd order）：以 Radix-8 阶段开始，后续各级均为 Radix-4 阶段

中间数据采用对 SIMD 友好的 AoSoA 内存布局；第一级和最后一级则分别融合了与目标 AoS 或 SoA 输入/输出格式之间的转换操作。

#### 高阶（High Order）

对于高阶（`switch_order <= order`），`zldsp_fft` 采用 Cooley–Tukey 与 Stockham 混合架构设计。它利用 Radix-4 Cooley–Tukey DIF 宏阶段（macro stages），将大尺寸变换分解为大小大致可容纳在 L1 缓存内的微型 CFFT（micro CFFT）。随后，每个 micro CFFT 均通过中阶 Stockham DIT 设计完成计算。最后，利用可复用的终端缓冲区（terminal buffer）结合 SIMD 寄存器分块转置，将生成的矩阵重排为自然序（natural order）。

#### 阶数切换阈值（Switch Order）

中阶与高阶之间的分界阈值根据检测到的 L1 缓存大小推导得出。算法实现会估算出适合其工作集（working set）的最大变换阶数，并按如下规则选取：

`switch_order = maximum_L1_order + 4`

## 参考文献

- Van Loan, Charles. Computational frameworks for the fast Fourier transform. Society for Industrial and Applied Mathematics, 1992.
- [Notes on FFTs: for implementers](https://fgiesen.wordpress.com/2023/03/19/notes-on-ffts-for-implementers/)
- [OTFFT documentation](http://wwwa.pikara.ne.jp/okojisan/otfft-en/stockham1.html)
