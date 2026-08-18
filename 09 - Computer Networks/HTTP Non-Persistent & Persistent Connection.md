---
title: "HTTP Non-Persistent & Persistent Connection | Set 1"
subject: "Computer Networks"
topic: "Application Layer"
source: "https://www.geeksforgeeks.org/computer-networks/http-non-persistent-persistent-connection/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Application Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/application-layer
---


> [!abstract] HTTP Non-Persistent & Persistent Connection | Set 1
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Application Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/http-non-persistent-persistent-connection/)

---

# HTTP Non-Persistent & Persistent Connection | Set 1

The Hypertext Transfer Protocol (HTTP) is an application-level protocol that uses TCP as an underlying transport and typically runs on port 80. HTTP is a stateless protocol i.e. server maintains no information about past client requests.
## **HTTP Connections**
1. Non-Persistent
2. Persistent
## Basic Pre-Requisite
The terminology which we must know before going deep into Persistent & Non-Persistent Connections is
1. [RTT(Round Trip Time)](https://www.geeksforgeeks.org/computer-networks/what-is-rttround-trip-time/)
2. [TCP 3-Way Handshake](https://www.geeksforgeeks.org/computer-networks/tcp-3-way-handshake-process/)
**1. RTT:** Time for a small packet to travel from client to server and back.
```
RTT = 2 X propagation time
```
1. For a connection Persistent or Non-persistent it is sure that to initiate a [TCP connection](https://www.geeksforgeeks.org/computer-networks/tcp-connection-establishment/) one RTT is used.
2. One RTT is used for the HTTP request and the first few bytes to the HTTP response to return. So to know the total file transmission time.
```
Total = 2RTT + transmit time
```
**2. TCP 3-Way Handshake:** TCP Connection establishes in 3 ways, that's why it is called a 3-way Handshake.
- Requesting the server for the connection.
- The server responds to whether the connection can be established or not.
- Acknowledgment by the client on the response sent by the server.
## **Difference between Persistent and Non-Persistent Connections**
| **Persistent HTTP** | **Non-Persistent HTTP** |
| --- | --- |
| The server leaves the connection open after sending a response. | Requires 2 RTTs per object. |
| Subsequent HTTP messages between the same client/server are sent over an open connection. | OS overhead for each TCP connection |
| The client sends requests as soon as it encounters a referenced object. | Browsers often open parallel TCP connections to fetch referenced objects. |
| As little as one RTT for all the referenced objects. | Here, at most one object can be sent over one TCP Connection. |
## **Non-Persistent Connection**
Non-Persistent Connections are those connections in which for each object we have to create a new connection for sending that object from source to destination. Here, we can send a maximum of one object from one [TCP](https://www.geeksforgeeks.org/computer-networks/what-is-transmission-control-protocol-tcp/) connection.
There are two types:
**1. Non-Persistent-Without parallel connection:** Each objection takes two RTTs (assuming no window limit) one for TCP connection and the other for HTTP image/text file.
**2. Non-Persistent-With parallel connection:** Non-Persistent with a parallel connection requires extra overhead in transferring data.
![Non-Persistent & Parallel Connection](assets/Non-Persistent---Parallel-Connections-76f188f23b.png)
Non-Persistent & Parallel Connection
### Advantages of Non-Persistent Connection
1. Wastage of Resources is very less because the connection opens only when there is some data to be sent.
2. Non-Persistent Connection is more secure because after sending the data, the connection gets terminated and nothing can be shared thereafter.
### Disadvantages of Non-Persistent Connection
1. In Non-Persistent Connection, it requires a greater CPU overhead for the transmission of data
## Persistent Connection
**1. Non-Pipelined Persistent Connection:** In a Non-pipeline connection, we first establish a connection that takes two RTTs then we send all the object's images/text files which take 1 RTT each (TCP for each object is not required).
**2. Pipelined Persistent Connection:** In Pipelined connection, 2RTT is for connection establishment and then 1RTT(assuming no window limit) for all the objects i.e. images/text.
![Persistent Without Pipelining and with Pipelining](assets/Persistent---Pipelined-Non-Pipelined-Con-69fd9eb417.jpg)
Persistent Without Pipelining and with Pipelining
### **Advantages of Persistent Connections**
- Lower CPU and memory usage because there is less number of connections.
- Allows HTTP pipelining of requests and responses.
- Reduced network congestion (fewer TCP connections).
- Reduced latency in subsequent requests (no handshaking).
- Errors can be reported without the penalty of closing the TCP connection.
### **Disadvantages of Persistent Connections**
- Resources may be kept occupied even when not needed and may not be available to others.
- Most modern browsers like Chrome, Firefox, and Internet Explorer use persistent connections.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/http-non-persistent-persistent-connection/)

## GATE CS

- Subject: Computer Networks
- Topic: Application Layer

> [!note] Related notes
>
> - [[Address Resolution in DNS]]
> - [[Basics of Wi-Fi]]
> - [[DHCP Relay Agent]]
> - [[DNS (Domain Name Server) NetWorking]]
> - [[DNS Spoofing or DNS Cache poisoning]]
> - [[Dynamic Host Configuration Protocol]]
> - [[File Transfer Protocol]]
> - [[How DHCP server dynamically assigns IP address to a host]]
> - [[LiFi vs WiFi]]
> - [[Multipurpose Internet mail extension]]
