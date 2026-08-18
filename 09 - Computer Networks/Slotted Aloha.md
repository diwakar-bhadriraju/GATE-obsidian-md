---
title: "What is Slotted ALOHA?"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/what-is-slotted-aloha/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] What is Slotted ALOHA?
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/what-is-slotted-aloha/)

---

# What is Slotted ALOHA?

Slotted ALOHA is an improved version of the Pure ALOHA protocol that was introduced to increase network efficiency and reduce collisions. The main idea behind Slotted ALOHA is to divide the channel into fixed-length time slots, where each station is allowed to transmit only at the beginning of a time slot.
![Throughput-Slotted-ALOHA](assets/What-is-Slotted-ALOHA-660-f6a689853c.png)
Slotted Aloha
> **Note:** This synchronization reduces the vulnerable period and improves the probability of successful transmissions.
## How Slotted ALOHA Works
1. **Time Slots:** The channel is divided into equal time slots, each equal to one frame transmission time.
2. **Synchronization:** All nodes are synchronized to these slots. A node that wants to transmit must wait for the beginning of the next time slot.
3. **Transmission:** The node sends its frame at the start of the time slot.
4. **Acknowledgment:** If the frame is received correctly, the receiver sends an acknowledgment (ACK).
5. **Collision Handling:** If multiple nodes transmit in the same slot, a collision occurs and all the frames are destroyed.
6. **Retransmission:** After a collision, nodes wait for a random back-off period before retransmitting to avoid repeated collisions.
![Slotted-ALOHA](assets/Slotted-ALOHA-768-b2ca25ab83.webp)
Working of Slotted ALOHA
## Applications of Slotted ALOHA
While rarely used in modern large-scale networks, Slotted ALOHA is still applied in:
- Satellite communication systems
- Wireless sensor networks
- RFID tag communication systems
- As a foundation for CSMA (Carrier Sense Multiple Access) protocols in Ethernet and Wi-Fi.
## Throughput of Slotted ALOHA
Throughput (S) is the rate of successful transmissions per slot and is given by:
>
$$
S = G \times e^{-G}
$$
**Where:**
-
$$
\text{S = }
$$
  throughput
-
$$
\text{G = }
$$
  offered load (average number of packet transmissions per slot)
- The maximum throughput occurs at
$$
\text{ G = 1}
$$
  :
$$
S_{max} = \frac{1}{e} \approx 0.368 \ (36.8\%)
$$
, This is twice as efficient as Pure ALOHA
$$
(18.4\%)
$$
.
## Assumptions of Slotted ALOHA
- All frames are of equal size.
- Time is divided into slots equal to one frame time.
- Nodes transmit only at the beginning of slots.
- All nodes are synchronized to the slot boundaries.
- Collisions can be detected within the slot duration.
## Advantages of Slotted ALOHA
- **Higher Efficiency:** Maximum throughput of 36.8%, double that of Pure ALOHA.
- **Simple Implementation**: Easy to design for systems with moderate traffic.
- **Better Collision Control:** Synchronization reduces collision probability.
- **Low Overhead:** Does not require heavy coordination or complex mechanisms.
## Disadvantages of Slotted ALOHA
- **Synchronization Overhead:** Requires clock synchronization among nodes.
- **Collisions Still Occur:** If two or more devices transmit in the same slot, collisions cannot be avoided.
- **Low Throughput Compared to Modern Protocols:** Even at best, efficiency is only
$$
36.8\%
$$
  .
- **Increased Delay:** Nodes must wait until the next slot to transmit, causing extra delay compared to Pure ALOHA.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/what-is-slotted-aloha/)

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
