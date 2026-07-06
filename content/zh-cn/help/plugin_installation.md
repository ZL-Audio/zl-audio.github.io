---
title: 插件安装
linkTitle: 插件安装
weight: 1
---

## 插件格式

- VST(VST2)：不提供
    - 现已无法从 Steinberg 获得发行许可。如果确有需要，请自行从代码进行构建。
- VST3：在 macOS、Windows 和 Linux 安装包中提供
- AU：在 macOS 安装包中提供
- LV2：在 Windows 和 Linux 安装包中提供
- AAX：在 macOS 和 Windows 安装包中提供
    - 因为该格式的插件需要额外的签名，部分安装包可能不包括/不更新该格式
- CLAP：不提供，等待 JUCE 官方支持
- Standalone：在部分插件的 macOS、Windows 和 Linux 安装包中提供
    - 该格式为独立运行的软件，需要设置音频路由以使其工作

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## 签名/公正

所有安装器均未经过公证，您需要自行选择是否信任安装器。当然，您也可以通过项目源码构建该插件（AAX 格式除外）。

## macOS 安装

macOS 安装器被封装在 `.dmg` 文件中。您需要打开它以使用 `.pkg` 安装器。

如果有两个 `.dmg` 文件，文件名中含有 `x86-64` 的是为载有 Intel 芯片的 macOS 系统准备的，而文件名中含有 `arm64` 的是为载有 Apple M 芯片的 macOS 系统准备的。然而，如果您在载有 Apple M 芯片的 macOS 系统上使用 Rosetta 模式，您必须使用含有 `x86-64` 的安装器，但这可能会导致插件性能下降。

在 macOS 系统上，插件需要 Metal 支持。插件无法在 macOS 10.13 之前的系统上运行，且不保证与 macOS 13 之前的系统兼容。除此以外，如果您对操作系统给出的警告信息感到困惑，请参阅[在 Mac 上安全地打开 App](https://support.apple.com/zh-cn/102445)。

如果您无法通过官方 macOS 渠道更新系统，您可以尝试使用 [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher) 进行升级（使用风险自负）。

{{% alert title="Warning" color="warning" %}}
在可以预见的未来（macOS 28 发布后），`x86-64` 版本将不再被提供。
{{% /alert %}}

## Windows 安装

Windows 安装器文件的后缀名为 `.msi`。

如果有两个 `.msi` 安装器，文件名中含有 `x86-64` 的是为 x86-64 架构的 Windows 系统准备的。您可以通过 `设置` - `系统` - `关于` - `设备规格` - `系统类型` 来查看您的系统架构。

如果有三个 `.msi` 安装器，文件名中含有 `x86-64-AVX2` 的是为支持 AVX2 的 x86-64 架构 Windows 系统准备的，获取更多信息请参见 [AVX2 支持](#avx2-支持)。

在 Windows 系统上，插件需要 Direct2D 支持。插件与 Windows 10 及更高版本兼容。

{{% alert title="Warning" color="warning" %}}
对于 Windows on ARM 用户，您需要选择与您的宿主（DAW）匹配的版本。以下信息可能已经过时。请参考您所使用宿主的官方支持文档。

请选择带有 `arm64` 的版本：如果您的 DAW 是纯 ARM64 架构，例如 Fender Studio Pro (ARM64)、Bitwig (ARM64)。该版本将获得最佳的原生性能。

请选择带有 `x86-64` 的版本：如果您的 DAW 是 x86-64 或 ARM64EC 架构，例如 Reaper (ARM64EC)、Cubase (ARM64EC)、FL Studio (x86_64)、Ableton (x86_64)。由于系统需要进行转译，该版本的性能会有所下降。
{{% /alert %}}

## Linux 安装

Linux 插件被压缩在 `.zip` 文件中。您需要解压它并手动将 `*.vst3` 文件移动到正确的文件夹中，例如 `~/.vst3`。

如果有两个 `.zip` 文件，文件名中含有 `x86-64` 的是为 x86-64 架构的 Linux 系统准备的，而文件名中含有 `arm64` 的是为 ARM64 架构的 Linux 系统准备的。

如果有三个 `.zip` 文件，文件名中含有 `x86-64-AVX2` 的是为支持 AVX2 的 x86-64 架构 Linux 系统准备的，获取更多信息请参见 [AVX2 支持](#avx2-支持)。

在 Linux 系统上，插件不支持硬件加速。插件是在 Ubuntu 22.04 上构建的，带有动态链接依赖。因此，我无法保证其与其他 Linux 发行版的兼容性。我建议您从源码编译该插件。

{{% alert title="Warning" color="warning" %}}
在可以预见的未来（Ubuntu 26.04 发布后），插件将在 Ubuntu 24.04 上构建，这将导致其与之前的 Linux 版本不兼容。
{{% /alert %}}

## AVX2 支持

以下 CPU 应支持 AVX2：

- Intel：Haswell 处理器（2013 年第二季度）及更新型号，不包括标有 Celeron 和 Pentium 的型号（对于 Celeron 和 Pentium，请按照[指南](https://www.intel.com/content/www/us/en/support/articles/000090473/processors/intel-core-processors.html)检查其 AVX2 支持情况）。
- AMD：Excavator 处理器（2015 年第二季度）及更新型号。

在支持 AVX2 的机器上，与 `x86-64` 版本相比，`x86-64-AVX2` 版本可显著降低 CPU 使用率（最高可降低 50%）。

在不支持 AVX2 的机器上，使用 `x86-64-AVX2` 版本极有可能会立即导致崩溃。

## 旧版安装指南
### macOS 安装

macOS 安装器被封装在 `.dmg` 中。您需要打开以得到 `.pkg` 安装器。

如果有两个 `.dmg` 文件，文件名中含有 `x86` 的是为载有 Intel 芯片的 macOS 系统 而 文件名中含有 `arm` 的是为载有 Apple M 芯片的 macOS 系统。然而，如果您在载有 Apple M 芯片的 macOS 系统上使用 Rosetta 模式，您必须使用 `x86`安装器，但其可能导致插件性能下降。

在 macOS 系统上，插件需要 Metal 支持。插件无法在 macOS 10.13 之前的系统上运行，与 macOS 13 之前的系统无法保证兼容性。除此以外，如果您对安装过程中的警告信息感到困惑，请参阅[在 Mac 上安全地打开 App](https://support.apple.com/zh-cn/102445)。

如果您无法通过 macOS 官方渠道更新系统，您可以尝试通过 [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher) 更新系统（使用风险自负）。

{{% alert title="Warning" color="warning" %}}
在可以预见的未来（macOS 28 发布后），`x86` 版本将不再被提供。
{{% /alert %}}

### Windows 安装

Windows 安装器后缀名为 `.exe`。

如果有两个 `.exe` 安装器，文件名中含有 `x86` 的是为 x86-64 架构的 Windows 系统。您可以通过 `设置` - `系统` - `关于` - `设备规格` - `系统类型` 查看。

在 Windows 系统上，插件需要 Direct2D 支持。插件与 Windows 10 及之后版本兼容。

{{% alert title="Warning" color="warning" %}}
对于 Windows on ARM 用户，请务必根据您使用的宿主来选择版本，而不仅仅是根据操作系统。以下信息有可能过时。请查看您所使用宿主的官方支持文档。

请选择带有 `arm` 的版本：如果您的 DAW 是纯 ARM64 架构，例如 Fender Studio Pro (ARM64)、Bitwig (ARM64)。该版本将提供最佳的原生性能。

请选择带有 `x86` 的版本：如果您的 DAW 是 x86-64 或 ARM64EC 架构，例如 Reaper (ARM64EC)、Cubase (ARM64EC)、FL Studio (x86_64)、Ableton (x86_64)。由于系统需要进行转译，该版本的性能会有所下降。
{{% /alert %}}

### Linux 安装

Linux 插件被压缩在 `.zip` 中。您需要解压后自行将 `*.vst3` 文件移动到正确的文件夹，例如`~/.vst3`。

如果有两个 `.zip` 文件，文件名中含有 `x86` 的是为 x86-64 架构的 Linux 系统 而 文件名中含有 `arm` 的是为 ARM64 架构的 Linux 系统。

在 Linux 系统上，插件无法提供硬件渲染。因为插件在 Ubuntu 22.04 上编译（动态链接依赖），我无法保证其与 Linux 发行版的兼容性。我推荐您从源码编译插件。

{{% alert title="Warning" color="warning" %}}
在可以预见的未来（Ubuntu 26.04 发布后），插件将在 Ubuntu 24.04 上编译，而这将导致其与之前的 Linux 版本不兼容。
{{% /alert %}}