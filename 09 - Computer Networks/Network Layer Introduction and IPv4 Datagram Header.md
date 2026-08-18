---
title: "IPv4 Datagram Header"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/introduction-and-ipv4-datagram-header/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] IPv4 Datagram Header
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/introduction-and-ipv4-datagram-header/)

---

# IPv4 Datagram Header

IP stands for Internet Protocol, and IPv4 refers to Internet Protocol Version 4. IPv4 was the first widely deployed version of the Internet Protocol and was introduced for use in the ARPANET in 1983. An IPv4 address is a 32-bit numeric value, which is represented in dotted decimal notation (for example, 192.168.1.1). IPv4 is responsible for logical addressing and routing of packets across networks.
![ipv4_packet_structure](assets/ipv4_packet_structure-48d8e13873.webp)
IPv4 Packet Structure
- [Internet Protocol Version 4 (IPv4)](https://www.geeksforgeeks.org/computer-networks/what-is-ipv4/) is the fourth version of the Internet Protocol.
- It is a connectionless protocol used in packet-switched networks.
- IPv4 is widely used for data communication over different types of networks, such as [Ethernet](https://www.geeksforgeeks.org/computer-networks/what-is-ethernet/).
- It provides logical addressing to uniquely identify each device on a network.
- IPv4 can be configured in different ways, including manual (static) and automatic (dynamic) configuration, depending on the network type.
- IPv4 uses 32-bit (4-byte) addresses.
- A total of 2³² addresses are possible in IPv4.
- IPv4 addresses are written in dotted-decimal notation, consisting of four octets separated by dots (e.g., 192.168.1.5).
- Traditionally, IPv4 addresses are divided into five classes: A, B, C, D, and E.
- Classes A, B, and C are used for unicast addressing and differ in network and host bit lengths.
- Class D addresses are reserved for [multicasting](https://www.geeksforgeeks.org/computer-networks/multicasting-in-computer-network/).
- Class E addresses are reserved for experimental purposes.
## Characteristics of IPv4
- IPv4 could be a 32-Bit IP Address.
- IPv4 could be a numeric address, and its bits are separated by a dot.
- The number of header fields is twelve and the length of the header field is twenty.
- It has Unicast, broadcast, and multicast style of addresses.
- IPv4 supports [VLSM (Virtual Length Subnet Mask).](https://www.geeksforgeeks.org/computer-networks/introduction-of-variable-length-subnet-mask-vlsm/)
- IPv4 uses the Post Address Resolution Protocol to map to the [MAC address.](https://www.geeksforgeeks.org/computer-networks/mac-address-in-computer-network/)
- [RIP](https://www.geeksforgeeks.org/computer-networks/routing-information-protocol-rip/) may be a routing protocol supported by the routed daemon.
- Networks ought to be designed either manually or with [DHCP](https://www.geeksforgeeks.org/computer-networks/dynamic-host-configuration-protocol-dhcp/).
- Packet fragmentation permits from routers and causing host.
## IPv4 Datagram Header
- **VERSION**:** Version of the IP protocol (4 bits), which is 4 for IPv4
- **HLEN:** IP header length (4 bits), which is the number of 32 bit words in the header. The minimum value for this field is 5 and the maximum is 15.
- **Type of service:**Low Delay, High Throughput, Reliability (8 bits)
- **Total Length:**Length of header + Data (16 bits), which has a minimum value 20 bytes and the maximum is 65,535 bytes.
- **Identification**:** Unique Packet Id for identifying the group of fragments of a single IP datagram (16 bits)
- **Flags**:** 3 flags of 1 bit each : reserved bit (must be zero), do not fragment flag, more fragments flag (same order)
- **Fragment Offset:** Represents the number of Data Bytes ahead of the particular fragment in the particular Datagram. Specified in terms of number of 8 bytes, which has the maximum value of 65,528 bytes.
- **Time to live**:** Datagram’s lifetime (8 bits), It prevents the datagram to loop through the network by restricting the number of Hops taken by a Packet before delivering to the Destination.
- **Protocol:**Name of the protocol to which the data is to be passed (8 bits)
- **Header Checksum**:** 16 bits header [checksum](https://www.geeksforgeeks.org/computer-networks/error-detection-code-checksum/) for checking errors in the datagram header
- **Source IP address**:** 32 bits IP address of the sender
- **Destination IP address**:** 32 bits [IP address](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/) of the receiver
- **Option:** Optional information such as source route, record route. Used by the Network administrator to check whether a path is working or not.
![IPv4-Datagram-Header](assets/IPv4-Datagram-Header-d45905c8e4.jpg)
IPv4 Datagram Header
Due to the presence of options, the size of the datagram header can be of variable length (20 bytes to 60 bytes).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/introduction-and-ipv4-datagram-header/)

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
