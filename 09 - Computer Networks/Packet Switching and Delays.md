---
title: "Packet Switching and Delays in Computer Network"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/packet-switching-and-delays-in-computer-network/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Packet Switching and Delays in Computer Network
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/packet-switching-and-delays-in-computer-network/)

---

# Packet Switching and Delays in Computer Network

Packet Switching is a method of sending data in small units called packets, each containing a header (control info) and payload. Packets travel independently using the Store-and-Forward technique, possibly via different paths, and are reassembled at the destination. No dedicated path or resource reservation is needed, making data transfer efficient and flexible.
![Packet Switching](assets/4514-660-d460879f19.png)
Packet Switching
### Types of Delays in Packet Switching
Packet switching involves several types of delays that can affect the overall transmission time of data from source to destination. These delays occur at different stages during packet processing and transmission. The main types of delays are:
- **Transmission Delay:**  Time required by the spent station to transmit data to the link.
- **Propagation Delay:**  It is the time of data propagation through the link. It depends on the distance and the propagation speed of the medium (e.g., fiber optic, copper).
- **Queueing Delay:**  It is the time spent by the packet at the destination's queue. It varies depending on network congestion and traffic load.
- **Processing Delay:**  Processing time for data at the destination. It includes error checking and protocol handling.
- **End-to-End Delay** : Total time it takes for a packet to travel from the source to the destination. It is the sum of all the above delays: End-to-End Delay= Processing + Queuing + Transmission + Propagation
> For more information on delays you can refer to the article [Delays in Computer network](https://www.geeksforgeeks.org/computer-networks/delays-in-computer-network/).
## **Advantages of Packet Switching**
- **More efficient bandwidth usage**: There is no need to reserve a dedicated path, which leads to better utilization of available bandwidth.
- **Minimal transmission latency**: Data can be transmitted as soon as it's ready, without waiting for a complete path to be established.
- **Higher reliability**: The destination can detect missing packets and request retransmission.
- **Greater fault tolerance**: If one link fails, packets can be rerouted through alternative paths.
- **Cost-effective**: Packet switching networks are generally cheaper and easier to implement and maintain.
## **Disadvantage of Packet Switching**
- **Unordered delivery**: Packets may arrive out of sequence, while circuit switching ensures ordered delivery since all data follows the same path.
- **Need for sequence numbers**: To reassemble data correctly, each packet must carry a sequence number.
- **Increased complexity at nodes**: Each node must be capable of routing packets dynamically, which adds to the complexity.
- **Potential transmission delays**: Rerouting and queuing can introduce delays, especially under high network load.
- **Less suitable for large, continuous data streams**: While ideal for small or burst data, packet switching can be less efficient for large, constant data transmissions compared to circuit switching.
## **Types of Packet Switching**
### **Connection-oriented Packet Switching (Virtual Circuit)**
Connection-oriented (Virtual Circuit) Packet Switching establishes a logical path between sender and receiver before data transfer. All packets follow this predefined route and are given sequence numbers to ensure they arrive in order. Each connection is identified by a Virtual Circuit ID assigned by the network.
This method involves three main phases:
**1. Setup Phase**: A path is established between sender and receiver. Address information is exchanged and recorded.
![set_up_phase_](assets/set_up_phase_-b0152f0f02.webp)
Set -up Phase
**2. Data Transfer Phase**: Packets are transmitted along the established route, with headers containing local information like length, timestamp, and sequence number.
![data_transfer_phase](assets/data_transfer_phase-18bfdc233e.webp)
Data Transfer Phase
**3. Tear Down Phase**: After the transmission is complete, the virtual circuit is released.
![tear_down_phase](assets/tear_down_phase-6ecf5cb2e0.webp)
Tear Down Phase
Some popular protocols which use the Virtual Circuit Switching approach are X.25, Frame-Relay, ATM, and MPLS(Multi-Protocol Label Switching).
### **Connectionless Packet Switching (Datagram)**
Connectionless (Datagram) Packet Switching treats each packet independently, with all addressing and control information included. No connection setup is needed, and packets may take different paths, possibly arriving out of order. Reliability and data integrity are handled by higher-layer protocols like TCP, providing flexibility and speed.
![datagram_packet_switching](assets/datagram_packet_switching-d8e65a8925.webp)
Datagram Packet Switching
## **Advantages of Packet Switching**
- **More efficient bandwidth usage**: There is no need to reserve a dedicated path, which leads to better utilization of available bandwidth.
- **Minimal transmission latency**: Data can be transmitted as soon as it's ready, without waiting for a complete path to be established.
- **Higher reliability**: The destination can detect missing packets and request retransmission.
- **Greater fault tolerance**: If one link fails, packets can be rerouted through alternative paths.
- **Cost-effective**: Packet switching networks are generally cheaper and easier to implement and maintain.
## **Disadvantage of Packet Switching**
- **Unordered delivery**: Packets may arrive out of sequence, while circuit switching ensures ordered delivery since all data follows the same path.
- **Need for sequence numbers**: To reassemble data correctly, each packet must carry a sequence number.
- **Increased complexity at nodes**: Each node must be capable of routing packets dynamically, which adds to the complexity.
- **Potential transmission delays**: Rerouting and queuing can introduce delays, especially under high network load.
- **Less suitable for large, continuous data streams**: While ideal for small or burst data, packet switching can be less efficient for large, constant data transmissions compared to circuit switching.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/packet-switching-and-delays-in-computer-network/)

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
