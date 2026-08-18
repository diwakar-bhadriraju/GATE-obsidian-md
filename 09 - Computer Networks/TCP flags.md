---
title: "TCP flags"
subject: "Computer Networks"
topic: "Transport Layer"
source: "https://www.geeksforgeeks.org/computer-networks/tcp-flags/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Transport Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/transport-layer
---


> [!abstract] TCP flags
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Transport Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/tcp-flags/)

---

# TCP flags

In TCP connection, flags are used to indicate a particular state of connection or to provide some additional useful information like troubleshooting purposes or to handle a control of a particular connection. Most commonly used flags are **"SYN", "ACK" and "FIN"**. Each flag corresponds to 1 bit information. 
**Types of Flags:** 
- **Synchronization (SYN) -** It is used in first step of [connection establishment](https://www.geeksforgeeks.org/computer-networks/tcp-connection-establishment/) phase or 3-way handshake process between the two hosts. Only the first packet from sender as well as receiver should have this flag set. This is used for synchronizing sequence number i.e. to tell the other end which sequence number they should accept.
- **Acknowledgement (ACK) -** It is used to acknowledge packets which are successful received by the host. The flag is set if the acknowledgement number field contains a valid acknowledgement number. 
  In given below diagram, the receiver sends an ACK = 1 as well as SYN = 1 in the second step of connection establishment to tell sender that it received its initial packet.
- **Finish (FIN) -** It is used to request for [connection termination](https://www.geeksforgeeks.org/computer-networks/tcp-connection-termination/) i.e. when there is no more data from the sender, it requests for connection termination. This is the last packet sent by sender. It frees the reserved resources and gracefully terminate the connection.
- **Reset (RST) -** It is used to terminate the connection if the RST sender feels something is wrong with the TCP connection or that the conversation should not exist. It can get send from receiver side when packet is send to particular host that was not expecting it.
- **Urgent (URG) -** It is used to indicate that the data contained in the packet should be prioritized and handled urgently by the receiver. This flag is used in combination with the Urgent Pointer field to identify the location of the urgent data in the packet.
- **Push (PSH) -** It is used to request immediate data delivery to the receiving host, without waiting for additional data to be buffered on the sender's side. This flag is commonly used in applications such as real-time audio or video streaming.
- **Window (WND) -** It is used to communicate the size of the receive window to the sender. The window size is the amount of data that the receiving host is capable of accepting at any given time. The sender should limit the amount of data it sends based on the size of the window advertised by the receiver.
- **Checksum (CHK) -** It is used to verify the integrity of the TCP segment during transmission. The checksum is computed over the entire segment, including the header and data fields, and is recalculated at each hop along the network path.
- **Sequence Number (SEQ) -** It is a unique number assigned to each segment by the sender to identify the order in which packets should be received by the receiver. The sequence number is used in conjunction with the acknowledgement number to ensure reliable data transfer and to prevent duplicate packets.
- **Acknowledgement Number (ACK) -** It is used to acknowledge the receipt of a TCP segment and to communicate the next expected sequence number to the sender. The acknowledgement number field contains the sequence number of the next expected segment, rather than the number of the last received segment.
**Finish (FIN) v/s Reset (RST) -** 
![](assets/po-1-1-8e3ec2a319.png)
- **Push (PSH) -** Transport layer by default waits for some time for application layer to send enough data equal to maximum segment size so that the number of packets transmitted on network minimizes which is not desirable by some application like interactive applications(chatting). Similarly transport layer at receiver end buffers packets and transmit to application layer if it meets certain criteria. 
  This problem is solved by using PSH. Transport layer sets PSH = 1 and immediately sends the segment to network layer as soon as it receives signal from application layer. Receiver transport layer, on seeing PSH = 1 immediately forwards the data to application layer. 
  In general, it tells the receiver to process these packets as they are received instead of buffering them.
- **Urgent (URG) -**Data inside a segment with URG = 1 flag is forwarded to application layer immediately even if there are more data to be given to application layer. It is used to notify the receiver to process the urgent packets before processing all other packets. The receiver will be notified when all known urgent data has been received.
**Push (PSH) v/s Urgent (URG) -** 
![](assets/po-1-2-b943ea5d28.png)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/tcp-flags/)

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
> - [[TCP Server-Client implementation in C]]
