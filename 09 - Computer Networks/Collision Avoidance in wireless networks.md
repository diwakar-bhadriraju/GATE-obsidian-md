---
title: "Collision Avoidance in wireless networks"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/collision-avoidance-in-wireless-networks/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Collision Avoidance in wireless networks
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/collision-avoidance-in-wireless-networks/)

---

# Collision Avoidance in wireless networks

We take a close look at so-called WiFi which is also known as IEEE standard 802.11
![](assets/HiddenNode-9df6c5d8d5.jpg)
Consider the situation depicted in the figure, where each of the four nodes is able to send and receive signals that reach just the nodes to its immediate left and right. For example, B can exchange frames with A and C but it cannot reach D, while C can reach B and D but not A. (A and D’s reach is not shown in the figure.) Suppose both A and C want to communicate with B and so they each send it a frame. A and C are unaware of each other since their signals do not carry that far. These two frames collide with each other at B, but unlike an Ethernet, neither A nor C is aware of this collision. A and C are said to be hidden nodes with respect to each other. According to Wikipedia, the hidden node problem can be defined as "In wireless networking, the **hidden node problem or hidden terminal problem** occurs when a node is visible to a wireless access point (AP), but not to other nodes communicating with that AP."
### Collision cannot be detected in hidden node problem
This is because the nodes **A** and **C** are out of range of each other(and so cannot detect a collision while transmitting). Thus, Carrier sense multiple access with collision detection (CSMA/CD) does not work, and collisions occur. The data received by the access point is corrupted due to the collision. To overcome the hidden node problem, RTS/CTS handshaking (IEEE 802.11 RTS/CTS) is implemented in addition to the Carrier sense multiple access with collision avoidance (CSMA/CA) scheme. A related problem, called the exposed node problem, occurs under the following stated circumstances: Suppose B is sending to A (as in the above Figure). Node C is aware of this communication because it hears B’s transmission. It would be a mistake for C to conclude that it cannot transmit to anyone just because it can hear B’s transmission. For example, suppose C wants to transmit to node D. This is not a problem since C’s transmission to D will not interfere with A’s ability to receive from B. We address these problems by an algorithm known as Multiple Access with Collision Avoidance (MACA). The sender and receiver exchange frames with each other before transmitting data. This informs all nearby nodes that a transmission is about to begin. Sender transmits **Request to Send (RTS)** frame to receiver. The receiver then replies with **clear to send (CTS)** frame back to the sender. Any node that receives CTS frame knows that it is close to the receiver, therefore, cannot transmit a frame. Any node that receives the RTS frame but not the CTS frame knows that is not close to the receiver to interfere with it, So it is free to transmit data. **Reference -** [Wikipedia](https://en.wikipedia.org/wiki/Multiple_Access_with_Collision_Avoidance_for_Wireless)
**Features of collision avoidance in wireless networks include:**
1. **Carrier Sense Multiple Access with Collision Avoidance (CSMA/CA):** This is a protocol used in wireless networks to prevent data collisions. CSMA/CA ensures that a device checks for the presence of other signals before transmitting data, thus reducing the risk of collisions.
2. **Clear Channel Assessment (CCA):** CCA is a mechanism used to determine whether a wireless channel is clear or busy before transmitting data. This feature helps to avoid collisions by ensuring that a device does not transmit data when the channel is already in use.
3. **Request to Send (RTS) and Clear to Send (CTS):** RTS and CTS are signals that are sent between devices to reserve a channel for data transmission. These signals help to prevent collisions by ensuring that only one device transmits data at a time.
4. **Collision Detection:** In cases where collisions do occur, collision detection helps to reduce their impact by allowing the devices to detect and retransmit the data.
5. **Backoff Algorithm:** Backoff algorithm is a feature that ensures that devices wait for a random period before attempting to retransmit data in the event of a collision. This feature helps to reduce the risk of multiple devices attempting to transmit data simultaneously, which could result in further collisions.
6. **Quality of Service (QoS):** QoS is a mechanism that prioritizes traffic based on its importance or urgency. By assigning different levels of priority to different types of traffic, QoS can help prevent collisions by ensuring that important traffic gets transmitted first, reducing the risk of collisions with less important traffic.
7. **Fragmentation:** Fragmentation is the process of breaking up large packets of data into smaller fragments before transmitting them. This helps to prevent collisions by reducing the amount of time that any one device is transmitting data, allowing other devices to access the channel more frequently.
8. **Power Control:** Power control is a feature that adjusts the power level of a wireless device based on its distance from the access point. By reducing the power level of devices that are close to the access point, power control can help prevent collisions by reducing the risk of interference with other devices on the network.
9. **Interference Avoidance:** Interference avoidance is a mechanism that identifies sources of interference on a wireless network and takes steps to avoid them. By avoiding sources of interference, such as other wireless networks or electronic devices, interference avoidance can help prevent collisions by reducing the risk of signal degradation or loss.
10. **Channel Bonding:** Channel bonding is the process of combining multiple wireless channels into a single, wider channel. By using channel bonding, wireless networks can increase their bandwidth and reduce the risk of collisions by allowing multiple devices to transmit data simultaneously on different channels.
### Advantages of collision avoidance in wireless networks:
1. **Improved network efficiency:** Collision avoidance helps to reduce the risk of data collisions, which can cause network congestion and slow down data transmission. By ensuring that devices transmit data one at a time, collision avoidance helps to improve network efficiency.
2. **Reduced data errors:** Data collisions can lead to data errors and packet loss. Collision avoidance helps to reduce these errors by ensuring that data is transmitted in a controlled manner.
3. **Better network throughput:** By reducing the risk of data collisions, collision avoidance helps to increase network throughput, allowing more data to be transmitted in a shorter period of time.
**Fairness:** Collision avoidance protocols like CSMA/CA ensure that all devices have an equal opportunity to transmit data, regardless of their position in the network. This helps to ensure fairness in the network.
### Disadvantages of collision avoidance in wireless networks:
1. **Increased latency:** Collision avoidance protocols like CSMA/CA introduce latency into the network, as devices have to wait for their turn to transmit data. This can lead to slower data transmission and increased response times.
2. **Network overhead:** Collision avoidance protocols require additional signaling between devices, which can increase network overhead and reduce overall network efficiency.
3. **Limited scalability:** Collision avoidance protocols like CSMA/CA may not scale well in larger networks with many devices. As the number of devices increases, the likelihood of collisions also increases, leading to decreased network efficiency.
4. **Complexity:** Implementing collision avoidance protocols can be complex and require additional hardware and software resources. This can make it more challenging to manage and troubleshoot network issues.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/collision-avoidance-in-wireless-networks/)

## GATE CS

- Subject: Computer Networks
- Topic: Data Link Layer

> [!note] Related notes
>
> - [[Aloha]]
> - [[Back-off Algorithm for CSMA CD]]
> - [[Bit Stuffing]]
> - [[Carrier sense multiple access]]
> - [[Collision Detection in CSMA CD]]
> - [[Computer Networks Error Detection]]
> - [[Controlled Access Protocols]]
> - [[Difference between Byte stuffing and Bit stuffing]]
> - [[Efficiency of CSMA CD]]
> - [[Efficiency of Token Ring]]
