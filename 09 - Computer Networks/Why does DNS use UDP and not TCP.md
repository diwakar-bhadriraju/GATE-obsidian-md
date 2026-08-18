---
title: "Why does DNS use UDP and not TCP?"
subject: "Computer Networks"
topic: "Application Layer"
source: "https://www.geeksforgeeks.org/computer-networks/why-does-dns-use-udp-and-not-tcp/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Application Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/application-layer
---


> [!abstract] Why does DNS use UDP and not TCP?
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Application Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/why-does-dns-use-udp-and-not-tcp/)

---

# Why does DNS use UDP and not TCP?

DNS is an application layer protocol. All application layer protocols use one of the two transport layer protocols, UDP and TCP. TCP is reliable and UDP is not reliable. DNS is supposed to be reliable, but it uses UDP, why? 
There are the following interesting facts about TCP and UDP on the transport layer that justify the above. 
**1)** UDP is much faster. TCP is slow as it requires a 3-way handshake. The load on DNS servers is also an important factor. DNS servers (since they use UDP) don't have to keep connections. 
**2)** DNS requests are generally very small and fit well within UDP segments. 
**3)** UDP is not reliable, but reliability can be added to the application layer. An application can use UDP and can be reliable by using a timeout and resend at the application layer. 
Actually, DNS primarily uses the User Datagram Protocol (UDP) on port number 53 to serve requests. DNS queries consist of a single UDP request from the client followed by a single UDP reply from the server. When the length of the answer exceeds 512 bytes and both client and server support EDNS, larger UDP packets are used. Otherwise, the query is sent again using the Transmission Control Protocol (TCP). TCP is also used for tasks such as zone transfers. Some resolver implementations use TCP for all queries.
Another reason DNS uses UDP is because it is a connectionless protocol, meaning that it does not establish a dedicated end-to-end connection before sending data. This makes it more suitable for DNS queries, which are often short and require quick responses. In contrast, TCP is a connection-oriented protocol, meaning it requires a more complex process to establish a connection before data can be transmitted.
Additionally, because DNS is a widely used protocol, there is a significant amount of traffic that needs to be handled by DNS servers. UDP is more scalable and efficient than TCP for handling large amounts of traffic, as it does not require the overhead of connection management.
https://en.wikipedia.org/wiki/Domain\_Name\_System#DNS\_protocol\_transport
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/why-does-dns-use-udp-and-not-tcp/)

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
> - [[HTTP Non-Persistent & Persistent Connection]]
> - [[LiFi vs WiFi]]
