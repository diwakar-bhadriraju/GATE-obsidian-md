---
title: "Introduction To Subnetting"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/introduction-to-subnetting/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Introduction To Subnetting
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/introduction-to-subnetting/)

---

# Introduction To Subnetting

Subnetting is the process of dividing a large IP network into smaller logical networks called subnets. Each subnet allows devices to communicate efficiently, improving network performance, security, and manageability.
- Each department is assigned a separate subnet
- Devices within a department communicate using their own subnet
- Inter-department traffic is routed through a router
- Broadcast traffic is limited to each subnet
- Network performance, security, and management are improved
## Need for Subnetting
Subnetting enables a single IP network to be divided into smaller, logical networks, allowing for efficient IP address usage, improved performance, and enhanced security control. Let's consider a company that follows classful addressing. It has a Class C network (192.168.1.0/24) with 256 IP addresses. It has three departments:
![192_168_1_0_24](assets/192_168_1_0_24-215ede37cf.webp)
Subnetting
### Without subnetting:
- All departments share the same network
- Only 80 IP addresses are used, leaving 176 unused
- Broadcast traffic floods the entire network
- Devices from different departments can access each other freely
### With subnetting:
- The network is divided into three smaller subnets
- Each department receives only the IPs it needs
- Traffic remains within each subnet, improving performance
- Departments are logically isolated, improving security
- IP addresses are used efficiently, with room for future growth
| Department | Devices | IPs Allocated (after subnetting) |
| --- | --- | --- |
| Sales | 20 | 32 (192.168.1.0/27) |
| HR | 10 | 16 (192.168.1.32/28) |
| IT | 50 | 64 (192.168.1.64/26) |
### By subnetting, we:
- Use IP addresses efficiently, allocating only what each department requires
- Improve network performance by containing traffic within each subnet
- Enhance security by isolating departments from one another
## Key Concept
**IP Addressing:** An [IP address](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/) uniquely identifies a device on a network and is divided into logical parts to support routing and communication. An IPv4 address is a 32-bit value written as four octets separated by dots (for example, 192.168.1.1).
- **Network portion:** Identifies the network to which the device belongs
- **Host portion:** Identifies the specific device within that network
In classful IPv4 addressing, IP addresses are divided into classes based on how many bits are used for the network ID and host ID.
- **Class A:** 8-bit network ID, 24-bit host ID
- **Class B:** 16-bit network ID, 16-bit host ID
- **Class C:** 24-bit network ID, 8-bit host ID
![network_id_and_host_id](assets/network_id_and_host_id-01e6b281f1.webp)
Classful Addressing
### Subnet Mask
A [**subnet mask**](https://www.geeksforgeeks.org/computer-networks/role-of-subnet-mask/) is a 32-bit number used in IP addressing to separate the network portion of an [IP address](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/) from the host portion.
- It helps computers and devices determine which part of an IP address refers to the network they are present,
- And which part refers to their specific location or address within that network.
![subnet_mask](assets/subnet_mask-94d2d4b6d4.webp)
Subnet mask
### **CIDR Notation: A Simplified Approach to Subnetting**
Instead of using a long subnet mask (e.g., 255.255.255.0), CIDR uses a simple format like /24. The number after the slash (/n) represents the number of bits used for the network portion of the IP address.
## Working
The working of subnets starts in such a way that firstly it divides the subnets into smaller subnets. For communicating between subnets, routers are used. Each subnet allows its linked devices to communicate with each other. Subnetting for a network should be done in such a way that it does not affect the network bits.
In class C the first 3 octets are network bits so it remains as it is. 
- **For Subnet-1:**  The first bit which is chosen from the host id part is zero and the range will be from (193.1.2.00000000 till you get all 1's in the host ID part i.e, 193.1.2.01111111) except for the first bit which is chosen zero for subnet id part.
Thus, the range of subnet 1 is: 193.1.2.0 to 193.1.2.127 
> Subnet id of Subnet 1 is: 193.1.2.0
> The direct Broadcast id of Subnet-1 is: 193.1.2.127
> The total number of hosts possible is: 126 (Out of 128, 2 id's are used for Subnet id & Direct Broadcast id)
> The subnet mask of Subnet- 1 is: 255.255.255.128
- **For Subnet-2:** The first bit chosen from the host id part is one and the range will be from (193.1.2.100000000 till you get all 1's in the host ID part i.e, 193.1.2.11111111).
Thus, the range of subnet-2 is: 193.1.2.128 to 193.1.2.255 
> Subnet id of Subnet 2 is : 193.1.2.128
> The direct Broadcast id of Subnet-2 is: 193.1.2.255
> The total number of hosts possible is: 126 (Out of 128, 2 id's are used for Subnet id & Direct Broadcast id)
> The subnet mask of Subnet- 2 is: 255.255.255.128
> The best way to find out the subnet mask of a subnet is to set the fixed bit of host-id to 1 and the rest to 0.
- A /24 network has 254 usable hosts (2 addresses reserved).
- After dividing into two /25 subnets, each subnet reserves 2 addresses.
- So total usable hosts become 252 instead of 254 due to extra reserved addresses.
**Note:**
1. To divide a network into four (2 2 ) parts you need to choose two bits from the host id part for each subnet i.e, (00, 01, 10, 11).
2. To divide a network into eight (2 3 ) parts you need to choose three bits from the host id part for each subnet i.e, (000, 001, 010, 011, 100, 101, 110, 111) and so on.
3. We can say that if the total number of subnets in a network increases the total number of usable hosts decreases.
The network can be divided into two parts: To divide a network into two parts, you need to choose one bit for each Subnet from the host ID part.
![nid_193_1_2_0](assets/nid_193_1_2_0-8229517c42.webp)
Subnet
In the above diagram, there are two Subnets. 
Note: It is a class C IP so, there are 24 bits in the network id part and 8 bits in the host id part.
## Advantages
- **Improved Security:** Subnets isolate departments, preventing unauthorized access (e.g., HR data hidden from Sales).
- **Traffic Prioritization:** Critical subnets (e.g., Sales hosting video conferences) can get higher priority.
- **Easier Maintenance:** Smaller, segmented networks are simpler to manage.
## Disadvantages
- **Extra Overhead:** Each subnet wastes 2 IP addresses (network ID and broadcast address).
- **Higher Cost:** Subnetting often requires additional devices like routers and switches, increasing expenses.
- **More Complexity:** Compared to a single flat network, subnetting adds extra steps in communication and requires careful planning.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/introduction-to-subnetting/)

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
