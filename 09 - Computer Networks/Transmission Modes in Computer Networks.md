---
title: "Transmission Modes"
subject: "Computer Networks"
topic: "Network Fundamental and Physical Layer"
source: "https://www.geeksforgeeks.org/computer-networks/transmission-modes-computer-networks/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Fundamental and Physical Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-fundamental-and-physical-layer
---


> [!abstract] Transmission Modes
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Fundamental and Physical Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/transmission-modes-computer-networks/)

---

# Transmission Modes

Transmission Modes describe how data is exchanged between two devices over a communication channel. They specify whether information moves in a single direction or in both directions, and whether devices can transmit at the same time.
- Defines the pattern of communication
- Determines sender and receiver roles
- Influences speed and performance
- Used in networking and telecommunication systems
![transmission_mode](assets/transmission_mode-44b22a16ca.webp)
Transmission Modes
> **Note:** It is also known as a communication mode. [Buses](https://www.geeksforgeeks.org/computer-organization-architecture/system-bus-design/) and networks are designed to allow communication to occur between individual devices that are interconnected
## Simplex Mode
Simplex Mode is a transmission mode in which communication occurs in only one direction, from a sender to a receiver, without any possibility of reverse data flow.
- One device acts only as transmitter
- The other device acts only as receiver
- No feedback or acknowledgment is supported
![Simplex Mode](assets/SiMpleduplex-25f84b8425.png)
> **Example:** [Keyboard](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-a-keyboard/) and traditional monitors. The keyboard can only introduce input, the monitor can only give the output. 
### **Advantages**
- Simple and easy to implement
- Lower installation and maintenance cost
- Utilizes the entire bandwidth for sending
- Suitable for broadcast-type applications
### **Disadvantages**
- No error reporting from receiver
- Not suitable for interactive systems
- Cannot confirm successful delivery
- Limited use in modern two-way communication systems
## Half-Duplex Mode
Half-Duplex Mode is a transmission mode in which communication can occur in both directions, but only one device can transmit at a time. The devices take turns sending and receiving data over the same channel.
- Supports bidirectional communication
- Uses a single shared communication channel
- Transmission occurs alternately between devices
![Half Duplex Mode](assets/halfduplex-2f362e4421.png)
> **Example:** Walkie-talkie in which message is sent one at a time and messages are sent in both directions. 
### **Advantages**
- More flexible than one-way communication
- Cost-effective compared to full-duplex systems
- Efficient use of a single channel
- Suitable for controlled communication environments
### **Disadvantages**
- Cannot send and receive simultaneously
- Possible delay due to turn-based transmission
- Performance decreases with heavy traffic
- Risk of collision if control mechanisms fail
## Full-Duplex Mode
Full-Duplex Mode is a transmission mode in which communication takes place in both directions at the same time. Both connected devices can transmit and receive data simultaneously without waiting for each other.
- Enables simultaneous two-way data exchange
- Uses separate channels or divided bandwidth
- Common in real-time communication systems
![](assets/fullduplex-b9e2e85c52.png)
> **Example:** Telephone Network in which there is communication between two persons by a telephone line, through which both can talk and listen at the same time. 
### **Advantages**
- Faster data transfer rate
- No waiting time between transmissions
- Improved communication efficiency
- Suitable for interactive applications
### **Disadvantages**
- Higher installation cost
- Requires more complex hardware
- Greater bandwidth requirement
- Increased system configuration complexity
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/transmission-modes-computer-networks/)

## GATE CS

- Subject: Computer Networks
- Topic: Network Fundamental and Physical Layer

> [!note] Related notes
>
> - [[Basics of Computer Networking]]
> - [[Difference between Broadband and]]
> - [[Difference between Unipolar, Polar and]]
> - [[Layers of OSI Model]]
> - [[Let’s experiment with Networking]]
> - [[Network goals]]
> - [[Network Topologies]]
> - [[Redundant link problems]]
> - [[TCP IP Model]]
> - [[Types of area networks – LAN, MAN and WAN]]
