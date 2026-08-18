---
title: "Controlled Access Protocols in Computer Network"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/controlled-access-protocols-in-computer-network/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Controlled Access Protocols in Computer Network
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/controlled-access-protocols-in-computer-network/)

---

# Controlled Access Protocols in Computer Network

In computer networks, Controlled Access Protocols (CAPs) manage how multiple devices share a common communication medium. These protocols control the right to transmit in such a way that collisions are avoided, efficiency is maintained, and fair access is ensured.
> **Note:** Unlike random access methods (e.g., ALOHA, CSMA), in controlled access, stations do not transmit at will. Instead, they follow a systematic method to determine which station has the right to send at a given time.
## What is Controlled Access?
In Controlled Access, before transmitting data, a station must first obtain permission to access the channel. At any given time, only one node can send data, preventing collisions. This coordination is achieved using one of three methods:
- Reservation
- Polling
- Token Passing
## Reservation
In this method, stations reserve slots in advance before transmission. The timeline has two parts:
- Reservation Interval (fixed length): divided into slots, one per station.
- Data Transmission Period (variable length): reserved stations send data in order.
![protocol_3](assets/protocol_3-7ef5de9eed.webp)
Reservation
> **Example: I**f there are M stations, the reservation interval is divided into M slots. Each station signals intent by inserting a bit into its slot. Then, only the reserved stations transmit in the data phase.
### Advantages
- Predictable access time and throughput.
- Priorities can be set for faster access.
- Supports QoS (Quality of Service) for applications like real-time audio/video.
- Efficient bandwidth utilization.
### Disadvantages
- Performance decreases under light loads (wasted slots).
- High dependency on controlled synchronization.
## Polling
Here, a controller (primary station) polls each node (secondary station) in sequence, granting permission to send. The controller sends a message with the address of a station. The addressed station responds:
- Sends data (if available)
![protocol_2](assets/protocol_2-5893cd1200.webp)
Polling
- Sends a NAK (poll reject) if no data is pending.
![protocol_1](assets/protocol_1-e9234f4122.webp)
Polling
###
 Advantages
- Predictable access times and bandwidth.
- High efficiency, since no slot is wasted.
- Priorities can be assigned.
### Disadvantages
- Extra overhead due to polling messages.
- High dependence on controller reliability.
- Turnaround time increases under light loads.
### Efficiency formula
$$
\eta = \frac{T_t}{T_t + T_{poll}}
$$
**where:**
-
$$
T_t =
$$
  data transmission time
-
$$
T_{poll} =
$$
  polling overhead time
## Token Passing
In Token Passing, stations are logically connected (ring or bus). A special frame called a token circulates among stations:
- The token represents permission to transmit.
- A station can send data only when it holds the token.
- If no data is ready, the token is simply passed on.
### protocol_4 Token Passing Common Implementations
- **Token Ring** – token passed in a ring topology.
- **Token Bus** – stations use a bus medium but pass the token in a predefined logical order.
### Advantages
- Excellent performance under high loads.
- Built-in error recovery and debugging features.
- Predictable throughput.
### Disadvantages
- Expensive setup and hardware.
- Token management issues (lost/duplicate tokens, station failures).
- Complex implementation.
### Performance Parameters
- Delay: Average delay
$$
= a/N
$$
  , where
$$
a = T_p/T_t
$$
  .
- Throughput:
> 1. For a<1a < 1a<1:
>
>
$$
S = \frac{1}{1 + a/N}
$$
>
>
> 2. For a>1a > 1a>1:
>
>
$$
S = \frac{1}{a(1 + 1/N)}
$$
**where:**
-
$$
N =
$$
  number of stations
-
$$
T_p =
$$
   propagation delay
-
$$
T_t =
$$
  transmission delay
## Comparison of Controlled Access Methods
| Feature | Reservation | Polling | Token Passing |
| --- | --- | --- | --- |
| Access Control | Slot-based reservation | Central controller polls | Token circulation |
| Efficiency | High (under heavy load) | Moderate (polling overhead) | High (predictable) |
| Collision Chance | None | None | None |
| Overhead | Reservation slots | Polling messages | Token management |
| Best For | Real-time multimedia | Small/medium networks | Large/high-load networks |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/controlled-access-protocols-in-computer-network/)

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
> - [[Difference between Byte stuffing and Bit stuffing]]
> - [[Efficiency of CSMA CD]]
> - [[Efficiency of Token Ring]]
