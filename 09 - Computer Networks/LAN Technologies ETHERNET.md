---
title: "What is Ethernet?"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/what-is-ethernet/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] What is Ethernet?
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/what-is-ethernet/)

---

# What is Ethernet?

A Local Area Network (LAN) is a high-speed data communication system interconnecting devices within a limited scope such as offices or campuses. While LANs may use wired or wireless media, Ethernet (IEEE 802.3) dominates as the primary wired LAN standard. It provides standardized framing, efficient media access control, and scalable physical layer options, enabling reliable communication from 10 Mbps to multi-hundred-gigabit speeds.
> **Note:** While wireless technologies like Wi - Fi have become popular, Ethernet continues to dominate in enterprises, data centers, and high - performance environments where speed and stability are critical.
## Evolution of Ethernet
Ethernet was invented by Robert Metcalfe in 1973, initially offering a data rate of 2.94 Mbps.
- **1982:** Ethernet Version 2 standardized with 10 Mbps.
- **1983:** IEEE 802.3 standardization accelerated adoption.
- Over time, Ethernet evolved to support 100 Mbps (Fast Ethernet), 1 Gbps (Gigabit Ethernet), 10 Gbps, 40 Gbps, 100 Gbps, and even 400 Gbps.
![ethernet_evolution](assets/ethernet_evolution-5abb0ff0b1.webp)
Ethernet Evolution
> **Note:** Today, Ethernet is the "de facto standard for wired networking" across homes, enterprises, and large - scale data centers.
## Types of Ethernet
### 1. Fast Ethernet
- **Speed:** 100 Mbps
- **Media:** Twisted pair (CAT5) and fiber optic cables
- **Variants:** 100BASE - TX, 100BASE - FX, 100BASE - T4
### 2. Gigabit Ethernet
- **Speed:** 1 Gbps (1000 Mbps)
- **Media:** CAT5e, CAT6, and fiber optic cables
- Common in modern office and home networks
### 3. 10 - Gigabit Ethernet
- **Speed:** 10 Gbps
- **Media:** CAT6a, CAT7, and fiber optic cables
- Supports long distances (up to 10 km with fiber)
- Widely used in data centers and enterprise backbones
### 4. Switch Ethernet
- Uses network switches for dedicated connections
- Each device gets a separate collision domain
- Supports speeds from 10 Mbps to 10 Gbps
## How Ethernet Works
Ethernet operates at the Physical Layer (Layer 1) and the Data Link Layer (Layer 2) of the OSI model.
- **Protocol Data Unit (PDU):** Frame (at Data Link Layer)
- **Access Control Mechanism:** CSMA/CD (Carrier Sense Multiple Access with Collision Detection) manages data collisions on shared media.
- **Encoding Technique:** Manchester Encoding, Bit '0' -> High - to - Low transition & Bit '1' -> Low - to - High transition
![manchester](assets/manchester-687fae7ca3.webp)
Encoding
> Baud rate = 2 × Bit rate
This ensures reliable data transmission over physical media.
## Key Features of Ethernet
- **Speed:** Supports from 10 Mbps to 400 Gbps.
- **Reliability:** Error detection ensures accurate data transfer.
- **Cost - effectiveness:** Inexpensive and widely available.
- **Interoperability:** Standardized under IEEE 802.3, ensuring compatibility.
- **Security:** Supports encryption and authentication mechanisms.
- **Scalability:** Easily accommodates additional devices.
- **Broad compatibility:** Works seamlessly with protocols like TCP/IP, HTTP, FTP.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/what-is-ethernet/)

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
