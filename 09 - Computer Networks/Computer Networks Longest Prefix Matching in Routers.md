---
title: "Longest Prefix Matching in Routers"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/longest-prefix-matching-in-routers/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Longest Prefix Matching in Routers
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/longest-prefix-matching-in-routers/)

---

# Longest Prefix Matching in Routers

**What is Forwarding?** 
Forwarding is moving incoming packets to the appropriate interface. Routers use a forwarding table to decide which incoming packet should be forwarded to which next hop. 
**What is an** **IP prefix?** 
IP prefix is a prefix of IP address. All computers on one network have the same IP prefix. For example, in 192.24.0.0/18, 18 is the length of the prefix and prefix is the first 18 bits of the address. 
**How does forwarding work?** 
Routers basically look at the destination address's IP prefix, searches the forwarding table for a match, and forward the packet to the corresponding next hop in the forwarding table. 
**What happens if the prefixes overlap?** 
Since prefixes might overlap (this is possible as classless addressing is used everywhere), an incoming IP's prefix may match multiple IP entries in a table. 
For example, consider the below forwarding table 
| Prefix | Next Hop |
| --- | --- |
| 192.24.0.0/18 | D |
| 192.24.12.0/22 | B |
In the above table, addresses from 192.24.12.0 to 192.24.15.255 overlap, i.e., match with both entries of the table. 
To handle the above situation, routers use the **Longest Prefix Matching** rule. The rule is to find the entry in a table which has the longest prefix matching with the incoming packet's destination IP and forward the packet to the corresponding next hope. 
In the above example, all packets in overlapping range (192.24.12.0 to 192.24.15.255) are forwarded to next hop B as B has a longer prefix (22 bits). 
![longestprefix](assets/Computer-Networks-Longest-Prefix-Matchin-1493919989.png)
**Example 1:** Routers forward a packet using forwarding table entries. The network address of the incoming packet may match multiple entries. How do routers resolve this? 
(A) Forward it to the router whose entry matches with the longest prefix of the incoming packet 
(B) Forward the packet to all routers whose network addresses match. 
(C) Discard the packet. 
(D) Forward it the router whose entry matches with the longest suffix of an incoming packet 
**Answer:** (A) The network addresses of different entries may overlap in the forwarding table. Routers forward the incoming packet to the router which hashes the longest prefix matching with the incoming packet. 
 **Example 2:** Classless Inter-domain Routing (CIDR) receives a packet with address 131.23.151.76. The router’s routing table has the following entries: (GATE CS 2015) 
```
Prefix           Output Interface Identifier
131.16.0.0/12              3
131.28.0.0/14              5
131.19.0.0/16              2
131.22.0.0/15              1
```
The identifier of the output interface on which this packet will be forwarded is \_\_\_\_\_\_. 
**Answer:** "1". We need to first find out matching table entries for an incoming packets with address "131.23.151.76". The address matches with two entries "131.16.0.0/12" and "131.22.0.0/15" (We found this by matching the first 12 and 15 bits respectively). 
So should the packet go to interface 3 or 1? We use Longest Prefix Matching to decide among the two. The most specific of the matching table entries is used as the interface. Since "131.22.0.0/15" is most specific, the packet goes to interface 1. 
**Exercise** 
Consider the following routing table of a router. 
| Prefix | Next Hop |
| --- | --- |
| 192.24.0.0/18 | D |
| 192.24.12.0/22 | B |
Consider the following three IP addresses.
1. 192.24.6.0
2. 192.24.14.32
3. 192.24.54.0
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/longest-prefix-matching-in-routers/)

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
> - [[Difference between layer-2 and layer-3 switches]]
