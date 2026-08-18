---
title: "Ethernet Frame Format"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/ethernet-frame-format/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Ethernet Frame Format
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/ethernet-frame-format/)

---

# Ethernet Frame Format

The basic frame format which is required for all MAC implementation is defined in **IEEE 802.3 standard**. Though several optional formats are being used to extend the protocol's basic capability. Ethernet frame starts with the Preamble and SFD, both work at the physical layer. The ethernet header contains both the Source and Destination MAC address, after which the payload of the frame is present. The last field is CRC which is used to detect the error. Now, let's study each field of basic frame format.
## Ethernet (IEEE 802.3) Frame Format
![Ethernet Frame Format](assets/IEEE-802-3-Ethernet-Frame-Format-6b01137b7f.png)
1. **PREAMBLE:**  Ethernet frame starts with a 7-Bytes Preamble. This is a pattern of alternative 0's and 1's which indicates starting of the frame and allow sender and receiver to establish bit synchronization. Initially, PRE (Preamble) was introduced to allow for the loss of a few bits due to signal delays. But today's high-speed Ethernet doesn't need a Preamble to protect the frame bits. PRE (Preamble) indicates the receiver that frame is coming and allow the receiver to lock onto the data stream before the actual frame begins.
2. **Start of frame delimiter (SFD):**  This is a 1-Byte field that is always set to 10101011. SFD indicates that upcoming bits are starting the frame, which is the destination address. Sometimes SFD is considered part of PRE, this is the reason Preamble is described as 8 Bytes in many places. The SFD warns station or stations that this is the last chance for synchronization.
3. **Destination Address:**  This is a 6-Byte field that contains the MAC address of the machine for which data is destined.
4. **Source Address:**  This is a 6-Byte field that contains the MAC address of the source machine. As Source Address is always an individual address (Unicast), the least significant bit of the first byte is always 0.
5. **Length:**  Length is a 2-Byte field, which indicates the length of the entire Ethernet frame. This 16-bit field can hold a length value between 0 to 65535, but length cannot be larger than 1500 Bytes because of some own limitations of Ethernet.
6. **Data:**  This is the place where actual data is inserted, also known as  **Payload**  . Both [IP header](https://www.geeksforgeeks.org/computer-networks/introduction-and-ipv4-datagram-header/) and data will be inserted here if Internet Protocol is used over Ethernet. The maximum data present may be as long as 1500 Bytes. In case data length is less than minimum length i.e. 46 bytes, then padding 0's is added to meet the minimum possible length.
7. **Cyclic Redundancy Check (CRC):**  CRC is 4 Byte field. This field contains a 32-bits hash code of data, which is generated over the Destination Address, Source Address, Length, and Data field. If the checksum computed by destination is not the same as sent checksum value, data received is corrupted.
8. **VLAN Tagging:**  The Ethernet frame can also include a VLAN (Virtual Local Area Network) tag, which is a 4-byte field inserted after the source address and before the EtherType field. This tag allows network administrators to logically separate a physical network into multiple virtual networks, each with its own VLAN ID.
9. **Jumbo Frames:**  In addition to the standard Ethernet frame size of 1518 bytes, some network devices support Jumbo Frames, which are frames with a payload larger than 1500 bytes. Jumbo Frames can increase network throughput by reducing the overhead associated with transmitting a large number of small frames.
10. **Ether Type Field:**  The EtherType field in the Ethernet frame header identifies the protocol carried in the payload of the frame. For example, a value of 0x0800 indicates that the payload is an IP packet, while a value of 0x0806 indicates that the payload is an ARP (Address Resolution Protocol) packet.
11. **Multicast and Broadcast Frames:**  In addition to Unicast frames (which are sent to a specific destination MAC address), Ethernet also supports Multicast and Broadcast frames. Multicast frames are sent to a specific group of devices that have joined a multicast group, while Broadcast frames are sent to all devices on the network.
12. **Collision Detection:**  In half-duplex Ethernet networks, collisions can occur when two devices attempt to transmit data at the same time. To detect collisions, Ethernet uses a [Carrier Sense Multiple Access with Collision Detection (CSMA/CD)](https://www.geeksforgeeks.org/computer-networks/collision-detection-csmacd/) protocol, which listens for activity on the network before transmitting data and backs off if a collision is detected.
> **Note:** Size of frame of Ethernet IEEE 802.3 varies 64 bytes to 1518 bytes including data length (46 to 1500 bytes).
## Brief Overview on Extended Ethernet Frame (Ethernet II Frame)
Standard IEEE 802.3 basic frame format is discussed above in detail. Now let's see the extended Ethernet frame header, using which we can get a Payload even larger than 1500 Bytes. 
![Extended Ethernet Frame](assets/Proposed-ETHERNET-Frame-Extension-58c7a15b0f.png)
**DA** [Destination [MAC Address](https://www.geeksforgeeks.org/computer-networks/mac-address-in-computer-network/)]: **6 bytes**SA** [Source MAC Address]: **6 bytes**Type** [0x8870 (Ethertype)]: **2 bytes**DSAP** [802.2 Destination Service Access Point] : **1 byte**SSAP** [802.2 Source Service Access Point] : **1 byte**Ctrl** [802.2 Control Field] : **1-byte**Data** [Protocol Data] : **> 46 bytes**FCS** [Frame Checksum]: **4 bytes** Although length field is missing in Ethernet II frame, the frame length is known by virtue of the frame being accepted by the network interface. **GATE CS Corner Questions** Practicing the following questions will help you test your knowledge. All questions have been asked in GATE in previous years or in GATE Mock Tests. It is highly recommended that you practice them.
1. [GATE CS 2007, Question 85](https://www.geeksforgeeks.org/questions/in-ethernet-when-manchester-encoding-is-used-the-bit/)
2. [GATE CS 2005, Question 74](https://www.geeksforgeeks.org/questions/suppose-the-round-trip-propagation-delay-for-a-10/)
3. [GATE CS 2004, Question 90](https://www.geeksforgeeks.org/questions/a-and-b-are-the-only-two-stations-on/)
4. [GATE IT 2005, Question 27](https://www.geeksforgeeks.org/questions/which-of-the-following-statements-is-true-about-csmacd/)
5. [GATE CS 2016 (Set 2), Question 34](https://www.geeksforgeeks.org/questions/in-an-ethernet-local-area-network-which-one-of/)
## Advantages
- **Simple Format:**  The Ethernet frame format is simple and easy to understand, making it easy to implement and troubleshoot Ethernet networks.
- **Flexibility:**  The Ethernet frame format is flexible and can accommodate different data sizes and network topologies, making it suitable for a wide range of network applications.
- **Widely Adopted:**  The Ethernet frame format is widely adopted and supported by a large number of vendors and network devices, ensuring compatibility and interoperability.
- **Error Detection:**  The Ethernet frame format includes a [cyclic redundancy check (CRC)](https://www.geeksforgeeks.org/dsa/modulo-2-binary-division/) field for error detection, which helps to ensure data integrity during transmission.
- **Support for VLANs:**  The Ethernet frame format supports virtual local area networks (VLANs), which allows network administrators to logically partition a physical LAN into multiple smaller virtual LANs for improved network management and security.
## Disadvantages
- **Limited Frame Size:**  The Ethernet frame format has a maximum frame size of 1500 bytes, which can limit the amount of data that can be transmitted in a single frame and can result in increased overhead due to [fragmentation](https://www.geeksforgeeks.org/computer-networks/fragmentation-network-layer/) and reassembly of larger packets.
- **Broadcast Storms:**  Ethernet networks use broadcast transmissions to send frames to all devices on the network, which can lead to broadcast storms if too many devices send broadcast frames simultaneously, resulting in network congestion and performance issues.
- **Security Vulnerabilities:**  The Ethernet frame format does not include built-in security features, making Ethernet networks vulnerable to security threats such as eavesdropping and [spoofing](https://www.geeksforgeeks.org/computer-networks/what-is-spoofing-in-cyber-security/) .
- **Limited Speed:**  Ethernet networks have a limited maximum speed, which may not be sufficient for high-speed applications or large-scale networks.
- **Limited Distance:**  The maximum distance between two devices on an Ethernet network is limited, which can restrict the physical coverage of the network.
## Conclusion
A fundamental aspect associated with network communication is Ethernet frame format specified under IEEE 802.3 standard. It enables one reliable and flexible way of sending data through the network. Even though it’s rather basic and widely utilized, it has its drawbacks such as maximum frame size and likelihood of security attacks. Thus, there is need for [Ethernet](https://www.geeksforgeeks.org/computer-networks/what-is-ethernet/) professionals to comprehend this format in order to efficiently design, implement or troubleshoot any Ethernet-based [local area network (LAN)](https://www.geeksforgeeks.org/computer-networks/lan-full-form/).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/ethernet-frame-format/)

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
