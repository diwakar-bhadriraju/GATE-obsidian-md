---
title: "Unicast Communication and Link State Routing"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/unicast-routing-link-state-routing/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Unicast Communication and Link State Routing
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/unicast-routing-link-state-routing/)

---

# Unicast Communication and Link State Routing

Unicast means the transmission from a single sender to a single receiver. It is a point-to-point communication between the sender and receiver. There are various unicast protocols such as TCP, HTTP, etc.  
- [TCP](https://www.geeksforgeeks.org/computer-networks/what-is-transmission-control-protocol-tcp/) (Transmission Control Protocol) is the most commonly used unicast protocol. It is a connection-oriented protocol that relies on acknowledgment from the receiver side.
- [HTTP](https://www.geeksforgeeks.org/blogs/http-full-form/) stands for HyperText Transfer Protocol. It is an object-oriented protocol for communication.
![unicast_example](assets/unicast_example-d60f664f76.webp)
Unicast Routing
## Major Protocols of Unicast Routing
1. **Distance Vector Routing:**  Distance-Vector routers use a distributed algorithm to compute their routing tables.
2. **Link-State Routing:**  Link-State routing uses link-state routers to exchange messages that allow each router to learn the entire network topology.
3. **Path-Vector Routing:** It is a routing protocol that maintains the path that is updated dynamically.
## Link State Routing
Link State Routing is a protocol where each router learns the entire network topology instead of just neighbor information. Using this knowledge, routers calculate the shortest path to every destination with Dijkstra’s algorithm.
**Key Features:**
1. **Neighborhood Knowledge:** Each router shares information about its directly connected links (cost and identity) rather than the full routing table.
2. **Flooding:** This information is broadcast to all routers in the network so that everyone has the same view of the topology.
3. **Information Sharing:** Updates are sent only when changes occur (not periodically).
**Phases of LSR:**
1. **Reliable Flooding:** Every router eventually learns the complete network graph.
2. **Route Calculation:** Each router applies Dijkstra’s algorithm to compute the optimal path to every other node.
## Features
- **Link State Packet:**  A small packet that contains routing information.
- **Link-State Database:**  A collection of information gathered from the link-state packet.
- **Shortest Path First Algorithm (Dijkstra algorithm):**  A calculation performed on the database results in the shortest path
- **Routing Table:**  A list of known paths and interfaces.
## Calculation of Shortest Path
To find the shortest path, each node needs to run the famous [Dijkstra algorithm](https://www.geeksforgeeks.org/dsa/dijkstras-shortest-path-algorithm-greedy-algo-7/). Let us understand how can we find the shortest path using an example.
**Note:** We use a boolean array **sptSet[]** to represent the set of vertices included in SPT. If a value **sptSet[v]** is true, then vertex v is included in SPT, otherwise not. Array **dist[]** is used to store the shortest distance values of all vertices.
Consider the below graph and src = 0.
![Shortest Path Calculation - Step 1](assets/Unicast-routing-1-4c7aa507db.png)
Shortest Path Calculation - Step 1
**STEP 1:** Initially, the shortest path tree set (**sptSet**) is empty, and the distances are:
`{0, ∞, ∞, ∞, ∞, ∞, ∞, ∞}` (where ∞ = infinity).
The vertex with the **minimum distance** is chosen **vertex 0**.
Add vertex 0 to sptSet i.e `sptSet = {0}`.
Update distances of vertices adjacent to 0:
- Distance to vertex 1 becomes **4**.
- Distance to vertex 7 becomes **8**.
So, the distance array is updated to:
`{0, 4, ∞, ∞, ∞, ∞, ∞, 8}` 
The following subgraph shows vertices and their distance values. Vertices included in SPT are included in GREEN color.
![Shortest Path Calculation - Step 2](assets/Unicast-routing-2-2-b7795dd984.png)
Shortest Path Calculation - Step 2
**STEP 2:** Pick the vertex with minimum distance value and not already included in SPT (not in sptSET). The vertex 1 is picked and added to sptSet. So sptSet now becomes {0, 1}. Update the distance values of adjacent vertices of 1. The distance value of vertex 2 becomes 12.
![Shortest Path Calculation - Step 3](assets/Unicast-routing-2-3-47e9d8ac42.png)
Shortest Path Calculation - Step 3
**STEP 3:** Pick the vertex with minimum distance value and not already included in SPT (not in sptSET). Vertex 7 is picked. So sptSet now becomes {0, 1, 7}. Update the distance values of adjacent vertices of 7. The distance value of vertex 6 and 8 becomes finite (15 and 9 respectively). 
![Shortest Path Calculation - Step 4](assets/Unicast-routing-2-4-709ede32fd.png)
Shortest Path Calculation - Step 4
**STEP 4:** Pick the vertex with minimum distance value and not already included in SPT (not in sptSET). Vertex 6 is picked. So sptSet now becomes {0, 1, 7, 6}. Update the distance values of adjacent vertices of 6. The distance value of vertex 5 and 8 are updated.
![Shortest Path Calculation - Step 5](assets/Unicast-routing-2-5-bfad513dfd.png)
Shortest Path Calculation - Step 5
We repeat the above steps until sptSet includes all vertices of the given graph. Finally, we get the following Shortest Path Tree (SPT).
![Shortest Path Calculation - Step 6](assets/Unicast-routing-2-6-aebfc741e1.png)
Shortest Path Calculation - Step 6
## Characteristics
- Requires a large amount of memory.
- Shortest path computations need more CPU cycles.
- Quickly reacts to topology changes.
- Authentication mechanisms can be used.
- No split horizon techniques are needed/possible.
- Example protocol: OSPF (Open Shortest Path First).
## Protocols of Link State Routing
1. [Open Shortest Path First (OSPF)](https://www.geeksforgeeks.org/computer-networks/open-shortest-path-first-ospf-protocol-fundamentals/)
2. Intermediate System to Intermediate System (IS-IS)
### Open Shortest Path First (OSPF)
- Type: Link-state, intradomain (interior) routing protocol developed by IETF.
- Nature: Open standard, classless (supports VLSM and CIDR).
- Updates: Multicast to 224.0.0.5 (all OSPF routers) and 224.0.0.6 (designated routers).
- Implementation: Runs at the network layer over IP, using protocol number 89.
- Algorithm: Uses Shortest Path First (SPF), i.e., Dijkstra’s algorithm.
- Advantage: Supports subnetting flexibility, fast convergence, and secure neighbor authentication.
### Intermediate System to Intermediate System (IS-IS)
- Type: Standardized link-state routing protocol for the OSI model.
- Identification: Routers are identified by a System ID.
- Updates: Sent via CLNS (Connectionless Network Service), so IS-IS does not require IP connectivity between routers.
- Use Case: Widely used in large service provider networks due to scalability.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/unicast-routing-link-state-routing/)

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
