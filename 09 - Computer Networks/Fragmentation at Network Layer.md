---
title: "Fragmentation in Network Layer"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/fragmentation-network-layer/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Fragmentation in Network Layer
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/fragmentation-network-layer/)

---

# Fragmentation in Network Layer

In computer networks, data is sent in small units called packets or datagrams. Sometimes, these datagrams are too large to pass through a network with a smaller size limit. To handle this, the datagram is broken into smaller parts is called fragmentation.
- IPv4 datagram size can be up to 65,535 bytes.
- Networks have a Maximum Transmission Unit (MTU) limit.
- Fragmentation splits large datagrams into smaller fragments.
- Each fragment has its own header.
- Fragmentation can occur at the source or routers.
- Reassembly happens only at the destination.
## Need for Fragmentation
When a large datagram is created by the source computer, it may need to travel through multiple networks to reach the destination. Each of these networks might support different maximum packet sizes. This leads to the need for fragmentation.
> **Note:** Although sending large datagrams is better for efficiency (because headers are not repeated), it’s not always possible due to the reasons below:
### Reasons for Fragmentation
- **Different Network Limits:** Each network has its own MTU. If a datagram is larger, it must be split.
- **Unknown Path MTU:** Source doesn’t always know the smallest MTU along the route.
- **Error Handling:** Smaller fragments reduce retransmission if a part is lost or corrupted.
- **Protocol & Hardware Limits:** Some devices and protocols limit maximum packet size.
- **Transmission Efficiency:** Large packets take longer in the network, delaying others
![Datagram-Header-Format_](assets/Datagram-Header-Format_-4126da2f2f.webp)
Header Format
## Fields Related to Fragmentation
The fields that are related to fragmentation and reassembly of an IPv4 datagram are:
### **Identification**
- This is a 16-bit field in the [IPv4 header](https://www.geeksforgeeks.org/computer-networks/introduction-and-ipv4-datagram-header/).
- It gives a unique number to each datagram sent from the source.
- The combination of the Identification field and source IP address helps to identify each datagram uniquely.
- When a datagram is sent, the system copies a counter value into this field and then increases the counter by 1 for the next datagram.
- If the datagram is broken into fragments, all fragments will have the same Identification number.
- At the destination, this number helps to match and reassemble the fragments into the original datagram.
### **Flags**
- The **Flags** field in the IPv4 header is 3 bits long.
- The first bit is reserved and not used.
- The second bit is the **Do Not Fragment (DF)** bit. If set to 1, the datagram must not be fragmented; if it cannot be sent due to size, it is discarded and an ICMP error message is sent. If set to 0, fragmentation is allowed.
- The third bit is the **More Fragments (MF)** bit. If set to 1, more fragments are coming. If set to 0, this is the last fragment or the datagram was not fragmented.
### **Fragment Offset**
- This is a 13-bit field.
- It shows the position of the fragment in the original datagram.
- It tells the destination where to place this fragment when reassembling the full datagram.
- The offset is measured in units of 8 bytes.
**Example:** Let’s say a large datagram has 4000 bytes of data. These bytes are numbered from 0 to 3999. Now, suppose this datagram is too large for the network and needs to be broken into 3 fragments.
Here’s how the fragmentation will happen:
**First Fragment**
- Carries bytes: 0 to 1399
- Fragment Offset: 0/8 = 0
- **Explanation**: This fragment starts at the beginning of the data. So its offset is 0.
**Second Fragment**
- Carries bytes: 1400 to 2799
- Fragment Offset: 1400/8 = 175
- **Explanation**: This fragment starts from byte 1400. Dividing by 8 gives offset 175.
**Third Fragment**
- Carries bytes: 2800 to 3999
- Fragment Offset: 2800/8 = 350
- **Explanation**: This is the last part, starting from byte 2800. Offset becomes 350.
![original_datagram](assets/original_datagram-20e81c777d.webp)
Fragmentation Example
## Fragmentation of Datagram
When data travels through a network, it is placed into a unit called a datagram. Every network, whether a Local Area Network ([LAN](https://www.geeksforgeeks.org/computer-networks/lan-full-form/)) or a Wide Area Network ([WAN](https://www.geeksforgeeks.org/computer-science-fundamentals/wan-full-form/)), has a limit on the maximum size of data it can handle at a time. This limit is known as the Maximum Transmission Unit ([MTU](https://www.geeksforgeeks.org/computer-networks/what-is-mtumaximum-transmission-unit/)).
**Fragmentation Process:**
- Only the data part of the datagram is split into fragments.
- The header of the original datagram is copied into each fragment to allow reassembly.
- Fragmentation can occur at the **source computer** or **any router** along the path.
**At Each Router:**
- The router removes the frame to access the datagram (**decapsulation**).
- It checks the MTU of the next network; if the datagram is too large, it fragments it.
- The datagram or fragments are encapsulated into a new frame suitable for the next network.
**Why Fragmentation May Happen Multiple Times:**
- The source may not know the exact path or MTU of every network along the route.
- Routes can change in a connectionless network like the Internet.
- Routers may fragment the datagram again if it encounters a network with a smaller MTU.
## Reassembly of Fragments
It takes place only at the destination and not at routers since packets take an independent path(datagram packet switching), so all may not meet at a router and hence a need of fragmentation may arise again. The fragments may arrive out of order also. 
![mf](assets/mf-522cc9a8be.webp)
Reassembly of Fragments
**Algorithm:**
1. Destination should identify that datagram is fragmented from MF, Fragment offset field.
2. Destination should identify all fragments belonging to same datagram from Identification field.
3. Identify the 1st fragment(offset = 0).
4. Identify subsequent fragments using header length, fragment offset.
5. Repeat until MF = 0.
**Efficiency:**
> **Efficiency (e)** = useful/total = (Data without header)/(Data with header) 
> **Throughput** = e \* B { where B is bottleneck bandwidth } 
**Example:** An IP router with a Maximum Transmission Unit (MTU) of 200 bytes has received an IP packet of size 520 bytes with an IP header of length 20 bytes. The values of the relevant fields in the IP header. 
**Explanation:** Since MTU is 200 bytes and 20 bytes is header size so, the maximum length of data = 180 bytes but it can't be represented in fragment offset since it is not divisible by 8 so, the maximum length of data feasible = 176 bytes. 
- Number of fragments = (520/200) = 3.
- Header length = 5 (since scaling factor is 4 therefore, 20/4 = 5)
- Efficiency, e = (Data without header)/(Data with header) = 500/560 = 89.2 % 
  ![fragment_offset](assets/fragment_offset-08a74ca09f.webp)
  Reassembly of Fragments
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/fragmentation-network-layer/)

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
