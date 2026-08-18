---
title: "Root Bridge Election in Spanning Tree Protocol"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/root-bridge-election-in-spanning-tree-protocol/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Root Bridge Election in Spanning Tree Protocol
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/root-bridge-election-in-spanning-tree-protocol/)

---

# Root Bridge Election in Spanning Tree Protocol

Redundant links are used to provide a backup path when one link goes down but a Redundant link can sometimes cause switching loops. The main purpose of Spanning Tree Protocol (STP) is to ensure that you do not create loops when you have redundant paths in your network. 
**Spanning Tree Protocol (STP) -** 
As IEEE STP is used to make a loop-free network by monitoring the network to track all the links and shut down the redundant ones. These are some important terms related to Spanning Tree Protocol: 
- **Bridge Priority Data Unit (BPDU) -** It contains the Bridge ID, Sender’s Bridge ID, Cost to the Root Bridge, Timer values on Root Bridge. All switches exchange BPDU in order to elect root bridge. The switch with the lowest Bridge ID become the root bridge.
- **Bridge ID -** It is an 8-byte field that is a combination of bridge priority (2 bytes) and Base Mac address (6 bytes) of a device. If there is a tie on bridge priority then the Base Mac address is considered.
- **Bridge Priority -** It is a priority, which is assigned to every switch, 32768 by default.
- **Root Bridge -** The root bridge is the bridge with the lowest Bridge ID. All the decisions like which ports are the root ports (the port with the best path to the root bridge) are made from the perspective of the root bridge.
- **Path cost -** A switch may encounter one or more switches in the path to the root bridge. All the paths are analyzed and the path with the lowest cost will be selected.
| Speed | Link Cost |
| --- | --- |
| 10 Mbps | 100 |
| 100 Mbps | 19 |
| 1 Gbps | 4 |
| 10 Gbps | 2 |
**Designated port -** The port which sends the best BPDU i.e ports on the root bridge will be in a forwarding state. 
**Root port -** The port which receives the best BPDU on a non-root bridge. Criteria for selecting root port: 
1. Lowest path cost to reach the root bridge
2. Lowest sender bridge ID
3. Lowest sender port ID
(Port priority + Port number) - Port priority is by default 128 and port number is the switch interface number. 
**Election procedure -** 
All the switches in the network declare themselves root bridges and start exchanging their own BPDU. The BPDU with the lowest bridge ID is considered as superior. Now the switch receiving the superior BPDU makes changes in its own BPDU and carries forward to its neighbours. It changes the value of root Bridge ID with its superior BPDU bridge ID. This process goes on until all the switches are satisfied with which bridge has the lowest bridge ID and hence that switch will be declared as the root bridge. 
Now according to the criteria, the root ports will be selected and then the port left will be in blocking mode. 
**Example -** 
![](assets/image1-6-7c0c8191e5.png)
Here is a small topology with three switches switch A (mac address-0000.0ACA7.A603), switch B(0030.F222.2794), and switch C(000A.41D5.7937) with all having default priority (32768). 
**Root Bridge election -** 
As all the switches have default priority therefore there is a tie on the basis of priority. Now, the switch with the lowest Mac address will become a root bridge. Here, switch A will become the root bridge as it has the lowest Mac address. Therefore, the ports of switch A will be in forwarding state i.e designated port. 
![](assets/image2-1-a13055d105.png)
**Root Ports Election -** 
The root ports are selected on non-root bridges, i.e. switch B and switch C. Now, for instance, if switch C choose the path through switch B then the cost will be (4+4=8) but if it chooses the directly connected path to switch A then the cost will be 4, therefore, both switch B and switch C will choose the ports connected to switch A as their root ports. 
Now, the only thing left is to find which port will be in forwarding mode and blocking mode respectively. Now as the link between switch B and switch C has the same cost as the root bridge, therefore, the switch with the lowest bridge I'd be in forwarding mode therefore switch C port will be in forwarding mode and switch B port will be in block mode.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/root-bridge-election-in-spanning-tree-protocol/)

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
