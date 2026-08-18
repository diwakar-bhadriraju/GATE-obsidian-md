---
title: "Floating Point Representation"
subject: "Digital Logic and Design"
topic: "Number Representation and Computer Arithmetic"
source: "https://www.geeksforgeeks.org/digital-logic/introduction-of-floating-point-representation/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Number Representation and Computer Arithmetic"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/number-representation-and-computer-arithmetic
---


> [!abstract] Floating Point Representation
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Number Representation and Computer Arithmetic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/introduction-of-floating-point-representation/)

---

# Floating Point Representation

The floating-point representation is a way to encode numbers in a format that can handle very large and very small values. It is based on scientific notation where numbers are represented as a fraction and an exponent. In computing, this representation allows for a trade-off between range and precision.
**Format:** A floating point number is typically represented as:
![algebra](assets/algebra-9fe1b48c0e.webp)
Value = Sign × Significand × BaseExponent
**Where:**
- Sign: Indicates whether the number is positive or negative.
- Significand (Mantissa): Represents the precision bits of the number.
- Base: Usually 2 in binary systems.
- Exponent: Determines the scale of the number.
## Need for Floating-Point Representation
The floating-point representation is crucial because:
- **Range:** It can represent a wide range of values from the very large to very small numbers.
- **Precision:** It provides a good balance between the precision and range, making it suitable for the scientific computations, graphics and other applications where exact values and wide ranges are necessary.
- **Flexibility:** It adapts to different scales of numbers allowing for the efficient storage and computation of real numbers in the computer systems.
## Number System and Data Representation
- **Number Systems:** The Floating point representation often uses binary (base-2) systems for the digital computers. Other number systems like decimal (base-10) or hexadecimal (base-16) may be used in the different contexts.
- **Data Representation:** This includes how numbers are stored in the computer memory involving binary encoding and the representation of the various data types.
### Table-Precision Representation
| Precision | Base | Sign | Exponent | Significant |
| --- | --- | --- | --- | --- |
| Single precision | 2 | 1 | 8 | 23+1 |
| Double precision | 2 | 1 | 11 | 52+1 |
## Components of Floating Point Numbers
The three components of floating point numbers are:
- **Sign bit**: Indicates positive or negative number.
- **Exponent**: Represents the power to which the base (usually 2) is raised.
- **Mantissa (Significand)**: Represents the significant digits of the number.
## Floating Point to Decimal Conversion
To convert the floating point into decimal, we have 3 elements in a 32-bit floating point representation: 
**Sign** bit is the first bit of the binary representation. '1' implies negative number and '0' implies positive number. **Example:**
> 11000001110100000000000000000000
This is negative number.
**Exponent** is decided by the next 8 bits of binary representation. 127 is the unique number for 32 bit floating point representation. It is known as bias. It is determined by 2k-1 -1 where 'k' is the number of bits in exponent field. 
There are 3 exponent bits in 8-bit representation and 8 exponent bits in 32-bit representation.
Thus
> bias = 3 for 8 bit conversion (23-1 -1 = 4-1 = 3) 
> bias = 127 for 32 bit conversion. (28-1 -1 = 128-1 = 127) 
**Example:**
> 01000001110100000000000000000000 
> 10000011 = (131)10 
> 131-127 = 4 
>
> Hence the exponent of 2 will be 4 i.e. 24 = 16.
**Mantissa** is calculated from the remaining 23 bits of the binary representation. It consists of '1' and a fractional part which is determined by: 
**Example:** 
> 01000001110100000000000000000000 
The fractional part of mantissa is given by: 
> 1\*(1/2) + 0\*(1/4) + 1\*(1/8) + 0\*(1/16) +......... = 0.625 
Thus the mantissa will be
> 1 + 0.625 = 1.625 
The decimal number hence given as:
> Sign\*Exponent\*Mantissa = (-1)0\*(16)\*(1.625) = 26
## Decimal to Floating Point Conversion
To convert the decimal into floating point, we have 3 elements in a 32-bit floating point representation: 
    i) Sign (MSB) 
    ii) Exponent (8 bits after MSB) 
    iii) Mantissa (Remaining 23 bits) 
**Sign bit** is the first bit of the binary representation. '1' implies negative number and '0' implies positive number. 
Example: To convert -17 into 32-bit floating point representation Sign bit = 1
**Exponent** is decided by the nearest smaller or equal to 2n number. For 17, 16 is the nearest 2n. Hence the exponent of 2 will be 4 since 24 = 16. 127 is the unique number for 32 bit floating point representation. It is known as bias. It is determined by 2k-1 -1 where 'k' is the number of bits in exponent field. 
> Thus bias = 127 for 32 bit. (28-1 -1 = 128-1 = 127) 
>
> Now, 127 + 4 = 131
>
> i.e. 10000011 in binary representation.
**Mantissa:** 17 in binary = 10001.
Move the binary point so that there is only one bit from the left. Adjust the exponent of 2 so that the value does not change. This is normalizing the number. 1.0001 x 24. Now, consider the fractional part and represented as 23 bits by adding zeros.
> 00010000000000000000000
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/introduction-of-floating-point-representation/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Number Representation and Computer Arithmetic

> [!note] Related notes
>
> - [[Booth’s Algorithm]]
> - [[Code Converters – BCD(8421) to from Excess-3]]
> - [[Code Converters – Binary to from Gray Code]]
> - [[Computer Arithmetic Set – 1]]
> - [[Computer Arithmetic Set – 2]]
> - [[Last Minute Notes – Digital Electronics]]
> - [[Non-Restoring Division For Unsigned Integer]]
> - [[Number System and base conversions]]
> - [[Program for Binary To Decimal Conversion]]
> - [[Program for Decimal to Binary Conversion]]
