---
layout: page
title: Code
permalink: /code/
---

<div class="screenshot">
	<a href="/assets/wireshark.png">
		<img title="Screenshot of our AWDL Wireshark dissector" alt="Screenshot of our AWDL Wireshark dissector" src="/assets/wireshark.png">
	</a>
	<div class="caption">Screenshot of our AWDL Wireshark dissector</div>
</div>


## Wireshark Dissector

Wireshark dissector for Apple Wireless Direct Link (AWDL) and Apple's CoreCapture logging framework.

<a href="https://github.com/seemoo-lab/wireshark-awdl"><svg class="svg-icon"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg> <span>Code</span></a>


## proxAWDL

Tunnels a regular TCP connection through an AWDL link by exploiting the [NetService](https://developer.apple.com/documentation/foundation/netservice) API.
On macOS, you may instead also use the special XNU socket option [`SO_RECV_ANYIF`](https://opensource.apple.com/source/xnu/xnu-4570.41.2/bsd/sys/socket.h) (`0x1104`) to allow a socket to send and receive via AWDL.

<a href="https://github.com/seemoo-lab/proxawdl"><svg class="svg-icon"><use xlink:href="{{ '/assets/minima-social-icons.svg#github' | relative_url }}"></use></svg> <span>Code</span></a>
