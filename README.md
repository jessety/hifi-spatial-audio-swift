<img src="https://raw.githubusercontent.com/highfidelity/hifi-spatial-audio-swift/main/utilities/spatialAudioLogo.svg" alt="High Fidelity Spatial Audio" width="375"/>

&nbsp;

[![GitHub issues](https://img.shields.io/github/issues/highfidelity/hifi-spatial-audio-swift?style=flat-square)](https://github.com/highfidelity/hifi-spatial-audio-swift/issues)

[![Discord](https://img.shields.io/discord/789545374837768242?label=discord&style=flat-square)](https://discord.gg/GrhxWPrp)
[![Twitter Follow](https://img.shields.io/twitter/follow/HighFidelityXR?style=flat-square)](https://twitter.com/HighFidelityXR)

The High Fidelity Spatial Audio Client Library for Swift allows developers to integrate High Fidelity's spatial audio technology into their projects.

# Getting Started
## Usage in Your iOS Apps
If you'd like to make use of the `HiFiSpatialAudio` Swift Package in your iOS apps:
1. Open your iOS app's code in XCode.
2. Click `File` in the top left, then click `Swift Packages`, then click `Add Package Dependency...`
3. Under "Search or enter package repository URL", paste the following URL:
    - https://github.com/highfidelity/hifi-spatial-audio-swift/
4. Click `Next`, then follow XCode's instructions.

## You'll Need a Developer Account
To use the Spatial Audio API, you'll need to sign up for a High Fidelity Developer Account. Sign up for free at [account.highfidelity.com](https://account.highfidelity.com).

## Documentation
[Click here to view documentation on the latest version of the Spatial Audio Client Library for Swift.](https://docs.highfidelity.com/swift/latest/index.html)

## Examples
You can explore some of the features of the Swift client library by compiling and running any of the included Test Apps in [the Test Apps subdirectory of this repository](https://github.com/highfidelity/hifi-spatial-audio-swift/tree/main/Test%20Apps). All of the sample apps run on an iPhone Simulator via XCode and on real iOS hardware.
- The `HiFiSpatialAudioTest` app is the simplest, most straightforward, and closest to "production-ready".
- The `HiFiUnionSquare` app is a complex app which uses device sensor fusion to place your avatar on a map of Union Square. Your avatar's position and orientation are driven by your phone's real-world position and orientation.
- The **(unfinished)** `HiFiPlace` app shows your avatar and other avatars on a map.

## Release Notes
Release notes for the Spatial Audio Client Library are available on [the GitHub releases page](https://github.com/highfidelity/hifi-spatial-audio-swift/releases).

## Additional Details
The `HiFiSpatialAudio` Swift Package is a Swift version of High Fidelity's Spatial Audio client library for TypeScript. [Click here to access documentation for the TypeScript version of our client library.](https://docs.highfidelity.com/js/latest/index.html)

The goal of this project is to mirror the functionality of the TypeScript library for iOS applications. However, you may find that not all features from the TS client library are present in the Swift client library. Additionally, some functionality may be different, and some functionality may be buggy.

# Important Information

## Audio Peripherals and Bluetooth
By default, the `HiFiSpatialAudio` Swift package will automatically use whatever stereophonic headphones or AirPods that may be connected by wire or by Bluetooth, using the Apple-defined behavior of “last peripheral connected, wins”. If there is no such stereo peripheral connected, the two speakers on the phone are used, where the “bottom” speaker is the left channel, and the “top” speaker is the right channel. The phone microphone is used.

The constructor for the `HiFiCommunicator` object also accepts a boolean named argument called `echoCancellingVoiceProcessingInMono`, which instead uses hardware echo cancellation and automatic gain control, but the output is monophonic and of “speech” quality. In this mode, wireless peripherals are connected via the “hands-free” Bluetooth mode. In this mode, if the wireless hardware contains a microphone, that microphone will be used for audio input.

# Other Information

## Explanation of Package Dependencies
The `HiFiSpatialAudio` package relies on several Swift Package Dependencies, all of which should be automatically downloaded before your project is built.

These Swift Package Dependencies include:
- `Gzip` (for un-gzipping binary peer data sent from the mixer)
- `Promises` (for JavaScript-like Promises)
- `Starscream` (for Web Sockets)
- A custom version of `WebRTC` for iOS, which includes stereo output support (for...WebRTC stuff)

## Generating Documentation
First, install Jazzy with `gem install jazzy` from a Terminal window.

Then, run the following command from the repository directory to generate documentation for the `HiFiSpatialAudio` Swift package:

```
jazzy
```
