---
title: "What is Pure ALOHA?"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/what-is-pure-aloha/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] What is Pure ALOHA?
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/what-is-pure-aloha/)

---

# What is Pure ALOHA?

Pure ALOHA is the original form of the ALOHA protocol. In this approach, A station transmits a frame whenever it has data to send. Since there is only one shared channel, there is always a risk of collisions between frames from different stations.
![Pure-ALOHA](assets/Pure-ALOHA-768-f88ef5bb36.webp)
Pure ALOHA
> **Note:** To ensure reliable communication, the receiver sends an acknowledgment (ACK) for each correctly received frame. If the sender does not receive an ACK within a time-out period, it assumes a collision has occurred and retransmits the frame.
## Key Mechanism
1. **Transmission:** A user sends a packet immediately when it is ready.
2. **Acknowledgment:** The receiver responds with an ACK if the frame is received correctly.
3. **Collision Handling:** If no ACK is received, the sender assumes a collision occurred.
4. **Random Back-off:** Before retransmitting, the sender waits for a random back-off time to reduce the chance of repeated collisions.
## Features of Pure ALOHA
- **Random Access:** Devices can send data anytime without waiting for a time slot.
- **Uncoordinated Transmission:** No central authority or coordination mechanism exists.
- **Simplicity:** Easy to implement and suitable for low-traffic systems.
- **Persistent Retransmission:** Devices retransmit after a random delay if a collision occurs.
- **Contention-Based:** Collisions are inherent and resolved using acknowledgment and retransmission.
## Vulnerable Time in Pure ALOHA
Collisions in Pure ALOHA occur if packets overlap at any point.
- Let each packet take 1 time unit (tp) to transmit.
- If a user starts sending a packet at time `t0`,
- Any packet generated in the interval (t0, t0 + tp) will collide with the beginning of the original packet.
- Any packet generated in (t0 + tp, t0 + 2tp) will collide with the end of the original packet.
> **Note:** The vulnerable period for a packet in Pure ALOHA is
>
>
$$
2 × t_p
$$
>
> . If another transmission starts within this period, both packets will be destroyed.
## Throughput Analysis of Pure ALOHA
The efficiency of Pure ALOHA can be calculated using probability.
**Throughput (S):**
$$
S = G \times e^{-2G}
$$
**where:**
-
$$
\text{S = }
$$
  throughput (successful transmissions per packet time).
-
$$
\text{G = }
$$
  average number of packets generated per packet time.
**Maximum Throughput:** Throughput is maximized when
$$
\text{G = 0.5}
$$
,
$$
S_{\text{max}} = 0.5 \times e^{-1} \approx 0.184
$$
. This means that only
$$
18.4\%
$$
 of the channel capacity is effectively used for successful transmission, while the rest is wasted due to collisions.
## Advantages
- Simple to design and implement.
- Suitable for low-traffic scenarios.
- Works well in environments with unpredictable transmission times.
## Disadvantages
- Very low efficiency (maximum
$$
18.4\%
$$
  ).
- High probability of collisions under heavy traffic.
- Unsuitable for real-time applications requiring guaranteed delivery.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/what-is-pure-aloha/)

## GATE CS

- Subject: Computer Networks
- Topic: Data Link Layer

> [!note] Related notes
>
> - [[Back-off Algorithm for CSMA CD]]
> - [[Bit Stuffing]]
> - [[Carrier sense multiple access]]
> - [[Collision Avoidance in wireless networks]]
> - [[Collision Detection in CSMA CD]]
> - [[Computer Networks Error Detection]]
> - [[Controlled Access Protocols]]
> - [[Difference between Byte stuffing and Bit stuffing]]
> - [[Efficiency of CSMA CD]]
> - [[Efficiency of Token Ring]]
