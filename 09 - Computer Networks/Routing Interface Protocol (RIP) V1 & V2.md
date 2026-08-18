---
title: "Routing Information Protocol (RIP) V1 & V2"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/routing-interface-protocol-rip-v1-v2/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Routing Information Protocol (RIP) V1 & V2
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/routing-interface-protocol-rip-v1-v2/)

---

# Routing Information Protocol (RIP) V1 & V2

**[Routing Information Protocol (RIP)](https://www.geeksforgeeks.org/computer-networks/routing-information-protocol-rip/)** protocol are the intradomain (interior) routing protocol which is based on distance vector routing and it is used inside an autonomous system.Routers and network links are called node. The first column of routing table is destination address. The cost of metric in this protocol is hop count which is number of networks which need to be passed to reach destination. Here infinity is defined by a fixed number which is 16 it means that using a Rip, network cannot have more than 15 hops.
#### RIP Version-1:
It is an open standard protocol means it works on the various vendor's routers. It works on most of the routers, it is classful routing protocol. Updates are broadcasted. Its administrative distance value is 120, it means it is not reliable, The lesser the administrative distance value the reliability is much more. Its metric is hop count and max hop count is 15. There will be a total of 16 routers in the network. When there will be the same number of hop to reach the destination, Rip starts to perform load balancing. Load balancing means if there are three ways to reach the destination and each way has same number of routers then packets will be sent to each path to reach the destination. This reduces traffic and also the load is balanced. It is used in small companies, in this protocol routing tables are updated in each 30 sec. Whenever link breaks rip trace out another path to reach the destination. It is one of the slowest protocol.
**Advantages of RIP ver1 -**
1. Easy to configure, static router are complex.
2. Less overhead
3. No complexity.
**Disadvantage of RIP ver1 -**
1. Bandwidth utilization is very high as broadcast for every 30 seconds.
2. It works only on hop count.
3. It is not scalable as hop count is only 15. If there will be requirement of more routers in the network it would be a problem .
4. Convergence is very slow, wastes a lot of time in finding alternate path.
#### RIP Version-2:
Due to some deficiencies in the original RIP specification, RIP version 2 was developed in 1993. It supports classless Inter-Domain Routing (CIDR) and has the ability to carry subnet information, its metric is also hop count, and max hop count 15 is same as rip version 1. It supports authentication and does subnetting and multicasting. Auto summary can be done on every router. In RIPv2 Subnet masks are included in the routing update. RIPv2 multicasts the entire routing table to all adjacent routers at the address 224.0.0.9, as opposed to RIPv1 which uses broadcast (255.255.255.255).
**Advantages of RIP ver2 -**
1. It's a standardized protocol.
2. It's VLSM compliant.
3. Provides fast convergence.
4. It sends triggered updates when the network changes.
5. Works with snapshot routing - making it ideal for dial networks.
**Disadvantage of RIP ver2 -** There lies some disadvantages as well:
1. Max hopcount of 15, due to the 'count-to-infinity' vulnerability.
2. No concept of neighbours.
3. Exchanges entire table with all neighbours every 30 seconds (except in the case of a triggered update).
#### RIP ver1 versus RIP ver2:
| RIP Ver1 | RIP Ver2 |
| --- | --- |
| RIP v1 uses what is known as classful routing | RIP v2 is a classless protocol and it supports variable-length subnet masking (VLSM), CIDR, and route summarization |
| RIPv1 routing updates are broadcasted | RIP v2 routing updates are multicasted |
| RIPv1 has no authentication | RIP v2 supports authentication |
| RIP v1 does not carry mask in updates | RIP v2 does carry mask in updates, so it supports for VLSM |
| RIP v1 is an older, no longer much used routing protocol | IP v2 can be useful in small, flat networks or at the edge of larger networks because of its simplicity in configuration and usage |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/routing-interface-protocol-rip-v1-v2/)

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
