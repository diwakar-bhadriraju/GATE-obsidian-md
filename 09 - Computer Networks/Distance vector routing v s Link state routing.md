---
title: "Difference between Distance vector routing and Link State routing"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/difference-between-distance-vector-routing-and-link-state-routing/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Difference between Distance vector routing and Link State routing
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/difference-between-distance-vector-routing-and-link-state-routing/)

---

# Difference between Distance vector routing and Link State routing

Routing is a process in computer networks which is used to find best path to transmit data packets from one node to another. **Distance Vector Routing** and **Link State Routing** are two most used dynamic routing algorithms. They both are a part of Intradomain routing which refer to routing of devices within a same network.
## Distance Vector Routing
Distance Vector Routing is an algorithm that is subject to change where a router calculates distances to every possible destination based on its immediate neighbors only, the router’s routing table is shared with routers that are directly connected, during regular intervals, this received information makes the routers update their tables while route computation uses [Bellman-Ford algorithm](https://www.geeksforgeeks.org/dsa/bellman-ford-algorithm-dp-23/) most of the time, in spite of being relatively simple. However, Distance Vector Routing has some problems such as [Count to Infinity](https://www.geeksforgeeks.org/computer-networks/route-poisoning-and-count-to-infinity-problem-in-routing/) or [persistent routing loops](https://www.geeksforgeeks.org/computer-networks/what-is-routing-loop-and-how-to-avoid-routing-loop/).
Read more about [Distance Vector Routing](https://www.geeksforgeeks.org/computer-networks/distance-vector-routing-dvr-protocol/).
## Link State Routing
Link State Routing, as opposed to Distance Vector Routing, is a dynamic routing algorithm such that each router maintains knowledge of the entire network, instead of sharing information only with neighbors, routers flood their link state information across the entire network to make sure all routers have the same view of the network topology, [Dijkstra’s Algorithm](https://www.geeksforgeeks.org/dsa/introduction-to-dijkstras-shortest-path-algorithm/) and other Link State Routing algorithms are employed in order to compute shortest path to all destinations, it does not lead to persistent loop but it can result in more network traffic due to flooding link state information.
Read more about [Link State Routing](https://www.geeksforgeeks.org/computer-networks/unicast-routing-link-state-routing/).
![](assets/intro-image-376aff07b7.jpeg)
Distance Vector Routing Vs Link State Routing
## **Comparison between Distance Vector Routing and Link State Routing**
| Distance Vector Routing | Link State Routing |
| --- | --- |
| Bandwidth required is less due to local sharing, small packets and no flooding. | Bandwidth required is more due to flooding and sending of large link state packets. |
| Based on local knowledge, since it updates table based on information from neighbours. | Based on global knowledge, it have knowledge about entire network. |
| Make use of [Bellman Ford Algorithm](https://www.geeksforgeeks.org/dsa/bellman-ford-algorithm-dp-23/). | Make use of [Dijakstra's algorithm.](https://www.geeksforgeeks.org/dsa/introduction-to-dijkstras-shortest-path-algorithm/) |
| Traffic is less. | Traffic is more. |
| Converges slowly i.e, good news spread fast and bad news spread slowly. | Converges faster. |
| [Count of infinity problem](https://www.geeksforgeeks.org/computer-networks/route-poisoning-and-count-to-infinity-problem-in-routing/). | No count of infinity problem. |
| [Persistent looping](https://www.geeksforgeeks.org/computer-networks/what-is-routing-loop-and-how-to-avoid-routing-loop/) problem i.e, loop will be there forever. | No persistent loops, only transient loops. |
| Practical implementation is [RIP](https://www.geeksforgeeks.org/computer-networks/routing-information-protocol-rip/) and [IGRP](https://www.geeksforgeeks.org/computer-networks/igrp-routing-protocol/). | Practical implementation is [OSPF](https://www.geeksforgeeks.org/computer-networks/open-shortest-path-first-ospf-protocol-states/) and [ISIS](https://www.geeksforgeeks.org/computer-networks/difference-between-ospf-and-is-is/). |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/difference-between-distance-vector-routing-and-link-state-routing/)

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
