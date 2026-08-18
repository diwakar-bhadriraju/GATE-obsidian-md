---
title: "Sliding Window Protocol"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-1/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Sliding Window Protocol
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-1/)

---

# Sliding Window Protocol

Sliding Window Protocol allows sending multiple packets before receiving acknowledgments.
- Using a "window" to manage packet flow, it improves network efficiency and throughput, especially over long-distance or high-latency connections.
- Sliding window protocols are used where reliable and ordered delivery of packets is needed, such as in the Data Link Layer and the Transmission Control Protocol in Transport Layer.
## Terminologies Related to Sliding Window Protocol
**1. Transmission Delay (Tt):** Time to transmit the packet from the host to the outgoing link. If B is the [Bandwidth](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-bandwidth-definition-working-importance-uses/) of the link and D is the Data Size to transmit
>
$$
T_t = \frac{\text{Data Size } (D)}{\text{Bandwidth } (B)}
$$
**2. Propagation Delay (Tp):** It is the time taken by the first bit transferred by the host onto the outgoing link to reach the destination. It depends on the distance d and the wave propagation speed s (depends on the characteristics of the medium).
>
$$
T_p = \frac{\text{Distance } (d)}{\text{Propagation Speed } (s)}
$$
**3. Efficiency:** It is defined as the ratio of total useful time to the total cycle time of a packet. For stop and wait protocol,
> Total time(TT) = Tt(data) + Tp(data) +
>  Tt(acknowledgement) + Tp(acknowledgement)
>  = Tt(data) + Tp(data) + Tp(acknowledgement)
>  = Tt + 2\*Tp
Since acknowledgements are very less in size, their transmission delay can be neglected.
>
$$
\text{Efficiency} = \frac{T_t}{T_t + 2 T_p} = \frac{1}{1 + 2a}, \quad a = \frac{T_p}{T_t}
$$
**4. Effective Bandwidth(EB) or Throughput** - Number of bits sent per second.
> EB = Data Size(D) / Total Cycle time(Tt + 2\*Tp)
> Multiplying and dividing by Bandwidth (B),
>  = (1/(1+2a)) \* B [ Using a = Tp/Tt ]
>  = Efficiency \* Bandwidth
**5. Capacity of link** - If a channel is [Full Duplex](https://www.geeksforgeeks.org/computer-networks/transmission-modes-computer-networks/), then bits can be transferred in both the directions and without any collisions. Number of bits a channel/Link can hold at maximum is its capacity.
> Capacity = Bandwidth(B) \* Propagation(Tp)
>
>  For Full Duplex channels,
>  Capacity = 2\*Bandwidth(B) \* Propagation(Tp)
## Concept of Pipelining
In [Stop and Wait protocol](https://www.geeksforgeeks.org/computer-networks/stop-and-wait-arq/), only 1 packet is transmitted at a time. After sending a packet, the sender must wait for an acknowledgement from the receiver before transmitting the next one.
The problem with this setup is low efficiency - the communication channel remains underutilized because only one packet is in transit, even though more packets could fit into the channel during the waiting time.
The total cycle time is:
$$
T_{\text{cycle}} = T_t + 2T_p
$$
Now, let’s calculate how many packets could ideally be transmitted during one cycle time:
- In Tt​ units → **1 packet** can be transmitted
- In 1 unit →
$$
\tfrac{1}{T_t}
$$
   packets can be transmitted
- In (Tt + 2Tp) units →
$$
\frac{T_t + 2T_p}{T_t} = 1 + \frac{2T_p}{T_t}
$$
If we use the notation
$$
a = \frac{T_p}{T_t}
$$
- Packets per cycle = 1+2a
![a](assets/a-a7ebffc2e2.webp)
Sliding Window
**Maximum packets that can be transmitted in a total cycle time:** After we have received the Ack for packet 0, window slides and the next packet can be assigned sequence number 0. We reuse the sequence numbers which we have acknowledged so that header size can be kept minimum as shown in the diagram given below.
![b](assets/b-b4eceae348.webp)
Sending Multilple Data Packets
**Maximum packets that can be transmitted in a total cycle time** = 1+2a
**Example:** Let Tt=1 ms (transmission time per packet) and Tp=1.5 ms (propagation time).
- After the sender transmits packet 0, it immediately sends packets 1, 2, and 3.
- The acknowledgment for packet 0 arrives after:
- 2(Tp) = 3 ms
In **Stop-and-Wait**, only 1 packet is transferred in:
- Tt​ + 2(Tp)​=4 ms
With Sliding Window, a window of packets is maintained packets that have been sent but not yet acknowledged—allowing multiple packets to be transmitted efficiently.
## Minimum Number of Bits For Sender Window
As we have seen above,
> Maximum window size = 1 + 2\*a where a = Tp/Tt
>  Minimum sequence numbers required = 1 + 2\*a.
Each packet in the current window is assigned a sequence number.
- **Sender window bits**: To represent the sender window, the number of bits required is:
$$
\text{Bits} = \lceil \log_2 (1 + 2a) \rceil
$$
- **Protocol header constraint**: Sometimes, the sequence number field in the header is fixed. If the field has **N bits**, we can have **2ⁿ sequence numbers**.
- **Window size**:
$$
\text{Window Size (ws)} = \min(1 + 2a, 2^N)
$$
- **Minimum bits to represent window**:
$$
\text{Bits} = \lceil \log_2 (ws) \rceil
$$
> This discussion covers sending windows only. Receiving windows, implemented using Go-Back-N or Selective Repeat for pipelining, will be discussed separately.
### Types of Sliding Window Protocol
There are two types of Sliding Window Protocol which include Go-Back-N ARQ and Selective Repeat ARQ:
1. **Go-Back-N ARQ:** Multiple frames can be sent before an acknowledgment is received. If a frame is lost or an acknowledgment is missing, all frames from that point onward are retransmitted.
2. **Selective Repeat ARQ:** Multiple frames are sent before acknowledgment, but only the lost or erroneous frames are retransmitted. The receiver can store out-of-order frames until the missing ones arrive.
### Related Articles:
> - [Go-Back-N ARQ](https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-2-receiver-side/)
> - [Selective Repeat ARQ](https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-3-selective-repeat/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-1/)

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
