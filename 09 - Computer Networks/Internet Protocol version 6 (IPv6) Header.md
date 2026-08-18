---
title: "Internet Protocol version 6 (IPv6) Header"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/internet-protocol-version-6-ipv6-header/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Internet Protocol version 6 (IPv6) Header
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/internet-protocol-version-6-ipv6-header/)

---

# Internet Protocol version 6 (IPv6) Header

The IPv6 header is the first part of an IPv6 packet, containing essential information for routing and delivering the packet across networks. The IPv6 header representation is a structured layout of fields in an IPv6 packet, including source and destination addresses, traffic class, flow label, payload length, next header, and hop limit. It ensures proper routing and delivery of data across networks.
![IPv6 Header](assets/ipv6-header-bcb5b80de9.png)
## IPv6 Fixed Header
The IPv6 header is a part of the information sent over the internet. It's always 40 bytes long and includes details like where data should go and how it should get there. This helps devices talk to each other and share information smoothly online.
### **Version (4-bits)**
The size of this field is 4-bit. Indicates the version of the Internet Protocol, which is always 6 for IPv6, so the bit sequence is 0110.
### Traffic Class(8-bit)
The Traffic Class field indicates class or priority of IPv6 packet which is similar to **Service Field** in IPv4 packet. It helps routers to handle the traffic based on the priority of the packet. If congestion occurs on the router then packets with the least priority will be discarded. 
As of now, only 4-bits are being used (and the remaining bits are under research), in which 0 to 7 are assigned to [Congestion controlled](https://www.geeksforgeeks.org/computer-networks/congestion-control-techniques-in-computer-networks/) traffic and 8 to 15 are assigned to Uncontrolled traffic. 
Priority assignment of Congestion controlled traffic : 
![Traffic class in IPv6](assets/congestion-table-2df88cec3f.png)
Uncontrolled data traffic is mainly used for Audio/Video data. So we give higher priority to Uncontrolled data traffic. 
The source node is allowed to set the priorities but on the way, routers can change it. Therefore, the destination should not expect the same priority which was set by the source node.
### **Flow Label (20-bits)**
Flow Label field is used by a source to label the packets belonging to the same flow in order to request special handling by intermediate IPv6 [routers](https://www.geeksforgeeks.org/computer-networks/introduction-of-a-router/), such as non-default [quality-of-service](https://www.geeksforgeeks.org/computer-networks/computer-network-quality-of-service-and-multimedia/) or real-time service. In order to distinguish the flow, an intermediate router can use the source address, a destination address, and flow label of the packets. Between a source and destination, multiple flows may exist because many processes might be running at the same time. Routers or Host that does not support the functionality of flow label field and for default router handling, flow label field is set to 0. While setting up the flow label, the source is also supposed to specify the lifetime of the flow. 
### **Payload Length (16-bits)**
It is a 16-bit (unsigned integer) field, indicates the total size of the [payload](https://www.geeksforgeeks.org/computer-networks/payload-in-computer-networks/) which tells routers about the amount of information a particular packet contains in its payload. The payload Length field includes extension headers(if any) and an upper-layer packet. In case the length of the payload is greater than 65,535 bytes (payload up to 65,535 bytes can be indicated with 16-bits), then the payload length field will be set to 0 and the jumbo payload option is used in the Hop-by-Hop options extension header. 
### **Next Header (8-bits)**
Next Header indicates the type of extension header(if present) immediately following the IPv6 header. Whereas In some cases it indicates the protocols contained within upper-layer packets, such as [TCP](https://www.geeksforgeeks.org/computer-networks/differences-between-tcp-and-udp/), UDP. 
### **Hop Limit (8-bits)**
Hop Limit field is the same as TTL in [IPv4](https://www.geeksforgeeks.org/computer-networks/what-is-ipv4/) packets. It indicates the maximum number of intermediate nodes [IPv6](https://www.geeksforgeeks.org/computer-networks/what-is-ipv6/) packet is allowed to travel. Its value gets decremented by one, by each node that forwards the packet and the packet is discarded if the value decrements to 0. This is used to discard the packets that are stuck in an infinite loop because of some routing error. 
### **Source Address (128-bits)**
Source Address is the 128-bit IPv6 address of the original source of the packet. 
### **Destination Address (128-bits)**
The destination Address field indicates the IPv6 address of the final destination(in most cases). All the intermediate nodes can use this information in order to correctly route the packet. 
## **Extension Headers**
In order to rectify the limitations of the **IPv4 Option Field**, Extension Headers are introduced in IP version 6. The extension header mechanism is a very important part of the IPv6 architecture. The next Header field of IPv6 fixed header points to the first Extension Header and this first extension header points to the second extension header and so on. 
![Extension Headers](assets/ext-header-caea032bb5.png)
### Types of Extension Header
IPv6 packet may contain zero, one or more extension headers but these should be present in their recommended order: 
![Order of different Extension Header](assets/next-header-2-68c0dc517c.png)
**Rule:** Hop-by-Hop options header(if present) should always be placed after the IPv6 base header. 
### **Conventions**
- Any extension header can appear at most once except Destination Header because Destination Header is present two times in the above list itself.
- If Destination Header is present before Routing Header then it will be examined by all intermediate nodes specified in the routing header.
- If Destination Header is present just above the Upper layer then it will be examined only by the Destination node.
### Rules of Headers
The order of the header is defined by some predefined rules which are given below:
- If there is a **hop-by-hop**  option then it must be after the  **base**  header of the IPv6 header.
- All headers except the destination header must be present once in the list.
- If the destination header appears before the routing header, then all the intermediate nodes that are in the routing header examine the destination header.
- If the destination header is present before the upper layer, then only the destination nodes will examine the destination header.
### Sequence of Headers
Given order in which all extension header should be chained in IPv6 packet and working of each extension header **:** 
![Working of Extension Header](assets/ext-header-1-f325a4502b.png)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/internet-protocol-version-6-ipv6-header/)

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
