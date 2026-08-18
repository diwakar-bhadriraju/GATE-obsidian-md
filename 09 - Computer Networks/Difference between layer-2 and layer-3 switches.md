---
title: "Difference between layer-2 and layer-3 switches"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/difference-between-layer-2-and-layer-3-switches/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Difference between layer-2 and layer-3 switches
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/difference-between-layer-2-and-layer-3-switches/)

---

# Difference between layer-2 and layer-3 switches

A **switch** is a device that sends a data packet to a local network. What is the advantage of a hub? A hub floods the network with the packet and only the destination system receives that packet while others just drop due to which the traffic increases a lot. To solve this problem switch came into the picture. A switch first learns, by flooding the network just like a hub to fill the MAC- address table, on which port a particular device is connected. After learning it sends packets to that particular host only. 
## What is a Layer-2 Switch?
A Layer-2 switch works at the Data Link layer or Layer 2 of the OSI reference model. It especially utilizes MAC addresses to direct information packets between devices that are on the exact same network.
- **MAC Address Table:** A Layer-2 switch will keep a MAC address table that identifies the MAC address of the connected device and the port number. This enables the switch to direct frames towards the correct destination.
- **VLAN Support:** Layer-2 switches can support VLANs (Virtual Local Area Networks), which means that the network can be segmented at this layer.
- **Switching Frames:** These forward [Ethernet](https://www.geeksforgeeks.org/computer-networks/what-is-ethernet/) frames are according to MAC addresses and are vital in minimizing collision within LANs.
- **Broadcast Domains:** Layer-2 switches do not partition broadcast domains, all the devices connected to a Layer-2 switch are in the same broadcast domain.
![](assets/SWITCH-9964d8bd68.png)
## What is a Layer-3 Switch?
A Layer-3 switch works at the third layer of the OSI mode and it has features of both a switch and a [router](https://www.geeksforgeeks.org/computer-networks/introduction-of-a-router/). It employs IP addresses in the forwarding of packets and routing among one or different networks/subnets. Layer-3 switches are characterized by:
- **Routing Capabilities:** Layer – 3 switches are different from Layer – 2 switches in that Layer – 3 switches are capable of routing by inspecting the IP headers of the packets and computing the best path for the data.
- **Inter-VLAN Routing:** Layer-3 switches can also forward traffic between VLANs, but this is often needed only in larger networks where [segmentation](https://www.geeksforgeeks.org/operating-systems/segmentation-in-operating-system/) has to be performed.
- **Reduced Latency:** Due to FULL layer routing implementation, this means that Layer-3 switches can avoid having to use a different router hence improving on the existing less latency in the networks.
- **Advanced Features:** Layer-3 switches are usually equipped with features such as ACL and QoS among others in the process of managing the switches.
![](assets/HUB-c540909115.png)![](assets/Untitled-drawing-4-1-8ba62ede92.png)
Layer 2 switch work on layer 2 of [OSI model](https://www.geeksforgeeks.org/computer-networks/open-systems-interconnection-model-osi/) i.e. data link layer and sends a "Frames" to destination port using MAC address table which stores the mac address of a device associated with that port. Layer 3 switch work on layer 3 of OSI model i.e. network layer where it route packet by using [IP address](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/), it is used widely on VLANs.
## Difference Between Layer-2 and Layer-3 Switches
**Layer 2 switches** operate at the data link layer, forwarding data based on MAC addresses, while **layer 3 switches** route traffic using IP addresses. Understanding the differences between these two layers is crucial for network design and performance optimization.
| Layer 2 Switch | Layer 3 Switch |
| --- | --- |
| Operate on layer 2 (Data link) of OSI model. | Operate on layer 3 (Network Layer) of OSI model. |
| Send "frames" to destination on the basis of MAC address. | Route Packet with help of IP address |
| Work with [MAC address](https://www.geeksforgeeks.org/computer-networks/mac-address-in-computer-network/) only | Can perform functioning of both 2 layer and 3 layer switch |
| Used to reduce traffic on local network. | Mostly Used to implement VLAN (Virtual Local area network) |
| Quite fast as they do not look at the Layer 3 portion of the data packets. | Takes time to examine data packets before sending them to their destination |
| It has single broadcast domain | It has multiple broadcast domain. |
| Can communicate within a network only. | Can communicate within or outside network. |
## Conclusion
Thus, Layer-2 and Layer-3 [switches](https://www.geeksforgeeks.org/computer-networks/types-of-switches-in-computer-network/) can be defined in terms of their functional layers and activities. In simple [LAN](https://www.geeksforgeeks.org/computer-networks/lan-full-form/) network which involves a basic level of network [segmentation](https://www.geeksforgeeks.org/operating-systems/segmentation-in-operating-system/), Layer-2 switches are preferred while for more complex network especially those involving routing and inter [VLAN](https://www.geeksforgeeks.org/computer-networks/virtual-lan-vlan/), Layer-3 switches are preferred. A switch is therefore dictated by the requirement and the size of the network you intend to connect.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/difference-between-layer-2-and-layer-3-switches/)

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
