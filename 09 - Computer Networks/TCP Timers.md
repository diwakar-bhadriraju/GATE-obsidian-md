---
title: "TCP Timers"
subject: "Computer Networks"
topic: "Transport Layer"
source: "https://www.geeksforgeeks.org/computer-networks/tcp-timers/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Transport Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/transport-layer
---


> [!abstract] TCP Timers
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Transport Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/tcp-timers/)

---

# TCP Timers

TCP uses several timers to ensure that excessive delays are not encountered during communications. Several of these timers are elegant, handling problems that are not immediately obvious at first analysis. Each of the timers used by TCP is examined in the following sections, which reveal its role in ensuring data is properly sent from one connection to another. 
**TCP implementation uses four timers -** 
- **Retransmission Timer -** To retransmit lost segments, TCP uses retransmission timeout (RTO). When TCP sends a segment the timer starts and stops when the acknowledgment is received. If the timer expires timeout occurs and the segment is retransmitted. RTO (retransmission timeout is for 1 RTT) to calculate retransmission timeout we first need to calculate the RTT(round trip time).
   **RTT three types -**
  - **Measured RTT(RTTm) -** The measured round-trip time for a segment is the time required for the segment to reach the destination and be acknowledged, although the acknowledgement may include other segments.
  - **Smoothed RTT(RTTs) -** It is the weighted average of RTTm. RTTm is likely to change and its fluctuation is so high that a single measurement cannot be used to calculate RTO.
```
Initially -> No valueAfter the first measurement -> RTTs=RTTmAfter each measurement -> RTTs= (1-t)*RTTs + t*RTTmNote: t=1/8 (default if not given)
```
- **Deviated RTT(RTTd) -** Most implementations do not use RTTs alone so RTT deviated is also calculated to find out RTO.
```
Initially -> No valueAfter the first measurement -> RTTd=RTTm/2After each measurement -> RTTd= (1-k)*RTTd + k*(RTTm-RTTs)Note: k=1/4 (default if not given)
```
- **Persistent Timer -** To deal with a zero-window-size deadlock situation, TCP uses a persistence timer. When the sending TCP receives an acknowledgment with a window size of zero, it starts a persistence timer. When the persistence timer goes off, the sending TCP sends a special segment called a probe. This segment contains only 1 byte of new data. It has a sequence number, but its sequence number is never acknowledged; it is even ignored in calculating the sequence number for the rest of the data. The probe causes the receiving TCP to resend the acknowledgment which was lost.
- **Keep Alive Timer -** A keepalive timer is used to prevent a long idle connection between two TCPs. If a client opens a TCP connection to a server transfers some data and becomes silent the client will crash. In this case, the connection remains open forever. So a keepalive timer is used. Each time the server hears from a client, it resets this timer. The time-out is usually 2 hours. If the server does not hear from the client after 2 hours, it sends a probe segment. If there is no response after 10 probes, each of which is 75 s apart, it assumes that the client is down and terminates the connection.
- **Time Wait Timer -** This timer is used during [tcp connection termination](https://www.geeksforgeeks.org/computer-networks/tcp-connection-termination/). The timer starts after sending the last Ack for 2nd FIN and closing the connection.
  **After a TCP connection is closed, it is possible for datagrams that are still making their way through the network to attempt to access the closed port. The quiet timer is intended to prevent the just-closed port from reopening again quickly and receiving these last datagrams.**
  The **quiet timer** is usually set to twice the maximum segment lifetime (the same value as the Time-To-Live field in an IP header), ensuring that all segments still heading for the port have been discarded.
**Note: TCP Timers** play a crucial role in managing the transmission of data packets, ensuring efficiency and reliability in communication.
**Reference -**
[TCP Timers - Que10](https://www.ques10.com/p/9848/explain-tcp-timers-or-list-and-explain-purpose-o-1/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/tcp-timers/)

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
