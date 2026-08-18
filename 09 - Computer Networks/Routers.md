---
title: "Router in Computer Networks"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/introduction-of-a-router/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Router in Computer Networks
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/introduction-of-a-router/)

---

# Router in Computer Networks

A router is a networking device that forwards data packets between different computer networks. It connects multiple packet-switched networks or subnetworks, managing traffic by directing packets to their intended IP addresses. Routers allow multiple devices to share an Internet connection efficiently.
![Router](assets/11-40-2f4cfe1d9f.png)
Router
> **Example:** When you access www.google.com, your request is broken into packets. These packets don’t travel directly to Google’s server-they pass through a series of routers that examine and forward them along the most efficient path until they reach the destination.
## How Does a Router Work?
Routers determine the path for a packet by examining its destination IP address and consulting the routing table, which contains information on network paths. They use a set of rules to identify the most efficient route for each packet.
- **Static routing:** Configured manually, suitable for small or stable networks.
- **Dynamic routing:** Automatically updated based on network activity, ideal for large or changing networks.
![Network_devices](assets/Network_devices-06ccb0148f.jpg)
Router Network
> **Note:** Routers often work with a modem (cable, DSL, or fiber) to enable Internet connectivity
## Functions of a Router
- **Forwarding:** Receives packets, examines headers, and forwards them to the correct output port.
- **Routing:** Determines the optimal path for packets using routing tables and algorithms.
- **Network Address Translation (NAT):** Translates private IPs to a public IP for Internet access.
- **Security:** Supports firewalls and other security measures.
- **VPN Connectivity:** Provides secure remote access to networks.
- **Bandwidth Management:** Controls data flow to prevent congestion.
- **Monitoring & Diagnostics:** Tracks traffic and helps troubleshoot network issues.
## Router Architecture
![routing_processor](assets/routing_processor-e00e6a103c.webp)
Architecture of Router
A typical router consists of:
- **Input Port:** Accepts packets, decapsulates them, and determines forwarding paths.
- **Switching Fabric:** The core of the router connecting input ports to output ports. Can be implemented via:
> **Memory switching:** CPU copies packets to output ports.
> **Bus switching:** Single bus transfers packets to the correct port.
> **Interconnection networks:** Complex designs connecting multiple input/output ports.
- **Output Port:** Transmits packets to outgoing links, managing queuing and link-layer functions.
- **Routing Processor:** Executes routing protocols and algorithms, maintaining the forwarding table.
## Common Routing Protocols
- **Open Shortest Path First (OSPF):** Determines the optimal path across networks.
- **Border Gateway Protocol (BGP):** Shares routing information between edge routers.
- **Interior Gateway Routing Protocol (IGRP):** Exchanges routing info within autonomous networks.
- **Enhanced IGRP (EIGRP):** Requests routing paths from neighbors if unknown.
- **Exterior Gateway Protocol (EGP):** Shares routing data between internet hosts.
## Applications of Routers
- Connect remote servers, networks, and devices globally.
- Support wired and wireless communication, including high-speed data transfer.
- Used by ISPs to transmit audio, video, image, and email efficiently.
- Implement access control, enabling selective resource usage.
## Types of Routers
1. **Broadband Routers:** Connect computers to the Internet and share the connection.
2. **Wireless Routers:** Create Wi-Fi networks in homes or offices.
3. **Wired Routers:** Connect multiple devices via Ethernet cables, common in schools and offices.
4. **Edge Routers:** Located at network boundaries, distributing packets to and from ISPs.
5. **Core Routers:** Operate within networks, handling heavy data traffic.
6. **Virtual Routers:** Software-based routers implemented on virtual machines for flexibility and scalability.
7. **Portable Routers:** Small devices creating private Wi-Fi for mobility.
## Security Challenges in Routers
- **Vulnerability Exploits:** Firmware flaws can be exploited by attackers; regular updates are necessary.
- **DDoS Attacks:** Distributed Denial-of-Service attacks can overload routers.
- **Default Admin Credentials:** Weak or unchanged credentials can allow unauthorized access.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/introduction-of-a-router/)

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
