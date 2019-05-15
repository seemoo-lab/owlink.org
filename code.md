---
layout: page
title: Code
permalink: /code/
---

As part of our research, we developed several tools including implementations of AWDL and AirDrop that we publish as open source software.

<div class="screenshot">
	<a href="/assets/owl.png">
		<img title="Console output of our AWDL implementation OWL" alt="Console output of our AWDL implementation OWL" src="/assets/owl.png">
	</a>
	<div class="caption">Console output of our AWDL implementation <i>OWL</i></div>
</div>

<img class="logo-left" title="OWL logo" alt="OWL logo" src="/assets/logos/owl.png">

## OWL

*OWL* is a an open implementation of the Apple Wireless Direct Link (AWDL) protocol written in C. It currently runs on Linux and macOS and requires a Wi-Fi card with support for monitor mode and frame injection.

<a href="https://github.com/seemoo-lab/owl"><svg class="svg-icon"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg> <span>Code</span></a>


<img class="logo-left" title="AirDrop logo" alt="AirDrop logo" src="/assets/logos/airdrop.png">

## OpenDrop

*OpenDrop* is a command-line tool written in Python that allows sharing files between devices directly over Wi-Fi. Its unique feature is that it is protocol-compatible with Apple AirDrop which allows to share files with Apple devices running iOS and macOS. To support communication with Apple devices, OpenDrop needs to run over an AWDL-compatible link and, thus, supports macOS and any platform that supports OWL.

<a href="https://github.com/seemoo-lab/opendrop"><svg class="svg-icon"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg> <span>Code</span></a>


<div class="screenshot">
	<a href="/assets/wireshark.png">
		<img title="Wireshark dissecting an AWDL frame" alt="Wireshark dissecting an AWDL frame" src="/assets/wireshark.png">
	</a>
	<div class="caption">Wireshark dissecting an AWDL frame</div>
</div>

<img class="logo-left" title="Wireshark logo" alt="Wireshark logo" src="/assets/logos/wireshark.png">

## Protocol Dissectors

Wireshark dissector for Apple Wireless Direct Link (AWDL) and Apple's CoreCapture logging framework.
**Note:** The AWDL dissector is included in the official Wireshark builds [since version 3.0.0](https://www.wireshark.org/docs/relnotes/wireshark-3.0.0.html).

<a href="https://github.com/seemoo-lab/wireshark-awdl"><svg class="svg-icon"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg> <span>Code</span></a>

## proxAWDL

Tunnels a regular TCP connection through an AWDL link by exploiting the [NetService](https://developer.apple.com/documentation/foundation/netservice) API.
On macOS, you may instead also use the special XNU socket option [`SO_RECV_ANYIF`](https://opensource.apple.com/source/xnu/xnu-4570.41.2/bsd/sys/socket.h) (`0x1104`) to allow a socket to send and receive via AWDL.

<a href="https://github.com/seemoo-lab/proxawdl"><svg class="svg-icon"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg> <span>Code</span></a>
