---
title: "TCP Connection Termination"
subject: "Computer Networks"
topic: "Transport Layer"
source: "https://www.geeksforgeeks.org/computer-networks/tcp-connection-termination/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Transport Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/transport-layer
---


> [!abstract] TCP Connection Termination
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Transport Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/tcp-connection-termination/)

---

# TCP Connection Termination

TCP connection termination is the process of closing an established TCP connection between two devices in an orderly way. It uses a four-step handshake (FIN-ACK exchange) to ensure that both sides have finished sending and receiving all data before the connection is fully closed.
## Types of TCP Connection Release
TCP supports two types of connection releases like most connection-oriented transport protocols: 
1. **Abrupt connection release:** In an Abrupt connection release, either one TCP entity is forced to close the connection or one user closes both directions of data transfer.
2. **Graceful connection release:** In the Graceful connection release, the connection is open until both parties have closed their sides of the connection.
### 1. Abrupt connection release
An abrupt connection release is carried out when an RST segment is sent. An RST segment can be sent for the below reasons: 
1. When a non-SYN segment was received for a non-existing TCP connection.
2. In an open connection, some TCP implementations send an RST segment when a segment with an invalid header is received. This will prevent attacks by closing the corresponding connection.
3. When some implementations need to close an existing TCP connection, they send an RST segment. They will close an existing TCP connection for the following reasons:
- Lack of resources to support the connection
- The remote host is now unreachable and has stopped responding.
> **Note:** When a TCP entity sends an RST segment, it should contain 00 if it does not belong to any existing connection else it should contain the current value of the sequence number for the connection and the acknowledgment number should be set to the next expected in sequence number on this connection. 
### 2. Graceful Connection Release
The common way of terminating a TCP connection is by using the TCP header’s FIN flag. This mechanism allows each host to release its own side of the connection individually. 
![initiator](assets/initiator-3a1cb9d35a.webp)
**How mechanism works In TCP :**
- **Step 1 (FIN from Client):** The client sends a FIN to the server to start closing and enters the FIN\_WAIT\_1 state.
- **Step 2 (ACK from Server):** The server acknowledges the FIN and the client moves to FIN\_WAIT\_2.
- **Step 3 (Client Waiting):** The client waits for the server’s FIN while in the FIN\_WAIT\_2 state.
- **Step 4 (FIN from Server):** The server sends its FIN after completing its closing tasks.
- **Step 5 (ACK from Client):** The client acknowledges the server’s FIN, enters TIME\_WAIT, and after a set delay, the connection closes fully.
## **TCP States Visited**
TCP connections follow a state machine on both the client and server sides. These states represent the progress of a connection from establishment to termination. The following explains the states visited during a normal TCP connection teardown when the client initiates the closure.
### 1. TCP states visited by Client Side
The accompanying figures illustrate the state transitions for both the client and server, assuming that the client initiates the connection teardown. These state-transition diagrams focus on the normal process of connection establishment and termination in TCP. They do not cover exceptional or simultaneous close scenarios, which involve more complex state interactions.
![tcp_states_visited_by_a_client_tcp_2](assets/tcp_states_visited_by_a_client_tcp_2-9f9a9a0cca.webp)
### **2. T**CP states visited by Server Side
When closing a TCP connection, the server first enters CLOSE\_WAIT upon receiving the client’s FIN and acknowledges it, then sends its own FIN and moves to LAST\_ACK, waiting for the client’s final acknowledgment before fully closing the connection. This ensures an orderly and graceful termination.
![tcp_states_visited_by_a_client_tcp](assets/tcp_states_visited_by_a_client_tcp-dcc6a9fd27.webp)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/tcp-connection-termination/)

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
> - [[TCP flags]]
> - [[TCP Server-Client implementation in C]]
