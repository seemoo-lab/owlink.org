---
layout: post
title:  "Who Can Find My Devices?"
date:   2021-03-04 08:00:00 +0200
---

Almost two years ago, Apple announced its new crowd-sourced Bluetooth location tracking system for offline devices. Meanwhile, Apple released a [partial specification](https://developer.apple.com/find-my/specification/) of its system. However, many components remained undisclosed -- until now.

In our paper **Who Can _Find My_ Devices? Security and Privacy of Apple’s Crowd-Sourced Bluetooth Location Tracking System**, which was just accepted at the Privacy Enhancing Technologies Symposium (PETS) 2021, we reverse engineer other relevant components of the system and conduct a comprehensive security and privacy analysis.
We discover two distinct vulnerabilities, one of which ([CVE-2020-9986](https://support.apple.com/en-us/HT211849)) has already been fixed by Apple. [Read our paper now!]({% link publications.md %})

## OpenHaystack

In addition to our paper, we are happy to release _OpenHaystack_, a framework for tracking personal Bluetooth devices via Apple's massive Find My network. Check out the code on [GitHub](https://github.com/seemoo-lab/openhaystack) and build your own 'AirTags' today!

![OpenHaystack screenshot]({% link /assets/openhaystack-screenshot.png %})

## Abstract

> Overnight, Apple has turned its hundreds-of-million-device ecosystem into the world’s largest crowd-sourced location tracking network called offline finding (OF). OF leverages online finder devices to detect the presence of missing offline devices using Bluetooth and report an approximate location back to the owner via the Internet. While OF is not the first system of its kind, it is the first to commit to strong privacy goals. In particular, OF aims to ensure finder anonymity, untrackability of owner devices, and confidentiality of location reports. This paper presents the first comprehensive security and privacy analysis of OF. To this end, we recover the specifications of the closed-source OF protocols by means of reverse engineering. We experimentally show that unauthorized access to the location reports allows for accurate device tracking and retrieving a user’s top locations with an error in the order of 10 meters in urban areas. While we find that OF’s design achieves its privacy goals, we discover two distinct design and implementation flaws that can lead to a location correlation attack and unauthorized access to the location history of the past seven days, which could deanonymize users. Apple has partially addressed the issues following our responsible disclosure. Finally, we make our research artifacts publicly available.
