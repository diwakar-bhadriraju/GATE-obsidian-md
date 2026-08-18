---
title: "Programmable Logic Array"
subject: "Digital Logic and Design"
topic: "Combinational Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/programmable-logic-array/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Combinational Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/combinational-circuit
---


> [!abstract] Programmable Logic Array
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Combinational Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/programmable-logic-array/)

---

# Programmable Logic Array

A Programmable Logic Array (PLA) is a digital device used to build custom combinational logic circuits. It contains programmable [**AND**](https://www.geeksforgeeks.org/digital-logic/and-gate/) and [**OR**](https://www.geeksforgeeks.org/digital-logic/or-gate/) gate networks, allowing the user to set up the logic functions needed for a specific task. Since PLAs are not given a fixed function during manufacturing, they can be configured before use to perform a variety of logic operations, making them a flexible option for creating specialized hardware designs.
- **Programmable AND and OR Gates:** PLA has two types of arrays, namely programmable AND gate array and programmable OR gate array so that the logic circuits can be designed in any way.
- **Reconfigurability:** As compared with other logic devices, the operation of PLAs is highly flexible, and these devices may be easily programmed to perform any of the numerous logical functions.
- **Partial Minterm Generation:** It is also to be noted here that PLA does not provide the full decoding of variables like [ROM](https://www.geeksforgeeks.org/computer-organization-architecture/read-only-memory-rom/) but it functions only on the necessary minterms.
- **Combination of Memory and Logic:** PLA has both the memory and the logic features, hence making it suitable for various applications.
## Basic Block Diagram for PLA
![n_x_k_fuses](assets/n_x_k_fuses-363496223e.webp)
The following truth table will be helpful in understanding the function on no of inputs: 
| A | B | C | F1 | F2 |
| --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 0 | 0 |
| 0 | 1 | 0 | 0 | 0 |
| 0 | 1 | 1 | 1 | 0 |
| 1 | 0 | 0 | 0 | 1 |
| 1 | 0 | 1 | 1 | 1 |
| 1 | 1 | 0 | 1 | 0 |
| 1 | 1 | 1 | 1 | 1 |
> F1 = AB'C' + ABC' + ABC 
> on simplifying we get : F1 = AC' + AB 
> F2 = A'BC + AB'C + ABC 
> on simplifying we get: F2 = BC + AC 
**For the realization of the** **above function following circuit diagram will be used.** 
![](assets/2-52-beabf7e2c8.png)
PLA is used for the implementation of various combinational circuits using a buffer, AND gate, and OR gate. In PLA, all the minterms are not realized but only required minterms are implemented. As PLA has a programmable AND gate array and a programmable OR gate array, it provides more flexibility but the disadvantage is, it is not easy to use. 
### The Operation of a PLA can be Summarized in Three Steps
1. **Programming**: The user defines the logic function to be implemented by the PLA by programming the input and output configurations into the device.
2. **Product term generation**: The inputs are applied to the AND gate array to produce a set of product terms.
**3. Sum term generation:** The product terms are then applied to the OR gate array to generate the final output.
PLAs are often used in digital systems as they are versatile and allow complex functions to be implemented easily. They are particularly useful for implementing Boolean expressions with many variables as the arrays of [AND gates](https://www.geeksforgeeks.org/digital-logic/and-gate/) and OR gates can be configured to handle large numbers of inputs.
## Comparison with other Programmable Logic Devices
- PLA has a programmable AND gate array and programmable OR gate array.
- PAL has a programmable AND gate array but a fixed OR gate array.
- ROM has a fixed AND gate array but programmable OR gate array.
- PLA is similar to a ROM in concept it does not provide full decoding of variables and does not generate all minterms as in the ROM.
- Though its name consists of the word "programmable", it does not require any type of programming like in C and C++.
## Applications
- PLA is used to provide control over datapath.
- PLA is used as a counter.
- PLA is used as a [decoder](https://www.geeksforgeeks.org/digital-logic/binary-decoder-in-digital-logic/).
- PLA is used as a BUS interface in programmed I/O.
## Advantages
- **Flexibility:** Both the programmable AND gates and also the programmable [OR gates](https://www.geeksforgeeks.org/digital-logic/or-gate/) offer the beneficial benefits of being used in a number of combinational circuits.
- **Efficient Minterm Usage:** It will only implement the necessary minterms thus making the design compact and more efficient.
- **Reconfigurability:** The PLAs can be reconfigured to perform different logic functions depending with the requirements of an application.
## Disadvantages
- **Complexity:** PLAs are slightly different from other programmable logic devices due to their high flexibility that makes the usage of PLAs a little complicated.
- **Cost:** It has higher cost as compared to the least complex logic devices such as PALs but it offers programming and flexible control.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/programmable-logic-array/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Combinational Circuit

> [!note] Related notes
>
> - [[BCD Adder]]
> - [[BCD to 7 Segment Decoder]]
> - [[Binary Decoder]]
> - [[Carry Look-Ahead Adder]]
> - [[Combinational circuits using Decoder]]
> - [[De-MUX]]
> - [[Encoder]]
> - [[Encoders and Decoders]]
> - [[Full Adder]]
> - [[Full Subtractor]]
