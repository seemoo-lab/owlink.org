---
layout: post
title:  "BTLEmap wins ACM WiSec ’20 Best Demo Award"
date:   2020-07-10 15:00:00 +0200
---

Our demo on **BTLEmap: Nmap for Bluetooth Low Energy** just received the *Best Demo Award* at [ACM WiSec ’20](https://wisec2020.ins.jku.at).
In short, BTLEmap allows you to view and inspect nearby Bluetooth Low Energy devices. The tool features a proximity view, a fingerprinting module, and a dissector for vendor-specific advertisements.
The code is available on [GitHub](https://github.com/seemoo-lab/BTLEmap).
Read the [paper](/publications/) or watch the talk for a short walk-through.

<div class="video-container-wide"><iframe src="https://www.youtube.com/embed/wsBZIqJHCHo?rel=0" allow="autoplay; encrypted-media" allowfullscreen></iframe></div>

## Abstract

> The market for Bluetooth Low Energy (BLE) devices is booming and, at the same time, has become an attractive target for adversaries. To improve BLE security at large, we present BTLEmap, an auditing application for BLE environments. BTLEmap is inspired by network discovery and security auditing tools such as Nmap for IP-based networks. It allows for device enumeration, Generic Attribute Profile (GATT) service discovery, and device fingerprinting. It also features a BLE advertisement dissector, data exporter, and a user-friendly UI including a proximity view. BTLEmap currently runs on iOS and macOS using Apple’s CoreBluetooth API but also accepts alternative data inputs such as a Raspberry Pi to overcome the restricted vendor API. The open-source project is under active development and will provide more advanced capabilities such as long-term device tracking (in spite of MAC address randomization) in the future.
