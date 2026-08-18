---
title: "Difference between Unicast, Broadcast and Multicast in Computer Network"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/difference-between-unicast-broadcast-and-multicast-in-computer-network/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Difference between Unicast, Broadcast and Multicast in Computer Network
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/difference-between-unicast-broadcast-and-multicast-in-computer-network/)

---

# Difference between Unicast, Broadcast and Multicast in Computer Network

The **cast** term here signifies some data(stream of packets) is being transmitted to the recipient(s) from the client(s) side over the communication channel that helps them to communicate. Let's see some of the "cast" concepts that are prevailing in the computer networks field. 
## What is Unicast?
This type of information transfer is useful when there is a participation of a single sender and a single recipient. So, in short, you can term it a one-to-one transmission. For example, if a device having IP address 10.1.2.0 in a network wants to send the traffic stream(data packets) to the device with IP address 20.12.4.2 in the other network, then unicast comes into the picture. This is the most common form of data transfer over networks. 
![Unicast](assets/UNICAST-1-f1583e8e47.png)
## What is Broadcast?
Broadcasting transfer (one-to-all) techniques can be classified into two types:
**Limited Broadcasting:** Suppose you have to send a stream of packets to all the devices over the network that your reside, this broadcasting comes in handy. For this to achieve, it will append 255.255.255.255 (all the 32 bits of IP address set to 1) called [**Limited Broadcast Address**](https://www.geeksforgeeks.org/computer-networks/what-is-limited-broadcast-address/) in the destination address of the datagram (packet) header which is reserved for information transfer to all the recipients from a single client (sender) over the network. 
![Broadcast](assets/NETWORK-CLUSTER-ce932ce325.png)
**Direct Broadcasting:** This is useful when a device in one network wants to transfer packet stream to all the devices over the other network. This is achieved by translating all the Host ID part bits of the destination address to 1, referred to as [**Direct Broadcast Address**](https://www.geeksforgeeks.org/computer-networks/types-of-broadcast-network/) in the datagram header for information transfer.
![Direct Broadcast](assets/DIRECT_BROADAST-40bdb45375.png)
This mode is mainly utilized by television networks for video and audio distribution. One important protocol of this class in Computer Networks is [Address Resolution Protocol (ARP)](https://www.geeksforgeeks.org/ethical-hacking/how-address-resolution-protocol-arp-works/) which is used for resolving an IP address into a physical address which is necessary for underlying communication. 
## What is Multicast?
In [multicasting](https://www.geeksforgeeks.org/computer-networks/multicasting-in-computer-network/), one/more senders and one/more recipients participate in data transfer traffic. In this method traffic recline between the boundaries of unicast (one-to-one) and broadcast (one-to-all). Multicast lets servers direct single copies of data streams that are then simulated and routed to hosts that request it. IP multicast requires the support of some other protocols like [**IGMP**](https://www.geeksforgeeks.org/computer-networks/what-is-igmpinternet-group-management-protocol/) **(Internet Group Management Protocol), Multicast routing** for its work. Also in Classful IP addressing **Class D** is reserved for multicast groups. 
**Questions Corner**
Practicing the following questions will help you test your knowledge. It is highly recommended that you practice them. 
1. [Direct Broadcast Address](https://www.geeksforgeeks.org/questions/if-direct-broadcast-address-of-subnet-is-201151631-which/)
2. [Direct Broadcast Address](https://www.geeksforgeeks.org/questions/if-direct-broadcast-address-is-201151631-which-of-the/)
3. [Direct Broadcast Address](https://www.geeksforgeeks.org/questions/if-subnet-mask-255255255224-which-of-the-following-will/)
| Feature | Unicast | Broadcast | Multicast |
| --- | --- | --- | --- |
| Definition | A communication where a message is sent from one sender to one receiver. | A communication where a message is sent from one sender to all receivers. | A communication where a message is sent from one sender to a group of receivers |
| Transmission | Data is sent to a single recipient | Data is sent to all recipients in a network | Data is sent to a group of recipients |
| Addressing | Uses a unique destination address | Uses a special broadcast address | Uses a special multicast address |
| Delivery | Guaranteed delivery | Not all devices may be interested in the data | Not all devices may be interested in the data |
| Network Traffic | Generates the least amount of network traffic | Generates the most amount of network traffic | Generates moderate network traffic |
| Security | More secure because data is sent to a specific recipient | Less secure because data is sent to all devices in the network | Moderately secure because data is sent to a specific group of devices |
| Examples | Email, file transfer | DHCP requests, ARP requests | Video streaming, online gaming |
| Destination | Single receiver | All receivers | Group of receivers |
| Bandwidth usage | Moderate | High | Moderate |
| Latency | Low | High | Moderate |
## Conclusion
The three principal “cast” methods- Unicast, Broadcast, and Multicast are defining in the field of [computer networks](https://www.geeksforgeeks.org/computer-networks/basics-computer-networking/). These all are useful for different factors and can be used for one-to-one, one-to-many or many-to-many transmissions. Knowing such types of [protocols](https://www.geeksforgeeks.org/computer-networks/types-of-network-protocols-and-their-uses/), the network administrators and developers can manage the load of networks and efficiently secure the data in the right manner. Whether it is to send an email (Unicast), to request for [DHCP](https://www.geeksforgeeks.org/computer-networks/dynamic-host-configuration-protocol-dhcp/) (Broadcast) or be sending a video stream to several users (Multicast), these methods are very important in the current society’s networks.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/difference-between-unicast-broadcast-and-multicast-in-computer-network/)

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
