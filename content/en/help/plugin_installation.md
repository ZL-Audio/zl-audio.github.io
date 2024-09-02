---
title: Plugin Installation
linkTitle: Plugin Installation
---

## Plugin Formats

- VST3: included in macOS, Windows and Linux installers
- AU: included in macOS installers
- LV2: included in Windows and Linux installers
- AAX: included in macOS and Windows installers
    - because AAX requires code-signing, some installers may not include/update this format
- CLAP: not included, awaiting official support from JUCE
- Standalone: included in macOS, Windows and Linux installers of some plugins
    - can serve as an independent application. You have to set up routing properly to make it functional.

<img src="/images/vst3.png" style="width: 120pt; max-width: 100%; height: auto"/>

VST® is a trademark of Steinberg Media Technologies GmbH, registered in Europe and other countries.

## Signing/Notarization

All installers have not been notarized. You should decide whether to trust the installers. Alternatively, you can build the plugin from the project source code (except AAX format).

## macOS Installation

The macOS installer is packaged in a `.dmg` file. You need to open it to use the `.pkg` installer.

On macOS, the plugin requires Metal support. For some unknown reason, the plugin is not compatible with macOS prior to macOS 12 (hopefully you can build it locally on macOS 10.15.4). Besides that, you may refer to [Safely open apps on your Mac](https://support.apple.com/en-us/102445) if you are confused by the alert given by your OS.

If you wish to run it on a system prior to macOS 12, you can build the plugin locally or updating your system. If you cannot update your system through official macOS support, you may update it with [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher) (use at your own risk).

## Windows Installation

The Windows installer file extension is `.exe`.

On Windows, the plugin requires Direct2D support. The plugin is compatible with Windows 10 and later.

If your hardware system is not well-suited for JUCE's Direct2D feature, or if you are using Windows 7, you can try the installer with `Software` in the file name. This installer sets up the plugin to use software rendering. Please note that software rendering may result in worse performance in the user interface compared to hardware rendering.

## Linux Installation

The Linux plugins are compressed in a `.zip` file. You need to unzip it and manually move the `*.vst3` file to the correct folder, such as `~/.vst3`.

On Linux, the plugin does not have hardware acceleration. The plugin is compatible with Mainstream Linux distributions.