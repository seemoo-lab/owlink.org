---
layout: post
title:  "MobiCom ’18 Paper Accepted"
date:   2018-07-23 14:52:00 +0200
---

Our paper on reverse engineering and analyzing the Apple Wireless Direct Link (AWDL) ad hoc protocol **One Billion Apples’ Secret Sauce: Recipe for the Apple Wireless Direct Link Ad hoc Protocol** was accepted at [ACM MobiCom ’18](https://sigmobile.org/mobicom/2018/program.php). Read our paper [here](/publications/). See you in New Delhi in October!

## Abstract

> Apple Wireless Direct Link (AWDL) is a proprietary and undocumented IEEE 802.11-based ad hoc protocol. Apple first introduced AWDL around 2014 and has since integrated it into its entire product line, including iPhone and Mac. While we have found that AWDL drives popular applications such as AirPlay and AirDrop on more than one billion end-user devices, neither the protocol itself nor potential security and Wi-Fi coexistence issues have been studied. In this paper, we present the operation of the protocol as the result of binary and runtime analysis. In short, each AWDL node announces a sequence of Availability Windows (AWs) indicating its readiness to communicate with other AWDL nodes. An elected master node synchronizes these sequences. Outside the AWs, nodes can tune their Wi-Fi radio to a different channel to communicate with an access point, or could turn it off to save energy. Based on our analysis, we conduct experiments to study the master election process, synchronization accuracy, channel hopping dynamics, and achievable throughput. We conduct a preliminary security assessment and publish an open source Wireshark dissector for AWDL to nourish future work.

## Video Teaser

<div class="video-container-wide"><iframe src="https://www.youtube.com/embed/bKG8ZZq4oTo?rel=0" allow="autoplay; encrypted-media" allowfullscreen></iframe></div>
