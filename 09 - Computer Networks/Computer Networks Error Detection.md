---
title: "Error Detection in Computer Networks"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/error-detection-in-computer-networks/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Error Detection in Computer Networks
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/error-detection-in-computer-networks/)

---

# Error Detection in Computer Networks

Error detection is a technique used in computer networks to identify whether transmitted data has been corrupted during communication. The sender adds redundant bits to the data before transmission, and the receiver verifies the integrity of the received frame by checking these bits. If an error is detected, the corrupted frame is discarded, and retransmission may be requested through appropriate error control mechanisms.
- Detects errors caused by noise, interference, or signal distortion
- Relies on redundant bits for consistency checking
- Common techniques include Parity Check, Checksum, and Cyclic Redundancy Check (CRC)
- Helps maintain data integrity and reliable communication
## Types of Errors
### 1. Single-Bit Error
A single-bit error occurs when **only one bit** of the transmitted data unit is altered during transmission, resulting in corrupted data.
![cn1](assets/cn1-5e7ecf42b7.webp)
Single-Bit Error
###
### 2. Burst Error
A burst error occurs when two or more consecutive bits in a data unit are corrupted during transmission.
![cn2](assets/cn2-14680e848e.webp)
Burst Error
## Error Detection Methods
To detect errors, a common technique is to introduce redundancy bits that provide additional information. Various techniques for error detection include:
- Simple Parity Check
- Two-Dimensional Parity Check
- Checksum
- Cyclic Redundancy Check (CRC)
## 1. Simple Parity Check
Simple bit parity is a basic error detection technique in which an extra bit, called a parity bit, is added to a data unit before transmission. This parity bit helps the receiver determine whether the transmitted data has been corrupted.
- Detects all single-bit errors in transmitted data.
- Detects any odd number of bit errors, since odd bit changes alter the parity.
- Easy to implement in both hardware and software.
- Fails to detect errors when an even number of bits are corrupted.
- Not suitable for noisy communication channels with frequent errors.
Parity bits are used to maintain a specific parity condition in the data. There are two types of parity:
- **Even Parity**: The parity bit is set so that the total number of 1s in the data (including the parity bit) is even.
- **Odd Parity**: The parity bit is set so that the total number of 1s in the data (including the parity bit) is odd.
![sender](assets/sender-8d99a88b4e.webp)
Simple Parity Check
This scheme makes the total number of 1’s even, that is why it is called even parity checking.
## 2. Two-Dimensional Parity Check
In two-dimensional parity check, parity bits are calculated for each row, similar to a simple parity check. In addition, parity bits are also computed for each column. These row and column parity bits are transmitted along with the data. At the receiver, parity bits are recalculated and compared with the received parity bits to detect errors.
- Can detect and correct all single-bit errors by identifying the exact row and column where the error occurred.
- Can detect many multiple-bit errors occurring at different positions in the data matrix.
- Provides better error detection capability than simple parity check.
- Certain patterns of multiple-bit errors may remain undetected.
- If parity bits themselves are corrupted, error detection may fail.
![original_data](assets/original_data-9d20b1b22e.webp)
2-D Parity Check
## 3. Checksum
Checksum is an error detection technique used to detect errors in transmitted data. In this method, the sender divides the data into fixed-size segments and computes a checksum using [1’s complement](https://www.geeksforgeeks.org/digital-logic/ones-complement/) arithmetic. The computed checksum is transmitted along with the data. At the receiver, the same computation is performed to verify data integrity.
- Can detect many types of errors, including single-bit and multiple-bit errors.
- Provides better error detection than simple parity and two-dimensional parity checks.
- Widely used in networking protocols such as IP, TCP, and UDP.
- Fast to compute and easy to implement in software.
- Supports only error detection and does not provide error correction.
- Some error patterns may go undetected, especially when errors cancel each other during addition.
- Less reliable compared to advanced techniques like Cyclic Redundancy Check (CRC).
### **Checksum - Operation at Sender's Side**
- The data is divided into k segments, each of m bits.
- All segments are added using 1’s complement arithmetic.
- The 1’s complement of the final sum is calculated to generate the checksum.
- The checksum is appended to the data and transmitted to the receiver.
### **Checksum - Operation at Receiver's Side**
- All received segments, including the checksum, are added using 1’s complement arithmetic.
- If the final result is all 1s, the data is considered error-free..
- Otherwise, the data is discarded, indicating that an error has occurred.
### reciever Checksum at Receiver 's and Sender's Side
> Read more about [Checksum](https://www.geeksforgeeks.org/computer-networks/error-detection-code-checksum/)
## 4. Cyclic Redundancy Check (CRC)
- CRC is based on binary division, unlike checksum which uses addition; redundant CRC bits are appended so the transmitted data becomes exactly divisible by a predefined generator polynomial.
- At the receiver, the data is divided using the same polynomial; a zero remainder means the data is accepted, while a non-zero remainder indicates transmission errors.
- Highly effective in detecting single-bit, multiple-bit, and burst errors, making it more reliable than parity checks and checksum methods.
- Widely used in communication protocols such as Ethernet, HDLC, and USB due to its strong error detection capability.
- Provides only error detection, not error correction; its effectiveness depends on the chosen generator polynomial.
- More computationally complex than simple parity or checksum methods and introduces additional processing overhead.
### divisor CRC **CRC Working**
We have given dataword of length n and divisor of length k.
**Step 1:** Append (k-1) zero's to the original message
**Step 2:** Perform modulo 2 division
**Step 3:** Remainder of division = CRC
**Step 4:** Code word = Data with append k-1 zero's + CRC
**Note:**
- CRC must be k-1 bits
- Length of Code word = n+k-1 bits
**Example**: Let's data to be send is 1010000 and divisor in the form of polynomial is x3+1. CRC method discussed below.
### original_message CRC Working
> To learn about CRC in detail, refer to: [Cyclic Redundancy Check(CRC)](https://www.geeksforgeeks.org/videos/cyclic-redundancy-checkcrc/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/error-detection-in-computer-networks/)

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
> - [[Controlled Access Protocols]]
> - [[Difference between Byte stuffing and Bit stuffing]]
> - [[Efficiency of CSMA CD]]
> - [[Efficiency of Token Ring]]
