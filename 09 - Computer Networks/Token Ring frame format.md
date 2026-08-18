---
title: "Token Ring Frame Format"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/token-ring-frame-format/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Token Ring Frame Format
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/token-ring-frame-format/)

---

# Token Ring Frame Format

In a Token Ring network, frames have a specific format to ensure reliable and orderly communication among nodes. The Token Ring uses a token-passing protocol for access control, and each frame follows a standardized structure as defined in IEEE 802.5.
## Structure of a Token Ring Frame
Token Ring is a networking technology where devices are connected in a logical ring. Communication is controlled by a special frame called a token. When a device holds the token, it can transmit data. A Token Ring frame has a specific format to ensure that data is transferred accurately and efficiently.
It consists of the following elements in the structure of the token ring format :
![tok-3](assets/tok-3-28acc7f120.png)
Token Ring Format
**Start Delimiter (SD) 1 Byte** : Used for the marking the beginning of the frame. This has a unique bit pattern so that the receiving station knows exactly when a new frame starts. It includes symbols to indicate timing and [frame synchronization](https://www.geeksforgeeks.org/computer-networks/framing-in-data-link-layer/).
**Access Control (AC) 1 Byte :**  Used to manage token passing and transmission control. Fields Include:
- **Priority bits (3 bits):** Used to determine the priority of the frame.
- **Token bit (T):** Indicates whether the frame is a token or data.
- **Monitor bit (M):** Ensures only one token exists in the ring.
- **Reservation bits (3 bits):** Allow a station to reserve the [token](https://www.geeksforgeeks.org/computer-networks/difference-between-token-ring-and-ethernet/) for higher priority transmissions.
![tok](assets/tok-76cacad865.png)
Access Control
**Frame Control (FC) 1 Byte :** It identifies the type of frame being transmitted. It helps devices interpret the rest of the frame correctly. First 2 bits indicates whether the frame contains data or control information. In control frames, this byte specifies the type of control information.Types:
- **Data Frame:** Carries user data.
- **MAC Frame:** Used for control purposes such as ring maintenance.
![tok-1](assets/tok-1-ac3fd41fb4.png)
Frame Control
**Destination Address (DA) 2 or 6 Bytes :** It specifies the intended receiver’s MAC address. The size depends on whether the network uses 16-bit or 48-bit addressing. This allows unicast, multicast, or broadcast communication.
**Source Address (SA) 2 or 6 Bytes :** It contains the [MAC address](https://www.geeksforgeeks.org/computer-networks/mac-address-in-computer-network/) of the sender. It has the same size as the destination address.
**Data Variable Length :** It carries the actual message or payload. It sizes typically up to 4,000 bytes, but can vary based on network configuration. This is the information the sender wants to deliver.
**Frame Check Sequence (FCS) 4 Bytes :** Used for error-checking using [Cyclic Redundancy Check (CRC)](https://www.geeksforgeeks.org/python/cyclic-redundancy-check-python/). It ensures the data was not corrupted in transit. The recipient recalculates the CRC and compares it to detect any errors. 32 bit CRC which is used to check for errors in the frame, i.e., whether the frame is corrupted or not. If the frame is corrupted, then its discarded.
**Ending Delimiter (ED) 1 Byte :** It marks the end of the frame allows the receiver to detect when the frame is complete. It has a specific bit pattern that signifies the end of data transmission.
**Frame Status (FS) 1 Byte :** It indicates whether the frame was recognized and copied by the destination.
- **A (Address Recognized):** Set by the recipient if it recognizes its address.
- **C (Frame Copied):** Set if the frame’s contents were successfully copied.
It makes use of 2 copies of AC bits are used as a error detection mechanism (100% redundancy) as CRC does not cover FS byte so that destination does not have to recalculate CRC when modifying AC bits.
![tok-4](assets/tok-4-919c76826a.png)
Frame status
**Special Frame The Token:**
- A special type of frame (only 3 bytes long) that circulates around the ring.
- Consists of **Start Delimiter + Access Control + End Delimiter**.
- Allows a station to transmit data only when it captures the token.
![tok-2](assets/tok-2-53fc0f1d64.png)
Token Frame
| Field | Size | Purpose |
| --- | --- | --- |
| Start Delimiter | 1 byte | Marks frame start, unique bit pattern |
| Access Control | 1 byte | Manages priority, token status, and ring monitoring |
| Frame Control | 1 byte | Identifies frame type (data or control) |
| Destination Address | 2 or 6 bytes | Address of the receiver |
| Source Address | 2 or 6 bytes | Address of the sender |
| Data | Variable | Payload (up to 4,000 bytes) |
| Frame Check Sequence | 4 bytes | Error detection via CRC |
| End Delimiter | 1 byte | Marks frame end |
| Frame Status | 1 byte | Indicates if frame was recognized and copied |
### Token Ring Network Functionality:
- **Token Passing:** Only the station (node) that currently holds the token is allowed to transmit data.
- **Sending Data:** Once the station finishes sending its data, it releases the token back into the network.
- **Orderly Access:** The token circulates in a logical ring among all stations, giving each one a turn to send.
- **Collision Free:** Since only one token exists and only the token holder can send data, this mechanism prevents collisions on the network.
- **Efficient Use:** This orderly process ensures fair and efficient use of the network medium.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/token-ring-frame-format/)

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
