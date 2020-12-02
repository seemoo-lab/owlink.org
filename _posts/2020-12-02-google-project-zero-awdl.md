---
layout: post
title:  "Google Project Zero: AWDL-based Zero-Click Exploit"
date:   2020-12-02 11:00:00 +0200
---

Ian Beer of Google Project Zero has a [cool writeup of a zero-click exploit](https://googleprojectzero.blogspot.com/2020/12/an-ios-zero-click-radio-proximity.html) that uses a vulnerability in the AWDL action frame parsing code. Thanks for crediting our efforts!

> There are a series of papers from the Secure Mobile Networking Lab at TU Darmstadt in Germany (also known as SEEMOO) which look at AWDL. The researchers there have done a considerable amount of reverse engineering (in addition to having access to some leaked Broadcom source code) to produce these papers; they are invaluable to understand AWDL and pretty much the only resources out there. 
> 
> The first paper One Billion Apples’ Secret Sauce: Recipe for the Apple Wireless Direct Link Ad hoc Protocol covers the format of the frames used by AWDL and the operation of the channel-hopping mechanism.
>
> The second paper A Billion Open Interfaces for Eve and Mallory: MitM, DoS, and Tracking Attacks on iOS and macOS Through Apple Wireless Direct Link focuses more on Airdrop, one of the OS features which uses AWDL. This paper also examines how Airdrop uses Bluetooth Low Energy advertisements to enable AWDL interfaces on other devices.
> 
> The research group wrote an open source AWDL client called OWL (Open Wireless Link). Although I was unable to get OWL to work it was nevertheless an invaluable reference and I did use some of their frame definitions.