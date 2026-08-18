---
title: "Transport Layer responsibilities"
subject: "Computer Networks"
topic: "Transport Layer"
source: "https://www.geeksforgeeks.org/computer-networks/transport-layer-responsibilities/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Transport Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/transport-layer
---


> [!abstract] Transport Layer responsibilities
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Transport Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/transport-layer-responsibilities/)

---

# Transport Layer responsibilities

The transport Layer is the second layer in the [TCP/IP model](https://www.geeksforgeeks.org/computer-networks/tcp-ip-model/) and the fourth layer in the [OSI model](https://www.geeksforgeeks.org/computer-networks/open-systems-interconnection-model-osi/). It is an end-to-end layer used to deliver messages to a host. It is termed an end-to-end layer because it provides a point-to-point connection rather than hop-to-hop, between the source host and destination host to deliver the services reliably. The unit of data encapsulation in the Transport Layer is a segment. 
## Working of Transport Layer
The transport layer takes services from the [Application layer](https://www.geeksforgeeks.org/computer-networks/application-layer-in-osi-model/) and provides services to the [Network layer](https://www.geeksforgeeks.org/computer-networks/network-layer-services-packetizing-routing-and-forwarding/).
**The transport layer ensures the reliable transmission of data between systems.** Understanding protocols like **TCP** and **UDP** is crucial. If you're aiming for a deeper understanding of transport layer protocols, the [**GATE CS Self-Paced Course**](https://www.geeksforgeeks.org/courses/category/gate?utm_source=test_series&utm_medium=cse/) offers comprehensive modules on networking, including detailed explanations of transport layer responsibilities and how they operate in real-world applications.
**At the sender's side:** The transport layer receives data (message) from the Application layer and then performs Segmentation, divides the actual message into segments, adds the source and destination's port numbers into the header of the segment, and transfers the message to the Network layer. 
**At the receiver's side:** The transport layer receives data from the Network layer, reassembles the segmented data, reads its header, identifies the port number, and forwards the message to the appropriate port in the Application layer. 
## Responsibilities of a Transport Layer
- The Process to Process Delivery
- End-to-End Connection between Hosts
- Multiplexing and Demultiplexing
- Congestion Control
- Data integrity and Error correction
- Flow control
### **1. The Process to Process Delivery**
While Data Link Layer requires the MAC address (48 bits address contained inside the Network Interface Card of every host machine) of source-destination hosts to correctly deliver a frame and the Network layer requires the IP address for appropriate routing of packets, in a similar way Transport Layer requires a Port number to correctly deliver the segments of data to the correct process amongst the multiple processes running on a particular host. A port number is a 16-bit address used to identify any client-server program uniquely.
![](assets/image-289-1206f8c6e8.png)
Process to Process Delivery
### **2. End-to-end Connection between Hosts**
The transport layer is also responsible for creating the end-to-end Connection between hosts for which it mainly uses TCP and UDP. TCP is a secure, connection-orientated protocol that uses a handshake protocol to establish a robust connection between two end hosts. TCP ensures the reliable delivery of messages and is used in various applications. UDP, on the other hand, is a stateless and unreliable protocol that ensures best-effort delivery. It is suitable for applications that have little concern with flow or error control and requires sending the bulk of data like video conferencing. It is often used in multicasting protocols.
![](assets/EotE-0514e605a9.png)
End to End Connection.
### **3. Multiplexing and Demultiplexing**
Multiplexing(many to one) is when data is acquired from several processes from the sender and merged into one packet along with headers and sent as a single packet. Multiplexing allows the simultaneous use of different processes over a network that is running on a host.  The processes are differentiated by their port numbers. Similarly, Demultiplexing(one to many) is required at the receiver side when the message is distributed into different processes. Transport receives the segments of data from the network layer distributes and delivers it to the appropriate process running on the receiver's machine.
![Multiplexing and Demultiplexing](assets/CN_Multiplexing-1-947369b2d9.jpg)
Multiplexing and Demultiplexing
### **4. Congestion Control**
Congestion is a situation in which too many sources over a network attempt to send data and the router buffers start overflowing due to which loss of packets occurs. As a result, the retransmission of packets from the sources increases the congestion further. In this situation, the Transport layer provides [Congestion Control](https://www.geeksforgeeks.org/computer-networks/congestion-control-in-computer-networks/) in different ways. It uses open-loop congestion control to prevent congestion and closed-loop congestion control to remove the congestion in a network once it occurred. TCP provides AIMD - additive increases multiplicative decrease and [leaky bucket technique](https://www.geeksforgeeks.org/computer-networks/leaky-bucket-algorithm/) for congestion control.
![Leaky Bucket Congestion Control Technique](assets/leaky-131f557763.jpg)
Leaky Bucket Congestion Control Technique
### **5. Data integrity and Error Correction**
The transport layer checks for errors in the messages coming from the application layer by using error detection codes, and computing checksums, it checks whether the received data is not corrupted and uses the ACK and NACK services to inform the sender if the data has arrived or not and checks for the integrity of data.
![Error Correction using Checksum](https://media.geeksforgeeks.org/wp-content/uploads/20230329114527/Checksum_1.jpg)
Error Correction using Checksum
### **6. Flow Control**
The transport layer provides a flow control mechanism between the adjacent layers of the TCP/IP model. TCP also prevents data loss due to a fast sender and slow receiver by imposing some flow control techniques. It uses the method of sliding window protocol which is accomplished by the receiver by sending a window back to the sender informing the size of data it can receive.
## Protocols of Transport Layer
- [Transmission Control Protocol (TCP)](https://www.geeksforgeeks.org/computer-networks/what-is-transmission-control-protocol-tcp/)
- [User Datagram Protocol (UDP)](https://www.geeksforgeeks.org/computer-networks/user-datagram-protocol-udp/)
- [Stream Control Transmission Protocol (SCTP)](https://www.geeksforgeeks.org/computer-networks/sctp-full-form/)
- [Datagram Congestion Control Protocol (DCCP)](https://www.geeksforgeeks.org/computer-networks/what-is-dccp-datagram-congestion-control-protocol/)
- [AppleTalk Transaction Protocol (ATP)](https://www.geeksforgeeks.org/computer-networks/what-is-atp-appletalk-transaction-protocol/)
- [Fibre Channel Protocol (FCP)](https://www.geeksforgeeks.org/computer-networks/fcp-fibre-channel-protocol/)
- [Reliable Data Protocol (RDP)](https://www.geeksforgeeks.org/computer-networks/principle-of-reliable-data-transfer-protocol/)
- [Reliable User Data Protocol (RUDP)](https://www.geeksforgeeks.org/computer-networks/reliable-user-datagram-protocol-rudp/)
- [Structured Steam Transport (SST)](https://www.geeksforgeeks.org/computer-networks/what-is-sst-structured-steam-transport/)
- [Sequenced Packet Exchange (SPX)](https://www.geeksforgeeks.org/computer-networks/what-is-spx-sequenced-packet-exchange/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/transport-layer-responsibilities/)

## GATE CS

- Subject: Computer Networks
- Topic: Transport Layer

> [!note] Related notes
>
> - [[Congestion Control]]
> - [[Differences between TCP and UDP]]
> - [[Error Control in TCP]]
> - [[Leaky Bucket Algorithm]]
> - [[Multiplexing and Demultiplexing in Transport Layer]]
> - [[TCP 3-Way Handshake Process]]
> - [[TCP Congestion Control]]
> - [[TCP Connection Establishment]]
> - [[TCP Connection Termination]]
> - [[TCP flags]]
