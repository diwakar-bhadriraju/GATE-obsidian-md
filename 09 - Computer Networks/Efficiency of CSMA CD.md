---
title: "Efficiency of CSMA/CD"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/efficiency-of-csma-cd/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Efficiency of CSMA/CD
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/efficiency-of-csma-cd/)

---

# Efficiency of CSMA/CD

**Prerequisite -** [Introduction to Ethernet](https://www.geeksforgeeks.org/computer-networks/what-is-ethernet/), [Basics of CSMA/ CD](https://www.geeksforgeeks.org/computer-networks/data-link-layer-in-osi-model/)
**Carrier sense multiple access with collision detection (CSMA/CD) -** The CSMA method does not tell us what to do in case there is a collision. Carrier sense multiple access with collision detection (CSMA/CD) adds to the CSMA algorithm to deal with the collision. In CSMA/CD, the size of a frame must be large enough so that collision can be detected by the sender while sending the frame. So, the frame transmission delay must be at least *two times* the maximum propagation delay. Assume some station transmitted data packet and successfully get to the destination but it is just the *Best Case*, so we have to take the *Worst Case* scenario in which there will be contention slots. Contention slots are those slots that are not able to transmit their journey due to the collision. Suppose station A transmitted data but collide and the worst-case time wasted is **2Tp** and then some station B found out a way to transmit the data so it took (As shown in Figure)
```
Tp ( propagation delay) + Tt(transmission time)
```
Now we don't know how many contention slots, so we consider the worst-case to be of **n** contention slots.
```
Efficiency = Tt / ( C*2*Tp + Tt + Tp)
Tt - transmission time
Tp - propagation time
C  - number of collision
```
![](assets/CSMA_CD-Diagram-f5bb51aa7f.png)
In CSMA/CD, for success, only 1 station should transmit while others shouldn't. Let p be the probability to transmit data successfully.
```
P(success) = nC1 * p * (1-p)n-1 (by using Binomial distribution)
```
For max P(success), differentiate with respect to p and equate to zero (to get maxima and minima).
```
We get P(max) = 1/e
```
Number of times we need to try before getting 1st success
```
1/P(MAX) = 1/(1/e) = e
```
Here number of times we need to try (C) = e. Put a = Tt/Tp and divide by T in Efficiency = Tt / (C\* 2 \* Tp + Tt + Tp) We get,
```
Efficiency = 1/(e*2a + 1 + a)
a = Tp/Tt
e = 2.72
Now
Efficiency = 1/( 1 + 6.44a)
```
**Further Analysis of Efficiency :**
```
Efficiency = 1/ (1 + 6.44a)
           = 1/ {1 + 6.44(Tp/Tt)}
           = 1/ {1 + 6.44((distance/speed)/(packet length/Bandwidth))}
           = 1/ {1+ 6.44 ((distance * bandwidth)/ (speed*packet length))}
```
From this derivation, we can conclude many relations :
- If distance increases, the efficiency of CSMA decreases.
- CSMA is not suitable for long-distance networks like WAN but works optimally for LAN.
- If the length of the packet is bigger, the efficiency of CSMA also increases; but the maximum limit for length is 1500 Bytes.
- Transmission Time >= 2\*Propagation Time
**GATE CS Corner Questions** 
Practicing the following questions will help you test your knowledge. All questions have been asked in GATE in previous years or in GATE Mock Tests. It is highly recommended that you practice them.
1. [GATE CS 2003, Question 90](https://www.geeksforgeeks.org/questions/a-2-km-long-broadcast-lan-has-107-bps/)
2. [GATE CS 2015 (Set 3), Question 65](https://www.geeksforgeeks.org/questions/consider-a-csmacd-network-that-transmits-data-at-a/)
3. [GATE IT 2005, Question 27](https://www.geeksforgeeks.org/questions/which-of-the-following-statements-is-true-about-csmacd/)
4. [GATE IT 2005, Question 71](https://www.geeksforgeeks.org/questions/a-network-with-csmacd-protocol-in-the-mac-layer/)
5. [GATE CS 2016 (Set 2), Question 63](https://www.geeksforgeeks.org/questions/a-network-has-a-data-transmission-bandwidth-of-20/)
6. [GATE IT 2008, Question 63](https://www.geeksforgeeks.org/questions/the-minimum-frame-size-required-for-a-csmacd-based/)
**Reference -** <https://www.youtube.com/watch?v=74zlRH-bj2c>
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/efficiency-of-csma-cd/)

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
> - [[Efficiency of Token Ring]]
