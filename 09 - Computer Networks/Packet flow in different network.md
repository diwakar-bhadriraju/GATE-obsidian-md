---
title: "Packet flow in different Network"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/packet-flow-in-different-network/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Packet flow in different Network
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/packet-flow-in-different-network/)

---

# Packet flow in different Network

Prerequisite - [How ARP works](https://www.geeksforgeeks.org/ethical-hacking/how-address-resolution-protocol-arp-works/), [Packet flow in the same network](https://www.geeksforgeeks.org/computer-networks/packet-flow-in-the-same-network/) 
To deliver the packet to the destination host, the source IP, destination IP, source MAC address and destination MAC address should be known. Some basic rules for the packet flow: 
1. If the destination host is present in the same network, then the packet is delivered directly to the destination host.
2. If the destination host is present in a different network then the packet is delivered to the default gateway first which in turn delivers the packet to the destination host.
3. If ARP is not resolved then ARP will be resolved first.
4. MAC address never crosses its broadcast domain.
**Explanation -** 
![](assets/Packet_flow_1-b0e0931300.jpg)
Here is a topology, in which there is host A (IP address - 10.0.0.10 and MAC address - 000D.BD22.7C22), host C (IP address - 10.0.0.9), host B (IP address - 20.0.0.10), host C (IP address-20.0.0.9 and MAC address - 00E0.A3E2.03DC) and the router (IP address - 10.0.0.20 and MAC address - 000B.BE8E.5201 on fa0/0,IP address - 20.0.0.20 and MAC address - 000B.BE8E.5202 on fa0/1 ). 
Now we will try to ping from host A (IP address - 10.0.0.10) to host B (IP address - 20.0.0.10). First, **AND operation** is performed by source host between source IP address, source subnet mask, and destination IP address, source subnet mask to know if the destination is present in same or different network. 
If the result is the same then the destination is in the same network otherwise in a different network. Here, the destination is present in different networks, therefore, the result will be different and the packet will be delivered to a default gateway. 
![](assets/Packet_flow_2-d445ad7658.jpg)
We see that 2 messages are generated ICMP(purple) and ARP(green). ARP has been generated because ARP has not been resolved. 
![](assets/Packet_flow_3-e34d2e6abb.jpg)
Now as the ARP should be resolved first, therefore the ARP request will be broadcast which is received by switch: 
![](assets/Packet_flow_4-12206582e4.jpg)
The switch in turn broadcast the ARP request to the host and the router. The PC discards the request and the router accepts it. 
![](assets/Packet_flow_5-d4bfe90614.jpg)![](assets/Packet_flow_6-303f3b14e6.jpg)
Now the ARP reply is unicast to host A by the router as shown in the above figure. 
![](assets/Packet_flow_7-e40c5ff282.jpg)![](assets/Packet_flow_8-2494810b86.jpg)
Now the ICMP packet will be unicast to the default gateway (IP address - 10.0.0.20 and MAC address - 000B.BE8E.5201) as shown in the above figures. 
**Note -** The ICMP packet will be unicast to the default gateway as the ARP has been resolved now. 
![](assets/Packet_flow_9-1-fd92cb7198.jpg)![](assets/Packet_flow_10-1-e3c812e5a9.jpg)
Now the ARP has to be resolved again because the router has to deliver the packet to host B and the ARP table has no entry for host B. Therefore, the ARP request is broadcast in the network 20.0.0.0/24. The packet is received by the Switch which in turn broadcast the request to host B and D. Host D will reject the request and host B will accept it and generate an ARP reply for the MAC address 000B.BE8E.5202 (router fa0/1 MAC address) because the ARP reply has to be given to that MAC address from which the ARP request has been received. 
![](assets/packetd12-1d5acc4b5a.png)
As you can see in the figure, the ARP reply packet is unicast to the router's interface fa0/1 MAC address(000B.BE8E.5202) and the source MAC is 00E0.A3E2.03DC. 
**Note -** Here, the target MAC address is the MAC address of host B (000B.BE8E.5202). Target MAC address is the MAC address of a device that the host wants to know through its ARP request to resolve ARP. 
![](assets/packetd15-64c9bbff92.png)![](assets/packetd16-4e767204df.png)![](assets/packetd17-a03f616c55.png)
Now the ICMP echo-request packet will be unicast to the host B as shown in the above 3 figures. 
![](assets/packetd16-4e767204df.png)![](assets/packetd15-64c9bbff92.png)![](assets/packetd18-7f4b98d006.png)![](assets/packetd19-67c7a71fcb.png)
Host B will generate an ICMP echo reply in response to the ICMP echo request for host A which will be delivered to the 20.0.0.20 (router's interface IP address) first and then unicast to host A. 
**How does** **the MAC address never crosses its broadcast domain?** 
![](assets/ppp-a462711edc.png)
This is the IP and Ethernet header when host A forwards the ICMP echo request to its default gateway. Therefore source IP is 10.0.0.10 and destination IP is 10.0.0.20, source MAC address is 000D.BD22.7C22 (host A MAC address) and destination MAC address is 000B.BE8E.5201 (router's fa0/0 interface MAC address). 
![](assets/pp-3-a20d7262a6.png)
But now when the ICMP echo request message is forwarded from the router's fa0/1 interface to host B then the source MAC address is changed to 000B.BE8E.5202 (router's fa0/1 interface MAC address) and destination MAC address is 00E0.A3E2.03DC (host B MAC address). 
Here router's fa0/0 interface MAC address is not used as the source MAC address, instead the fa0/1 MAC address is used as a MAC address. Therefore, fa0/0 is not used in other broadcast domains (20.0.0.0/24 network) therefore MAC address never crosses its broadcast domain. IN this way, PING is performed in 2 different networks.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/packet-flow-in-different-network/)

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
