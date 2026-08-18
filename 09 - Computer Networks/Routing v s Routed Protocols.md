---
title: "Routing v/s Routed Protocols in Computer Network"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/routing-v-s-routed-protocols-in-computer-network/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Routing v/s Routed Protocols in Computer Network
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/routing-v-s-routed-protocols-in-computer-network/)

---

# Routing v/s Routed Protocols in Computer Network

In networking, it's essential to understand the difference between routing protocols and routed protocols, as they play distinct roles in how data is delivered across networks. Routed protocols are those protocols which support such data traffic. Examples of routed protocols are IPv4, IPv6 and AppleTalk.
Routing protocols are the ones that are responsible for sending them. Examples of routing protocols are [RIP](https://www.geeksforgeeks.org/computer-networks/routing-information-protocol-rip/)(Routing Information Protocol), [EIGRP](https://www.geeksforgeeks.org/computer-networks/eigrp-fundamentals/)(Enhanced Interior Gateway Routing Protocol) and [OSPF](https://www.geeksforgeeks.org/computer-networks/open-shortest-path-first-ospf-protocol-states/)(Open Shortest Path First).
The Network Layer of the OSI Model is responsible for providing logical addressing, which routers use to select best path for routing packets. There are two types of packets used at this layer :
- **Data Packets -** The user data is transferred in the inter-network by these data packets.
- **Route Update Packets -** The information about the networks connected to all the routers is updated to the neighbouring routers through route update packets.
Both the Routing and Routed Protocols are discussed below
![Routing-vs-Routed-Protocols_](assets/Routing-vs-Routed-Protocols_-36d334040b.webp)
Routing Vs Routed Protocols
## Routing Protocols
Routing Protocols are used by routers to communicate with each other and learn the best path for forwarding data across a network.
**Key Functions:**
- Build and maintain routing tables.
- Share network topology information with other routers.
- Determine the optimal path for data packets.
**Common Routing Protocols:**
| Protocol | Type | Description |
| --- | --- | --- |
| RIP | Distance Vector | Older, simple, uses hop count |
| OSPF | Link State | Faster, scalable, widely used |
| EIGRP | Hybrid | Cisco proprietary, efficient |
| BGP | Path Vector | Used between ISPs and large networks |
Routing Protocols can be classified on the basis of different characteristics :
![Routing-Protocols](assets/Routing-Protocols-bb15a36d18.png)
Routing Types
**Static Routing:** Routes are manually configured by the network administrator and do not dynamically update based on network changes. This type of routing is best suited for small networks where the network topology does not change frequently.
**Dynamic Routing:** Routes are automatically updated based on changes in the network topology. This type of routing is best suited for large, complex networks where the network topology changes frequently. There are several types of dynamic routing protocols, including:
- Distance Vector Routing Protocols: Examples include Routing Information Protocol (RIP) and Interior Gateway Routing Protocol (IGRP).
- Link-State Routing Protocols: Examples include Open Shortest Path First (OSPF) and Intermediate System to Intermediate System (IS-IS).
- Hybrid Routing Protocols: An example is Enhanced Interior Gateway Routing Protocol (EIGRP), which combines characteristics of both distance vector and link-state routing.
- Path Vector Routing Protocols: Border Gateway Protocol (BGP) is the most common Path Vector routing protocol and is used for routing between Autonomous Systems (AS) across the Internet.
**Hierarchical Routing:** Network is divided into multiple levels or domains, with each level or domain having its own routing protocol. This type of routing is best suited for large, complex networks that need to be divided into manageable sections.
### **Advantages of Routing Protocols**
- **Efficient Resource Utilization:** Enables data to be forwarded through the most suitable paths, helping optimize bandwidth usage, reduce delays, and improve overall network performance.
- **Scalability:** Supports the growth of networks by adapting to the addition of new devices, links, and routing domains without requiring extensive manual reconfiguration.
- **Reliability and Fault Tolerance:** Automatically adjusts to network failures or topology changes by selecting alternate paths, ensuring continuous communication and minimizing service disruption.
- **Flexibility:** Can operate effectively across different network architectures and topologies, making it suitable for a wide range of deployment environments.
## Routed Protocols
Routed Protocols are actual network protocols that are used to carry user data (such as emails, web pages, or files) across the network.
**Key Functions:**
- Carry data from one host to another across networks.
- Use routing tables to decide where data should go.
**Common Routed Protocols :**
| Protocol | Description |
| --- | --- |
| IP | Most widely used , forms the backbone of the internet. |
| IPX | Used in older Novell networks (largely obsolete). |
| AppleTalk | Used in older Apple networks (obsolete). |
### **Advantages of Routed Protocols**
- End-to-End Communication: Routed protocols enable end-to-end communication between devices on a network, irrespective of the underlying network topology.
- Interoperability: Routed protocols facilitate interoperability between devices and network types, allowing communication between devices running different network protocols.
- Addressing: Routed protocols provide addressing schemes that allow devices to identify and communicate with each other across the network.
- Reliability: Routed protocols ensure reliable delivery of data by providing error checking and correction mechanisms, ensuring that data is transmitted without errors.
### Key Difference between them
| Feature | **Routing Protocols** | **Routed Protocols** |
| --- | --- | --- |
| Purpose | Discover and maintain routes. | Send user data through those routes. |
| Example Protocols | RIP, OSPF, BGP, EIGRP. | IP, IPX, AppleTalk. |
| Function | Build/update routing tables. | Use routing tables to deliver packets. |
| Used by | Routers | End devices and routers. |
| Data Type Handled | Control information (routing updates). | Actual user data. |
### Comparing both in Real Life Analogy
Now let's take an real-life analogy to better understand the difference between routed and routing protocols. Suppose you want to go to your home after your semester examinations. You book a cab or take a bus to your home. In the path of your journey, you encounter several sign boards which help you take proper or best path, or in case of a cab, Google Maps will help you in choosing the best route.
In this analogy, consider yourself as the DATA, the bus or cab as the ROUTED PROTOCOL and the sign boards or the GPS installed in your driver's phone as the ROUTING PROTOCOL.
Similarly, in a network routers use routing protocols to determine the best path for a packet to travel through the inter-network more efficiently. Routed protocols are assigned to an interface and determine the method of delivering the packet. Now, lets move on to the different types of routing protocols.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/routing-v-s-routed-protocols-in-computer-network/)

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
