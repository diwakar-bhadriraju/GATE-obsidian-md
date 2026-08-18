---
title: "IPv4 Classless Subnet equation"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/ipv4-classless-subnet-equation/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] IPv4 Classless Subnet equation
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/ipv4-classless-subnet-equation/)

---

# IPv4 Classless Subnet equation

Prerequisite - [Classless Addressing](https://www.geeksforgeeks.org/computer-networks/ip-addressing-classless-addressing/), [Supernetting](https://www.geeksforgeeks.org/computer-networks/supernetting-in-network-layer/)
**Problem -** How to calculate Network Address, Broadcast Address, First and Last IP address of a given IP Address in the CIDR(Classless Inter-Domain Routing) Notation.
There is a simple equation to calculate the above mentioned Addresses which is used and tested with Class C Networks*.*
Firstly, remember the No. of IP Addresses with respect to the Network Prefix(the value after the Slash(/) in CIDR Notation) as shown in the Table below.
```
Network Prefix:  Number of IP Addresses(IPs)
24            :      256 IPs
25            :      128 IPs
26            :      64 IPs
27            :      32 IPs
28            :      16 IPs
29            :      8 IPs
30            :      4 IPs
```
Note that in the above table the Number of Hosts for mentioned Network Prefixes will be 2 less than the No. of IP Addresses, because the First IP Address is the Network Address and the Last IP Address is the Broadcast Address.
**Using Equation:**
```
Network ID: floor(Host Address/Subnet Number of Hosts) * Subnet Number of Hosts
Broadcast ID: (Host ID + (Subnet Number of Hosts-1))
First Host: Network ID + 1
Last Host: Broadcast ID - 1
```
**Ex1: 192.168.1.65/28:**
```
65/16 = 4.0625
Network Address: 192.168.1.64            (4*16 = 64)
Broadcast Address: 192.168.1.79     (64+(16-1) = 79)
First Host Address: 192.168.1.65       (64 + 1 = 65)
Last Host Address: 192.168.1.78       (79 - 1 = 78 )
```
**Ex2: 192.168.20.166/25:**
```
166/128 = 1.296875
Network Address: 192.168.20.128          (1*128 = 128)
Broadcast Address: 192.168.20.255          (128+(128-1) = 255)
First Host Address: 192.168.20.129     (128 + 1 = 129)
Last Host Address: 192.168.20.254      (255 - 1 = 254)
```
**Ex3: 192.168.30.14/29:**
```
14/8 = 1.75
Network Address: 192.168.30.8              (1*8 = 8)
Broadcast Address: 192.168.30.15       (8+(8-1) = 15)
First Host Address: 192.168.30.9         (8 + 1 = 9)
Last Host Address: 192.168.30.14        (15 - 1 = 14)
```
**Ex4: 192.168.20.86/30:**
```
86/4 = 21.5
Network Address: 192.168.20.84            (21*4 = 84)
Broadcast Address: 192.168.20.87      (84+(4-1) = 87)
First Host Address: 192.168.20.85       (84 + 1 = 85)
Last Host Address: 192.168.20.86        (87 - 1 = 86)
```
**The above Examples work for only Class C Networks, as we are assuming the host part of the IP Address to be the last octet as in the case of Class C Networks.**
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/ipv4-classless-subnet-equation/)

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
