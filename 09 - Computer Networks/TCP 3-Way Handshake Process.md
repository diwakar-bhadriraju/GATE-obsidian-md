---
title: "TCP 3-Way Handshake Process"
subject: "Computer Networks"
topic: "Transport Layer"
source: "https://www.geeksforgeeks.org/computer-networks/tcp-3-way-handshake-process/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Transport Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/transport-layer
---


> [!abstract] TCP 3-Way Handshake Process
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Transport Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/tcp-3-way-handshake-process/)

---

# TCP 3-Way Handshake Process

The TCP 3-Way Handshake is the process used by the Transmission Control Protocol (TCP) to establish a reliable connection between a client and a server before data transmission begins. It synchronises sequence numbers and ensures that both the client and server are ready to exchange data reliably.
![image](assets/image-3abe1fba68.png)
## TCP Flags Used in Handshake
| **Flag** | **Purpose** |
| --- | --- |
| **SYN (Synchronize)** | Initiates a TCP connection by sending the client's Initial Sequence Number (ISN). |
| **ACK (Acknowledgment)** | Acknowledges the received sequence number and confirms successful receipt of the segment. |
| **SYN + ACK (Combination of SYN and ACK Flags)** | Acknowledges the client's ISN while sending the server's own Initial Sequence Number (ISN). |
## TCP 3-way Handshake Process
- **Step 1 (SYN):** In the first step, the client wants to establish a connection with a server, so it sends a segment with SYN(Synchronize Sequence Number) which informs the server that the client is likely to start communication and with what sequence number it starts segments with
- **Step 2 (SYN + ACK):** Server responds to the client request with SYN-ACK signal bits set. Acknowledgement(ACK) signifies the response of the segment it received and SYN signifies with what sequence number it is likely to start the segments with
- **Step 3 (ACK):** In the final part client acknowledges the response of the server and they both establish a reliable connection with which they will start the actual data transfer.
## Numerical Example of Sequence and Acknowledgment Numbers
![host_p](assets/host_p-3c342ffe7a.webp)
Assume:
- Client Initial Sequence Number (ISN) = 1000
- Server Initial Sequence Number (ISN) = 5000
### Step 1: Client -> Server (SYN)
- Sequence Number = 1000
- SYN flag = 1
- No acknowledgment number (since this is the first segment)
The client proposes its starting sequence value.
### Step 2: Server -> Client (SYN-ACK)
- Sequence Number = 5000
- Acknowledgment Number = 1001
- (1000 + 1)
The server acknowledges the client’s SYN by adding 1 to the client’s sequence number.
 The value increases by 1 because the SYN consumes one sequence number.
### Step 3: Client -> Server (ACK)
- Sequence Number = 1001
- Acknowledgment Number = 5001
- (5000 + 1)
The client acknowledges the server’s SYN by adding 1 to the server’s sequence number.
### How Synchronization Happens
- Each side shares its Initial Sequence Number.
- Each side confirms the other’s sequence number using acknowledgment.
- After both acknowledgments are verified, the connection enters the ESTABLISHED state.
This ensures both endpoints agree on starting sequence values before actual data transmission begins.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/tcp-3-way-handshake-process/)

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
> - [[TCP Congestion Control]]
> - [[TCP Connection Establishment]]
> - [[TCP Connection Termination]]
> - [[TCP flags]]
> - [[TCP Server-Client implementation in C]]
