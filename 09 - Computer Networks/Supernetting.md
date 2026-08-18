---
title: "Supernetting in Network Layer"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/supernetting-in-network-layer/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Supernetting in Network Layer
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/supernetting-in-network-layer/)

---

# Supernetting in Network Layer

Supernetting is the opposite of subnetting. While subnetting splits a large network into smaller subnets, supernetting combines multiple smaller networks with similar prefixes into a larger network (supernet). It reduces routing table size, simplifies routing, and optimizes IP address usage, primarily through route summarization.
### Benefits of Supernetting:
- Saves storage space in routing tables
- Reduces the number of routing updates
- Simplifies routing decisions
- Helps manage the growth of routing tables as the Internet expands
### Important Points for Supernetting
- All the Networks should be contiguous.
- The block size of every network should be equal and must be in form of 2n.
- First Network id should be exactly divisible by whole size of supernet.
**Example:** Combining Four Class C Networks
Consider Networks:
> 200.1.0.0,
> 200.1.1.0,
> 200.1.2.0,
> 200.1.3.0
Original Routing Table:
| Network Id | Subnet Mask | Interface |
| --- | --- | --- |
| 200.1.0.0 | 255.255.255.0 | A |
| 200.1.1.0 | 255.255.255.0 | B |
| 200.1.2.0 | 255.255.255.0 | C |
| 200.1.3.0 | 255.255.255.0 | D |
First, let's check whether three conditions are satisfied or not: 
**1. Contiguous Networks**
- All networks must be **next to each other** without gaps.
- Example: `200.1.0.0 – 200.1.0.255` is the first network.
- Add 1 to the last IP (`200.1.0.255 + 1 = 200.1.1.0`) to get the next network.
- Repeat to ensure all networks are contiguous.
**2. Equal Network Size**
- All networks must have the **same number of IP addresses**.
- For Class C networks, each has 256 addresses (`/24`).
**3. First IP Aligns with Supernet Size**
- Total supernet size = sum of all networks (in powers of 2, e.g., 4 × 256 = 1024 addresses).
- Convert the first IP to binary.
- If the **last n bits** (where n = bits representing supernet size) are all 0, the first IP is correctly aligned for supernetting.
In the given example first IP is 200.1.0.0 and whole size of supernet is 4\*28 = 210. If last 10 bits of first IP address are zero then IP will be divisible. 
![Supernet example](assets/11001000-1-e11a59d822.jpg)
Last 10 bits of first IP address are zero (highlighted by green color). All conditions are satisfied, so these four networks can be combined into **one supernet**.
### **Advantages of Supernetting**
- Control and reduce network traffic
- Helpful to solve the problem of lacking IP addresses
- Minimizes the routing table i.e, it cannot cover a different area of the network when combined and all the networks should be in the same class and all IP should be contiguous
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/supernetting-in-network-layer/)

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
> - [[Collision Domain and Broadcast Domain]]
> - [[Computer Network Circuit Switching VS Packet Switching]]
> - [[Computer Network Servers]]
> - [[Computer Networks Longest Prefix Matching in Routers]]
