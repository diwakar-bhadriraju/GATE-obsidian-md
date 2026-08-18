---
title: "TCP Congestion Control"
subject: "Computer Networks"
topic: "Transport Layer"
source: "https://www.geeksforgeeks.org/computer-networks/tcp-congestion-control/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Transport Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/transport-layer
---


> [!abstract] TCP Congestion Control
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Transport Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/tcp-congestion-control/)

---

# TCP Congestion Control

TCP congestion control manages data flow to prevent network overload. It uses a congestion window and policies to adjust transmission rates. While the receiver sets a window size, the network also influences it by signaling the sender to slow down if it cannot handle the data rate.
## Congestion Policy in TCP
- **Slow Start Phase:**  Starts slow increment is exponential to the threshold.
- **Congestion Avoidance Phase:**  After reaching the threshold increment is by 1.
- **Congestion Detection Phase:**  The sender goes back to the Slow start phase or the Congestion avoidance phase.
### 1. Slow Start Phase
TCP increases its congestion window exponentially to quickly probe the network capacity at the beginning of a connection.
**Exponential Increment**: In this phase after every [RTT](https://www.geeksforgeeks.org/computer-networks/what-is-rttround-trip-time/) the congestion window size increments exponentially. 
**Example:** If the initial congestion window size is 1 segment, and the first segment is successfully acknowledged, the congestion window size becomes 2 segments. If the next transmission is also acknowledged, the congestion window size doubles to 4 segments. This exponential growth continues as long as all segments are successfully acknowledged.
> Initially cwnd = 1
> After 1 RTT, cwnd = 2^(1) = 2
> 2 RTT, cwnd = 2^(2) = 4
> 3 RTT, cwnd = 2^(3) = 8
### 2. Congestion Avoidance Phase
TCP increases its congestion window linearly to prevent network congestion after the slow start.
**Additive Increment:** This phase starts after the threshold value also denoted as ssthresh. The size of CWND (Congestion Window) increases additive. After each RTT cwnd = cwnd + 1.
**For example:** if the congestion window size is 20 [segments](https://www.geeksforgeeks.org/computer-networks/difference-between-segments-packets-and-frames/) and all 20 segments are successfully acknowledged within an RTT, the congestion window size would be increased to 21 segments in the next RTT. If all 21 segments are again successfully acknowledged, the congestion window size will be increased to 22 segments, and so on.
> Initially cwnd = i
> After 1 RTT, cwnd = i+1
> 2 RTT, cwnd = i+2
> 3 RTT, cwnd = i+3
### 3. Congestion Detection Phase
TCP detects network congestion through packet loss or duplicate ACKs and triggers window reduction to control traffic
**Multiplicative Decrement:** If congestion occurs, TCP reduces the congestion window. The sender detects congestion when a packet needs retransmission, either due to an RTO timeout or receiving three duplicate ACKs.
**Case 1:** Retransmission due to Timeout – In this case, the congestion possibility is high.
> (a) ssthresh is reduced to half of the current window size.
> (b) set cwnd = 1
> (c) start with the slow start phase again.
**Case 2:** Retransmission due to 3 Acknowledgement Duplicates – The congestion possibility is less.
> (a) ssthresh value reduces to half of the current window size.
> (b) set cwnd= ssthresh
> (c) start with congestion avoidance phase
**Example:** A TCP connection starts in slow start. By the 5th round, the congestion window reaches the ssthresh (32) and switches to congestion avoidance until the 10th round. At round 10, 3 duplicate ACKs trigger additive increase. At round 16, a timeout occurs, reducing the window. The task is to plot transmission rounds (time) vs congestion window size.
![Congestion Detection Phase in TCP](assets/Imagereedit-a64afa0a61.jpg)
Congestion Detection Phase
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/tcp-congestion-control/)

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
> - [[TCP Connection Establishment]]
> - [[TCP Connection Termination]]
> - [[TCP flags]]
> - [[TCP Server-Client implementation in C]]
