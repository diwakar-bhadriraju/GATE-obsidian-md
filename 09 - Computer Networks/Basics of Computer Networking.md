---
title: "Basics of Computer Networking"
subject: "Computer Networks"
topic: "Network Fundamental and Physical Layer"
source: "https://www.geeksforgeeks.org/computer-networks/basics-computer-networking/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Fundamental and Physical Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-fundamental-and-physical-layer
---


> [!abstract] Basics of Computer Networking
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Fundamental and Physical Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/basics-computer-networking/)

---

# Basics of Computer Networking

Computer network is a collection of interconnected devices that communicate with each other to exchange data and resources. It enables efficient communication and supports services like email, file sharing, and internet access.
- Nodes are physical devices such as computers, mobiles, or printers.
- Routers and switches control the flow of information.
- Transmission media carry data from one device to another.
- Wired media includes Ethernet and optical fiber cables.
![network](assets/network-1eceb7d861.webp)
Basic of Computer Networks
## Working
Computer network operates by enabling devices to communicate and exchange data using a shared communication system. Each device in the network follows predefined rules to ensure that data is transmitted accurately, efficiently, and securely.
![frame_25](assets/frame_25-660-3f3bcaf2d4.webp)
Working Structure
- A network consists of nodes such as computers, servers, routers, and switches that send or receive data.
- These nodes are connected through links, which may be wired (cables, optical fiber) or wireless (Wi-Fi, radio signals).
- When data is sent, it is broken into small packets and transmitted across the network.
- Protocols define how data packets are formatted, transmitted, received, and acknowledged.
- Each device is identified by a unique IP address, which ensures data reaches the correct destination.
- Network devices like switches and routers forward data packets along the best available path.
- Security mechanisms, such as firewalls, monitor traffic and allow or block data based on security rules.
## Types of Computer Network Architecture
Computer Network falls under these broad Categories:
- **Client-Server Architecture:** Represents a type of computer network architecture in which nodes function as servers or clients, where the server manages client behavior, known as [Client-Server Architecture](https://www.geeksforgeeks.org/system-design/client-server-model/).
- **Peer-to-Peer Architecture:** Operates without any central server, allowing each device to act as either a client or a server, known as [P2P (Peer-to-Peer) Architecture](https://www.geeksforgeeks.org/computer-networks/what-is-p2p-peer-to-peer-process/).
## Network Devices
These are physical devices that connect computers, printers and other electronic equipment to a network and enable data sharing, transferring and managing.
### 1. Router
Functions as a networking device that connects multiple networks and directs data between them.
- Connects local networks to the internet
- Determines the best path for data packets
- Uses IP addresses to forward data correctly
### 2. Switch
Connects devices within the same network and manages internal data communication.
- Connects computers, printers, and servers
- Sends data only to the intended device
- Improves network efficiency and performance
### 3. Hub
Acts as a basic device that connects multiple devices within a network.
- Broadcasts data to all connected devices
- Does not filter or manage traffic
- Less secure and less efficient than a switch
### 4. Bridge
Connects two network segments and filters traffic between them.
- Reduces unnecessary data transmission
- Improves network performance
- Works using MAC addresses
### 5. Gateway
Connects two different networks that use different protocols.
- Translates data between different systems
- Enables communication between dissimilar networks
- Commonly used to connect private networks to external networks
### 6. Access Point (AP)
Provides wireless connectivity to devices in a network.
- Extends a wired network into Wi-Fi
- Allows mobile devices to connect wirelessly
- Improves network coverage area
### 7. Modem
Converts digital data into signals suitable for transmission and vice versa.
- Connects a home or office network to the ISP
- Converts digital signals to analog and back
- Enables internet access
### 8. Firewall
Security device that monitors and controls network traffic.
- Blocks unauthorized access
- Filters incoming and outgoing data
- Protects networks from cyber threats
## Goals and Uses
- **Resource Sharing:** Allow multiple users to share hardware, software, and data resources efficiently.
- **Internet and Cloud Access:** Enable access to the Internet, online services, and cloud-based applications.
- **Cost Efficiency:** Reduce operational and infrastructure costs through shared resources and centralized systems.
- **Reliability and Availability:** Improve system reliability using backup paths and fault-tolerant mechanisms.
- **Scalability and Growth:** Support easy expansion by adding new devices and services as demand increases.
- **Security and Control:** Protect data and network resources using authentication, access control, and monitoring.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/basics-computer-networking/)

## GATE CS

- Subject: Computer Networks
- Topic: Network Fundamental and Physical Layer

> [!note] Related notes
>
> - [[Difference between Broadband and]]
> - [[Difference between Unipolar, Polar and]]
> - [[Layers of OSI Model]]
> - [[Let’s experiment with Networking]]
> - [[Network goals]]
> - [[Network Topologies]]
> - [[Redundant link problems]]
> - [[TCP IP Model]]
> - [[Transmission Modes in Computer Networks]]
> - [[Types of area networks – LAN, MAN and WAN]]
