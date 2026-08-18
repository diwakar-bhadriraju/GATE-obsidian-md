---
title: "Framing in Data Link Layer"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/framing-in-data-link-layer/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Framing in Data Link Layer
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/framing-in-data-link-layer/)

---

# Framing in Data Link Layer

A frame is the basic unit of data transmission at the Data Link Layer, consisting of a structured group of bits that carries data along with control information.
- Frames include control information such as addressing and error detection.
- Framing is performed at the Data Link Layer (DLL) of the OSI model.
- It divides a continuous stream of bits into manageable and meaningful units.
- Framing enables reliable transmission and proper processing at the receiver.
- It helps in synchronization between the sender and receiver.
![1](assets/1-c8871a9ca8.webp)
Data Link layer services
> **Note:** Framing is crucial in techniques like Time Division Multiplexing (TDM), where data is sent in fixed time slots. Data Link Layer technologies such as Ethernet, Token Ring, and Frame Relay use well-defined frame formats to ensure proper data identification and reliable communication.
## Purpose of Framing
Framing serves several purposes in the Data Link Layer:
- It defines clear frame boundaries so the receiver can correctly identify each frame.
- It carries source and destination addresses to support accurate point-to-point communication.
- It supports error detection and correction to maintain data integrity.
- It ensures reliable and well-organized data transmission.
> **Note:** The framing and reassembly process is handled entirely by the Data Link Layer and remains transparent to the user.
## Types of Framing
### 1. Fixed-Size Framing
- Frames have a predefined fixed size
- No start or end delimiters are required, as the frame length defines the boundary.
- **Drawback:** Causes internal fragmentation when data is smaller than the frame size, leading to bandwidth wastage.
- **Solution:** **Padding** is added to fill unused space and complete the frame.
![2](assets/2-98b96ef21f.webp)
DLL - Upper to Lower Level
### 2. Variable-Size Framing
Variable-size framing uses explicit frame boundary indicators to identify the start and end of a frame.
- **Length Field:**
   The frame contains a length field that specifies its size (used in IEEE 802.3 Ethernet). If this field is corrupted, the receiver cannot correctly interpret the frame.
- **End Delimiter (ED):**
   A unique pattern marks the end of the frame (used in Token Ring). The delimiter pattern may also appear within the data.
To resolve delimiter ambiguity, **stuffing techniques** are applied:
#### **(a) Character/Byte Stuffing**
- Used when data is character-based.
- If the data contains the special delimiter character (e.g., `$`), an escape character (e.g., `\O`) is inserted to distinguish it.
> **Example:** If ED = $, and data contains $, it becomes \O$.
> **Disadvantage:** High processing overhead and obsolete in modern systems.
**(b) Bit Stuffing**
![3](assets/3-4c9ec369e2.webp)
Bit Stuffing
- ED pattern is a sequence of bits (e.g., `01111`).
- Whenever this pattern appears in data, a `0` is inserted to prevent confusion.
> **Example Problem:** Data = 011100011110, ED = 0111, After bit stuffing -> 011010001101100
> **Another Example:** Data = 110001001, ED = 1000, After bit stuffing -> 11001010011
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/framing-in-data-link-layer/)

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
