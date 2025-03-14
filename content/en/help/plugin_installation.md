---
title: Plugin Installation
linkTitle: Plugin Installation
---

## Plugin Formats

- VST(VST2): not included
    - It is no longer possible to get permission from Steinberg. If you do need such format, you have to build it by yourself.
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

On macOS, the plugin requires Metal support. The plugin is not compatible with macOS prior to macOS 10.13 and is not guaranteed to be compatible with macOS prior to macOS 13. Besides that, you may refer to [Safely open apps on your Mac](https://support.apple.com/en-us/102445) if you are confused by the alert given by your OS.

If you cannot upgrade your system through official macOS support, you may upgrade it with [OpenCore Legacy Patcher](https://github.com/dortania/OpenCore-Legacy-Patcher) (use at your own risk).

## Windows Installation

The Windows installer file extension is `.exe`.

On Windows, the plugin requires Direct2D support. The plugin is compatible with Windows 10 and later.

## Linux Installation

The Linux plugins are compressed in a `.zip` file. You need to unzip it and manually move the `*.vst3` file to the correct folder, such as `~/.vst3`.

On Linux, the plugin does not have hardware acceleration. The plugin is compatible with Mainstream Linux distributions.

## Subscribe to Release Notifications

> If you want to subscribe to release notifications of a plugin (including pre-releases):

1. Register a GitHub account and set your email address.
2. Go to the plugin's project page, e.g., https://github.com/ZL-Audio/ZLEqualizer.
3. On the right-top corner, there is a `Watch` button. Click the button, select `Custom`, tick `Releases`, and click `Apply`.
4. Done!

> If you want to unsubscribe, do the opposite:

1. Go to the plugin's project page, e.g., https://github.com/ZL-Audio/ZLEqualizer.
2. On the right-top corner, there is a `Watch` button. Click the button and select `Ignore`.
3. Done!