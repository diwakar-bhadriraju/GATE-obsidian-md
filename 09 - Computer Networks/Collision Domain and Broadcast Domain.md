---
title: "Collision Domain and Broadcast Domain in Computer Network"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/collision-domain-and-broadcast-domain-in-computer-network/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Collision Domain and Broadcast Domain in Computer Network
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/collision-domain-and-broadcast-domain-in-computer-network/)

---

# Collision Domain and Broadcast Domain in Computer Network

Routers and switches are preferred over hubs, repeaters, and bridges because they manage network traffic more efficiently. While a hub is just a multi-port repeater and a switch is a multi-port bridge, older devices create more collisions and offer fewer ports, making them unsuitable for modern networks. Concepts like collision and broadcast domains explain how newer devices reduce collisions and control traffic better.
**Key Points:**
- Hubs/repeaters = one large collision domain.
- Switches = separate collision domains.
- Routers = separate broadcast domains.
- Older devices have fewer ports and less control.
![](assets/Computer-Network-Broadcast-Domain-Collis-7ce50c22ed.png)
### **1.** Collision Domain
A **Collision Domain** is an area of a network where all devices share the same communication medium. When one device sends data, every other device in that domain must listen, even if the message isn’t for them. If two devices transmit at the same time, their data collides, forcing them to stop and resend later. This issue occurs only in **half-duplex** communication.
### Advantages:
- **Higher Performance**: Fewer collisions mean less retransmission and faster data flow.
- **Efficient Bandwidth Use:** Each device or small group gets its own collision domain, reducing disruption.
- **Better Stability**: Problems in one collision domain don’t impact others, improving overall network reliability.
### Disadvantages:
- **Limited Scalability:** Larger collision domains increase collisions, causing congestion and reduced performance.
- **Difficult Management**: Frequent collisions make it harder to identify and troubleshoot network issues.
- **Reduced Efficiency**: More retransmissions and congestion lead to overall poor network reliability and speed.
### 2. Broadcast Domain
A **Broadcast Domain** is a network area where any broadcast message sent by one device must be received by all others, which can lead to LAN congestion and reduced bandwidth. Therefore, increasing the number of both collision domains and broadcast domains helps improve network efficiency by isolating traffic and ensuring better bandwidth for all users.
### Advantages:
- **Efficient Network Communication**: Supports protocols like ARP and DHCP that rely on sending messages to all devices at once.
- **Simplified Network Management:** Proper segmentation (e.g., VLANs) makes it easier to group devices and apply network policies.
- **Improved Collaboration**: Allows devices within the same domain to easily discover and communicate with each other, supporting local network services..
### Disadvantages:
- **More Congestion:** Large broadcast domains create too much broadcast traffic, slowing the network and causing packet loss.
- **Lower Security:** All devices see broadcast packets, increasing risks like sniffing and ARP spoofing.
- **Reduced Efficiency:** Bigger broadcast domains waste bandwidth and hurt overall performance.
#### So, which of our network devices break collision domains, and which of them break broadcast domains?
**HUB**
- A hub does **not** break collision domains or broadcast domains.
- All devices connected to a hub share **one collision domain** and **one broadcast domain**.
- It doesn’t segment the network; it only connects devices.
**SWITCH**
- A switch **breaks collision domains** — each port is its own collision domain.
- This reduces collisions and improves performance.
- However, a switch does **not** break broadcast domains — all ports still share **one broadcast domain**.
**ROUTER**
- A router breaks **both collision domains and broadcast domains**.
- It separates networks completely, preventing broadcasts from crossing over.
- This makes routers essential for controlling traffic and improving network efficiency.
> Also, as repeaters and bridges differ from hubs and switches only in terms of the number of ports, a repeater does not break collision and broadcast domains, while a bridge breaks only collision domains.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/collision-domain-and-broadcast-domain-in-computer-network/)

## GATE CS

- Subject: Computer Networks
- Topic: Network Layer

> [!note] Related notes
>
> - [[Administrative Distance (AD) and Autonomous System (AS)]]
> - [[ARP, Reverse ARP(RARP), Inverse ARP (InARP), Proxy ARP and Gratuitous ARP]]
> - [[C Program to find IP Address, Subnet Mask & Default Gateway]]
> - [[Circuit Switching]]
> - [[Classes of routing protocols – Set 3]]
> - [[Classification of Routing Algorithms – Set 1]]
> - [[Computer Network Circuit Switching VS Packet Switching]]
> - [[Computer Network Servers]]
> - [[Computer Networks Longest Prefix Matching in Routers]]
> - [[Difference between layer-2 and layer-3 switches]]
