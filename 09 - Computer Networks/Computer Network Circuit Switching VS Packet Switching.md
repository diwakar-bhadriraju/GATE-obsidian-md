---
title: "Difference between Circuit Switching and Packet Switching"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/difference-between-circuit-switching-and-packet-switching/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Difference between Circuit Switching and Packet Switching
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/difference-between-circuit-switching-and-packet-switching/)

---

# Difference between Circuit Switching and Packet Switching

**Switching** is the process of transferring data packets from one device to another in a network or from one network to another, using specific devices called **switches**. There are three types of switching methods:
- [Message Switching](https://www.geeksforgeeks.org/computer-networks/message-switching-techniques/)
- [Circuit Switching](https://www.geeksforgeeks.org/computer-networks/circuit-switching-in-computer-network/)
- [Packet Switching](https://www.geeksforgeeks.org/computer-networks/difference-between-message-and-packet-switching/)
## Circuit Switching
[Circuit switching](https://www.geeksforgeeks.org/computer-networks/circuit-switching-in-computer-network/) is a communication method where a dedicated communication path, or circuit, is established between two devices before data transmission begins. The circuit remains dedicated to the communication for the duration of the session, and no other devices can use it while the session is in progress. Circuit switching is commonly used in voice communication and some types of data communication.
## **Advantages of Circuit Switching**
- **Guaranteed bandwidth:** Circuit switching provides a dedicated path for communication, ensuring that bandwidth is guaranteed for the duration of the call.
- **Low latency:** Circuit switching provides low latency because the path is predetermined, and there is no need to establish a connection for each packet.
- **Predictable performance:** Circuit switching provides predictable performance because the [bandwidth](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-bandwidth-definition-working-importance-uses/) is reserved, and there is no competition for resources.
- **Suitable for real-time communication:** Circuit switching is suitable for real-time communication, such as voice and video, because it provides low latency and predictable performance.
## **Disadvantages of Circuit Switching**
- **Inefficient use of bandwidth:** Circuit switching is inefficient because the bandwidth is reserved for the entire duration of the call even when no data is being transmitted.
- **Limited scalability:** Circuit switching is limited in its scalability because the number of circuits that can be established is finite which can limit the number of simultaneous calls that can be made.
- **High cost:** Circuit switching is expensive because it requires dedicated resources, such as hardware and bandwidth for the duration of the call.
## Packet Switching
[Packet switching](https://www.geeksforgeeks.org/computer-networks/packet-switching-and-delays-in-computer-network/) is a communication method where data is divided into smaller units called packets and transmitted over the network. Each packet contains the source and destination addresses, as well as other information needed for routing. The packets may take different paths to reach their destination, and they may be transmitted out of order or delayed due to network congestion.
## **Advantages of Packet Switching**
- **Efficient use of bandwidth:** Packet switching is efficient because bandwidth is shared among multiple users and resources are allocated only when data needs to be transmitted.
- **Flexible**: Packet switching is flexible and can handle a wide range of data rates and packet sizes.
- **Scalable:** Packet switching is highly scalable and can handle large amounts of traffic on a network.
- **Lower cost:** Packet switching is less expensive than circuit switching because resources are shared among multiple users.
## **Disadvantages of Packet Switching**
- **Higher latency:** Packet switching has higher [latency](https://www.geeksforgeeks.org/computer-networks/what-is-latency/) than circuit switching because packets must be routed through multiple nodes which can cause delay.
- **Limited QoS:** Packet switching provides limited QoS guarantees. It means that different types of traffic may be treated equally.
- **Packet loss:** Packet switching can result in packet loss due to [congestion](https://www.geeksforgeeks.org/computer-networks/congestion-control-in-computer-networks/) on the network or errors in transmission.
- **Unsuitable for real-time communication:** Packet switching is not suitable for real-time communication, such as voice and video, because of the potential for latency and packet loss.
## Difference between Circuit Switching and Packet Switching
| **Circuit Switching** | **Packet Switching** |
| --- | --- |
| Circuit switching has 3 phases:  i) Connection Establishment.  ii) Data Transfer.  iii) Connection Released. | In Packet switching directly data transfer takes place. |
| In circuit switching, each data unit knows the entire path address which is provided by the source. | In Packet switching, each data unit just knows the final destination address intermediate path is decided by the routers. |
| In Circuit switching, data is processed at the source system only | In Packet switching, data is processed at all intermediate nodes including the source system. |
| The delay between data units in circuit switching is uniform. | The delay between data units in packet switching is not uniform. |
| Resource reservation is the feature of circuit switching because the path is fixed for data transmission. | There is no resource reservation because bandwidth is shared among users. |
| Circuit switching is more reliable. | Packet switching is less reliable. |
| Wastage of resources is more in Circuit Switching | Less wastage of resources as compared to Circuit Switching |
| It is not a store and forward technique. | It is a store and forward technique. |
| Transmission of the data is done by the source. | Transmission of the data is done not only by the source but also by the intermediate routers. |
| Congestion can occur during the connection establishment phase because there might be a case where a request is being made for a channel but the channel is already occupied. | Congestion can occur during the data transfer phase, a large number of packets comes in no time. |
| Circuit switching is not convenient for handling bilateral traffic. | Packet switching is suitable for handling bilateral traffic. |
| In Circuit switching, the charge depends on time and distance and not on traffic in the network. | In Packet switching, the charge is based on the number of bytes and connection time. |
| Recording of packets is never possible in circuit switching. | Recording of packets is possible in packet switching. |
| In Circuit Switching there is a physical path between the source and the destination | In Packet Switching there is no physical path between the source and the destination |
| Circuit Switching does not support store and forward transmission | Packet Switching supports store and forward transmission |
| Call setup is required in circuit switching. | No call setup is required in packet switching. |
| In circuit switching each packet follows the same route. | In packet switching packets can follow any route. |
| The circuit switching network is implemented at the physical layer. | Packet switching is implemented at the datalink layer and network layer |
| Circuit switching requires simple protocols for delivery. | Packet switching requires complex protocols for delivery. |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/difference-between-circuit-switching-and-packet-switching/)

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
> - [[Computer Network Servers]]
> - [[Computer Networks Longest Prefix Matching in Routers]]
> - [[Difference between layer-2 and layer-3 switches]]
