---
title: "Difference between Byte stuffing and Bit stuffing"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/difference-between-byte-stuffing-and-bit-stuffing/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Difference between Byte stuffing and Bit stuffing
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/difference-between-byte-stuffing-and-bit-stuffing/)

---

# Difference between Byte stuffing and Bit stuffing

In Data Communication Bit and Byte both techniques ensure that special control information which is being correctly transmitted without any mistake. Framing, which is the division of a stream of bits from the network layer into manageable units (called frames). Each frame consists of the sender's address and a destination address. The destination address defines where the packet is to go and the sender's address helps the recipient acknowledge the receipt. So, there are two ways to overcome this problem:
1. Using Byte stuffing (or character stuffing)
2. Using Bit stuffing
## What is Byte stuffing?
Byte stuffing is a technique used in data communication to assure that unique control characters under a data stream are not wrongly interpreted as part of the actual data. This method is commonly used in communication protocols that use particular byte sequences to signal the start and end of data frames.
## How Byte Stuffing Works?
In several communication protocols, particular byte sequences are allocated for control goals, such as analyzing the start or end of a frame. For example, a protocol might use the byte 0x7E to indicate the start and end of a frame. Although, if this byte appears naturally in the data being transmitted, it could cause the receiver to accidentally interpret it as the end of the frame, causing errors.
**To prevent this, byte stuffing is used**:
1. **Identify Control Characters:** When the sender comes across a control character inside the data, it adds an additional byte (typically an escape character, like 0x7D) preceding the control character.
2. **Modify the Data:** If the data includes a byte that corresponds to the control character (e.g., 0x7E), the sender adds an escape byte before it. If the data includes the escape byte itself, the sender also inserts another escape byte to differentiate it.
3. **Transmit the Data:** The modified (stuffed) data is then transmitted to the receiver.
4. **Unstuffing at the Receiver:** Upon receiving the data, the receiver detects the escape character and knows to treat the following byte as data, not as a control character. The escape character is then removed, restoring the original data.
## Applications
Byte stuffing is mostly used in protocols like [PPP](https://www.geeksforgeeks.org/computer-networks/point-to-point-protocol-ppp-frame-format/) (Point-to-Point Protocol) and in sequential communication protocols. By assuring that control characters inside the data are suitably managed, byte stuffing helps keep clear communication, avoiding data loss or error.
Bit stuffing is a technique implemented in data communication to restrict specific bit patterns in the data to stop from being confused with control signals, such as frame delimiters. This technique is particularly helpful in protocols that send data as a continuous stream of bits, where sure bit patterns are occupied for signaling the start or end of a frame.
## What is Bit stuffing?
Bit stuffing is a technique implemented in data communication to restrict specific bit patterns in the data to stop from being confused with control signals, such as frame delimiters. This technique is particularly helpful in protocols that send data as a continuous stream of bits, where sure bit patterns are occupied for signaling the start or end of a frame.
## How Bit Stuffing Works?
Across several transmission protocols, a specific sequence of bits is used to indicate the limits of a data frame. For example, a common bit arrangement used as a frame marker might be "01111110". Although, if this bit sequence appears naturally within the data payload, it could be mistakenly interpreted as the start or end of a frame, leading to errors in data interpretation.
**To avoid this issue, bit stuffing is used:**
1. **Identify Bit Pattern:** The sender monitors the data stream for a bit pattern that matches the one used as a frame delimiter. Typically, this is a sequence of five or more consecutive "1"s.
2. **Insert a Bit:** Whenever the sender detects five consecutive "1"s in the data, it automatically inserts a "0" bit immediately after this sequence. This insertion breaks up the pattern so that it no longer matches the frame delimiter.
3. **Transmit the Data:** The modified (stuffed) bit stream is then transmitted to the receiver.
4. **Unstuffing at the Receiver:** Upon receiving the data, the receiver identifies sequences of five consecutive "1"s followed by a "0". The receiver then removes this "0" bit, restoring the original data stream.
## Example of Bit Stuffing
Suppose the data to be transmitted includes the bit sequence 0111110110. Since 0111110 is a common frame delimiter, the protocol requires bit stuffing. The sender would insert a "0" after the first five "1"s, changing the sequence to 01111100110. The receiver, upon recognizing the stuffed "0", would remove it to reconstruct the original bit sequence.
## Applications
Bit stuffing is widely used in protocols like [HDLC](https://www.geeksforgeeks.org/computer-networks/basic-frame-structure-of-hdlc/) (High-Level Data Link Control) and CAN (Controller Area Network) in automotive and industrial applications. These protocols require precise frame delimiting to ensure reliable communication, and bit stuffing provides a straightforward way to differentiate control signals from actual data.
## Difference Between Byte Stuffing and Bit Stuffing
**Byte stuffing** and **bit stuffing** are two techniques used to handle frame boundaries in data link protocols. While both methods serve to prevent accidental framing, their approaches differ significantly.
| Feature | Byte stuffing | Bit stuffing |
| --- | --- | --- |
| Definition | Byte stuffing is used to prevent the occurrence of a specific byte in a data stream by adding an extra byte. | Bit stuffing is used to prevent the occurrence of a specific bit sequence in a data stream by inserting an additional bit. |
| Concept | Adds an extra byte to the data when a special byte is found. | Adds an extra bit to the data when a special bit pattern is found. |
| Special byte/bit | Flag byte (01111110) | Flag bit pattern (01111110) |
| Insertion | Extra byte is inserted after each occurrence of the flag byte. | Extra bit is inserted after each occurrence of the flag bit pattern. |
| Removal | The extra byte is removed at the receiver end. | The extra bit is removed at the receiver end. |
| Efficiency | Less efficient due to the addition of an extra byte. | More efficient as only an extra bit is added. |
| Applications | Adopted in protocols like PPP and HDLC. | Adopted in protocols like Ethernet and Token Ring. |
| Objective | To prevent data loss due to errors caused by the presence of a specific byte in the data stream. | To prevent data loss due to errors caused by the presence of a specific byte in the data stream. |
| How it works | The specific byte is replaced with a unique escape byte, followed by a second byte that indicates the original byte's value. | The specific bit sequence is replaced with a unique bit sequence that indicates the original bit sequence's value. |
| Overhead | Adds overhead to the data stream by adding an extra byte for every occurrence of the specific byte. | Adds overhead to the data stream by adding an extra bit for every occurrence of the specific bit sequence. |
| Efficiency | Less efficient than bit stuffing, as it requires the addition of an entire byte to the data stream. | More efficient than byte stuffing, as it requires the addition of only one bit to the data stream. |
| Usage | Typically used in protocols that use fixed-length frames or packets, such as PPP and HDLC. | Typically used in asynchronous transmission, such as in serial communication, and protocols that use variable-length frames or packets, such as Ethernet. |
**Byte stuffing** is a byte (usually escape character(ESC)), which has a predefined bit pattern is added to the data section of the frame when there is a character with the same pattern as the flag. Whenever the receiver encounters the ESC character, it removes it from the data section and treats the next character as data, not a flag. But the problem arises when the text contains one or more escape characters followed by a flag.
Example:
![Byte stuffing](assets/Bit_Byte_Stuffing_1-f76a84766f.jpg)
**Bit stuffing -** Mostly flag is a special 8-bit pattern "01111110" used to define the beginning and the end of the frame. Problem with the flag is the same as that was in the case of byte stuffing. So, in this protocol what we do is, if we encounter 0 and five consecutive 1 bits, an extra 0 is added after these bits. This extra stuffed bit is removed from the data by the receiver. The extra bit is added after one 0 followed by five 1 bits regardless of the value of the next bit. Also, as the sender side always knows which sequence is data and which is flag it will only add this extra bit in the data sequence, not in the flag sequence. 
Example: 
![Bit stuffing](assets/Bit_Byte_Stuffing_2-4b93a05226.jpg)
**Byte stuffing:** It is used to convert a message format of a sequence of bytes that may contain reserved values into another byte sequence that does not contain reserved values. It is also known as character-oriented framing. Here, a special byte is stuffed before flag and esc also that special byte is escape(ESC).
**Bit stuffing:** It is used for inserting one or more non-information bits into a message to be transmitted, to break message sequence for synchronization. It is also known as bit-oriented framing. Here,0 bit stuffed after five consecutive 1 bits.i.e extra bit is added after five consecutive ones.
## Conclusion
Bit and byte stuffing are essential techniques in digital communication for maintaining data integrity and ensuring that the transmitted data is not mistakenly interpreted as control information. By inserting additional bits or bytes into the data stream, these methods prevent the data from mimicking control characters or bit patterns that are critical for framing and synchronization. As a result, they play a crucial role in enabling reliable and accurate data transmission across various communication protocols. Understanding and implementing these techniques are fundamental to designing robust communication systems that can handle diverse data without compromising on accuracy or efficiency.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/difference-between-byte-stuffing-and-bit-stuffing/)

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
> - [[Efficiency of CSMA CD]]
> - [[Efficiency of Token Ring]]
