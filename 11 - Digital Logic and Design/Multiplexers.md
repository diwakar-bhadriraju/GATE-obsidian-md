---
title: "Multiplexers"
subject: "Digital Logic and Design"
topic: "Combinational Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/multiplexers-in-digital-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Combinational Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/combinational-circuit
---


> [!abstract] Multiplexers
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Combinational Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/multiplexers-in-digital-logic/)

---

# Multiplexers

A multiplexer is a combinational circuit that has many data inputs and a single output, depending on control or select inputs. For N input lines, log2(N) selection lines are required, or equivalently, for 2n input lines, n selection lines are needed.
- Multiplexers are also known as "N-to-1 selectors," parallel-to-serial converters, many-to-one circuits, and universal logic circuits.
- They are mainly used to increase the amount of data that can be sent over a network within a certain amount of time and bandwidth.
![Multiplexer](assets/Untitled-Diagram---2024-05-14T094946432-25fb1b6785.webp)
Multiplexer
## Types of Mux
The Mux can be of different types based on input but in this article, we will go through two major types of mux, which are
- **2x1 Mux**
- **4x1 Mux**
## 2x1 Multiplexer
The 2x1 is a fundamental circuit which is also known 2-to-1 multiplexer that are used to choose one [signal](https://www.geeksforgeeks.org/electrical-engineering/signals/)  from two inputs and transmits it to the output. The 2x1 mux has two input lines, one output line, and a single selection line. It has various applications in digital systems such as in microprocessor it is used to select between two different data sources or between two different instructions.
### Block Diagram of 2:1 Multiplexer with Truth Table
Given Below is the Block Diagram and Truth Table of 2:1 Mux. In this Block Diagram where I0 and I1 are the input lines, Y is the output line and S0 is a single select line.
![2-1-Multiplexer](assets/2-1-Multiplexer--2--f0cdabea4c.png)
Block Diagram of 2:1 Multiplexer with Truth Table
The output of the 2x1 Mux will depend on the selection line S0,
- When S is 0(low), the I0 is selected
- when S0 is 1(High), I1 is selected
### Logical Expression of 2x1 Mux
Using the Truth Table ,the Logical Expression for Mux can be determined as
>
$$
Y=\overline{S_0}.I_0+S_0.I_1
$$
### Circuit Diagram of 2x1 Multiplexers
Using truth table the  [circuit](https://www.geeksforgeeks.org/physics/electric-circuit/)  diagram can be given as
![Circuit Diagram of 2x1 Mux](assets/Circuit-diagram--1--fb1966c8e4.webp)
Circuit Diagram of 2x1 Mux
## 4×1 Multiplexer
The 4x1 Multiplexer which is also known as the 4-to-1 multiplexer. It is a multiplexer that has 4 inputs and a single output. The Output is selected as one of the 4 inputs which is based on the selection inputs. The number of the Selection lines will depend on the number of the input which is determined by the equation
$$
log_2n
$$
 ,In 4x1 Mux the selection lines can be determined as
$$
log_4=2
$$
 ,slo two selections are needed.
### Block Diagram of 4×1 Multiplexer
In the Given Block Diagram I0, I1, I2, and I3 are the 4 inputs and Y is the Single output which is based on Select lines S0 and S1.
![4:1 Multiplexer](assets/1-78-98b950aa3b.png) The output of the multiplexer is determined by the binary value of the selection lines
- When S1S0=00, the input I0 is selected.
- When S1S0=01, the input I1 is selected.
- When S1S0=10, the input I2 is selected.
- When S1S0=11, the input I3 is selected.
### Truth Table of 4×1 Multiplexer
Given Below is the  [Truth Table](https://www.geeksforgeeks.org/electronics-engineering/truth-table/)  of 4x1 Multiplexer
![ Truth Table 4:1 Multiplexer](assets/2-42-03ea959e5d.jpg)
### Circuit Diagram of 4x1 Multiplexers
Using truth table the circuit diagram can be given as
![Circuit Diagram of 4:1 Multiplexers](assets/3-58-5e70274d5d.png)
Multiplexer can act as universal combinational circuit. All the standard logic gates can be implemented with multiplexers.
## Implementation of Different Gates with 2:1 Mux
Given below are the Implementation of Different gate using 2:1 Mux
### **Implementation of NOT gate using 2 : 1 Mux**
The Not gate from 2:1 Mux can be obtained by
- Connect the input signal to one of the data input lines(I0).
- Then connect a line (0 or 1) to the other data input line(I1)
- Connect the same input line Select line S0 which is connected to D0.
Given Below is the Diagram for the Logical Representation of  [**NOT gate**](https://www.geeksforgeeks.org/digital-logic/not-gate/)  **using 2 : 1 Mux**
![ Implementation of NOT gate using 2 : 1 Mux](assets/4-35-c40d7f2257.png)
### **Implementation of AND gate using 2 : 1 Mux**
The And gate from 2:1 Mux can be obtained by
- Connect the input Y to I1.
- Connect the input X to the selection line S0.
- Connect a line(0) to I0.
Given Below is the Diagram for the Logical Representation of  [**AND gate**](https://www.geeksforgeeks.org/digital-logic/and-gate/) **using 2 : 1 Mux**
![Implementation of AND gate using 2 : 1 Mux](assets/5-26-5451ce8bde.png)
For further more on the [**Implementation of AND gate using 2 : 1 Mux**](https://www.geeksforgeeks.org/digital-logic/implementation-of-and-gate-using-2-1-mux/)
### **Implementation of OR gate using 2 : 1 Mux**
The OR gate from 2:1 Mux can be obtained by
- Connect input X to the selection line S0.
- Connect input Y to I1.
- Connect Line(1) to I1.
Given Below is the Diagram for the Logical Representation of  [**OR gate**](https://www.geeksforgeeks.org/digital-logic/or-gate/)  **using 2 : 1 Mux**
![Implementation of OR gate using 2 : 1 Mux ](assets/6-21-6129e319cf.png)
Implementation of NAND, NOR, XOR and XNOR gates requires two 2:1 Mux. First multiplexer will act as NOT gate which will provide complemented input to the second multiplexer.
### **Implementation of NAND gate using 2 : 1 Mux**
The NAND gate from 2:1 Mux can be obtained by
- In first mux take inputs and 1 and 0 and y as selection line.
- In Second MUX the Output from mux is connected to I1.
- line(1) is given to the I0.
- x is given as selection line for the second Mux.
Given Below is the Diagram for the Logical Representation of  [**NAND gate**](https://www.geeksforgeeks.org/digital-logic/what-is-nand-gate/)  **using 2 : 1 Mux**
![Implementation of NAND gate using 2 : 1 Mux](assets/7-14-b01c3a271a.png)
For further more on the  [**Implementation of NAND gate using 2 : 1 Mux**](https://www.geeksforgeeks.org/electronics-engineering/implementation-of-nand-gate-using-2-1-mux/)
### **Implementation of NOR gate using 2 : 1 Mux**
The Nor gate from 2:1 Mux can be obtained by
- In first mux take inputs and 1 and 0 and y as selection line.
- In Second MUX the Output from mux is connected to I0.
- line(0) is given to the I1.
- x is given as selection line for the second Mux.
Given Below is the Diagram for the Logical Representation of  [**NOR gate**](https://www.geeksforgeeks.org/digital-logic/nor-gate/)  **using 2 : 1 Mux**
![Implementation of NOR gate using 2 : 1 Mux](assets/8-8-c805dbfbd7.png)
For further more on the  [**Implementation of NOR gate using 2 : 1 Mux**](https://www.geeksforgeeks.org/digital-logic/implementation-of-nor-gate-using-2-1-mux/)
### **Implementation of EX-OR gate using 2 : 1 Mux**
The Nor gate from 2:1 Mux can be obtained by
- In first mux take inputs and 1 and 0 and y as selection line.
- In Second MUX the Output from mux is connected to I1.
- y is given to the I0.
- x is given as selection line for the second Mux.
Given Below is the Diagram for the Logical Representation of  [**EX-OR gate**](https://www.geeksforgeeks.org/digital-logic/xor-gate/)  **using 2 : 1 Mux**
![Implementation of EX-OR gate using 2 : 1 Mux](assets/9-9-41cae5f9e4.png)
### **Implementation of EX-NOR gate using 2 : 1 Mux**
Given Below is the Diagram for the Logical Representation of  [**EX-OR gate**](https://www.geeksforgeeks.org/digital-logic/xor-gate/)  **using 2 : 1 Mux**
The Nor gate from 2:1 Mux can be obtained by
- In first mux take inputs and 1 and 0 and y as selection line.
- In Second MUX the Output from mux is connected to I0.
- y is given to the I1.
- x is given as selection line for the second Mux.
![Implementation of EX-NOR gate using 2 : 1 Mux](assets/10-4-6815068715.png)
## **Implementation of Higher Order MUX using Lower Order MUX**
Given Below are the Implementation of Higher Order MUX Using Lower Order MUX
### **4 : 1 MUX using 2 : 1 MUX**
Three 2: 1 MUX are required to implement 4 : 1 MUX.
![ 4 : 1 MUX using 2 : 1 MUX](assets/Multiplexers-in-Digital-Logic-eb334ac083.webp)
4 : 1 MUX using 2 : 1 MUX
Similarly,
While an 8:1 MUX requires seven (7) 2:1 MUX, a 16:1 MUX requires fifteen (15) 2:1 MUX, and a 64:1 MUX requires sixty-three (63) 2:1 MUX. Hence, we can draw the conclusion that an
$$
2^n:1
$$
 MUX requires sixty-three (63) 2:1 MUX. Hence, we can draw the conclusion that an 2  **n**  :1 MUX requires (2n−1)2:1 MUX (2  **n**  −1)2:1  **MUX.**
### **16 : 1 MUX using 4 : 1 MUX**
Given Below is the logical Diagram of 16:1 Mux Using 4:1 Mux
![16 : 1 MUX using 4 : 1 MUX](assets/12-4-edeb09527b.png)
In general, to implement B : 1 MUX using A : 1 MUX , one formula is used to implement the same.
 B / A = K1,
 K1/ A = K2,
 K2/ A = K3
 KN-1 / A = KN  = 1 (till we obtain 1 count of MUX).
 And then add all the numbers of MUXes = K1 + K2 + K3 + .... + K  N  .
 To implement 64 : 1 MUX using 4 : 1 MUX
 Using the above formula, we can obtain the same.
 64 / 4 = 16
 16 / 4 = 4
 4 / 4 = 1 (till we obtain 1 count of MUX)
 Hence, total number of 4 : 1 MUX are required to implement 64 : 1 MUX = 16 + 4 + 1 = 21.
 f(A, B, C) =
$$
\sum
$$
 (1, 2, 3, 5, 6) with don't care (7)
Using A and B as the select lines for 4 : 1 MUX,
**AB as select:**  Expanding the minterms to its boolean form and will see its 0 or 1 value in Cth place so that they can be placed in that manner.
![AB as select](assets/13-2-06fa9f70d2.png)
**AC as select**  : Expanding the minterms to its  [Boolean](https://www.geeksforgeeks.org/digital-logic/boolean-algebra/)  form and will see its 0 or 1 value in Bth place so that they can be place in that manner.
![AC as select](assets/14-1-1ed9e1a450.png)**BC as select**: Expanding the  [minterms](https://www.geeksforgeeks.org/digital-logic/what-is-minterm/)  to its boolean form and will see its 0 or 1 value in A  th  place so that they can be place in that manner.
![](assets/15-1-dec67d6df6.png)
## Applications of MUX
- **Data Routing** : The Mux is used for data routing in the digital system where they select one of the several data lines and re-route it the output.
- **Data Selection** : The Mux is used for data selection where they select data source according to the select lines.
- **Analog-to-Digital Conversion** : The Mux are used in  [ADC](https://www.geeksforgeeks.org/digital-logic/analog-to-digital-conversion/)  to select different analog input channels.
- **Address Decoding** : The Mux are used in  [Microprocessors](https://www.geeksforgeeks.org/electronics-engineering/introduction-of-microprocessor/)  or memory for address decoding.
- **Logic Function Implementation** : Mux can be used to implement various logic functions.
> **➣** **Also Check** - [Demultiplexer(DEMUX)](https://www.geeksforgeeks.org/electronics-engineering/what-is-demultiplexerdemux/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/multiplexers-in-digital-logic/)

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
