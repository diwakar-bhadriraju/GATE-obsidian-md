---
title: "What is Internet Protocol Version 6 (Pv6)"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/internet-protocol-version-6-ipv6/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] What is Internet Protocol Version 6 (Pv6)
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/internet-protocol-version-6-ipv6/)

---

# What is Internet Protocol Version 6 (Pv6)

IPv6 is the upgraded Internet Protocol, designed to meet the growing demand for IP addresses that IPv4 cannot handle due to its limited address space.
**Key Features of IPv6:**
- 128-bit address space (2¹²⁸ possible addresses).
- Written in hexadecimal, separated by colons (:).
- Consists of 8 groups, each representing 2 bytes (16 bits).
- Each hexadecimal digit equals 4 bits (1 nibble).
- Groups are separated by a colon (:).
## Components in IPv6 Address Format
- There are 8 groups and each group represents 2 Bytes (16-bits).
- Each Hex-Digit is of 4 bits (1 nibble)
- Delimiter used - colon (:)
![abcd_ef01_2345_6789_abcd_b201_5482_d023](assets/abcd_ef01_2345_6789_abcd_b201_5482_d023-6abf5a9c49.webp)
Example of IPV6 Address
## Need For IPv6
IPv6 was mainly introduced to solve IPv4 address depletion caused by the rapid growth of devices (especially IoT) and to improve efficiency, support multimedia, and enhance security. Key features include:
1. **Large Address Space:** 128-bit addresses (vs 32-bit in IPv4) vastly increase available addresses.
2. **Better Header Format:** Base header separated from optional fields, speeding up routing.
3. **New Options & Extensibility:** Allows additional functionalities and future protocol extensions.
4. **Resource Allocation:** New fields Traffic Class and Flow Label enable special handling for real-time audio/video.
5. **Enhanced Security:** Built-in encryption and authentication ensure confidentiality and integrity.
6. **Addressing Methods:** Supports Unicast, Multicast, and Anycast.
## Addressing Methods
- **Unicast Address:** Identifies a single device; packets are delivered to that one specific interface.
- **Multicast Address:** Identifies a group of devices; packets are delivered to all members of the group simultaneously.
- **Anycast Address:** Assigned to multiple devices; packets are delivered to the nearest device in the group.
**Note:** Broadcast is not defined in IPv6.
## **Types of IPv6 Address**
We have 128 bits in IPv6 address but by looking at the first few bits we can identify what type of address it is. 
| Prefix | Allocation | Fraction of Address Space |
| --- | --- | --- |
| 0000 0000 | Reserved | 1/256 |
| 0000 0001 | Unassigned (UA) | 1/256 |
| 0000 001 | Reserved for NSAP | 1/128 |
| 0000 01 | UA | 1/64 |
| 0000 1 | UA | 1/32 |
| 0001 | UA | 1/16 |
| 001 | Global Unicast | 1/8 |
| 010 | UA | 1/8 |
| 011 | UA | 1/8 |
| 100 | UA | 1/8 |
| 101 | UA | 1/8 |
| 110 | UA | 1/8 |
| 1110 | UA | 1/16 |
| 1111 0 | UA | 1/32 |
| 1111 10 | UA | 1/64 |
| 1111 110 | UA | 1/128 |
| 1111 1110 0 | UA | 1/512 |
| 1111 1110 10 | Link-Local Unicast Addresses | 1/1024 |
| 1111 1110 11 | Site-Local Unicast Addresses | 1/1024 |
| 1111 1111 | Multicast Address | 1/256 |
> **Note:** In IPv6, all 0’s and all 1’s can be assigned to any host, there is not any restriction like IPv4. 
### **Provider-Based Unicast Address**
Used for global communication in IPv6.
![Provider-based Unicast address](assets/IP_v6_2-0ecf0f9d3f.png)
- **Prefix (First 3 bits):** Identifies the address as provider-based.
- **Registry ID (5 bits):** Specifies the regional registry. Out of 32 possible IDs (2⁵), only 4 are currently in use.
![Registry ID](assets/IP_v6_4-4a1c74ce89.png)
- **Provider Id:** Depending on the number of service providers that operate under a region, certain bits will be allocated to the Provider Id field. This field need not be fixed. Let’s say if Provider Id = 10 bits then Subscriber Id will be 56 - 10 = 46 bits.
- **Subscriber Id:** After Provider Id is fixed, the remaining part can be used by ISP as a normal IP address.
- **Intra Subscriber:** This part can be modified as per the need of the organization that is using the service
### Geography-Based Unicast Address
These are designed for **location-based routing**.
- **Global Routing Prefix:** Encodes geographical details such as latitude and longitude. Currently not in practical use.
- **Interface ID:** Replaces the IPv4 host ID, uniquely identifying an interface on a node.
![IP_v6_5](assets/IP_v6_5-f6c68db537.png)
Geography-Based Unicast Address
### Some Special Addresses
 **1.** **Unspecified**
![ Unspecified address](assets/IP_v6_6-50118f8aad.png)**2. Loopback**
![Loopback Address](assets/IP_v6_7-1a5baae971.png)**3. IPv4 Compatible**
![IPv4 Compatible ](assets/IP_v6_8-9aca3534f7.png)**4. IPv4 mapped**
## IPv4 mapped**Local Unicast Addresses**
These are of two types:
### **1. Link-Local Address**
![Link-Local Address](assets/IP_v6_10-cd9d0fd4c8.png)
A link-local address is used for addressing a single link. It can also be used to communicate with nodes on the same link. The link-local address always begins with 1111111010 (i.e. FE80). The router will not forward any packet with Link-local address. 
### **2. Site Local Address**  Site Local Address
Site local addresses are equivalent to a private IP address in IPv4. Likely, some address space is reserved, which can only be routed within an organization. The first 10-bits are set to 1111111011, which is why Site local addresses always begin with FEC0. The following 32 bits are Subnet IDs, which can be used to create a subnet within the organization. The node address is used to uniquely identify the link; therefore, we use a 48-bits MAC address here. 
## Advantages of IPv6
- **Realtime Data Transmission:** Data is transmitted immediately with minimal delay. Example: Live streaming of sports events with 5–6 seconds delay.
- **IPv6 Authentication:**Ensures data comes from the legitimate sender and hasn’t been altered. Example: Verifying messages using hash values.
- **IPv6 Encryption:**Can encrypt messages at the network layer, even if the application layer doesn’t, providing built-in security.
- **Faster Router Processing:**IPv6 has a fixed 40-byte header, allowing routers to process packets faster compared to IPv4’s 20–60 byte variable header.
## Disadvantages of IPV6
- **Transition Period:** Due to widespread use of IPv4, shifting completely to IPv6 will take a long time.
- **Communication Barrier:** IPv4 and IPv6 machines cannot communicate directly with each other.
- **No Backward Compatibility:** IPv6 cannot run on IPv4-capable computers because it's not supported by IPv4 systems.
- **Conversion Challenges:** IPv6's inability to uniquely identify each device on the network makes the transition from IPv4 time-consuming.
- **Protocol Isolation:** IPv4 and IPv6 cannot communicate with each other directly, preventing cross-protocol communication.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/internet-protocol-version-6-ipv6/)

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
