---
title: "Basics of Wi-Fi"
subject: "Computer Networks"
topic: "Application Layer"
source: "https://www.geeksforgeeks.org/computer-networks/basics-of-wi-fi/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Application Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/application-layer
---


> [!abstract] Basics of Wi-Fi
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Application Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/basics-of-wi-fi/)

---

# Basics of Wi-Fi

Wireless networking technology that enables devices to connect to a local network and the Internet using radio waves instead of cables is known as Wi-Fi.
- Uses radio waves instead of physical cables for data transmission.
- Based on IEEE 802.11 standards.
- Enables wireless local area networks (WLAN) using access points.
- Supports devices like laptops, smartphones, and tablets.
- Operates at the Physical and Data Link layers of the OSI model.
![base_station_or_enth](assets/base_station_or_enth-7a447b25a1.webp)
Wireless access point connecting multiple devices such as smartphones, laptops, and cameras to a network.
## Access Point (AP)
Acts as a wireless LAN base station that connects wireless devices to a wired network, typically the Internet, using an Access Point (AP).
- Acts as a central transmitter and receiver for wireless devices
- Allows multiple devices to connect simultaneously
- Bridges wireless users to a wired LAN
- Plays a crucial role in WLAN communication
## Wi-Fi Architecture
The [IEEE 802.11 architecture](https://www.geeksforgeeks.org/computer-organization-architecture/ieee-802-11-architecture/) defines two main types of services:
### 1. Basic Service Set (BSS)
Known for fundamental building block of a wireless LAN.
Types of BSS:
**1.1 Infrastructure BSS**
- Includes one access point
- Wireless devices communicate through the AP
- Can exchange data with other BSSs
**2.2 Independent BSS (IBSS) / Ad-hoc Network**
- No access point is present
- Devices communicate directly with each other
- Cannot communicate with other BSSs
- Suitable for small, temporary networks
![419253544](assets/419253544-19cbffed20.webp)
IBSS (ad hoc) vs BSS (infrastructure) Wi-Fi communication.
### 2. Extended Service Set (ESS)
Formed by connecting two or more Basic Service Sets (BSSs) through a distribution system like Ethernet, this arrangement is known as an Extended Service Set (ESS).
- Multiple BSSs are interconnected
- Each BSS has its own access point
- Allows seamless roaming between BSSs
- Used in large networks like campuses and offices
### Types of Stations in ESS
- **Mobile Stations:** Wireless devices within a BSS
- **Stationary Stations:** Access points connected to the wired LAN
![419253546](assets/419253546-e4c0e1d1b1.webp)
ESS with multiple access points for wider coverage.
## Features of Wi-Fi
- **Wireless Connectivity:** Allows devices to connect without physical cables, providing mobility and flexibility.
- **High Speed:** Supports fast data transfer rates suitable for streaming, browsing, and file sharing.
- **Easy Setup:** Simple to install and configure; most modern devices have built-in Wi-Fi support.
- **Multiple Device Support:** Enables multiple users and devices to connect simultaneously to the same network.
- **Security:** Uses encryption methods such as WPA and WPA2 to protect data from unauthorized access.
- **Range:** Coverage depends on router power, environmental conditions, and physical obstacles.
- **Compatibility:** Works with a wide range of devices including smartphones, laptops, tablets, and smart home devices.
- **Interference:** Performance may be affected by other wireless devices and physical barriers.
- **Reliability:** Network speed and stability can decrease due to congestion or weak signal strength.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/basics-of-wi-fi/)

## GATE CS

- Subject: Computer Networks
- Topic: Application Layer

> [!note] Related notes
>
> - [[Address Resolution in DNS]]
> - [[DHCP Relay Agent]]
> - [[DNS (Domain Name Server) NetWorking]]
> - [[DNS Spoofing or DNS Cache poisoning]]
> - [[Dynamic Host Configuration Protocol]]
> - [[File Transfer Protocol]]
> - [[How DHCP server dynamically assigns IP address to a host]]
> - [[HTTP Non-Persistent & Persistent Connection]]
> - [[LiFi vs WiFi]]
> - [[Multipurpose Internet mail extension]]
