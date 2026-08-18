---
title: "Collision Detection in CSMA/CD"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/collision-detection-csmacd/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Collision Detection in CSMA/CD
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/collision-detection-csmacd/)

---

# Collision Detection in CSMA/CD

CSMA/CD (Carrier Sense Multiple Access/ Collision Detection) is a media access control method that was widely used in Early Ethernet technology/LANs, when there used to be shared Bus Topology and each node (Computers) was connected by Coaxial Cables.
![CSMACD](assets/CSMACD-87514ba2c3.webp)
Collision
> **Note:** Nowadays Ethernet is Full Duplex and Topology is either Star (connected via Switch or Router) or point-to-point ( Direct Connection). Hence CSMA/CD is not used but they are still supported though. 
## How Does CSMA/CD Work?
**Step 1:** Check if the sender is ready to transmit data packets.
**Step 2:**
- Check if the transmission link is idle.
- The sender has to keep on checking if the transmission link/medium is idle.
- For this, it continuously senses transmissions from other nodes.
- The sender sends dummy data on the link. If it does not receive any collision signal, this means the link is idle at the moment.
- If it senses that the carrier is free and there are no collisions, it sends the data. Otherwise, it refrains from sending data.
**Step 3:**
- Transmit the data & check for collisions.
- The sender transmits its data on the link.
- CSMA/CD does not use an 'acknowledgment' system. It checks for successful and unsuccessful transmissions through collision signals.
- During transmission, if a collision signal is received by the node, transmission is stopped.
- The station then transmits a jam signal onto the link and waits for random time intervals before it resends the frame.
- After some random time, it again attempts to transfer the data and repeats the above process.
**Step 4:** If no collision was detected in propagation, the sender completes its frame transmission and resets the counters.
## How Does a Station Know if Its Data Collide?
![collision_occurs](assets/collision_occurs-1804893889.webp)
Collision Occurs
Consider the above situation, Two stations, A & B:
- Propagation Time:
$$
T_p = 1 hr
$$
   ( Signal takes 1 hr to go from A to B)
- At time t=0, A transmits its data, t= 30 mins -> Collision occurs
- After the collision occurs, a collision signal is generated and sent to both A & B to inform the stations about the collision.
- Since the collision happened midway, the collision signal also takes 30 minutes to reach A & B.
- Therefore,
$$
t=1 hr
$$
   -> A & B receive collision signals. This collision signal is received by all the stations on that link.
## How to Ensure that it is our Station’s Data that Collided?
For this, Transmission time (Tt) > Propagation Time (Tp) [Rough bound], This is because we want that before we transmit the last bit of our data from our station, we should at least be sure that some of the bits have already reached their destination. This ensures that the link is not busy and collisions will not occur. 
![collision_occurs_2](assets/collision_occurs_2-bad23a0233.webp)
Collision Occurs
> At time t=0, A transmits its data, t= 50:59 mins : Collision occurs
- This collision occurs just before the data reaches B. Now the collision signal takes 50:59 minutes again to reach A.
- Hence, A receives the collision information approximately after 2 hours, that is, after
$$
2 * T_p
$$
  .
- Hence, to ensure tighter bound, to detect the collision completely,
$$
T_t > >= 2 * T_p
$$
  .
- This is the maximum collision time that a system can take to detect if the collision was of its own data.
## What should be the Minimum length of the Packet to be Transmitted?
Transmission Time = Tt = Length of the packet/ Bandwidth of the link. Substituting above, we get, Length of the packet/ Bandwidth of the link>= 2 \* Tp
$$
\text{Length of the packet} >= 2 * Tp * \text{Bandwidth of the link}
$$
> **Note:** Padding helps in cases where we do not have such long packets. We can pad extra characters to the end of our data to satisfy the above condition. 
## Features of CSMA/CD
- **Carrier Sense:** Before transmitting data, a device listens to the network to check if the transmission medium is free. If the medium is busy, the device waits until it becomes free before transmitting data.
- **Multiple Access:** In a CSMA/CD network, multiple devices share the same transmission medium. Each device has equal access to the medium and any device can transmit data when the medium is free.
- **Collision Detection:** If two or more devices transmit data simultaneously, a collision occurs. When a device detects a collision, it immediately stops transmitting and sends a jam signal to inform all other devices on the network of the collision. The devices then wait for a random time before attempting to transmit again, to reduce the chances of another collision.
- **Backoff Algorithm:** In CSMA/CD, a backoff algorithm is used to determine when a device can retransmit data after a collision. The algorithm uses a random delay before a device retransmits data, to reduce the likelihood of another collision occurring.
- **Minimum Frame Size:** CSMA/CD requires a minimum frame size to ensure that all devices have enough time to detect a collision before the transmission ends. If a frame is too short, a device may not detect a collision and continue transmitting, leading to data corruption on the network.
## Limitations of CSMA/CD
- **Limited Scalability:** CSMA/CD has limitations in terms of scalability and it may not be suitable for large networks with a high number of devices.
- **Vulnerability to Collisions:** While CSMA/CD can detect collisions, it cannot prevent them from occurring. Collisions can lead to data corruption, retransmission delays and reduced network performance.
- **Inefficient Use of Bandwidth:** CSMA/CD uses a random [backoff algorithm](https://www.geeksforgeeks.org/computer-networks/back-off-algorithm-csmacd/) that can result in inefficient use of network [bandwidth](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-bandwidth-definition-working-importance-uses/) if a device continually experiences collisions.
- **Susceptibility to Security Attacks:** CSMA/CD does not provide any security features and the protocol is vulnerable to security attacks such as packet sniffing and [spoofing](https://www.geeksforgeeks.org/computer-networks/what-is-spoofing-in-cyber-security/).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/collision-detection-csmacd/)

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
> - [[Computer Networks Error Detection]]
> - [[Controlled Access Protocols]]
> - [[Difference between Byte stuffing and Bit stuffing]]
> - [[Efficiency of CSMA CD]]
> - [[Efficiency of Token Ring]]
