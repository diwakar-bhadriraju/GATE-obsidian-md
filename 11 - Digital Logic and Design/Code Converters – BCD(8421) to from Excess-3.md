---
title: "Code Converters - BCD(8421) to/from Excess-3"
subject: "Digital Logic and Design"
topic: "Number Representation and Computer Arithmetic"
source: "https://www.geeksforgeeks.org/digital-logic/code-converters-bcd8421-to-from-excess-3/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Number Representation and Computer Arithmetic"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/number-representation-and-computer-arithmetic
---


> [!abstract] Code Converters - BCD(8421) to/from Excess-3
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Number Representation and Computer Arithmetic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/code-converters-bcd8421-to-from-excess-3/)

---

# Code Converters - BCD(8421) to/from Excess-3

Binary codes enable the representation and processing of numerical data in binary format. BCD (8421) and Excess-3 are binary codes widely used for encoding decimal numbers in computing and digital electronics. Converting between BCD and Excess-3 is essential in systems like calculators, digital displays and error detection circuits where efficient number handling is required.
- Binary Coded Decimal (BCD) employs 4-bit binary numbers to represent every decimal digit between 0 and 9.
- Excess-3 is a non-weighted binary code that results from adding 3 to the equivalent BCD value.
- Code converters perform the conversion between BCD and Excess-3 automatically, providing precise interpretation of data in digital circuits.
- These conversions are applied to digital clocks, arithmetic circuits, and digital instruments for their ease of simplifying hardware logic and enhancing reliability.
## Understanding BCD (8421) and Excess-3 Codes
### 1. BCD (8421) Code
BCD (Binary Coded Decimal) is a way to represent each decimal digit individually using binary numbers. The most common form, called the 8421 code, assigns a unique 4-bit binary number to each decimal digit from 0 to 9.
> 0 is represented as 0000
> 1 is represented as 0001
> 2 is represented as 0010
> 3 is represented as 0011
> 4 is represented as 0100
> 5 is represented as 0101
> 6 is represented as 0110
> 7 is represented as 0111
> 8 is represented as 1000
> 9 is represented as 1001
For example,
Let's take the decimal number **59**.
- The digit **5** in BCD (8421) is **0101**
- The digit **9** in BCD (8421) is **1001**
So, the decimal number **59** is represented in BCD as **0101 1001**.
The 8421 code is widely used in applications that require precise decimal calculations, such as digital clocks, calculators, and financial systems. By encoding each digit separately, BCD simplifies arithmetic operations and makes converting between decimal and binary straightforward, ensuring fast and reliable digital processing.
### **2. Excess-3 Code**
Excess-3 code is a BCD code where each decimal digit is represented by its 4-bit binary value plus 3. For example, decimal 0 is 0011 in Excess-3 (0 + 3 = 3 in binary). This code is self-complementary, meaning the 1's complement of an Excess-3 number equals the Excess-3 code of the 9's complement of the decimal digit.
For example,
> Decimal 3 in BCD is 0011; in Excess-3, it is 0110 (3 + 3).
>
> The 1's complement of 0110 is 1001, which is the Excess-3 code for 6 (9 - 3), showing the self-complementary property.
>
> Excess-3 simplifies subtraction and complements in digital systems by allowing bit inversion to find 9's complements.
## Converting BCD(8421) to Excess-3
As is clear by the name, a BCD digit can be converted to its corresponding Excess-3 code by simply adding 3 to it. Since we have only 10 digits(0 to 9) in decimal, we don't care about the rest and marked them with a cross(X).
Let A, B, C and D be the bits representing the binary numbers, where D is the LSB and A is the MSB, and let w, x, y and z be the bits representing the gray code of the binary numbers, where z is the LSB and w is the MSB. 
The truth table for the conversion is given below. The X's mark is don't care condition. 
![](assets/Screenshot3-1da709c734.png)
To find the corresponding digital circuit, we will use the [K-Map](https://www.geeksforgeeks.org/digital-logic/introduction-of-k-map-karnaugh-map/) technique for each of the Excess-3 code bits as output with all of the bits of the BCD number as input.
![35777](assets/35777-e52d93b883.png)
Corresponding minimized Boolean expressions for Excess-3 code bits:
> **w** = **A** + **BC** + **BD**
> **x** = **B**′**C** + **B**′**D** + **BC**′**D**′
The corresponding digital circuit:
![](assets/bcd-circuit-daa964ef1d.jpg)
## Converting Excess-3 to BCD(8421)
Excess-3 code can be converted back to BCD in the same manner. 
Let A, B, C and D be the bits representing the binary numbers, where D is the LSB and A is the MSB, and 
let w, x, y and z be the bits representing the gray code of the binary numbers, where z is the LSB and w is the MSB. 
The truth table for the conversion is given below. The X's mark is don't care condition. 
![](assets/Screenshot4-cb14405293.png)
**K-Map for D**
![](assets/bcd-dkmap-0a4a233618.jpg)
**K-Map for C**
![](assets/bcd-ckmap-18297db44c.jpg)
**K-Map for B**
![](assets/bcd-bkmap-7b794265fe.jpg)
**K-Map for A**
![](assets/bcd-kmapa-1-300x272-3f2b71ff88.jpg)
Corresponding minimized Boolean expressions for Excess-3 code bits:
> **A** = **wx** + **wyz**
> **B** = **x**′**y**′ + **x**′**z**′ + **xyz**
> **C** = **y**′**z** + **yz**′
> **D** = **z**′
The corresponding digital circuit:
Here E3​, E2​, E1​ and E0​ correspond to w, x, y and z and B3, B2, B1 and B0 correspond to A, B, C and D.
![Excess-3 to BCD](assets/BCD-excess-3-circuit-cf2cb81b92.jpg)
## Difference Between BCD and Excess-3
| Feature | BCD | Excess-3 |
| --- | --- | --- |
| Coding Method | Represents directly each decimal digit with its binary equivalent. | Represents each decimal digit with its binary equivalent plus 3. |
| Value range | Encodes decimal digits 0-9. | Encodes decimal digits 3-12 (with 0-9 wrapped around). |
| Arithmetic Operations | Additional logic needed for arithmetic operations. | Arithmetic operations are simplified by self- complementary. |
| Error Detection | Not very effective in detecting and correcting errors. | It is better in the error detection capability since it applies an encoding technique. |
| Complement Operation | The operation is slightly harder in implementing complex operations. | Complement operation in a more straightforward way due to self-complementing nature. |
| Binary Representation | Uses 4-bit binary to represent each decimal digit. | Uses 4-bit binary, but added 3 to the binary representation of each decimal digit. |
| Conversion Complexity | Direct conversion to/from decimal. | For conversion, add or subtract 3 for the binary value. |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/code-converters-bcd8421-to-from-excess-3/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Number Representation and Computer Arithmetic

> [!note] Related notes
>
> - [[Booth’s Algorithm]]
> - [[Code Converters – Binary to from Gray Code]]
> - [[Computer Arithmetic Set – 1]]
> - [[Computer Arithmetic Set – 2]]
> - [[Floating Point Representation]]
> - [[Last Minute Notes – Digital Electronics]]
> - [[Non-Restoring Division For Unsigned Integer]]
> - [[Number System and base conversions]]
> - [[Program for Binary To Decimal Conversion]]
> - [[Program for Decimal to Binary Conversion]]
