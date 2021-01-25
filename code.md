---
layout: page
title: Code
permalink: /code/
---

As part of our research, we developed several tools including implementations of AWDL and AirDrop that we publish as open source software.

<div class="screenshot">
	<a href="{% link /assets/owl.png %}">
		<img title="Console output of our AWDL implementation OWL" alt="Console output of our AWDL implementation OWL" src="/assets/owl.png">
	</a>
	<div class="caption">Console output of our AWDL implementation <i>OWL</i></div>
</div>

<img class="logo-left" title="OWL logo" alt="OWL logo" src="{% link /assets/logos/owl.svg %}">

## OWL

*OWL* is a an open implementation of the Apple Wireless Direct Link (AWDL) protocol written in C. It currently runs on Linux and macOS and requires a Wi-Fi card with support for monitor mode and frame injection.

<a href="https://github.com/seemoo-lab/owl"><svg class="svg-icon"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg> <span>Code</span></a>


<img class="logo-left" title="AirDrop logo" alt="AirDrop logo" src="{% link /assets/logos/airdrop.svg %}">

## OpenDrop

*OpenDrop* is a command-line tool written in Python that allows sharing files between devices directly over Wi-Fi. Its unique feature is that it is protocol-compatible with Apple AirDrop which allows to share files with Apple devices running iOS and macOS. To support communication with Apple devices, OpenDrop needs to run over an AWDL-compatible link and, thus, supports macOS and any platform that supports OWL.

<a href="https://github.com/seemoo-lab/opendrop"><svg class="svg-icon"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg> <span>Code</span></a>


## OpenWifiPass

*OpenWifiPass* is a command-line tool written in Python that allows for [sharing a Wi-Fi password with macOS or iOS devices](https://support.apple.com/en-us/HT209368). OpenWifiPass currently only supports the grantor role of Apple's Wi-Fi Password Sharing protocol.

<a href="https://github.com/seemoo-lab/openwifipass"><svg class="svg-icon"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg> <span>Code</span></a>


<img class="logo-left" title="BTLEmap logo" alt="BTLEmap logo" src="{% link /assets/logos/btlemap.png %}">

## BTLEmap

*BTLEmap* is an auditing tool for Bluetooth Low Energy (BLE) environments. It allows for viewing and inspecting nearby BLE devices. The tool features a proximity view, a fingerprinting module, and a dissector for vendor-specific advertisements.

<a href="https://github.com/seemoo-lab/btlemap"><svg class="svg-icon"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg> <span>Code</span></a>


<div class="screenshot">
	<a href="{% link /assets/wireshark.png %}">
		<img title="Wireshark dissecting an AWDL frame" alt="Wireshark dissecting an AWDL frame" src="{% link /assets/wireshark.png %}">
	</a>
	<div class="caption">Wireshark dissecting an AWDL frame</div>
</div>

<img class="logo-left" title="Wireshark logo" alt="Wireshark logo" src="{% link /assets/logos/wireshark.png %}">

## Protocol Dissectors

Wireshark dissector for Apple Wireless Direct Link (AWDL) and Apple's CoreCapture logging framework.
**Note:** The AWDL dissector is included in the official Wireshark builds [since version 3.0.0](https://www.wireshark.org/docs/relnotes/wireshark-3.0.0.html).

<a href="https://github.com/seemoo-lab/wireshark-awdl"><svg class="svg-icon"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg> <span>Code</span></a>

## proxAWDL

Tunnels a regular TCP connection through an AWDL link by exploiting the [NetService](https://developer.apple.com/documentation/foundation/netservice) API.
On macOS, you may instead also use the special XNU socket option [`SO_RECV_ANYIF`](https://opensource.apple.com/source/xnu/xnu-4570.41.2/bsd/sys/socket.h) (`0x1104`) to allow a socket to send and receive via AWDL.

<a href="https://github.com/seemoo-lab/proxawdl"><svg class="svg-icon"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg> <span>Code</span></a>
