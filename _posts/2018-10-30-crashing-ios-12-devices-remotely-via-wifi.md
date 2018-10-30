---
layout: post
title:  "Crashing iOS 12 Devices Remotely via Wi-Fi"
date:   2018-10-30 20:03:00 +0200
---

We have disclosed a vulnerability (CVE-2018-4368) to Apple that allowed us to crash [iOS](https://support.apple.com/en-in/HT209192) (and also [macOS](https://support.apple.com/en-in/HT209193), [tvOS](https://support.apple.com/en-in/HT209194), and [watchOS](https://support.apple.com/en-in/HT209195)) devices remotely via Wi-Fi.
We demonstrate a working exploit which allows us to target a single device but also all devices in proximity in parallel. The exploit does not require any user interaction and, thus, might force a device into an indefinite boot loop.
Apple has just released security updates for all of its operating systems which we recommend everyone to install.

This work was a collaboration between the [Secure Mobile Networking Lab headed by Prof. Matthias Hollick](https://www.seemoo.tu-darmstadt.de) from TU Darmstadt and [Prof. Guevara Noubir](http://www.ccs.neu.edu/home/noubir/) from Northeastern University.

## Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/M5D9NeKapUo?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
