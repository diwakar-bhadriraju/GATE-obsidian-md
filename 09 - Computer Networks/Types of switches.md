---
title: "Types of Switches in Computer Network"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/types-of-switches-in-computer-network/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Types of Switches in Computer Network
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/types-of-switches-in-computer-network/)

---

# Types of Switches in Computer Network

In computer networks, switches are critical devices that manage the flow of data between devices in a local area network (LAN). Acting as central connection points, switches help efficiently transmit data packets from one device to another, enabling smooth communication and resource sharing.
> **Note:** Unlike hubs, switches are intelligent and operate primarily at the Data Link Layer (Layer 2) of the OSI model, although some advanced switches operate at the Network Layer (Layer 3).
## What is a Network Switch?
A network switch is a hardware device that connects multiple devices (computers, printers, servers, etc.) in a LAN and uses MAC addresses to forward data frames to the appropriate destination. It operates by inspecting incoming frames and deciding where to forward them, thus reducing unnecessary network traffic.
![Network-Switch-01-copy-660](assets/Network-Switch-01-copy-660-d6862d2f1a.webp)
Network Switch
### Basic Functions of a Switch:
- **Frame Switching:** Forwarding data based on MAC addresses.
- **MAC Address Learning:** Automatically building a MAC address table to map devices to switch ports.
- **Loop Prevention:** Using protocols like Spanning Tree Protocol (STP) to avoid network loops.
- **Full-Duplex Communication:** Allowing simultaneous data transmission and reception.
## Types of Switches
### 1. Unmanaged Switches
**Description:** Unmanaged switches are plug-and-play devices with no configuration options. They are typically used in small networks or home environments.
**Key Features:**
- Simple to use with no management interface.
- Limited or no security features.
- Fixed configuration with no VLAN support.
- Operates only in Layer 2 (Data Link Layer).
> **Use Case:** Ideal for small office/home office (SOHO) networks where advanced features are not required.
### 2. Managed Switches
**Description:** Managed switches provide advanced features for network configuration, management and monitoring.
**Key Features:**
- Supports VLANs (Virtual Local Area Networks).
- Allows Quality of Service (QoS) settings.
- Provides SNMP (Simple Network Management Protocol) for remote monitoring.
- Enables configuration of port speed, duplex mode and security settings.
- Can operate at Layer 2 and Layer 3 (routing).
> **Use Case:** Used in enterprise networks where network control, performance optimization and security are critical.
### 3. Smart Switches (Web-Managed Switches)
**Description:** Smart switches are a middle ground between unmanaged and managed switches. They provide some management features through a web interface, making them easier to configure than fully managed switches.
**Key Features:**
- Basic VLAN and QoS support.
- Limited SNMP support.
- Web-based GUI for configuration.
- Less expensive than fully managed switches.
> **Use Case:** Suitable for small to medium-sized business networks that require some level of network management.
### 4. Layer 2 Switches
**Description:** Layer 2 switches work at the Data Link Layer (Layer 2) of the OSI model and use MAC addresses to forward data frames.
**Key Features:**
- MAC address learning and forwarding.
- Supports VLAN segmentation.
- No routing capability.
> **Use Case:** Ideal for basic network segmentation in LANs.
### 5. Layer 3 Switches (Multilayer Switches)
**Description:** Layer 3 switches combine the functionality of a switch and a router. They operate at both the Data Link Layer and the Network Layer (Layer 3), enabling routing between VLANs.
**Key Features:**
- Performs IP routing between VLANs.
- Supports advanced routing protocols like OSPF and RIP.
- Offers high performance for inter-VLAN traffic.
> **Use Case:** Used in large enterprise networks where routing between multiple VLANs is necessary for efficiency.
### 6. PoE Switches (Power over Ethernet)
**Description:** PoE switches provide electrical power to network devices (such as IP cameras, VoIP phones and wireless access points) over Ethernet cables along with data.
**Key Features:**
- Simplifies deployment of devices without needing separate power supplies.
- PoE standards include IEEE 802.3af (PoE), IEEE 802.3at (PoE+) and IEEE 802.3bt (PoE++).
> **Use Case:** Ideal for deploying devices in locations where power outlets are scarce.
## Uses of Network Switch
- **Connect Multiple Devices**: Allows multiple devices (computers, printers, servers) to connect within a Local Area Network (LAN).
- **Efficient Data Transmission**: Forwards data frames only to the intended recipient device using MAC addresses, reducing network traffic.
- **Network Segmentation (VLANs)**: Supports Virtual Local Area Networks (VLANs) to logically segment the network for improved security and performance.
- **Improved Bandwidth Utilization**: Provides full-duplex communication, enabling simultaneous sending and receiving of data on a port.
- **Power over Ethernet (PoE)**: Supplies power to network devices (e.g., IP phones, wireless access points) over Ethernet cables, reducing cabling complexity.
- **Reduces Collisions**: Unlike hubs, switches create separate collision domains per port, minimizing network collisions.
![Types-of-Switches-in-Computer-Network-(1)](assets/Types-of-Switches-in-Computer-Network--1-e66759baa0.webp)
Uses of Network Switch
- **Network Management and Monitoring**: Managed switches allow monitoring of network traffic, configuring QoS, security settings and remote management.
- **Inter-VLAN Routing (Layer 3 Switches)**: Enables communication between VLANs without needing separate routers, improving speed and efficiency.
- **Enhanced Security**: Supports features like port security, access control lists (ACLs) and VLAN isolation to restrict unauthorized access.
- **Scalable Network Expansion**: Easy to expand the network by adding additional switches to increase the number of connected devices.
- **High-Speed Performance**: Operates at high data rates (1 Gbps, 10 Gbps, etc.), making it suitable for bandwidth-intensive applications.
- **Loop Prevention and Redundancy**: Uses Spanning Tree Protocol (STP) to prevent network loops and provide fault tolerance.
## Difference between Switch, Hub and Repeater
| Feature | Switch | Hub | Router |
| --- | --- | --- | --- |
| Layer | Layer 2 (Layer 3 for Layer 3 Switch) | Physical Layer (Layer 1) | Network Layer (Layer 3) |
| Traffic Handling | Intelligent frame forwarding using MAC addresses | Broadcasts frames to all devices | Routes packets using IP addresses |
| Efficiency | High efficiency, reduces collisions | Low efficiency, high collisions | Efficient routing across networks |
| VLAN Support | Yes (Managed Switch) | No | N/A |
| PoE Support | Yes (PoE Switches) | No | Some specialized routers |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/types-of-switches-in-computer-network/)

## GATE CS

- Subject: Computer Networks
- Topic: Data Link Layer

> [!note] Related notes
>
> - [[Aloha]]
> - [[Back-off Algorithm for CSMA CD]]
> - [[Bit Stuffing]]
> - [[Carrier sense multiple access]]
> - [[Collision Avoidance in wireless networks]]
> - [[Collision Detection in CSMA CD]]
> - [[Computer Networks Error Detection]]
> - [[Controlled Access Protocols]]
> - [[Difference between Byte stuffing and Bit stuffing]]
> - [[Efficiency of CSMA CD]]
