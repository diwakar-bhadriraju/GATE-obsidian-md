---
title: "Binary Decoder in Digital Logic"
subject: "Digital Logic and Design"
topic: "Combinational Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/binary-decoder-in-digital-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Combinational Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/combinational-circuit
---


> [!abstract] Binary Decoder in Digital Logic
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Combinational Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/binary-decoder-in-digital-logic/)

---

# Binary Decoder in Digital Logic

A binary decoder is a digital circuit used to convert binary-coded inputs into a unique set of outputs. It does the opposite of what an encoder does. A decoder takes a binary value (such as 0010) and activates exactly one output line corresponding to that value while all other output lines remain inactive.
This functionality is widely used in digital systems where we need to convert serial or binary-coded data into multiple outputs, such as in memory address decoding, display systems, and control logic.
A decoder uses n input lines to generate 2ⁿ unique outputs. Each binary input combination maps to exactly one output being active. For example:
- A 2-bit decoder has 2 inputs and 4 outputs (2² = 4).
- A 4-bit decoder has 4 inputs and 16 outputs (2⁴ = 16).
This mapping ensures only one output line is active at a time, based on the input binary code.
**Active Low Inputs**
In many binary decoders, the inputs or outputs may be active low. This means that:
- A signal is considered active when it is at a LOW logic level (0).
- A signal is inactive when at a HIGH logic level (1).
This convention is especially useful in integrated circuits where active-low logic is more noise-resistant and power-efficient.
## Types of Binary Decoders
There are several variations of binary decoders, depending on the application:
**1. Standard Binary Decoder**
- Converts n binary inputs into 2ⁿ unique outputs.
- **Example:** 3-to-8 decoder, 4-to-16 decoder.
**2. Priority Decoder**
- Assigns priority to inputs and outputs.
- If multiple inputs are active, the output reflects the input with the highest priority.
**3. Error-Detecting Decoder**
- Checks input binary codes for validity.
- If an illegal code is detected, it activates an error signal.
![](assets/decoder-1-da379c62e6.jpg)
## 2-to-4 Binary Decoder
A 2-to-4 decoder is a [combinational digital circuit](https://www.geeksforgeeks.org/digital-logic/what-is-combinational-circuit/) that takes 2 binary inputs and activates one of four outputs, based on the input combination. Only one output is active at a time, and all others remain low.
The circuit decodes the 2-bit binary input into one of the four output lines.
| A | B | Output Q0 | Output Q1 | Output Q2 | Output Q3 |
| --- | --- | --- | --- | --- | --- |
| 0 | 0 | 1 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 0 | 0 |
| 1 | 0 | 0 | 0 | 1 | 0 |
| 1 | 1 | 0 | 0 | 0 | 1 |
A binary decoder takes binary inputs and activates only one output corresponding to that input, while all other outputs stay LOW (0).
**Standard 2-to-4 Decoder Outputs:**
Given binary inputs A and B, the outputs are:
- Q0 = A'B' (when A = 0, B = 0)
- Q1 = A'B (when A = 0, B = 1)
- Q2 = AB' (when A = 1, B = 0)
- Q3 = AB (when A = 1, B = 1)
**Note:** Only one output is HIGH (1) at a time depending on the combination of A and B.
**Enable Input (E):**
An additional input called Enable (E) is used to control the output.
- When E = 0 → All outputs are forced to 0 (OFF).
- When E = 1 → Outputs are determined by the values of A and B as per the above logic.
**Modified Outputs with Enable:**
Each output is ANDed with Enable, so:
- Q0 = E ⋅ A'B'
- Q1 = E ⋅ A'B
- Q2 = E ⋅ AB'
- Q3 = E ⋅ AB
This ensures that the decoder is active only when Enable = 1.
## **Implementing Logic Functions Using Decoders**
A decoder can be used to implement any logic function by generating minterms and combining them with [OR gates](https://www.geeksforgeeks.org/digital-logic/or-gate/).
**Steps to Implement a Logic Function:**
**1. Express the Function in Sum of Minterms (SOP):** Write the logic function as a sum of minterms. Each minterm corresponds to a unique combination of input variables where the function outputs 1.
**2. Select an Appropriate Decoder:** Choose an n-to-2ⁿ decoder, where 'n' is the number of input variables. This decoder will generate all possible minterms for the input variables.
**3. Connect Decoder Outputs to an OR Gate:** Identify the decoder outputs corresponding to the [minterms](https://www.geeksforgeeks.org/digital-logic/what-is-minterm/) present in the function. Connect these outputs to an OR gate to obtain the final function output.
## Advantages of using Binary Decoders in Digital Logic
**1.Increased flexibility**: Binary decoders provide a flexible way to select one of multiple outputs based on a binary code, allowing for a wide range of applications.
**2. Improved performance:** By converting a serial code into a parallel set of outputs, binary decoders can improve the performance of a digital system by reducing the amount of time required to transmit information from a single input to multiple outputs.
**3. Improved reliability:** By reducing the number of lines required to transmit information from a single input to multiple outputs, binary decoders can reduce the possibility of errors in the transmission of information.
## Disadvantages of using Binary Decoders in Digital Logic
**1. Increased complexity:** Binary decoders are typically more complex circuits compared to [demultiplexers](https://www.geeksforgeeks.org/electronics-engineering/what-is-demultiplexerdemux/), and require additional components to implement.
**2. Limited to specific applications:** Binary decoders are only suitable for applications where a serial code must be converted into a parallel set of outputs.
**3. Limited number of outputs:** Binary decoders are limited in their number of outputs, as the number of outputs is determined by the number of inputs and the binary code used.
## **Application of Binary Decoder in Digital Logic**
**1. Memory Addressing:** Select specific memory locations in systems by decoding address inputs.
**2. Control Circuits:** Generate control signals in microprocessors by decoding instruction opcodes.
**3. Display Drivers:** Drive display devices like LEDs by illuminating specific segments based on binary inputs.
**4. Address Decoding:** Generate chip select signals for memory or peripheral devices.
**5. Digital Communication:** Decode received digital data in communication systems.
**6. Error Correction:** Identify and correct errors in digital data through decoding mechanisms.
> Read more about [Application of Decoder](https://www.geeksforgeeks.org/digital-logic/applications-of-decoders/)
**Related Questions:**
1. [GATE CS 2007, Question 85](https://www.geeksforgeeks.org/questions/how-many-3-to-8-line-decoders-with-an-enable-input/)
2. [GATE CS 20130, Question 65](https://www.geeksforgeeks.org/questions/in-the-following-truth-table-v-1-if/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/binary-decoder-in-digital-logic/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Combinational Circuit

> [!note] Related notes
>
> - [[BCD Adder]]
> - [[BCD to 7 Segment Decoder]]
> - [[Carry Look-Ahead Adder]]
> - [[Combinational circuits using Decoder]]
> - [[De-MUX]]
> - [[Encoder]]
> - [[Encoders and Decoders]]
> - [[Full Adder]]
> - [[Full Subtractor]]
> - [[Grey Code]]
