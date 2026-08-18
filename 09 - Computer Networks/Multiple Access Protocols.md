---
title: "Multiple Access Protocols in Computer Network"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/multiple-access-protocols-in-computer-network/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Multiple Access Protocols in Computer Network
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/multiple-access-protocols-in-computer-network/)

---

# Multiple Access Protocols in Computer Network

Multiple Access Protocols are a set of rules used in computer networks to control how multiple devices share and access a common communication channel. Since simultaneous transmissions by multiple devices can lead to data collisions and loss, these protocols ensure orderly, fair, and efficient use of the shared medium by coordinating when and how each device is allowed to transmit data.
![Multiple-Access-Control](assets/Multiple-Access-Control-768-b463be59dd.webp)
Multiple Access Protocols
> **Note:** These protocols manage network traffic by controlling which device can transmit, when it can transmit how collisions are handled. Without them, simultaneous transmissions would lead to interference, packet loss degraded performance.
## Role in the OSI Model
The Data Link Layer is responsible for the transmission of data between nodes. It has two major functions:
1. **Data Link Control (DLC):** Ensures reliable transmission using framing, error control flow control (e.g., Stop-and-Wait ARQ).
2. **Multiple Access Control (MAC):** Manages access when multiple stations share a common channel (non-dedicated link).
![jpg](assets/jpg-300-a787348eec.jpg)
Data Link Layer Functions
## Types of Multiple Access Protocols
Multiple Access Protocols are categorized into three major types:
- Random Access Protocols
- Controlled Access Protocols
- Channelization Protocols
## Random Access Protocols
In this approach, all stations have equal priority. Transmission decisions are based on the state of the channel (idle or busy). Below are its Features:
- No fixed order of transmission.
- No fixed time slot assignment.
### 1. ALOHA
- Designed for wireless LANs and shared media.
- Multiple stations can transmit simultaneously, leading to collisions.
![ALOHA](assets/ALOHA-71747fb98d.webp)
ALOHA
**Types of Aloha:**
- Pure ALOHA
- Slotted ALOHA
### 2. CSMA (Carrier Sense Multiple Access)
Before transmitting, stations sense the medium:
- If idle -> transmit.
- If busy -> wait.
![CSMA](assets/CSMA-660-36e5cf2ac3.webp)
CSMA
**Types of CSMA:**
- CSMA/CD (Collision Detection)
- CSMA/CA (Collision Avoidance)
> **Note:** Still vulnerable to collisions due to propagation delay.
## Controlled Access Protocols
Here, devices take turns accessing the channel, preventing collisions. For example:
- **Reservation:** Stations reserve slots before transmission.
- **Polling:** Central controller polls each device in turn.
- **Token Passing:** A token (special packet) is passed; only the device holding the token can transmit.
## Channelization Protocols
Bandwidth is divided and allocated so that multiple users can transmit simultaneously.
### 1. Frequency Division Multiple Access (FDMA)
- Bandwidth is divided into frequency bands.
- Guard bands prevent overlap.
### 2. Time Division Multiple Access (TDMA)
- Time is divided into slots.
- Each station transmits only in its assigned slot.
- Needs synchronization.
### 3. Code Division Multiple Access (CDMA)
- All stations transmit simultaneously using unique codes.
- Widely used in mobile communication.
### 4. Orthogonal Frequency Division Multiple Access (OFDMA)
- Bandwidth divided into small subcarriers.
- Widely used in 4G/5G for high data rates.
- High throughput, supports multimedia.
- Complex design, high power requirements.
### 5. Spatial Division Multiple Access (SDMA)
- Uses multiple antennas (MIMO).
- Separates users spatially.
- Improves data rate and signal quality.
## Features of Multiple Access Protocols
- **Contention-Based Access:** Devices compete for channel.
- **Carrier Sensing:** Medium is sensed before transmitting.
- **Collision Handling:** Detection (CSMA/CD) or avoidance (CSMA/CA).
- **Token Passing:** Sequential access control.
- **Bandwidth Utilization:** Varies depending on protocol efficiency.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/multiple-access-protocols-in-computer-network/)

## GATE CS

- Subject: Computer Networks
- Topic: Data Link Layer

> [!note] Related notes
>
> - [[Aloha]]
> - [[Back-off Algorithm for CSMA CD]]
> - [[Bit Stuffing]]
> - [[Carrier sense multiple access]]
> - [[Collision Avoidance in wireless networks]]
> - [[Collision Detection in CSMA CD]]
> - [[Computer Networks Error Detection]]
> - [[Controlled Access Protocols]]
> - [[Difference between Byte stuffing and Bit stuffing]]
> - [[Efficiency of CSMA CD]]
