---
title: "What is a Network Switch and How Does it Work?"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/what-is-a-network-switch-and-how-does-it-work/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] What is a Network Switch and How Does it Work?
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/what-is-a-network-switch-and-how-does-it-work/)

---

# What is a Network Switch and How Does it Work?

The Switch is a network device that is used to segment the networks into different subnetworks called subnets or LAN segments. It is responsible for filtering and forwarding the packets between LAN segments based on MAC address. 
Switches have many ports, and when data arrives at any port, the destination address is examined first and some checks are also done and then it is processed to the devices. Different types of communication are supported here like unicast, multicast, and broadcast communication.
## Features of Network Switches
- It operates in the Data Link Layer in the [OSI Model](https://www.geeksforgeeks.org/computer-networks/open-systems-interconnection-model-osi/).
- It performs error checking before forwarding data.
- It transfers the data only to the device that has been addressed.
- It operates in full duplex mode.
- It allocates each [LAN](https://www.geeksforgeeks.org/computer-networks/lan-full-form/) segment to a limited bandwidth.
- It uses Unicast (one-to-one), multicast (one-to-many), and broadcast (one-to-all) transmission modes.
- Packet-switching techniques are used to transfer data packets from source to destination.
- Switches have a more significant number of ports.
## Why Are Network Switches Valuable?
Switches are one of the most important things for transferring information between different endpoints. Some of the benefits are mentioned below.
- Switches are having [full-duplex communication](https://www.geeksforgeeks.org/computer-networks/transmission-modes-computer-networks/) which helps in making effective use of bandwidth.
- Switches help to provide a wired connection to printers, IoT devices, wireless points, and many more devices.
- IoT Devices send data through Network Switches that help in making smarter surroundings with the help of [Artificial Intelligence](https://www.geeksforgeeks.org/artificial-intelligence/what-is-artificial-intelligence-ai/).
- Network Devices are made with the help of Switches that carry a large number of traffic in telecommunication.
## Types of Switches
Switches are mainly classified into the following types that are mentioned below.
- **Virtual Switches:** Virtual Switches are the switches that are inside Virtual Machine hosting environments.
- **Routing Switches:** These are the switches that are used to connect LANs.They also have the work of performing functions in the Network Layer of the OSI Model.
- **Unmanaged Switches:** Unmanaged Switches are the devices that are used to enable Ethernet devices that help in automatic data passing. These are generally used for home networks and small businesses. In case of the requirement of more switches, we just add more switches by plug and play method.
- **Managed Switches:** Managed Switches are switches having more complex networks. SNMP (Simple Network Management Protocol) can be used for configuring managed switches. These types of switches are mostly used in large networks having complex architecture. They provide better security levels and precision control but they are more costly than Unmanaged switches.
- **LAN Switches:** LAN (Local Area Network) Switches are also called ethernet switches or data switches. LAN switches always try to avoid overlapping of data packets in the network just by allocating bandwidth in such a manner.
- **PoE Switches:** [Power over Ethernet(PoE)](https://www.geeksforgeeks.org/computer-networks/what-is-power-over-ethernet-poe/) are the switches used in Gigabit Ethernets. PoE help in combining data and power transmission over the same cable so that it helps in receiving data and electricity over the same line.
- **Smart Switches:** Smart Switches are switches having some extra controls on data transmissions but also have extra limitations over managed Switches. They are also called partially managed switches.
- **Stackable Switches:** Stackable switches are connected through a backplane to combine two logical switches into a single switch.
- **Modular Switches:** These types of switches help in accommodating two or more cards. Modular switches help in providing better flexibility.
## What is a Layer 2 Switch?
A Layer 2 switch operates at Layer 2 of OSI model, which is the Data Link Layer. The switch forwards data packets depending on the devices’ MAC (Media Access Control) addresses that are in its network. Most commonly they are found in Local Area Networks (LAN) where their main purpose includes providing different collision domains while reducing congestion within that network .To enable delivery of this data to specific destination layer II switches find out appropriate port for these packets on MAC basis.
## What is a Layer 3 Switch?
A Layer 3 Switch is identical to an ordinary switch in its operation with a router at the same time, working at both data link layer (Layer 2) and network layer (Layer 3) under the Open Systems Interconnection model. Layer 3 switches can route packets between diverse subnets or VLANs (virtual LANs) with the application of IP addresses, similar to the manner in which networking devices called routers handle them. Hence they are suitable for big-sized networks necessitating fast switching together with routing abilities.
## What is an Unmanaged Switch?
A basic, plug-and-play network device called unmanaged switch permits automatic communication between Ethernet devices. Where the network design is uncomplicated and there is no need for intricate settings, unmanaged switches are mostly found in home networks or small businesses. They do not include any configuration choices or advanced functions thus they are convenient to install and use.
## What is a Managed Switch?
A managed switch has more sophisticated functionalities and elevated authority on network configurations as opposed to an unmanaged one. They let the net admins set up, manage and observe their net working so as to enhance its effectiveness and safeguard it against possible hacks or any other form of interference. Managed switches also provide remote alterations through SNMP (Simplified Network Management Protocol). Other different protocols such as VLANs, QoS (Quality of Service), and redundancy alternatives are supported by such switches too.
## How Does a Network Switch Works?
When the source wants to send the data packet to the destination, the packet first enters the switch and the switch reads its header and finds the MAC address of the destination to identify the device then it sends the packet out through the appropriate ports that lead to the destination devices.
Switch establishes a temporary connection between the source and destination for communication and terminates the connection once the conversation is done. Also, it offers full bandwidth to network traffic going to and from a device simultaneously to reduce collision.
![How Does a Network Switch Works?](assets/Network-Switch-01-copy-660-06b456e85d.webp)
How Does a Network Switch Works?
## Switching Techniques
Switching techniques are used to decide the best route for data transmission between source and destination. These are classified into three categories :
- [Circuit Switching](https://www.geeksforgeeks.org/computer-networks/circuit-switching-in-computer-network/)
- [Message Switching](https://www.geeksforgeeks.org/computer-networks/message-switching-techniques/)
- [Packet Switching](https://www.geeksforgeeks.org/computer-networks/packet-switching-and-delays-in-computer-network/)
## How To Set Up a Network Switch?
There are different kinds of switches that work according to the tasks defined. For a small network LAN, or for a home network, a network switch is used by plugging into a port of the router. Below mentioned are the steps which are used in setting up network switches.
**Step 1:** Switch has to be bought as per the requirement of the network.
**Step 2:** The switch port has to be connected directly to the router using the cable. Generally, if there is an uplink port present in the switch, the wire should be connected to that port, if the uplink power is not present, then the wire has to be connected to any port of the router.
**Step 3:** After proper connection, the [IP addresses](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-an-ip-address/) of devices are configured.
## Difference Between Network Switch and Router
| Network Switch | Router |
| --- | --- |
| Network Switch works on Layer 2 of the OSI Model. | The router is primarily a device of Layer 3 of the OSI Model. |
| The resource is shared among multiple devices with the help of a single LAN using a network switch. | Data is moved between two or more computers with the help of a router. |
| Network switches uses data frames. | Routers use data packets. |
| Switches only work in a Wired network connection. | Router works with both wired and wifi networks. |
| Switches use MAC Addresses for transferring data to the proper destination. | Routers use IP Addresses for the same work. |
## Uses of Network Switches
Network Switches are an important part of Network communication. Some of the use cases are mentioned below.
- Network switches help provide automatic link connections that remove time-consuming settings and provide easy access to network devices.
- Switches provide a better, more secure, reliable network having more control over data.
- Generally, switches work in full duplex mode, which helps in continuous data transmission and that improves better connectivity.
- As MAC Address is used for the devices connected to it, that helps in the delivery of messages to only the required destination, not everywhere.
- Network Switches work for home networks or local networks where streaming works are performed regularly.
## Difference between Network Switch and Hub
| Network Switch | Hub |
| --- | --- |
| Network Switch is a device of layer 2 of the OSI Model. | Hub is a physical device of Layer 1 of the OSI Model. |
| Network Switch is a little more complex than a Hub. | Hub is a simple device as compared to Network Switch. |
| Network Switch easily manages data in and out, hence less communication collision. | Communication Collisions usually happen in a Hub. |
| Network Switches transfer data together by connecting devices. | The main task of Hub is to connect all nodes of the network. |
| Switches prevent collision with the help of [Ethernet frames](https://www.geeksforgeeks.org/computer-networks/ethernet-frame-format/). | Hubs cannot help in preventing collisions. |
## Advantages of Switches
- Prevents traffic overloading in a network by segmenting the network into smaller subnets.
- Increases the bandwidth of the network.
- Less frame collision as the switch creates the collision domain for each connection.
## Disadvantages of Switches
- It can not stop traffic destined for a different LAN segment from traveling to all other LAN segments.
- Switches are more expensive.
## Conclusion
In contemporary networking, it is essential to use network switches because of efficient information flow between machines on Local Area Network. Depending on the needs of a certain organization with varying networking requirements, they can select among different types of switches ranging from simple non-managed types to sophisticated managed types. When talking about the role of networking and the need for layers 2 and 3 switches, one cannot ignore their importance as far as connection separation as well as routing is concerned. Also, there are other features like Power over Ethernet (PoE) and modularity that give more flexibility in case an application requires something specific.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/what-is-a-network-switch-and-how-does-it-work/)

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
