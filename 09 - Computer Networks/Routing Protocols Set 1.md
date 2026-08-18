---
title: "Distance Vector Routing (DVR) Protocol"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/distance-vector-routing-dvr-protocol/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Distance Vector Routing (DVR) Protocol
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/distance-vector-routing-dvr-protocol/)

---

# Distance Vector Routing (DVR) Protocol

Distance Vector Routing (DVR) is a protocol where each router keeps a table showing the distance (in hops) to all other routers. Routers regularly share these tables with neighbors, so they can update routes and always find the shortest, most efficient paths for data.
The Distance Vector Routing Algorithm is based on the [Bellman-Ford Algorithm](https://www.geeksforgeeks.org/dsa/bellman-ford-algorithm-dp-23/). It was first used in the old ARPANET.
- Each router tells its neighbors about changes in the network topology (like new links or failures).
- Each router uses this information to recalculate the shortest paths to every destination.
### **Bellman-Ford Basics**
Each router maintains a distance vector table that shows the shortest known distance to every other router.
Information stored in a DV router includes:
- A unique Router ID
- Link cost for each connection (can be static or dynamic)
- Number of intermediate hops needed to reach other routers
Initialization:
- Distance to itself = 0
- Distance to all other routers = infinity
## **Working**
**1. Routers share information**: Each router sends its distance vector to all its neighbors.
**2. Routers update information**:
- When a router receives a neighbor’s table, it saves it.
- If new information changes the shortest path, the router updates its own table.
- Updates also occur if a link goes down.
$$
D_x(y) = \min \{ C(x,v) + D_v(y) \}
$$
**3. Distance calculation:**
 The cost of reaching a destination is calculated using the Bellman-Ford equation:
Where:
- Dx​(y) = cost from router x to destination y
- C(x,v) = cost from router x to neighbor v
- Dv(y)= cost from neighbor v to destination y
**Example:** Consider 3-routers X, Y and Z as shown in figure. Each router have their routing table. Every routing table will contain distance to the destination nodes.
![Distance Vector Routing (DVR)](assets/DVP1-050c2b40ca.jpg)
Consider router X , X will share it routing table to neighbors and neighbors will share it routing table to it to X and distance from node X to destination will be calculated using bellmen- ford equation.
> Dx(y) = min { C(x,v) + Dv(y)} for each node y ? N
As we can see that distance will be less going from X to Z when Y is intermediate node(hop) so it will be update in routing table X.
![Distance Vector Routing (DVR)](assets/dvp2-c34717219d.jpg)
Similarly for Z also:
![Distance Vector Routing (DVR)](assets/dvp3-18b9224a75.jpg)
Finally the routing table for all:
![Distance Vector Routing (DVR)](assets/dvp4-90cbd65aa1.jpg)
## Applications
- **Computer Networking** : It helps route data packets in networks.
- **Telephone Systems**: It's used in some telephone switching systems.
- **Military Applications**: It has been used to route missiles.
## **Advantages**
- **Shortest Path:** Finds the best route for data.
- **Wide Usage:** Works in LANs, MANs, and WANs.
- **Easy to Implement:** Simple setup with low resource requirements.
## Disadvantages
- **Slow Convergence:** Takes time to adapt to changes.
- **Count-to-Infinity Problem:** Can keep increasing hop counts endlessly in some failure cases.
- **More Traffic:** Routers share updates periodically, even if nothing changes, which wastes bandwidth.
- **Scalability Issues:** Large networks mean larger routing tables, which can cause congestion on WAN links.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/distance-vector-routing-dvr-protocol/)

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
