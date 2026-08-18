---
title: "Booth's Algorithm"
subject: "Digital Logic and Design"
topic: "Number Representation and Computer Arithmetic"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-booths-algorithm/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Number Representation and Computer Arithmetic"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/number-representation-and-computer-arithmetic
---


> [!abstract] Booth's Algorithm
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Number Representation and Computer Arithmetic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-booths-algorithm/)

---

# Booth's Algorithm

Booth’s algorithm is a method for multiplying signed binary numbers in two’s complement representation. It improves efficiency by minimizing the number of required arithmetic operations.
- The method works by examining pairs of adjacent bits in the multiplier and deciding whether to add, subtract, or do nothing with the multiplicand, followed by an arithmetic shift.
- This approach simplifies handling of consecutive sequences of 1s or 0s, making multiplication faster and more effective than the standard binary method.
**Hardware Implementation of Booth's Algorithm**
The hardware implementation of the booth algorithm requires the register configuration shown in the figure below:                                                         ![](assets/booth2-3236fff2d5.png)
## **Booth's Algorithm Flowchart**
We name the registers as AC, BR and QR, respectively. Qn designates the least significant bit of the multiplier in the register QR. An extra flip-flop Qn+1is appended to QR to facilitate a double inspection of the multiplier. The flowchart for the booth algorithm is shown below:
![BoothsAlgo](assets/BoothsAlgo-5018dada81.webp)
Booth’s Algorithm Flowchart
### Booth’s Algorithm Steps
Initialize AC = 0, Qₙ₊₁ = 0, and set SC = n (number of bits in the multiplier).
Check the two least significant bits (Qₙ and Qₙ₊₁).
 If (Qₙ, Qₙ₊₁) = 10, perform AC = AC − BR (subtract multiplicand).
 If (Qₙ, Qₙ₊₁) = 01, perform AC = AC + BR (add multiplicand).
 If (Qₙ, Qₙ₊₁) = 00 or 11, no operation is performed (AC remains unchanged).
Perform an arithmetic right shift (ashr) on the combined register (AC, QR, Qₙ₊₁), preserving the sign bit of AC.
Decrement the sequence counter (SC).
If SC ≠ 0, repeat the steps starting from checking (Qₙ, Qₙ₊₁).
After all iterations, the final product is obtained in the combined register (AC, QR).
**Example -** A numerical example of booth's algorithm is shown below for n = 4. It shows the step by step multiplication of -5 and -7.
**Step-by-Step Execution:**
**Iteration 1:**
 Qₙ Qₙ₊₁ = 10
 Perform AC = AC − BR = 0101
 Arithmetic right shift of (AC, QR, Qₙ₊₁):
 AC = 0010, QR = 1100, Qₙ₊₁ = 1
 SC = 3
**Iteration 2:**
 Qₙ Qₙ₊₁ = 01
 Perform AC = AC + BR = 1101
 Arithmetic right shift of (AC, QR, Qₙ₊₁):
 AC = 1110, QR = 1110, Qₙ₊₁ = 0
 SC = 2
**Iteration 3:**
 Qₙ Qₙ₊₁ = 00
 No operation
 Arithmetic right shift of (AC, QR, Qₙ₊₁):
 AC = 1111, QR = 0111, Qₙ₊₁ = 0
 SC = 1
**Iteration 4:**
 Qₙ Qₙ₊₁ = 10
 Perform AC = AC − BR → AC = 0100
 Arithmetic right shift of (AC, QR, Qₙ₊₁):
 AC = 0010, QR = 0011, Qₙ₊₁ = 1
 SC = 0
Product is calculated as follows:
> Product = AC QR
> Product = 0010 0011 = 35
## **Application of Booth's Algorithm**
- **Processors and ALUs:** Booth’s Algorithm enables efficient signed multiplication inside microchips and processors by reducing the number of additions/subtractions, leading to faster arithmetic logic unit (ALU) operations essential for computing, graphics, and cryptography.
- **Digital Signal Processing (DSP):** It accelerates multiplication tasks in DSP applications such as filtering and convolution for real-time audio, video, and signal processing.
- **Hardware Accelerators:** Specialized hardware for image processing, neural networks, and AI use Booth’s Algorithm to speed up multiplication operations.
- **Cryptography:** Cryptographic operations involving large-number exponentiation benefit from faster multiplication with Booth’s Algorithm, improving encryption and signature processes.
- **High-Performance Computing (HPC):** Large-scale scientific and mathematical computations employ Booth’s Algorithm for optimized multiplication, enhancing overall system performance.
- **Embedded Systems:** Resource-limited embedded devices improve multiplication efficiency and power consumption by using Booth’s Algorithm.
- **Network Packet Processing:** Booth’s Algorithm helps efficient multiplication in network devices for operations on packet headers and payloads.
Basically, Corner's Calculation finds its application any place productive paired duplication is required, particularly in situations where speed, power proficiency, and equipment streamlining are significant elements.
**Best Case and Worst Case :** Best case is when there is a large block of consecutive 1's and 0's in the multipliers, so that there is minimum number of logical operations taking place, as in addition and subtraction. Worst case is when there are pairs of alternate 0's and 1's, either 01 or 10 in the multipliers, so that maximum number of additions and subtractions are required. **GATE Practice Questions -**
1. [GATE IT 2008 | Question 40](https://www.geeksforgeeks.org/questions/the-two-numbers-given-below-are-multiplied-using-the/)
2. [GATE IT 2006 | Question 38](https://www.geeksforgeeks.org/questions/when-multiplicand-y-is-multiplied-by-multiplier-x/)
3. [GATE IT 2005 | Question 8](https://www.geeksforgeeks.org/questions/using-booths-algorithm-for-multiplication-the-multiplier-57-will/)
4. [GATE CS 1996 | Question 23](https://www.geeksforgeeks.org/questions/booths-algorithm-for-integer-multiplication-gives-worst-performance-when/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-booths-algorithm/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Number Representation and Computer Arithmetic

> [!note] Related notes
>
> - [[Code Converters – BCD(8421) to from Excess-3]]
> - [[Code Converters – Binary to from Gray Code]]
> - [[Computer Arithmetic Set – 1]]
> - [[Computer Arithmetic Set – 2]]
> - [[Floating Point Representation]]
> - [[Last Minute Notes – Digital Electronics]]
> - [[Non-Restoring Division For Unsigned Integer]]
> - [[Number System and base conversions]]
> - [[Program for Binary To Decimal Conversion]]
> - [[Program for Decimal to Binary Conversion]]
