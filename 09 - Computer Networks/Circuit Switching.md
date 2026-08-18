---
title: "Circuit Switching in Computer Network"
subject: "Computer Networks"
topic: "Network Layer"
source: "https://www.geeksforgeeks.org/computer-networks/circuit-switching-in-computer-network/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-layer
---


> [!abstract] Circuit Switching in Computer Network
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/circuit-switching-in-computer-network/)

---

# Circuit Switching in Computer Network

Circuit Switching establishes a dedicated path between sender and receiver before communication, using the full network bandwidth. Data flows without delay, and bit delay remains constant. While it guarantees a fixed data rate, it is costly and inefficient for high-traffic or large networks due to reserved resources.
- Bandwidth is divided into pieces.
- Bit delay is constant during communication.
- Data can flow without delay once the circuit is established.
![Circuit-Switching](assets/Circuit-Switching-660-23db7755c1.webp)
The telephone system network is one of the examples of Circuit switching. FDM (Frequency Division Multiplexing) and TDM (Time Division Multiplexing) are two methods of multiplexing multiple signals into a single carrier. 
**1. Frequency Division Multiplexing (FDM):**
- Divides total bandwidth into non-overlapping frequency bands.
- Each band carries a separate signal simultaneously.
- Used in radio, TV, and optical fiber for multiple independent signals.
**2. Time Division Multiplexing (TDM):**
- Transmits multiple signals over the same channel at different time slots.
- Uses synchronized switches at both ends.
- Suitable for long-distance links with heavy data traffic.
- Also called a digital circuit switch
## Phases of Circuit Switching
- **Circuit Establishment:** A dedicated circuit between the source and destination is constructed via a number of intermediary switching center's. Communication signals can be requested and received when the sender and receiver communicate signals over the circuit.
- **Data Transfer:** Data can be transferred between the source and destination once the circuit has been established. The link between the two parties remains as long as they communicate.
- **Circuit Disconnection:** Disconnection in the circuit occurs when one of the users initiates the disconnect. When the disconnection occurs, all intermediary linkages between the sender and receiver are terminated.
![Phases of Circuit Switching](assets/Circuit-Switching-a811ff6208.gif)
## Formulas Used in Circuit Switching
> 1. Transmission rate = Link Rate or Bit rate / no. of slots = R/h bps
>
> 2. Transmission time = size of file / transmission rate
>  = x / (R/h)
>  = (x\*h)/R second
>
> 3. Total time to send packet to destination = Transmission time + circuit setup time
>
> 4. Transmission rate from frames/sec and bits/slot:
>
> Transmission Rate=F⋅B bits/sec
## What is Circuit Switching Used For?
- **Continuous connections:** Circuit switching is used for connections that must be maintained for long periods, such as long-distance communication. Circuit switching technology is used in traditional telephone systems.
- **Dial-up network connections:** When a computer connects to the internet through a dial-up service, it uses the public switched network. Dial-up transmits [Internet Protocol (IP)](https://www.geeksforgeeks.org/computer-science-fundamentals/types-of-internet-protocols/) data packets via a circuit-switched telephone network.
- **Optical circuit switching:** Data centre networks also make use of circuit switching. Optical circuit switching is used to expand traditional data centres and fulfil increasing bandwidth demands.
## **Advantages of Circuit Switching**
- **Guaranteed data rate:** Dedicated channel ensures consistent transmission speed.
- **No delay in data flow:** Dedicated path allows continuous data transfer.
- **High reliability:** Reserved path prevents data loss or corruption.
- **Quality of service (QoS):** Supports prioritization of critical traffic like voice or video.
## **Disadvantages of Circuit Switching**
- **Limited scalability:** Not suitable for large networks; needs a dedicated path for each communication.
- **Vulnerable to failures:** If a path fails, communication is disrupted.
- **Limited flexibility:** Dedicated circuits cannot be used by others until communication ends.
- **Wastes resources:** Bandwidth is reserved even when no data is sent.
- **High cost:** Setting up and maintaining dedicated paths is expensive.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/circuit-switching-in-computer-network/)

## GATE CS

- Subject: Computer Networks
- Topic: Network Layer

> [!note] Related notes
>
> - [[Administrative Distance (AD) and Autonomous System (AS)]]
> - [[ARP, Reverse ARP(RARP), Inverse ARP (InARP), Proxy ARP and Gratuitous ARP]]
> - [[C Program to find IP Address, Subnet Mask & Default Gateway]]
> - [[Classes of routing protocols – Set 3]]
> - [[Classification of Routing Algorithms – Set 1]]
> - [[Collision Domain and Broadcast Domain]]
> - [[Computer Network Circuit Switching VS Packet Switching]]
> - [[Computer Network Servers]]
> - [[Computer Networks Longest Prefix Matching in Routers]]
> - [[Difference between layer-2 and layer-3 switches]]
