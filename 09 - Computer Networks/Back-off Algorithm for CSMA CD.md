---
title: "Back-off Algorithm for CSMA/CD"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/back-off-algorithm-csmacd/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Back-off Algorithm for CSMA/CD
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/back-off-algorithm-csmacd/)

---

# Back-off Algorithm for CSMA/CD

Prerequisite - [Basics of CSMA/ CD](https://www.geeksforgeeks.org/computer-networks/data-link-layer-in-osi-model/), [Collision Detection in CSMA/CD](https://www.geeksforgeeks.org/computer-networks/collision-detection-csmacd/) 
Back-off algorithm is a **collision resolution** mechanism which is used in random access MAC protocols (CSMA/CD). This algorithm is generally used in Ethernet to schedule re-transmissions after collisions. If a collision takes place between 2 stations, they may restart transmission as soon as they can after the collision. This will always lead to another collision and form an infinite loop of collisions leading to a deadlock. To prevent such scenario back-off algorithm is used. Let us consider a scenario of 2 stations A and B transmitting some data: 
![](assets/qw-1-665c90c716.png)
 After a collision, time is divided into discrete slots (**T**slot**) whose length is equal to 2t, where t is the maximum propagation delay in the network. The stations involved in the collision randomly pick an integer from the set K i.e {0, 1}. This set is called the contention window. If the sources collide again because they picked the same integer, the contention window size is doubled and it becomes {0, 1, 2, 3}. Now the sources involved in the second collision randomly pick an integer from the set {0, 1, 2, 3} and wait for that number of time slots before trying again. Before they try to transmit, they listen to the channel and transmit only if the channel is idle. This causes the source which picked the smallest integer in the contention window to succeed in transmitting its frame. So, the Back-off algorithm defines a **waiting time for the stations involved in collision**, i.e. for how much time the station should wait to re-transmit.
```
Waiting time = back–off timeLet n = collision number or re-transmission serial number. Then, Waiting time = K * Tslotwhere K = [0, 2n – 1 ]
```
**Example -Case-1 :** Suppose 2 stations A and B start transmitting data (Packet 1) at the same time then, collision occurs. So, the collision number n for both their data (Packet 1) = 1. Now, both the station randomly pick an integer from the set K i.e. {0, 1}. ![](assets/qw1-1-e8ed63a201.png)
- **When both A and B choose K = 0**  --> Waiting time for A = 0 \* T  slot  = 0 Waiting time for B = 0 \* T  slot  = 0 Therefore, both stations will transmit at the same time and hence collision occurs.
- **When A chooses K = 0 and B chooses K = 1**  --> Waiting time for A = 0 \* T  slot  = 0 Waiting time for B = 1 \* T  slot  = T  slot  Therefore, A transmits the packet and B waits for time T  slot  for transmitting and hence A wins.
- **When A chooses K = 1 and B chooses K = 0**  --> Waiting time for A = 1 \* T  slot  = T  slot  Waiting time for B = 0 \* T  slot  = 0 Therefore, B transmits the packet and A waits for time T  slot  for transmitting and hence B wins.
- **When both A and B choose K = 1**  --> Waiting time for A = 1 \* T  slot  = T  slot  Waiting time for B = 1 \* T  slot  = T  slot  Therefore, both will wait for the same time T  slot  and then transmit. Hence, a collision occurs.
```
Probability that A wins = 1/4Probability that B wins = 1/4Probability of collision  = 2/4
```
**Case-2:** Assume that A wins in Case 1 and transmitted its data(Packet 1). Now, as soon as B transmits its packet 1, A transmits its packet 2. Hence, collision occurs. Now collision no. n becomes 1 for packet 2 of A and becomes 2 for packet 1 of B. For packet 2 of A, K = {0, 1} For packet 1 of B, K = {0, 1, 2, 3} 
![](assets/qw2-1-dde088038f.png)
```
Probability that A wins = 5/8Probability that B wins = 1/8Probability of collision  = 2/8
```
So, the probability of collision decreases as compared to Case 1. 
### Here are some of its key features:
When a collision occurs, the transmitting device waits for a random amount of time before retransmitting the packet. The random delay helps to prevent multiple devices from retransmitting their packets simultaneously and causing another collision.
The random delay time is determined using an exponential back-off algorithm. The delay time starts at a minimum value and doubles after each collision, up to a maximum value. The maximum delay time is usually set to 1024 slot times, where a slot time is the time it takes for a signal to travel from one end of the network segment to the other.
The back-off algorithm is implemented in hardware on the network interface card (NIC) of each device. When a collision is detected, the NIC generates a random number between 0 and 2^n-1, where n is the number of collisions that have occurred. The NIC then multiplies the random number by the slot time to determine the delay time before retransmitting.
If the maximum number of retransmissions is reached without successful transmission, the device gives up and reports a transmission error.
**Advantage -**
- Collision probability decreases exponentially.
- **Improves network performance:**  Back-off algorithm reduces the number of collisions and retransmissions, thus improving the overall network performance.
- **Increases channel utilization**  : By reducing the number of collisions, back-off algorithm increases the channel utilization, leading to better use of network resources.
- **Reduces delays:**  By reducing the number of collisions, back-off algorithm reduces the waiting time between transmission attempts, resulting in lower delays.
- **Fairness:**  The back-off algorithm ensures that all nodes in the network have an equal chance to access the channel, which promotes fairness in the distribution of network resources.
- **Adaptability:**  The back-off algorithm is adaptable to changing network conditions. When the network is busy, it increases the waiting time before retransmission attempts, and when the network is idle, it reduces the waiting time, thus ensuring efficient use of network resources.
- **Scalability:**  The back-off algorithm is scalable, as it can be used in networks of any size, from small local networks to large wide-area networks.
- **Energy Efficiency:**  By reducing the number of collisions and retransmissions, the back-off algorithm reduces the energy consumption of network nodes, which is particularly important in battery-powered devices such as mobile phones and IoT devices.
- **Robustness:**  The back-off algorithm is robust, as it can handle a high number of nodes trying to access the channel simultaneously without causing the network to crash or degrade in performance.
**Disadvantages -**
- **Capture effect:**  Station who wins ones keeps on winning.
- Works only for 2 stations or hosts.
- **Increased overhead**  : Back-off algorithm adds additional overhead to the network due to the need to wait for a random time before retransmitting a packet.
- **Complexity**  : Back-off algorithm is a complex algorithm that requires a high level of implementation complexity.
- **Vulnerability to attacks**  : Back-off algorithm is vulnerable to certain attacks, such as denial-of-service (DoS) attacks, where an attacker can manipulate the random time intervals to cause the network to stop functioning.
- **Limited Performance:**  While the back-off algorithm can improve network performance in low- to medium-load scenarios, it may not be effective in high-load scenarios where the number of nodes trying to access the network is very high.
- **Inefficient in Time-Sensitive Applications:**  The back-off algorithm may not be suitable for time-sensitive applications, such as real-time video streaming or voice over IP (VoIP), where even a slight delay can cause significant problems.
- **Limited Scalability:**  While the back-off algorithm can be used in networks of any size, it may become less effective in larger networks where the number of nodes trying to access the channel simultaneously is very high.
- **Sensitivity to Distance and Interference:**  The back-off algorithm is sensitive to distance and interference, as nodes that are physically closer to each other may have a higher probability of colliding and may require longer random waiting times.
- **Limited Support for Quality of Service:**  The back-off algorithm does not provide support for quality of service (QoS), which is an important feature for many networking applications, such as video streaming, voice over IP (VoIP), and online gaming.
**GATE Practice Question -**
1. [GATE-CS-2004 | Question 90](https://www.geeksforgeeks.org/questions/a-and-b-are-the-only-two-stations-on/)
2. [GATE-CS-2016 (Set 2) | Question 34](https://www.geeksforgeeks.org/questions/in-an-ethernet-local-area-network-which-one-of/)
3. [GATE-IT-2004 | Question 85](https://www.geeksforgeeks.org/questions/consider-a-simplified-time-slotted-mac-protocol-where-each/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/back-off-algorithm-csmacd/)

## GATE CS

- Subject: Computer Networks
- Topic: Data Link Layer

> [!note] Related notes
>
> - [[Aloha]]
> - [[Bit Stuffing]]
> - [[Carrier sense multiple access]]
> - [[Collision Avoidance in wireless networks]]
> - [[Collision Detection in CSMA CD]]
> - [[Computer Networks Error Detection]]
> - [[Controlled Access Protocols]]
> - [[Difference between Byte stuffing and Bit stuffing]]
> - [[Efficiency of CSMA CD]]
> - [[Efficiency of Token Ring]]
