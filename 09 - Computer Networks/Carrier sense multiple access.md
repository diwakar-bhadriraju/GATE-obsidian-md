---
title: "Carrier Sense Multiple Access (CSMA)"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/carrier-sense-multiple-access-csma/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Carrier Sense Multiple Access (CSMA)
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/carrier-sense-multiple-access-csma/)

---

# Carrier Sense Multiple Access (CSMA)

Carrier Sense Multiple Access (CSMA) is a method used in computer networks to help devices share a communication channel without interfering with each other. Before a device sends data, it listens to the channel (or senses the carrier) to check if it’s free.
- If the channel is busy, the device waits until it becomes idle.
- This helps prevent data collisions, which can happen when two devices try to send data at the same time.
- CSMA is widely used in networking technologies like Ethernet and Wi-Fi.
> **Note:** It works at the data link layer and was designed to reduce the chances of network traffic collisions, making communication smoother and more efficient. By checking the medium before transmitting, devices using CSMA improve overall network performance.
## Types of CSMA Protocol
There are two main types of Carrier Sense Multiple Access (CSMA) protocols, each designed to handle how devices manage potential data collisions on a shared communication channel. These types differ based on how they respond to the detection of a busy network:
1. CSMA/CA
2. CSMA/CD
### Vulnerable Time in CSMA
Vulnerable time is the short window in which there's a risk of collision between two devices trying to send data on the network at the same time. In CSMA-based networks like Ethernet or Wi-Fi, each device listens to the channel before transmitting.
![CSMA](assets/CSMA-768-1fab1f630e.webp)
Propagation Time
- If the channel seems free, the device waits a tiny moment and then begins sending.
- However, another device might also sense the channel as free at the same time and they both may start transmitting causing a collision.
- This small time window, where such collisions can still happen even after sensing, is called the vulnerable time.
> **Note:** Vulnerable Time = Propagation Time (Tp), This is the time it takes for a signal to travel from one device to another.
## Types of CSMA Access Modes
There are 4 types of access modes available in CSMA. It is also referred as 4 different types of CSMA protocols which decide the time to start sending data across shared media.
- **1-Persistent:** It senses the shared channel first and delivers the data right away if the channel is idle. If not, it must wait and continuously track for the channel to become idle and then broadcast the frame without condition as soon as it does. It is an aggressive transmission algorithm.
- **Non-Persistent:** It first assesses the channel before transmitting data; if the channel is idle, the node transmits data right away. If not, the station must wait for an arbitrary amount of time (not continuously) and when it discovers the channel is empty, it sends the frames.
- **P-Persistent:** It consists of the 1-Persistent and Non-Persistent modes combined. Each node observes the channel in the 1-Persistent mode and if the channel is idle, it sends a frame with a P probability. If the data is not transferred, the frame restarts with the following time slot after waiting for a (
$$
\text{q = 1 - p}
$$
   probability) random period.
- **O-Persistent:** A supervisory node gives each node a transmission order. Nodes wait for their time slot according to their allocated transmission sequence when the transmission medium is idle.
## What is CSMA/CA?
- CSMA/CA is a medium access control (MAC) protocol that prevents data collisions in wireless communication.
- It works by avoiding collisions before they occur.
- This is necessary because, in wireless systems, detecting collisions is difficult due to the high energy required for transmission compared to receiving.
- Thus, CSMA/CA forms the backbone of Wi-Fi (IEEE 802.11) and other wireless technologies.
## Why is CSMA/CA Needed?
- In wired networks, devices can detect collisions (CSMA/CD).
- In wireless networks, detecting collisions is nearly impossible because, the transmitting device cannot listen to the channel while sending. Signal interference, noise and hidden terminal problems make detection unreliable.
- Hence, CSMA/CA focuses on collision prevention rather than collision detection.
## Working Principle of CSMA/CA
The CSMA/CA protocol ensures that before a device transmits, it checks if the communication channel is free and then uses additional strategies to minimize collision chances.
### Process Steps:
1. **Initialize Attempt Counter (K = 0):** Each device keeps track of retransmission attempts.
2. **Sense the Channel:** The device listens to see if the channel is busy, If busy -> Wait until it becomes free.
3. **Interframe Space (IFS):** After the channel is idle, the device waits for a short fixed time.
4. **Check Again:** If still idle after IFS, continue; otherwise, repeat sensing.
5. **Random Backoff:** Choose a random number `R` in a contention window to delay transmission.
6. **Transmit Data Frame.**
7. **Wait for Acknowledgment (ACK):** If ACK received -> Success & If ACK not received -> Assume collision, retry
$$
(K = K+1)
$$
   .
8. **Retry Limit:** If attempts exceed maximum
$$
K_{max}
$$
   , abort transmission.
## Strategies Used in CSMA/CA
1. **Interframe Space (IFS):** A short waiting period after the channel becomes idle to avoid immediate collisions. Devices with shorter IFS have higher priority.
2. **Contention Window:** A device waits for a random number of time slots before transmission, reducing the chance of simultaneous access.
3. **Acknowledgments (ACKs):** The receiver sends back an acknowledgment if data is received correctly. If no ACK is received, retransmission occurs.
4. **RTS/CTS Mechanism (Optional):** Request-to-Send (RTS) -> Sender asks for permission. Clear-to-Send (CTS) -> Receiver replies if the channel is clear.
> **Note:** This helps solve the hidden terminal problem in wireless networks.
## Features of CSMA/CA
- **Carrier Sensing:** Devices listen to the channel before transmitting.
- **Collision Avoidance:** Uses random backoff and IFS to prevent overlaps.
- **Acknowledgments:** Ensures reliable data delivery.
- **Fairness:** Prevents a single device from monopolizing the channel.
- **Binary Exponential Backoff:** Wait times increase exponentially after repeated collisions.
- **Wireless Adaptability:** Ideal for high-error, high-traffic wireless environments.
## Applications of CSMA/CA
- **Wi-Fi (IEEE 802.11 standard):** Used in almost all modern WLANs.
- **Wireless LANs (WLANs):** To manage multiple devices in the same range.
- **Ad-hoc Networks:** Where devices communicate directly without centralized control
## Comparison of Various Protocols
| **Protocol** | **Transmission behavior** | **Collision detection method** | **Efficiency** | **Use cases** |
| --- | --- | --- | --- | --- |
| **Pure ALOHA** | Sends frames immediately | No collision detection | Low | Low-traffic networks |
| **Slotted ALOHA** | Sends frames at specific time slots | No collision detection | Better than pure ALOHA | Low-traffic networks |
| **CSMA/CD** | Monitors medium after sending a frame, retransmits if necessary | Collision detection by monitoring transmissions | High | Wired networks with moderate to high traffic |
| **CSMA/CA** | Monitors medium while transmitting, adjusts behavior to avoid collisions | Collision avoidance through random backoff time intervals | High | Wireless networks with moderate to high traffic and high error rates |
## Pros of CSMA
- **Increased Efficiency:** CSMA ensures that only one device communicates on the network at a time, reducing collisions and improving network efficiency.
- **Simplicity:** It is a simple protocol that is easy to implement and does not require complex hardware or software.
- **Flexibility:** It is a flexible protocol that can be used in a wide range of network environments, including wired and wireless networks.
- **Low cost:** It does not require expensive hardware or software, making it a cost-effective solution for network communication.
## Cons of CSMA
- **Limited Scalability:** CSMA is not a scalable protocol and can become inefficient as the number of devices on the network increases.
- **Delay:** In busy networks, the requirement to sense the medium and wait for an available channel can result in delays and increased latency.
- **Limited Reliability:** It can be affected by interference, noise and other factors, resulting in unreliable communication.
- **Vulnerability to Attacks:** It can be vulnerable to certain types of attacks, such as jamming and denial-of-service attacks, which can disrupt network communication.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/carrier-sense-multiple-access-csma/)

## GATE CS

- Subject: Computer Networks
- Topic: Data Link Layer

> [!note] Related notes
>
> - [[Aloha]]
> - [[Back-off Algorithm for CSMA CD]]
> - [[Bit Stuffing]]
> - [[Collision Avoidance in wireless networks]]
> - [[Collision Detection in CSMA CD]]
> - [[Computer Networks Error Detection]]
> - [[Controlled Access Protocols]]
> - [[Difference between Byte stuffing and Bit stuffing]]
> - [[Efficiency of CSMA CD]]
> - [[Efficiency of Token Ring]]
