---
title: "Raspberry Pi 3 'No Wireless Interface Found'"
date: 2017-08-07
categories:
- tech
- hardware
tags:
- Raspberry Pi 3
draft:          false
comments:       true
showTags:       true
showPagination: true
showSocial:     true
showDate:       true
---

Solution to a problem faced using a Raspberry Pi 3 (Raspbian) with built in Wi-Fi capabilities. Adding Wireless Networks to the appropriate file.

<!--more-->

Until recently I have always used my RP3 running Raspbian with my personal hotspot that I carried around with me for wifi. A while ago, I went into my `/etc/networking/interfaces` and edited the file to add my SSID and Network Password. This was super convenient, the RP3 (with built in wifi and bluetooth), would always connect to my hotspot upon booting up every time. I enabled SSH and knew the IP address so I never had a need to hook my RP3 up to another internet source.

Today I wanted to use my RP3 without my regular hotspot, I wanted to connect to the public network available. I plugged in a monitor (HDMI), keyboard and mouse and booted the Pi up. Once the GUI loaded to the desktop, I pressed the Wi-Fi icon on the top right which only showed "No Wireless Interface Found". After a bunch of debugging and testing my network I finally decided to check out the `/etc/networking/interfaces` file I had altered a while back. I removed the SSID and Network Password, rebooted the RP3 and the Network interface worked correctly, displaying all the nearby networks available.

#### TL;DR
You should **NOT** alter the `/etc/networking/interfaces` file to add a network SSID and Password. This may cause your Network interface to stop working properly by overriding it with a hardcoded network connection.

_**Note**: You must use elevated privileges when editing the files mentioned below. You can do this by running `sudo nano /etc/networking/interfaces` for instance._

Your `/etc/networking/interfaces` file should be:
```
# interfaces(5) file used by ifup(8) and ifdown(8)

# Please note that this file is written to be used with dhcpcd
# For static IP, consult /etc/dhcpcd.conf and 'man dhcpcd.conf'

# Include files from /etc/network/interfaces.d:
source-directory /etc/network/interfaces.d

auto lo
iface lo inet loopback

iface eth0 inet manual

allow-hotplug wlan0
iface wlan0 inet manual
    wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf

allow-hotplug wlan1
iface wlan1 inet manual
    wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
```

If you would like to add a network to default to upon bootup, add this to the `/etc/wpa_supplicant/wpa_supplicant.conf`:
```
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="<network_ssid>"
    psk="<network_password>"
}
```
