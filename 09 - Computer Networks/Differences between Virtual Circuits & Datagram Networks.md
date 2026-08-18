---
title: "Differences Between Virtual Circuits and Datagram Networks"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/differences-between-virtual-circuits-and-datagram-networks/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Differences Between Virtual Circuits and Datagram Networks
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/differences-between-virtual-circuits-and-datagram-networks/)

---

# Differences Between Virtual Circuits and Datagram Networks

Computer networks that provide connection-oriented services are called Virtual Circuits while those providing connection-less services are called Datagram networks. For prior knowledge, the Internet that we use is based on a Datagram network (connection-less) at the network level as all packets from a source to a destination do not follow the same path. 
## **Virtual Circuits**
- It is connection-oriented, meaning that there is a reservation of resources like buffers, [CPU](https://www.geeksforgeeks.org/computer-science-fundamentals/central-processing-unit-cpu/), [bandwidth](https://www.geeksforgeeks.org/computer-networks/introduction-to-bandwidth/), etc. for the time in which the newly set VC is going to be used by a data transfer session.
- The first sent packet reserves resources at each server along the path. Subsequent packets will follow the same path as the first sent packet for the connection time.
- Since all the packets are going to follow the same path, a global header is required. Only the first packet of the connection requires a global header, the remaining packets generally don’t require global headers.
- Since all packets follow a specific path, packets are received in order at the destination.
- Virtual Circuit Switching ensures that all packets successfully reach the Destination. No packet will be discarded due to the unavailability of resources.
- From the above points, it can be concluded that [Virtual Circuits](https://www.geeksforgeeks.org/computer-networks/virtual-circuit-in-computer-network/) are a highly reliable method of data transfer.
- The issue with virtual circuits is that each time a new connection is set up, resources and extra information have to be reserved at every router along the path, which becomes problematic if many clients are trying to reserve a router's resources simultaneously.
- It is used by the [ATM (Asynchronous Transfer Mode) Network](https://www.geeksforgeeks.org/computer-networks/asynchronous-transfer-mode-atm-in-computer-network/), specifically for Telephone calls.
### Types of Virtual Circuit
**1. Permanent Virtual Circuits(PVC):** The communication management station, which is the telco's central office, manually configures the switches, which offer performance comparable to dedicated lines. The main use for these always-on circuits is high-speed communication. PVCs require telco resources (switches) to be allocated to a single communication circuit whether or not that circuit is in use, making them an expensive solution for wide-area networks (WANs).
**2. Switched Virtual circuits (SVCs):** As soon as a communication session is established, the switches are set up. SVCs are released at the conclusion of the session and can be used to create new channels of communication. This is the process of normal phone communication. SVCs, which are billed on a per-minute basis, are generally utilised in WANs when backups to dedicated leased lines are required.
### Benefits of Virtual Circuit
- The recipient receives the sender's packets in the same order as they were sent.
- A secure network link is called a virtual circuit.
- Overhead is not required for any packet.
- A single global packet overhead is used in a virtual circuit.
### Drawbacks of Virtual Circuits
- The cost of implementing a virtual circuit is high.
- It provides only services based on connections.
- In order to transmit, a new link needs to be created permanently.
## **Datagram Networks**
- It is a [connection-less service](https://www.geeksforgeeks.org/computer-networks/connection-less-service/#:~:text=A%20Connectionless%20Service%20is%20technique,source%20and%20receiver%20or%20destination.). There is no need for reservation of resources as there is no dedicated path for a connection session.
- All packets are free to use any available path. As a result, intermediate routers calculate routes on the go due to dynamically changing routing tables on routers.
- Since every packet is free to choose any path, all packets must be associated with a header with proper information about the source and the upper layer data.
- The connection-less property makes data packets reach the destination in any order, which means that they can potentially be received out of order at the receiver's end.
- Datagram networks are not as reliable as Virtual Circuits.
- The major drawback of Datagram Packet switching is that a packet can only be forwarded if resources such as the buffer, CPU, and bandwidth are available. Otherwise, the packet will be discarded.
- But it is always easy and cost-efficient to implement datagram networks as there is no extra headache of reserving resources and making a dedicated each time an application has to communicate.
- It is generally used by the IP network, which is used for Data services like the Internet.
### Benefits of Datagram Networks
- The flexibility of datagram networks is one of its main benefits.
- They are better at managing network congestion. Datagram networks are able to adjust to variations in network traffic and identify several paths for packets to take in order to reach their intended destination because every packet is handled separately.
- In big and complicated networks in particular, this can lead to decreased latency and increased network performance.
- In addition, datagram networks scale more easily than other kinds of networks. Datagram networks are the ideal option for contemporary communication systems, such as the Internet of Things (IoT) and real-time data streaming applications, due to their scalability.
### Drawbacks of Datagram Networks
- The lack of assured delivery in datagram networks is one of their primary disadvantages. There is no assurance that all packets will arrive at their destination or in the right order because they are sent separately.
- Datagram networks also have the drawback of being vulnerable to security breaches. Datagram networks are particularly susceptible to network assaults including spoofing, eavesdropping, and denial of service (DoS) attacks since they don't create a dedicated connection between the sender and the recipient.
- Moreover, datagram networks may not always support guarantees of quality of service (QoS). While certain applications may benefit from QoS capabilities provided by some protocols, like the Real-time Transport Protocol (RTP), datagram networks as a whole do not provide a centralised method for allocating priorities and controlling network traffic.
## Difference Between Virtual Circuits and Datagram Networks
| Criteria | Virtual Circuit Networks | Datagram Networks |
| --- | --- | --- |
| **Connection Establishment** | Prior to data transmission, a connection is established between sender and receiver. | No connection setup is required. |
| **Routing** | Routing decisions are made once during connection setup and remain fixed throughout the duration of the connection. | Routing decisions are made independently for each packet and can vary based on network conditions. |
| **Flow Control** | Uses explicit flow control, where the sender adjusts its rate of transmission based on feedback from the receiver. | Uses implicit flow control, where the sender assumes a certain level of available bandwidth and sends packets accordingly. |
| **Congestion Control** | Uses end-to-end congestion control, where the sender adjusts its rate of transmission based on feedback from the network. | Uses network-assisted congestion control, where routers monitor network conditions and may drop packets or send congestion signals to the sender. |
| **Error Control** | Provides reliable delivery of packets by detecting and retransmitting lost or corrupted packets. | Provides unreliable delivery of packets and does not guarantee delivery or correctness. |
| **Overhead** | Requires less overhead per packet because connection setup and state maintenance are done only once. | Requires more overhead per packet because each packet contains information about its destination address and other routing information. |
| **Example Protocol** | ATM, Frame Relay | IP (Internet Protocol) |
## Conclusion
- Another term for virtual circuits is connection-oriented switching. Virtual circuit switching establishes a predetermined path before a message is sent.
- The path in virtual circuits is called a virtual circuit because it seems to the user to be a dedicated physical circuit.
- In datagram networks, sometimes referred to as packet-switching technology, each packet—also known as a datagram—is regarded as an autonomous entity. The switch uses the destination information included in each packet to guide the packet to its intended location.
- Reserving resources is not necessary in Datagram Networks since there isn't a specific channel for connection sessions. Packets now have a header containing all of the data intended for the destination.
- Datagram networks use first-come, first-serve (FCFS) scheduling to manage resource distribution.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/differences-between-virtual-circuits-and-datagram-networks/)

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
