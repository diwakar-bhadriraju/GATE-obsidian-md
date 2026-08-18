---
title: "Classes of Routing Protocols"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/classes-of-routing-protocols/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Classes of Routing Protocols
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/classes-of-routing-protocols/)

---

# Classes of Routing Protocols

Routing protocols are essential for determining how data packets are transferred across networks. They help routers communicate with each other to find the most efficient paths for data to travel.
Routing protocols are typically divided into categories like **distance vector**, **link-state**, and **hybrid protocols**. Distance vector protocols, such as RIP, determine routes based on the number of hops. Link-state protocols, like OSPF, rely on a more detailed understanding of the entire network topology. Hybrid protocols, such as EIGRP, incorporate elements from both approaches to balance efficiency and accuracy.
## **1. Distance Vector Routing Protocol**
These protocols select the best path based on hop counts to reach a destination network in a particular direction. Dynamic protocol like [RIP](https://www.geeksforgeeks.org/computer-networks/routing-information-protocol-rip/) is an example of a distance vector routing protocol. Hop count is each router that occurs between the source and the destination network. The path with the least hop count will be chosen as the best. 
### **Features**
- Updates of the network are exchanged periodically.
- Updates (routing information) are not broadcasted but shared to neighboring nodes only.
- Full routing tables are not sent in updates; only the distance vector is shared.
- Routers always trust routing information received from neighbor routers. This is also known as routing rumors.
### **Advantages**
- **Simple to Use** : Easy setup and operation.
- **Low Resource Usage** : Requires minimal CPU and memory.
- **Automatic Updates** : Handles network changes automatically.
- **Good for Small Networks** : Works well in simple setups.
### **Disadvantages**
- **Slow Convergence** : Takes time to update routes after a network change.
- **Limited Scalability** : Not efficient for large networks.
- **High Bandwidth Use** : Frequent updates may consume more network bandwidth.
- **Less Accurate** : Routes may not always be optimal.
## **2. Link State Routing Protocol**
These protocols know more about Internetwork than any other distance vector routing protocol. These are also known as SPF (Shortest Path First) protocol. [OSPF](https://www.geeksforgeeks.org/computer-networks/open-shortest-path-first-ospf-protocol-states/) is an example of link-state routing protocol. 
### **Features**
- Hello, messages, also known as keep-alive messages are used for neighbor discovery and recovery.
- The concept of triggered updates is used i.e. updates are triggered only when there is a topology change.
- Only that many updates are exchanged which is requested by the neighbor router.
### Tables Used in Link State Routing
Link state routing protocol maintains three tables namely: 
- **Neighbor table:** the table which contains information about the neighbors of the router only, i.e, to which adjacency has been formed.
- **Topology table:** This table contains information about the whole topology i.e contains both best and backup routes to a particular advertised networks.
- **Routing table:** The [Routing table](https://www.geeksforgeeks.org/computer-networks/routing-tables-in-computer-network/) contains all the best routes to the advertised network.
### **Advantages**
- **Faster Updates** : Quickly adapts to network changes.
- **Accurate Routing** : Provides optimal routes with a complete network view.
- **Works for Large Networks** : Suitable for big, complex networks.
- **Prevents Routing Loops** : Avoids errors in route calculations.
- **More Reliable** : Less prone to mistakes in routing.
### Disadvanatges
- **High Resource Usage** : Requires more memory and processing power.
- **Complex Setup** : More difficult to configure and maintain.
- **Increased Bandwidth** : Uses more bandwidth for network updates.
- **Not Ideal for Small Networks** : Overhead is unnecessary in small setups.
## **3. Hybrid Protocol**
It is also known as hybrid routing protocol which uses the concept of both distance vector and link-state routing protocol. [Enhanced Interior Gateway Routing Protocol (EIGRP)](https://www.geeksforgeeks.org/computer-networks/eigrp-fundamentals/) is an example of this class of routing protocol. EIGRP acts as a link-state routing protocol as it uses the concept of Hello protocol for neighbor discovery and forming an adjacency. Also, partial updates are triggered when a change occurs. EIGRP acts as a distance-vector routing protocol as it learned routes from directly connected neighbors.
### Advanatages
- **Combines Strengths** : Mixes benefits of distance vector and link state routing.
- **Scalable** : Works well in both small and large networks.
- **Quick Updates** : Adapts fast to network changes.
- **Efficient Bandwidth** : Uses less bandwidth than pure link state.
- **Better for Larger Networks** : More suitable for bigger networks.
### Disadvanatges
- **Complex Setup** : Harder to configure and manage.
- **Higher Resource Use** : Requires more memory and [CPU](https://www.geeksforgeeks.org/computer-organization-architecture/what-are-the-functions-of-a-cpu/) .
- **Inconsistent Updates** : Can sometimes lead to slower updates.
## Conclusion
Routing protocols help routers find the best paths for data to travel across a network. The three main types are **distance vector**, **link-state**, and **hybrid protocols**. Distance vector protocols choose paths based on the number of hops and are best for smaller networks. Link-state protocols build a network map to select the shortest paths, making them ideal for larger networks. Hybrid protocols combine both methods, providing efficiency for networks of any size. Using the right protocol ensures that data flows efficiently and improves network performance.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/classes-of-routing-protocols/)

## GATE CS

- Subject: Computer Networks
- Topic: Network Layer

> [!note] Related notes
>
> - [[Administrative Distance (AD) and Autonomous System (AS)]]
> - [[ARP, Reverse ARP(RARP), Inverse ARP (InARP), Proxy ARP and Gratuitous ARP]]
> - [[C Program to find IP Address, Subnet Mask & Default Gateway]]
> - [[Circuit Switching]]
> - [[Classification of Routing Algorithms – Set 1]]
> - [[Collision Domain and Broadcast Domain]]
> - [[Computer Network Circuit Switching VS Packet Switching]]
> - [[Computer Network Servers]]
> - [[Computer Networks Longest Prefix Matching in Routers]]
> - [[Difference between layer-2 and layer-3 switches]]
