---
title: "Stop and Wait ARQ"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/stop-and-wait-arq/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Stop and Wait ARQ
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/stop-and-wait-arq/)

---

# Stop and Wait ARQ

**Stop-and-Wait ARQ** is a reliable data link layer protocol in which the sender transmits one frame at a time and waits for an acknowledgment (ACK) before sending the next frame. If the ACK is not received within a specified timeout period, the same frame is retransmitted to ensure reliability.
- Operates in connection-oriented communication
- Provides error control using acknowledgments and retransmissions
- Ensures flow control by allowing only one outstanding frame
- Uses two sequence numbers (0 and 1) to prevent duplication
- Considered a special case of Sliding Window Protocol (window size = 1)
- Achieves one frame per RTT, resulting in low efficiency for large bandwidth–delay products
## Important Terms
- **Propagation Delay:** The time taken by a data packet to travel physically from the sender to the receiver over the communication medium.
> [Propagation Delay](https://www.geeksforgeeks.org/electronics-engineering/propagation-delay/) = (Distance between nodes) / (Propagation speed of Signal)
- **Roundtrip Time (RTT):**  The total time taken for a data frame to reach the receiver plus the time taken for the acknowledgment (ACK) to return to the sender.
- **Timeout (TO):** The maximum time the sender waits for an acknowledgment before retransmitting the frame. Timeout = Estimated RTT + Safety Margin
## 1. Simple Stop and Wait
#### At Sender
- **Rule 1:** The sender transmits only one data packet at a time.
- **Rule 2:** The sender sends the next packet only after receiving an acknowledgment (ACK) for the previously sent packet.
#### At Receiver
- **Rule 1:** The receiver sends an acknowledgment immediately after successfully receiving and processing a data packet.
- **Rule 2:** Acknowledgments are sent after each packet is consumed, ensuring proper [flow Control](https://www.geeksforgeeks.org/computer-networks/flow-control-in-data-link-layer/) flow control between sender and receiver.
![Stop and Wait](assets/Stop-and-Wait-ARQ-d38663c2df.png)
### **1. Lost Data**
If a sender transmits a frame and it gets lost in the network, the receiver does not receive it and therefore does not send an acknowledgment (ACK). However, the sender does **not wait forever**. It starts a **timer** after transmitting the frame. If the ACK is not received before the timeout expires, the sender retransmits the same frame.
### Lost Data**2. Lost Acknowledgement**
In this case, the sender sends a data packet which is successfully received by the receiver. The receiver sends an acknowledgment, but the ACK is lost in the network. As the sender does not receive the acknowledgment, it assumes the packet was not received and does not send the next packet, because Stop-and-Wait requires an ACK before proceeding.
![Lost Acknoeledgement](assets/Stop-and-Wait-ARQ-3-2eb1b4f382.png)
### **3. Delayed Acknowledgement/Data**
Here, the sender sends a data packet and the receiver sends an acknowledgment, but the ACK arrives after the sender’s timeout period. The sender may mistakenly interpret this delayed acknowledgment as the response to a later transmission, causing confusion and possible data duplication. This problem highlights the need for sequence numbers and timeouts in ARQ protocols.
## 2. Stop and Wait for ARQ (Automatic Repeat Request)
Stop-and-Wait ARQ (Automatic Repeat Request) overcomes the problems of lost data, lost acknowledgments, and delayed frames by using acknowledgments, sequence numbers, and timeouts. It provides both  [error control](https://www.geeksforgeeks.org/computer-networks/error-control-in-data-link-layer/) through retransmissions and flow control by allowing only one outstanding frame at a time, ensuring reliable data communication.
![Stop and Wait ARQ](assets/Stop-and-Wait-ARQ-4-e6f2910b58.png)
### **1. Time Out**
Timeout is the maximum time the sender waits for an acknowledgment (ACK) after sending a data frame. If the ACK is not received within this period, the sender assumes the frame or ACK was lost or corrupted and retransmits the same frame to ensure reliable communication.
![Time Out](assets/Stop-and-Wait-ARQ-5-57f1fa8851.png)
### **2. Sequence Number (Data)** -
In Stop-and-Wait ARQ, each data frame is assigned a sequence number by the sender. This helps the receiver uniquely identify each frame, detect duplicate frames, and send the correct acknowledgment. The sender transmits the next frame only after receiving the acknowledgment for the current frame, ensuring reliable data delivery.
![Sequence number for data](assets/Stop-and-Wait-ARQ-6-08e7a29b9b.png)
### **3. Sequence Number**
In Stop-and-Wait ARQ, acknowledgments (ACKs) also carry sequence numbers. After successfully receiving a data frame, the receiver sends an ACK indicating the sequence number of the next expected frame. The sender uses this information to confirm successful delivery and decide whether it can proceed with the next transmission or needs to retransmit a frame.
## Working of Stop and Wait for ARQ
- The sender A transmits a data frame with sequence number 0.
- After successfully receiving the frame, the receiver B sends an acknowledgment (ACK) with sequence number 1, indicating that it is expecting the next frame.
- The sender waits for this acknowledgment before sending the next data frame.
- Stop-and-Wait ARQ uses only a one-bit sequence number (0 and 1), which means only one frame can be in transit or buffered at any time at both the sender and receiver.
![Working Stop and Wait ARQ ](assets/Stop-and-Wait-ARQ-7-48716ceb0c.png)
## **Constraints in Stop and Wait ARQ**
- Stop-and-Wait ARQ has low efficiency because the sender must wait for an acknowledgment before transmitting the next packet.
- This waiting time causes poor channel utilization, especially on high-bandwidth and high-delay links such as satellite networks.
- The protocol allows only one frame in transit, which limits throughput when the bandwidth–delay product is high.
- Efficiency can be improved by increasing the window size, which is why more advanced protocols like Go-Back-N ARQ and Selective Repeat ARQ are preferred.
- Stop-and-Wait ARQ is most suitable for networks with low propagation delay, such as Local Area Networks (LANs).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/stop-and-wait-arq/)

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
