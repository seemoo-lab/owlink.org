---
layout: post
title:  "Howto: Use AirDrop on a Raspberry Pi 3"
date:   2019-05-16 07:28:00 +0200
---

In this article, we are going to get AirDrop running on a Raspberry Pi 3 (not B+, unfortunately) running Raspbian Stretch.
While AirDrop itself implements a HTTP-based protocol (see [OpenDrop](/code/)), it uses a dedicated Wi-Fi based link layer called Apple Wireless Direct Link (AWDL). In order to use AirDrop, we'll enable AWDL capabilities on the Raspberry Pi using [OWL](/code/), our open AWDL implementation. OWL is implemented as user space program and requires a Wi-Fi card with working monitor mode and frame injection.


## Enable monitor mode with frame injection

Since the BCM43430A1 Wi-Fi chip in the RPi3 does not support monitor mode out-of-the-box, we'll use [Nexmon](https://nexmon.org) to patch the firmware.
The following steps are adapted from the project's [README](https://github.com/seemoo-lab/nexmon/blob/master/README.md).

First, we need to install some dependencies.

```bash
sudo apt update && apt upgrade
sudo apt install raspberrypi-kernel-headers git \
                 libgmp3-dev gawk qpdf bison flex make
sudo apt remove wpasupplicant
```

Then, we prepare Nexmon...

```bash
git clone https://github.com/seemoo-lab/nexmon.git
cd nexmon
touch DISABLE_STATISTICS
```

... and compile required libraries and tools.

```bash
sudo su
if [[ ! -f /usr/lib/arm-linux-gnueabihf/libisl.so.10 ]]; then \
   cd buildtools/isl-0.10/ && ./configure && make && make install && \
   ln -s /usr/local/lib/libisl.so \
         /usr/lib/arm-linux-gnueabihf/libisl.so.10 && \
   cd ../../ ; fi
source setup_env.sh
make
cd utilities/nexutil/ && make && make install && cd ../../
```

We are now ready to build and install the monitor mode firmware patch.

```bash
cd patches/bcm43430a1/7_45_41_46/nexmon/
make
make backup-firmware
make install-firmware
```

> Note that the above step is only necessary for Wi-Fi chips/drivers where monitor mode and frame injection support is missing. Other chips using the ath9k driver such as the Atheros AR9280 work out-of-the-box. Since Nexmon does not offer frame injection for the BCM43455C0 chip yet, you currently cannot use OWL on a 3B+ model.


## Install OWL

Next, we are installing [OWL](https://github.com/seemoo-lab/owl), our AWDL implementation. First, we need some libraries (libpcap, libev, and libnl).

```bash
sudo apt install libpcap-dev libev-dev libnl-3-dev \
                 libnl-genl-3-dev libnl-route-3-dev
```

Then, it should be as easy as:

```bash
git clone https://github.com/seemoo-lab/owl.git
cd owl
git submodule update --init
mkdir build
cd build
cmake ..
make
sudo make install
```


## Install OpenDrop

In the last step, we'll install our AirDrop-compatible [OpenDrop](https://github.com/seemoo-lab/opendrop) client and server.
Again, we need some dependencies:

```bash
sudo apt install python3 python3-pip libjpeg-dev libopenjp2-7-dev
```

Then, we can clone and install the software.

```bash
git clone https://github.com/seemoo-lab/opendrop.git
sudo pip3 install ./opendrop
```


<div class="screenshot">
	<a href="/assets/raspi-airdrop.png">
		<img title="Sending a file to a Raspberry Pi 3 via AirDrop" alt="Sending a file to a Raspberry Pi 3 via AirDrop" src="/assets/raspi-airdrop.png">
	</a>
	<div class="caption">Sending a file to a Raspberry Pi 3 via AirDrop</div>
</div>

## Receive files via AirDrop

Now that all tools are installed, we can start a test run and use the Raspberry Pi to receive files via AirDrop.

Since we use Nexmon to enable monitor mode, we need to manually enable monitor mode and set the correct Wi-Fi channel (the RPi3 only supports the 2.4 GHz band, so we'll use channel 6).

```bash
sudo iw phy `iw dev wlan0 info | gawk '/wiphy/ {printf "phy" $2}'` interface add mon0 type monitor
sudo ifconfig mon0 up
sudo nexutil -k6
```

Next, we start `owl` to enable frame reception via AWDL (option `-N` tells `owl` that the interface is already in monitor mode, you can add `-v` to increase the logging output).

```bash
sudo owl -i mon0 -N
```

In a second shell, we can start the `opendrop` receiver.

```bash
opendrop receive
```

Now, when opening the sharing pane on an iOS device, a new receiver appears after a short delay and we can send files! 
