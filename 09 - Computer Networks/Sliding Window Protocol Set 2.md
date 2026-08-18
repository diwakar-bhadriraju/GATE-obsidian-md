---
title: "Go Back N - Sliding Window Protocol"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-2-receiver-side/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Go Back N - Sliding Window Protocol
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-2-receiver-side/)

---

# Go Back N - Sliding Window Protocol

Go-Back-N (GBN) is a sliding window–based Automatic Repeat Request (ARQ) protocol, in which the sender can transmit multiple frames (up to a fixed window size) without waiting for an acknowledgement for each frame.
- If a frame is lost or corrupted, the receiver discards that frame.
- All subsequent out-of-order frames are also discarded.
- The sender retransmits the erroneous frame and all following frames in the current window.
- Example: If frames 1 to 5 are sent and frame 3 is lost, the sender retransmits frames 3, 4, and 5.
## Characteristics of Go-Back-N (GBN)
### **Sender Window Size (W**s**)**
In Go-Back-N, the sender window size (Ws) is equal to N.
 For example, in GBN-10, the sender can transmit 10 frames without waiting for acknowledgements.
The value of N must be greater than 1 to enable pipelining.
 When N = 1, Go-Back-N behaves like the Stop-and-Wait ARQ protocol.
> When processing delay, queuing delay, and ACK transmission delay are ignored, the efficiency of GBN is = N / (1+2a)
where,
- a=Tp / Tt​​
- Tp​ = Propagation delay
- Tt​ = Transmission delay of data frame
- N = Sender window size
### **Efficiency with Non-Zero Delays**
When processing delay, queuing delay, and acknowledgment transmission delay are not zero, efficiency is calculated using:
> Efficiency = N \* (Useful time) / (Total Time)
where, useful time=Tt
> Total time = Tt + 2 \* Tp + Pr + Pq + Tt(ack)
where,
- Tt =Transmission delay of sender side
- Tp = Propagation Delay
- Pr = Processing Delay
- Pq = Queuing Delay
- Tt(ack) = Transmission Delay of Acknowledgement
So, the general efficiency expression becomes:
>
$$
Efficiency=Tt​+2Tp​+Pr​+Pq​+Tt​(ack)NTt​​
$$
If B is the channel bandwidth, then
> Throughput = Efficiency × B
For the ideal case (no extra delays):
> Throughput = (N / 1 + 2a) \* B
### **2. Receiver Window Size (W**R**)**
- Receiver window size (WR) is always 1.
- Receiver accepts only the next expected frame.
- Frames arriving out of order are discarded.
- Receiver does not buffer out-of-order frames.
### **3. Acknowledgements**
Acknowledgments are control messages sent by the receiver to confirm the successful reception of data frames. They play a crucial role in ensuring reliable communication. If the sender does not receive an acknowledgment within a specified timeout interval, it assumes the frame was lost or corrupted and retransmits it.
### **Types of ACKs**
**Cumulative ACK**
- A single ACK confirms the receipt of all frames up to a particular sequence number.
- Used in Go-Back-N (GBN).
- Reduces acknowledgment traffic, improving efficiency.
- If an ACK is lost, multiple frames may be considered unacknowledged, causing unnecessary retransmissions.
**Independent ACK**
- Each frame is acknowledged separately.
- Used in Selective Repeat ARQ.
- Provides higher reliability by avoiding retransmission of correctly received frames.
- Increases control overhead due to a higher number of ACKs.
## Working of GB-N Protocol
**Sender Side**
- The sender maintains a sliding window of size N (e.g., in GBN-4, the window size is 4).
- It can transmit up to N frames without waiting for individual ACKs.
- Each transmitted frame is associated with a timer.
- When an ACK is received, the sender slides the window forward, allowing transmission of new frames.
- If a timeout occurs for a frame, the sender retransmits that frame and all subsequent frames in the current window.
**Receiver Side**
- The receiver maintains a window size of 1 (WR = 1).
- It accepts only the next expected frame in sequence.
- If the expected frame is received correctly, then the receiver sends an ACK, and updates the expected sequence number.
- If an out-of-order frame is received, then the receiver discards the frame, and resends the ACK for the last correctly received frame.
![Sliding_SET_2-1](assets/Sliding_SET_2-1-1afd5cb8df.jpg)
## **Relationship Between Window Size and Sequence Numbers**
In sliding window protocols such as Go-Back-N (GBN) and Selective Repeat (SR), the window size and sequence number space are tightly coupled to ensure correct and reliable data delivery.
- The window size defines how many frames the sender can transmit without waiting for acknowledgments, enabling pipelined transmission.
- Sequence numbers are assigned to frames to maintain ordering and to help the receiver identify missing or duplicate frames.
To avoid ambiguity caused by sequence number reuse, the combined size of the sender and receiver windows must not exceed the available sequence number space. If the window size is too large, a sequence number may be reused before the earlier frame with the same number is acknowledged, making it difficult for the receiver to distinguish new frames from duplicates.
Relation between window size and sequence number is given by the formula:
> Ws + WR <= ASN
where,
Ws = Sender window size
WR = Receiver window size
ASN = Available sequence number
In Go-Back-N (GBN), the receiver window size is always **1**:
> Ws + 1 <= ASN
If the sender window size is N, then:
Minimum sequence numbers required = N + 1
Hence, the number of bits required for sequence numbering in GBN is:
> Bits Required in GBN = ⌈ log2 (N + 1)⌉
The extra +1 ensures that duplicate frames are correctly identified and prevents confusion caused by premature sequence number reuse.
## **Example of** GB-N Protocol
Consider an Example of GB4.
- Sender window size is 4 therefore we require a minimum of 4 sequence numbers to label each packet in the window.
- Now suppose receiver has received all the packets(0, 1, 2 and 3 sent by sender) and hence is now waiting for packet number 0 again (We can not use 4 here as we have only 4 sequence numbers available since N = 4).
- Now suppose the cumulative ack for the above 4 packets is lost in the network.
- On sender side, there will be timeout for packet 0 and hence all the 4 packets will be transmitted again.
- Problem now is receiver is waiting for new set of packets which should have started from 0 but now it will receive the duplicate copies of the previously accepted packets.
- In order to avoid this, we need one extra sequence number.
- Now the receiver could easily reject all the duplicate packets which were starting from 0 because now it will be waiting for packet number 4 (We have added an extra sequence number now).
This is explained with the help of the illustrations below. Trying with Sequence numbers 4.
![Sliding_SET_2-3](assets/Sliding_SET_2-3-1d5cfa795e.jpg)
Now, trying with one extra sequence number.
![Sliding_SET_2-4](assets/Sliding_SET_2-4-beab659f9f.jpg)
Now it is clear as to why we need an extra 1 bit in the GBN protocol.
Go-Back-N is easy to implement and ensures reliable data transfer. By supporting pipelined transmission, it achieves higher throughput than Stop-and-Wait, particularly in low-error and high-delay networks.
In error-prone networks, GBN is inefficient because a single lost frame triggers retransmission of multiple frames. This causes unnecessary retransmissions and leads to poor bandwidth utilization.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-2-receiver-side/)

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
