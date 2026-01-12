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

macOS 安装器被封装在 `.dmg` 中。您需要打开以得到 `.pkg` 安装器。

如果有两个 `.dmg` 文件，文件名中含有 `x86` 的是为载有 Intel 芯片的 macOS 系统 而 文件名中含有 `arm` 的是为载有 Apple M 芯片的 macOS 系统。然而，如果您在载有 Apple M 芯片的 macOS 系统上使用 Rosetta 模式，您必须使用 `x86`安装器，但其可能导致插件性能下降。

在 macOS 系统上，插件需要 Metal 支持。插件无法在 macOS 10.13 之前的系统上运行，与 macOS 13 之前的系统无法保证兼容性。除此以外，如果您对安装过程中的警告信息感到困惑，请参阅[在 Mac 上安全地打开 App](https://support.apple.com/zh-cn/102445)。

如果您无法通过 macOS 官方渠道更新系统，您可以尝试通过 [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher) 更新系统（使用风险自负）。

## Windows 安装

Windows 安装器后缀名为 `.exe`。

如果有两个 `.exe` 安装器，文件名中含有 `x86` 的是为 x86-64 架构的 Windows 系统 而 文件名中含有 `arm` 的是为 ARM64 架构的 Windows 系统。您可以通过 `设置` - `系统` - `关于` - `设备规格` - `系统类型` 查看。

在 Windows 系统上，插件需要 Direct2D 支持。插件与 Windows 10 及之后版本兼容。

## Linux 安装

Linux 插件被压缩在 `.zip` 中。您需要解压后自行将 `*.vst3` 文件移动到正确的文件夹，例如`~/.vst3`。

如果有两个 `.zip` 文件，文件名中含有 `x86` 的是为 x86-64 架构的 Linux 系统 而 文件名中含有 `arm` 的是为 ARM64 架构的 Linux 系统。

在 Linux 系统上，插件无法提供硬件渲染。因为插件在 Ubuntu 22.04 上编译（动态链接依赖），我无法保证其与 Linux 发行版的兼容性。我推荐您从源码编译插件。