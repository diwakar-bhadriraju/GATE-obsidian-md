---
title: "Open Shortest Path First (OSPF) Protocol Fundamentals"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/open-shortest-path-first-ospf-protocol-fundamentals/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Open Shortest Path First (OSPF) Protocol Fundamentals
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/open-shortest-path-first-ospf-protocol-fundamentals/)

---

# Open Shortest Path First (OSPF) Protocol Fundamentals

Open Shortest Path First (OSPF) is a link-state Interior Gateway Protocol (IGP) developed by the Internet Engineering Task Force (IETF) to provide efficient routing within an Autonomous System (AS). OSPF uses the Shortest Path First (SPF) algorithm, developed by Dijkstra, to determine the best route to each destination.
![OSPF](assets/OSPF-a1c24195a3.webp)
OSPF Network Topology
> **Note:** Unlike distance-vector protocols (like RIP), OSPF does not send periodic updates, instead, it triggers updates only when a change occurs in the network. This makes OSPF faster, more scalable and more efficient, making it widely used in large enterprise and service provider networks.
## Open Shortest Path First (OSPF) Basics
- **Protocol Type**: Interior Gateway Protocol (IGP).
- **Protocol Number**: 89.
- **Administrative Distance (AD)**: 110.
- **Classless Protocol**: Supports VLSM and CIDR.
- **OSPF Multicast Addresses**:
> **224.0.0.5:** All OSPF routers.
> **224.0.0.6:** Designated Router (DR) and Backup Designated Router (BDR).
## OSPF Terminologies
**1. Link-State Advertisements (LSAs)**: Carry network topology information.
**2. Link-State Database (LSDB)**: Collection of all LSAs in the area.
### **3. Areas**
- **Backbone Area (Area 0)**: Core of the OSPF domain; all other areas must connect here.
- **Normal Areas**: Standard areas that connect to Area 0.
- **Stub Areas**: Reduce routing table size by limiting external route information.
### 4. Router Types
- **Internal Router:** Operates inside a single area.
- **Area Border Router (ABR):** Connects multiple areas to Area 0.
- **Autonomous System Boundary Router (ASBR):** Connects OSPF to other routing protocols.
- **Designated Router (DR):** Elected on broadcast/multi-access networks to reduce adjacencies.
- **Backup Designated Router (BDR):** Backup for DR to ensure redundancy.
### 5. Neighbor Adjacency Requirements
- Same Area ID.
- Unique Router ID.
- Matching Subnet, Hello/Dead timers and Authentication.
## OSPF Configuration Steps
1. Assign a Router ID (manual or automatic).
2. Enable OSPF on interfaces using network statements.
3. Define areas and network types (Area 0 is mandatory).
4. Set authentication (Null, Plain-text or MD5).
5. **Verification commands**:
> show ip ospf neighbor – Displays OSPF neighbors.
> show ip ospf database – Displays LSDB.
## OSPF Message Types
1. **Hello Message**: Discovers and maintains neighbor relationships.
2. **Database Description (DBD)**: Summarizes LSDB contents for comparison.
3. **Link-State Request (LSR)**: Requests missing LSAs from neighbors.
4. **Link-State Update (LSU)**: Contains full LSAs to update neighbors.
5. **Link-State Acknowledgment (LSAck)**: Confirms receipt of LSUs.
## OSPF Timers
- **Hello Timer**: Interval between Hello packets (default: 10 sec).
- **Dead Timer**: Time to declare a neighbor down if Hellos are missing (default: 40 sec).
- **Adjustable Timers**: Can be modified for faster or slower detection depending on the network.
## OSPF Network Types
- **Point-to-Point**: Direct link between two routers.
- **Broadcast Multi-Access**: (e.g., Ethernet) DR/BDR election required.
- **Point-to-Multipoint**: Treats each connection as point-to-point.
- **NBMA (Non-Broadcast Multi-Access)**: (e.g., Frame Relay) Manual neighbor configuration needed.
## Pros of OSPF
- Supports IPv4 and IPv6.
- Load balancing across equal-cost paths.
- Supports VLSM and route summarization.
- Triggered updates -> fast convergence.
- Loop-free topology ensured by SPF algorithm.
- Classless (supports CIDR).
## Cons of OSPF
- High CPU/RAM usage due to SPF calculations.
- Complex configuration compared to RIP.
- Requires consistent area design.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/open-shortest-path-first-ospf-protocol-fundamentals/)

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
