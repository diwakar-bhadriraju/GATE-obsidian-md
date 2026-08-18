---
title: "Selective Repeat - Sliding Window Protocol"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-3-selective-repeat/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Selective Repeat - Sliding Window Protocol
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-3-selective-repeat/)

---

# Selective Repeat - Sliding Window Protocol

The Selective Repeat Protocol (SRP) is a reliable data transmission technique that enhances protocols like Go-Back-N by retransmitting only those packets that are lost or corrupted, rather than resending all subsequent packets after an error. This selective retransmission reduces unnecessary overhead and improves efficiency, especially on unreliable or noisy communication links.
- **Window Size:** The sender’s window (Ws) and the receiver’s window (Wr) are of equal size. This keeps transmission and reception synchronised.
- **Packet Handling:** The receiver can accept packets that arrive out of order. Correct packets are buffered until missing ones are retransmitted.
- **Retransmission Mechanism:** The sender retransmits only the packets that are not acknowledged. Retransmission occurs after a timeout or on receiving a Negative Acknowledgement (NAK).
- **Efficiency:** Selective retransmission reduces unnecessary packet resending. This improves bandwidth utilisation on unreliable links.
- **Efficiency Formula:** The efficiency of SRP is given by
> η = N / 1+2a
>
> ​where N is the window size and a=Tp/Tt
### Why Window Size is Important
Selective Repeat Protocol (SRP): the sender and receiver window size must be less than or equal to 2m-1, which is half of the available sequence number space. If the window size exceeds this limit, sequence numbers may wrap around before earlier packets are acknowledged. As a result, the receiver may be unable to distinguish between new packets and old retransmitted packets. This ambiguity can cause incorrect packet acceptance and lead to transmission errors.
![Selective-Repeat-Sliding-Window-Protocol](assets/Selective-Repeat-Sliding-Window-Protocol-b8c21f7e57.jpg)
Sender only retransmits frames, for which a NAK is received
The efficiency of the Selective Repeat Protocol (SRP) is the same as that of the Go-Back-N protocol. It is defined as the ratio of the data transmission time to the total time taken for successful transmission and acknowledgment. The efficiency is given by:
> η = Tt(data) / Tt(data) + 2Tp + Tq + Tpro + Tt(ack)
where,
- Tt(data) = transmission delay of the data packet.
- Tp = propagation delay.
- Tq = queuing delay.
- Tpro = processing delay.
- Tt(ack) = transmission delay of the acknowledgment packet.
### **Buffers and Sequence Numbers**
**Buffers Required:**
- In Selective Repeat Protocol, buffering is needed at both ends.
- The sender requires N buffers, and the receiver also requires N buffers. Hence, the total buffers required are 2N.
**Sequence Numbers:**
- To uniquely identify frames and avoid ambiguity, sequence numbers are required at both the sender and receiver.
- The total number of sequence numbers needed is 2N.
**Efficiency Relation:**
- The efficiency of Selective Repeat Protocol is the same as that of Go-Back-N.
   It is given by:
> η = N / 1+2a
>
> where, a = Tp/Tt
Tp is the propagation delay and Tt​ is the transmission delay.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-3-selective-repeat/)

## GATE CS

- Subject: Computer Networks
- Topic: Data Link Layer

> [!note] Related notes
>
> - [[Aloha]]
> - [[Back-off Algorithm for CSMA CD]]
> - [[Bit Stuffing]]
> - [[Carrier sense multiple access]]
> - [[Collision Avoidance in wireless networks]]
> - [[Collision Detection in CSMA CD]]
> - [[Computer Networks Error Detection]]
> - [[Controlled Access Protocols]]
> - [[Difference between Byte stuffing and Bit stuffing]]
> - [[Efficiency of CSMA CD]]
