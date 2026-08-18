---
title: "Types of Network Address Translation (NAT)"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/types-of-network-address-translation-nat/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Types of Network Address Translation (NAT)
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/types-of-network-address-translation-nat/)

---

# Types of Network Address Translation (NAT)

Prerequisite - [Network address translation (NAT)](https://www.geeksforgeeks.org/computer-networks/network-address-translation-nat/) 
Network Address Translation (NAT) is a process in which one or more local IP address is translated into one or more Global IP address and vice versa in order to provide Internet access to the local hosts. NAT generally operates on a router or firewall. 
**Network address translation (NAT) working -**
Generally, the border router is configured for NAT i.e the router which has one interface in the local (inside) network and one interface in the global (outside) network. When a packet traverse outside the local (inside) network, then NAT converts that local (private) IP address to a global (public) IP address. When a packet enters the local network, the global (public) IP address is converted to a local (private) IP address. 
If NAT runs out of addresses, i.e., no address is left in the pool configured then the packets will be dropped and an Internet Control Message Protocol (ICMP) host unreachable packet to the destination is sent. 
**NAT types -** 
There are 3 types of NAT: 
**1. Static NAT -** 
In this, a single private IP address is mapped with a single Public IP address, i.e., a private IP address is translated to a public IP address. It is used in Web hosting. 
**Configuration -** 
![](assets/staticRFWE-679c84a8d1.png)
Here is a small topology in which there is PC having IP address 192.168.1.1/24, Router R1 having IP address 192.168.1.2/24 on interface fa0/0, 12.1.1.1/24 on fa0/1, and server having IP address 73.1.1.2/24. 
Now, inside local and inside global are shown in the figure. Configuring the static NAT through command IP nat inside source static INSIDE\_LOCAL\_IP\_ADDRESS INSIDE\_GLOBAL\_IP\_ADDRESS. 
```
R1(config)# ip nat inside source static 192.168.1.1 12.1.1.1
```
Now, we have configured the router's inside interface as IP NAT inside and outside interface as IP NAT outside. 
```
R1(config)# int fa0/0
R1(config-if)# ip nat inside
R1(config)# int fa0/1
R1(config-if)# ip nat outside
```
**2. Dynamic NAT -** 
In this type of NAT, multiple private IP addresses are mapped to a pool of public IP addresses. It is used when we know the number of fixed users who want to access the Internet at a given point in time. 
**Configuration -** 
![](assets/staticRFWE-679c84a8d1.png)
There is a PC having IP address 192.168.1.1/24, Router R1 having IP address 192.168.1.2/24 on interface fa0/0, 12.1.1.1/24 on fa0/1, and a server having IP address 73.1.1.2/24. 
Now, first configuring the access-list: 
```
R1(config)# access-list 1 permit 192.168.1.0 0.0.0.255
```
Configuring the nat pool from which a public IP will be selected. 
```
R1(config)# ip nat pool pool1 12.1.1.1 12.1.1.3 netmask 255.255.255.0
```
Now, enabling Dynamic NAT: 
```
R1(config)# ip nat inside source list 1 pool pool1
```
At last, we have to configure router interfaces as inside or outside. 
```
R1(config)# int fa0/0
R1(config-if)# ip nat inside
R1(config)# int fa0/1
R1(config-if)# ip nat outside
```
**3. Port Address Translation (PAT) -** 
This is also known as NAT overload. In this, many local (private) IP addresses can be translated to a single public IP address. Port numbers are used to distinguish the traffic, i.e., which traffic belongs to which IP address. This is most frequently used as it is cost-effective as thousands of users can be connected to the Internet by using only one real global (public) IP address. 
**Configuration -** 
![](assets/staticRFWE-679c84a8d1.png)
Taking the same topology, There is PC1 having IP address 192.168.1.1/24, Router R1 has IP address 192.168.1.2/24 on interface fa0/0, 12.1.1.1/24 on fa0/1, and the server has IP address 73.1.1.2/24. 
Now, first configuring the access-list: 
```
R1(config)# access-list 1 permit 192.168.1.0 0.0.0.255
```
Configuring the nat pool from which a public IP will be selected. 
```
R1(config)# ip nat pool pool1 12.1.1.1 12.1.1.1 netmask 255.255.255.0
```
Here, note that the nat pool is shrunk to one IP address only and the IP address used is the outside interface IP address of the router. If you have additional IP then you can use that also. 
Now, enabling Dynamic NAT overload (PAT): 
```
R1(config)# ip nat inside source list 1 pool pool1 overload
```
Or we can also use 
```
R1(config)# ip nat inside source list 1 interface fastEthernet 0/1 overload
```
At last, we have to configure router interfaces as inside or outside. 
```
R1(config)# int fa0/0
R1(config-if)# ip nat inside
R1(config)# int fa0/1
R1(config-if)# ip nat outside
```
**How NAT protect you:-**
-It hides the IP address of any devices on your network from the outside world giving them all a single address.
-It requires every incoming packet of information to have been asked for by a device. if a malicious data packet isn't on the list of expected communications it gets rejected.
-Some firewalls can use whitelisting to block unauthorized outgoing traffic so if you do contract a piece of malware your firewall may prevent it from communicating with your device.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/types-of-network-address-translation-nat/)

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
