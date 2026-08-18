---
title: "Sliding Window protocols Summary With Questions"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/sliding-window-protocols-summary-with-questions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Sliding Window protocols Summary With Questions
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/sliding-window-protocols-summary-with-questions/)

---

# Sliding Window protocols Summary With Questions

Sliding Window Protocol is a flow control mechanism used in data link and transport layers to manage the reliable and efficient transmission of frames or packets between sender and receiver. Key Concepts in Sliding Window Protocol :
- **Window Size**: Refers to the number of frames that can be sent before requiring an acknowledgment.
- **Sender Window**: Controls how many frames the sender can transmit before pausing for an ACK.
- **Receiver Window**: Indicates how many frames the receiver is ready to accept.
- **Acknowledgment (ACK)**: Receiver confirms the successful reception of frames.
- **Types of Sliding Window Protocols**:
  - **Stop-and-Wait**: Sends one frame at a time, waits for ACK.
  - **Go-Back-N (GBN)**: Sender can send several frames (window size N) without waiting, but on error, retransmits from the erroneous frame onward.
  - **Selective Repeat (SR)**: Only the erroneous or lost frames are resent, not the whole sequence.
- **Useful time** : Tt(data)
- **Total Time** : Tt(data) + 2\*Tp + Tq + Tpro + Tt(ack)
- **Efficiency = Tt(data) /Tt(data) + 2\*Tp + Tq + Tpro + Tt(ack)**
```
Tt(data) :Transmission delay for Data packetTp : Propagation delay for Data packetTq: Queuing delayTpro: Processing delayTt(ack): Transmission delay for acknowledgment
```
## Stop And Wait
[Stop and Wait ARQ](https://www.geeksforgeeks.org/computer-networks/stop-and-wait-arq/) is a Sliding Window Protocol method used for the reliable delivery of data frames. The stop-and-wait ARQ is used for noisy channels or links to handle flow and error control between sender and receiver. The Stop and Wait ARQ protocol sends a data frame and then waits for an acknowledgment (ACK) from the receiver.
- Sender window size (Ws) = 1
- Receiver window size (Wr) = 1
- Sequence Number ≥ 1 + 1
- Uses independent acknowledgement
- Discards out of order packets
- **Efficiency= (Useful time)/(Total Time)**
![Stop-and-Wait-ARQ](assets/Stop-and-Wait-ARQ-660x621-af5b97c590.png)
STOP AND WAIT WORKING
## **Go Back N**
In [Go-Back-N](https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-2-receiver-side/), the sender can send multiple data packets without waiting for an acknowledgement for each one. However, it can only send a certain number of packets (this is called the window size). If one packet is lost or not acknowledged, the sender must go back and resend that packet and all the packets that followed it, even if they were received correctly.
- Sender window size Ws = N
- Receiver window size Wr = 1
- Sequence number ≥ N + 1
- Can use both cumulative or independent acknowledgement depends on acknowledge timer
- Discards out of order packets
- **Efficiency= N\*(Useful time)/(Total Time)**
![Sliding_SET_2-1](assets/Sliding_SET_2-1-768-2dd0a03349.jpg)
GB-N WORKING DIAGRAM
## **Selective Repeat**
[**Selective Repeat** protocol (SRP)](https://www.geeksforgeeks.org/computer-networks/sliding-window-protocol-set-3-selective-repeat/) is mostly identical to GBN protocol, except that buffers are used and the receiver, and the sender, each maintains a window of size. SRP works better when the link is very unreliable. Because in this case, retransmission tends to happen more frequently, selectively retransmitting frames is more efficient than retransmitting all of them. SRP also requires full-duplex link.
- Sender window size Ws = N
- Receiver window size Wr = N
- Sequence Number ≥ N + N
- Uses only independent acknowledgement
- Can Accept out of order packets
- **Efficiency= N\*(Useful time)/(Total Time)**
![Sliding-Window-Protocol](assets/Sliding-Window-Protocol-8cd65c34f0.jpg)
SELECTIVE REPEAT WORKING
### Practice Questions
**Example-1.** In Stop and wait protocol every 4th packet is lost and we need to send total 10 packets so how many transmission it took to send all the packets?
**Explanation**
> 1 2 3 4 5 6 7 8 9 10 (Initially)
>  ^
> 1 2 3 4 4 5 6 7 8 9 10 (Packet no. 4 retransmitted)
>  ^
> 1 2 3 4 4 5 6 7 7 8 9 10 (Packet no. 10 retransmitted)
>  ^
> 1 2 3 4 4 5 6 7 7 8 9 10 10 (Result)
>
> So, we retransmitted packet number 4, 7, 10 Total count = 13
**Example-2.** In S&W protocol if Error probability is p and no. of packets to send is 'n'. How many packets we have to send ?
**Explanation**
> Total retransmissions = n\*p0+ n\*p1+ n\*p2 + n\*p3 + n\*p4 + ... = n(1 + p + p2 + p3 + p4 + ...) = n\*(1 / (1-p)) using infinite GP sum formula
**Example-3.** In GBN sender Window size = 10 and Tp = 49.5ms & Tt = 1ms. What is the Efficiency of the protocol and Throughput given Bandwidth = 1000 bps?
**Explanation**
> Efficiency = N/(1+2a) as there is only transmission delay and propagation delay , N = 10 (given), a = Tp/Tt = 49.5
>
> Efficiency = 10/(1 + 2 \* 49.5)
>
> = 10/100
>
> = 0.1 or 10%
>
> Throughput = Efficiency \* Bandwidth = 0.1 \* 1000 = 100
**Example-4.** In GB3 if every 5th packet is lost & we need to send 10 packets so how many retransmissions are required ?
**Explanation**
> 1 2 3 4 5 6 7 | 8 9 10
>  ^ $ (packet no. 5 lost)
> 1 2 3 4 5 6 7 5 6 7 8 9 | 10
>  \* ^ $
> 1 2 3 4 5 6 7 5 6 7 8 9 7 8 9 10
>  \* ^ $
> 1 2 3 4 5 6 7 5 6 7 8 9 7 8 9 10 9 10 (count starts from \* till ^)
> (from ^ to $ retransmission is done)
> **Note -** From the Last packet is window size to lost pocket we resend the entire window. Total no. of transmissions = 18
**Example-5.** In SR Ws = 5 and we are sending 10 packets where every 5th packet is lost find number of retransmissions?
**Explanation**
> 1 2 3 4 5 6 7 8 9 10
>  ^
> 1 2 3 4 5 5 6 7 8 9 10
>  ^
> 1 2 3 4 5 5 6 7 8 9 9 10
>
> We see here there is no role of Window size in SR only the lost packet is resent. Total transmissions = 12
**Example-6.** If there is K bits sequence no. define require sender window size and receiver window size for S&W, GBN & SR?
**Explanation**
> Given, K bits,
>
> For S&W Ws = 1 and Wr = 1
>
> For GBN, Ws = 2K-1 and Wr = 1
>
> For SR, Ws = 2K-1 and Wr = 2(K-1)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/sliding-window-protocols-summary-with-questions/)

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
