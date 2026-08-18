---
title: "Types of Spanning Tree Protocol (STP)"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/types-of-spanning-tree-protocol-stp/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Types of Spanning Tree Protocol (STP)
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/types-of-spanning-tree-protocol-stp/)

---

# Types of Spanning Tree Protocol (STP)

In Ethernet networks, switches use frames to forward data between devices. However, if there are multiple active paths between switches (such as when switches are interconnected), a loop can occur, causing frames to circulate indefinitely. This loop results in broadcast storms, high CPU utilization, and network congestion, severely affecting performance. **Spanning Tree Protocol (STP)** is a network protocol used to prevent loops in such Ethernet networks.
It uses a tree-like structure where switches elect one root switch and then calculate the shortest path to this root. The network topology is adjusted to create a loop-free path structure while the redundant paths are put in a standby state.
## **Types of Spanning Tree Protocol (STP)**
Several variations of [STP](https://www.geeksforgeeks.org/chemistry/stp-formula/) are used to address different network requirements, each with specific enhancements and optimizations over the original standard. The most common types of STP include:
| **Protocol** | **IEEE Standard** | **Key Difference** | **Used In / Vendor** |
| --- | --- | --- | --- |
| **Spanning Tree Protocol (STP)** | IEEE 802.1D | Single spanning tree for entire network; slow convergence. | STP |
| **Rapid Spanning Tree Protocol (RSTP)** | IEEE 802.1w | Faster convergence than STP; still one spanning tree. | RSTP |
| **Multiple Spanning Tree Protocol (MSTP)** | IEEE 802.1s | Supports multiple spanning trees by grouping VLANs; load balancing. | MSTP |
| **Per VLAN Spanning Tree Plus (PVST+)** | Cisco (based on 802.1D) | Maintains separate STP instance per VLAN; better path optimization but slower convergence. | PVST+ |
| **Rapid Per VLAN Spanning Tree Plus (RPVST+)** | Cisco (based on 802.1w) | Rapid convergence with separate RSTP instances per VLAN. | RPVST+ |
### **IEEE 802.1D**
This is also known as CST (Common Spanning Tree). It is a spanning tree standard developed by IEEE which elects only one [root bridge](https://www.geeksforgeeks.org/computer-networks/root-bridge-election-in-spanning-tree-protocol/) per whole topology. All the traffic flows over the same path (the best path to the root bridge) but this doesn't hold good always as there can be scenarios in which the optimised path to reach a [VLAN](https://www.geeksforgeeks.org/computer-networks/virtual-lan-vlan/) is different than the path obtained on electing the root bridge. CST prevents loops by blocking redundant paths and allowing only one active path between any two switches. However, it is slow to react to changes, taking up to 32 seconds to converge.
**Advantages:** 
- Less [CPU](https://www.geeksforgeeks.org/computer-science-fundamentals/central-processing-unit-cpu/) and memory required.
- Simple and widely supported across different network devices for easy implementation.
**Disadvantages:**
- Lesser optimization as the path calculated as the best cost to root bridge might not be the best path to reach a network.
- No load balancing.
### **Rapid Spanning Tree Protocol (RSTP)**
It is a spanning standard developed on [IEEE 802.1w](https://www.geeksforgeeks.org/computer-networks/difference-between-spanning-tree-protocol-stp-and-rapid-spanning-tree-protocol-rstp/) which provides faster convergence than CST but holds the same idea of finding a single root bridge in the topology. RSTP prevents loops by quickly detecting link failures and using rapid state transitions on ports to block redundant paths, allowing only loop-free active paths. The bridge resources needed in RSTP is higher than CST but less than PVST+ . 
**Advantages:**
- Prevents network loops.
- Prevents redundancy.
- Faster Convergence.
- Backward compatible with STP.
**Disadvantages:**
- It requires more CPU and memory than Classic STP.
- It can be complex to configure in large networks.
- It does not support per-VLAN load balancing since it uses a single spanning tree for all VLANs
### **Multiple STP (MSTP)**
This standard is developed by IEEE in which grouping of VLANs is done and for each single group, RSTP is run. This is basically a Spanning Tree Protocol running over another Spanning Tree Protocol. It prevents loops by creating multiple spanning tree instances that block redundant paths within each VLAN group, ensuring loop-free and efficient forwarding across the network.
**Advantages:**
- High redundancy
- load balancing can be achieved.
- lower CPU and memory usage is required
**Disadvantages:**
- More configuration is required and not easy to implement.
- Complex troubleshooting due to multiple spanning tree instances running simultaneously.
### **Per VLAN Spanning Tree + (PVST+)**
It is a spanning tree standard developed by Cisco for its devices which finds the root bridge per VLAN. It is a Cisco default version of STP. It finds separate 802.1d spanning tree instance for each VLAN. It also provides backward compatibility with 802.1d or CST. It prevents loops by blocking redundant paths within each VLAN’s spanning tree instance, allowing only one active path per VLAN. This approach optimizes path selection for each [VLAN](https://www.geeksforgeeks.org/computer-networks/virtual-lan-vlan/) but converges as slowly as CST.
**Advantages:** 
- PVST+ provides more optimization on the performance of a network than CST as it selects root bridges per VLAN.
- Bandwidth consumption is lesser than CST.
- Optimum load balancing is achieved.
**Disadvantages:**
- This is slow as CST i.e. convergence time is slow. By default, Cisco switches take 50 seconds for converging.
- More resources (CPU and memory) is required.
### **Rapid Per VLAN Spanning Tree + (RPVST+)**
This Spanning Tree standard is developed by Cisco which provides faster convergence than PVST+ and finds separate instance of 802.1w per VLAN. It prevents loops by quickly blocking redundant paths within each VLAN’s spanning tree instance, allowing only one active loop-free path per VLAN. However, it requires more CPU and memory resources than other STP standards.
**Advantages:**
1. RPVST+ provides quicker recovery from network changes compared to older protocols like PVST+, reducing downtime.
2. It runs a separate spanning tree instance for each VLAN, allowing more efficient and flexible load balancing across the network.
**Disadvantages:**
1. It requires more CPU power and memory because it maintains a separate spanning tree for each VLAN.
2. Managing multiple spanning trees for many VLANs can be complex and harder to troubleshoot.
3. Limited compatibility with non-Cisco devices, which may cause interoperability issues in mixed vendor networks.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/types-of-spanning-tree-protocol-stp/)

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
