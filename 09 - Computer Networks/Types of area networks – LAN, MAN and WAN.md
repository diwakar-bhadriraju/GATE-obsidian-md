---
title: "Types of Network - PAN, LAN, WAN and MAN"
subject: "Computer Networks"
topic: "Network Fundamental and Physical Layer"
source: "https://www.geeksforgeeks.org/types-of-area-networks-lan-man-and-wan/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Fundamental and Physical Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-fundamental-and-physical-layer
---


> [!abstract] Types of Network - PAN, LAN, WAN and MAN
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Fundamental and Physical Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/types-of-area-networks-lan-man-and-wan/)

---

# Types of Network - PAN, LAN, WAN and MAN

Network allows computers to connect and communicate with different computers via any medium. LAN, MAN, and WAN are the three major types of networks designed to operate over the area they cover. These different types of networks can be categorized based on the area they cover (ranging from personal connections to global networks), the type of communication they use, and their architectural design.
![file_handling_3](assets/file_handling_3-1c655eef96.webp)
Types of Networks
## **1. Personal Area Network (PAN)**
A PAN is a short-range network that connects personal devices like smartphones, tablets, and computers. It typically covers less than 10 meters (about 33 feet) and usually uses wireless technologies such as Bluetooth. PAN is smaller than other networks like LAN or WAN and is mainly used for data sharing between a few devices.
![personal_area_network](assets/personal_area_network-660-05a159c8fc.webp)
Pan
**Advantages:**
- Allows for easy communication between personal devices in close proximity.
- Uses wireless technology, which eliminates the need for wires and cables.
- PANs are designed to be energy efficient, which means that devices can communicate with each other without draining their batteries quickly.
**Disadvantages:**
- Limited coverage area.
- PANs have limited bandwidth, so they are not suitable for large-scale or high-speed data transfer.
- May experience interference from other wireless devices.
## **2**. **Local Area Network (LAN)**
A LAN connects computers and devices within a small area like a home, office, school, or hospital. It usually uses switches, routers, and private IP addresses. LANs are high-speed, inexpensive to set up, and easy to maintain.
- **Coverage:** Up to 2 km (limited area).
- **Speed:** Earlier 4–16 Mbps; now 100–1000 Mbps.
- **Medium:** Mostly wired (Ethernet cables, twisted-pair, coaxial), though wireless can also be used.
- **Example:** Students playing a multiplayer game in the same room without internet.
![local_area_network](assets/local_area_network-660-b2823f904b.webp)
Lan
**Advantages:**
- Provides fast data transfer rates and high-speed communication.
- Easy to set up and manage.
- Can be used to share peripheral devices such as printers and scanners.
**Disadvantages:**
- Limited geographical coverage.
- Limited scalability and may require significant infrastructure upgrades to accommodate growth.
- May experience congestion and network performance issues with increased usage.
## **3. Metropolitan Area Network (MAN)**
A MAN spans 5–50 km, covering more area than a LAN but less than a WAN. It connects computers across a city or between nearby cities. MANs provide high-speed connectivity (in Mbps), can act as ISPs, and are useful for organizations needing fast communication. However, they are costly, complex to design, and harder to maintain.
![metropolitan_area_network_man_](assets/metropolitan_area_network_man_-660-76a1347881.webp)
Man
**Advantages:**
- Provides high-speed connectivity over a larger geographical area than LAN.
- Can be used as an ISP for multiple customers.
- Offers higher data transfer rates than WAN in some cases.
**Disadvantages:**
- Can be expensive to set up and maintain.
- May experience congestion and network performance issues with increased usage.
- May have limited fault tolerance and security compared to LANs.
## **4. Wide Area Network (WAN)**
A WAN covers large geographical areas (above 50 km), often connecting multiple LANs through telephone lines, radio waves, or satellites. It can be private (for organizations) or public (like the internet). WANs offer high-speed communication but are costly to set up and maintain.
![Local-Area-Network](assets/Local-Area-Network-bcd90aee4e.webp)
Covers large geographical areas, connecting networks across countries or continents.
**Advantages:**
- Covers large geographical areas and can connect remote locations.
- Provides connectivity to the internet.
- Offers remote access to resources and applications.
**Disadvantages:**
- Can be expensive to set up and maintain.
- Offers slower data transfer rates than LAN or MAN.
- May have lower fault tolerance and security compared to LANs.
## Based on Types of Communication
Networks can also be divided based on the types of communication they use:
### 1. Point-to-Point
A Point-to-Point network creates a direct connection between two devices (e.g., computer and printer). Data is transmitted without intermediaries, using either wired (cables) or wireless (infrared, radio) links. It is simple, dedicated, and commonly used for two-device communication.
![Point-to-Point-Network](assets/Point-to-Point-Network-fad0df59bb.webp)
Point-to-Point Network
**Advantages:**
- Provides a dedicated and direct connection, ensuring reliable communication between two devices.
- Simple to set up and configure due to the limited number of devices involved.
- Offers low latency as there are no intermediate devices or complex routing.
**Disadvantages:**
- Not scalable, as adding more devices requires additional dedicated links.
- May require physical cables for wired connections, which can limit flexibility.
- Lacks fault tolerance; if the direct link fails, communication is disrupted.
### 2. Multipoint Networks
A multipoint network allows more than two devices to share a single communication link. The channel capacity is either shared at the same time (spatially) or in turns (temporally).
![tempralSharing](assets/tempralSharing-e01d017127.jpg)
Multipoint Network
**Advantages:**
- Allows multiple devices to share a single communication channel, reducing the need for multiple dedicated links.
- More cost-effective than point-to-point networks for connecting multiple devices.
- Supports dynamic communication, where devices can join or leave the network easily.
**Disadvantages:**
- Shared bandwidth can lead to congestion and reduced performance when many devices are active.
- Potential for interference or collisions in spatially shared connections.
- Security risks may increase as multiple devices access the same communication medium.
### 3. Broadcast Networks
Broadcast networks use a single communication channel where one sender transmits data that can be received by multiple parties simultaneously. In this setup, data travels in one direction, from the sender to all potential receivers. A common example is a radio station, where the station broadcasts signals that can be picked up by any radio receiver within range. Another example is a television network broadcasting to multiple viewers.
![Broadcast-communication-open-to-all](assets/Broadcast-communication-open-to-all-54ce869b37.webp)
Broadcast Networks
**Advantages:**
- Efficient for distributing data to a large number of recipients simultaneously.
- Simple to implement for one-to-many communication scenarios.
- Reduces the need for individual connections to each receiver, saving resources.
**Disadvantages:**
- Data is sent in one direction, limiting two-way communication.
- No guarantee that all intended recipients receive the data reliably.
- Can lead to bandwidth wastage if not all receivers need the transmitted data.
## Related Articles
> - [Architecture based classification](https://www.geeksforgeeks.org/computer-networks/classification-of-computer-network-on-basis-of-architecture/)
> - [Internet, Intranet and Extranet](https://www.geeksforgeeks.org/computer-networks/internet-intranet-and-extranet/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/types-of-area-networks-lan-man-and-wan/)

## GATE CS

- Subject: Computer Networks
- Topic: Network Fundamental and Physical Layer

> [!note] Related notes
>
> - [[Basics of Computer Networking]]
> - [[Difference between Broadband and]]
> - [[Difference between Unipolar, Polar and]]
> - [[Layers of OSI Model]]
> - [[Let’s experiment with Networking]]
> - [[Network goals]]
> - [[Network Topologies]]
> - [[Redundant link problems]]
> - [[TCP IP Model]]
> - [[Transmission Modes in Computer Networks]]
