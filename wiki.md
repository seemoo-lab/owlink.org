---
layout: page
title: Wiki
permalink: /wiki/
---

### What is Apple Wireless Direct Link (AWDL)?

According to [US patent 20180083858A1](https://patents.google.com/patent/US20180083858A1/en), AWDL was designed as a successor to the unsuccessful Wi-Fi IBSS a.k.a. ad hoc mode:

> The limitations of IBSS mode (and its Wi-Fi infrastructure predecessors) led the Wi-Fi Alliance to define Wi-Fi Direct. Further, due to concerns regarding Wi-Fi Direct, Apple Wireless Direct Link (AWDL) was developed by Apple and eventually adopted by the Wi-Fi Alliance as the basis for Neighbor Awareness Networking (NAN).


### How does AWDL work?

In technical terms, [we found](/publications/) that AWDL works essentially works as follow:

> In short, each AWDL node announces a sequence of Availability Windows (AWs) indicating its readiness to communicate with other AWDL nodes. An elected master node synchronizes these sequences. Outside the AWs, nodes can tune their Wi-Fi radio to a different channel to communicate with an access point, or could turn it off to save energy.

We published an [Wireshark dissector for AWDL](/code/) if you are interested in the frame format details or if you want to know which other protocols might use AWDL.

### Which services use AWDL?

We compiled a non-exhaustive list with applications which use (✓) or do not use (✗) AWDL, an access point (AP) network, or Bluetooth Low Energy (BLE). We mark entries that require further investigation with (?). If you have updates, feel free to [contact us](/contact/).

| Service                | AWDL | AP   | BLE  | Comment  |
| ---------------------- |:----:|:----:|:----:| -------- |
| AirDrop                | ✓    | ✗    | ✓    | Exchange files between two adjacent devices. |
| Wi-Fi Password Sharing | ✗    | ✗    | ?    | Uses "[a similar mechanism to AirDrop.][wifi-password-sharing]"
| AirPlay                | ✓    | ✓    | ?    | Stream media to an Apple TV, HomePod, etc. |
| CarPlay                | ?    | ?    | ?    | Apparently [uses iPhone's hot spot function.][carplay-wwdc2017] |
| Auto Unlock            | ✓    | ✗    | ✓    | Unlock Mac with Apple Watch. Uses AWDL to enable direct communication for ranging process. Part of [*Continuity* framework][continuity]. |
| Handoff                | ✗    | ✗    | ✓    | "[Each Mac, iPhone, iPad, or iPod touch has Wi-Fi turned on][handoff]" is not a requirement. Part of [*Continuity* framework][continuity]. |
| Universal Clipboard    | ?    | ?    | ?    | Part of [*Continuity* framework][continuity]. |
| iPhone Cellular Calls  | ✗    | ✓    | ✗    | Requirement: "[Each device is connected to the same network using Wi-Fi or Ethernet][phone]." Part of [*Continuity* framework][continuity]. |
| iOS Automatic Setup    | ?    | ?    | ?    | [Transfers (complete) backup][ios-backup] from one device to another. |
| Setup Apple TV         | ?    | ?    | ?    |          |

[carplay-wwdc2017]: https://developer.apple.com/videos/play/wwdc2017/717/ "Developing Wireless CarPlay Systems, WWDC 2017"
[continuity]: https://support.apple.com/en-us/HT204681 "Use Continuity to connect your Mac, iPhone, iPad, iPod touch, and Apple Watch"
[handoff]: https://support.apple.com/en-us/HT204681#handoff
[phone]: https://support.apple.com/en-us/HT204681#phone
[wifi-password-sharing]: https://www.apple.com/business/docs/iOS_Security_Guide.pdf "Wi-Fi password sharing"
[ios-backup]: https://support.apple.com/en-us/HT201269 "Transfer content from your previous iOS device to your new iPhone, iPad, or iPod touch"
