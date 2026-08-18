---
title: "Flip-Flop Types"
subject: "Digital Logic and Design"
topic: "Sequential Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/flip-flop-types-their-conversion-and-applications/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Sequential Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/sequential-circuit
---


> [!abstract] Flip-Flop Types
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Sequential Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/flip-flop-types-their-conversion-and-applications/)

---

# Flip-Flop Types

The flip-flop is a circuit that maintains a state until directed by input to change the state. A basic flip-flop can be constructed using four-NAND or four-NOR gates. A flip-flop is popularly known as the basic digital memory circuit. It has its two states as logic 1(High) and logic 0 (Low) states.
- A flip-flop is a sequential circuit which consists of a single binary state of information or data.
- The digital circuit is a flip-flop which has two outputs and are of opposite states. It is also known as a Bistable Multivibrator.
## **Types of Flip-Flops**
Given Below are the Types of Flip-Flop
- SR Flip Flop
- JK Flip Flop
- D Flip Flop
- T Flip Flop
Logic diagrams and truth tables of the different types of flip-flops are as follows:  
## S-R Flip Flop
In the flip flop, with the help of preset and clear when the power is switched ON, the states of the circuit keeps on changing, that is it is uncertain. It may come to set(Q=1) or reset(Q’=0) state. In many applications, it is desired to initially set or reset the flip flop that is the initial state of the flip flop that needs to be assigned. This thing is accomplished by the preset(PR) and the clear(CLR).
### Block Diagram of S-R Flip Flop
Given Below is the Block Diagram of [S-R Flip Flop](https://www.geeksforgeeks.org/digital-logic/sr-flip-flop/)
![SR-Flip-Flop1](assets/SR-Flip-Flop1-70e76b0f2b.png)
S-R Flip Flop
### Circuit Diagram and Truth Table of S-R Flip Flop
Given Below is the Diagram of S-R Flip Flop with its Truth Table
![SR_flip](assets/SR_flip-dbf3d06b11.png)
### Operations of S-R Flip Flop
Given Below is the Operations of S-R Flip Flop
- **Case 1(PR=CLR=1):** The asynchronous inputs are inactive and the flip flop responds freely to the S,R and the CLK inputs in the normal way.
- **Case 2(PR=0 and CLR=1):**This is used when the Q is set to 1.
- **Case 3(PR=1 and CLR=0):**This is used when the Q’ is set to 1.
- **Case 4(PR=CLR=0):** This is an invalid state.
> Characteristics Equation for SR Flip Flop
>
> **Q**N+1** **=  Q**N**R' + SR'**
## J-K Flip Flop
In JK flip flops, The basic structure of the flip flop which consists of Clock (CLK), Clear (CLR), Preset (PR).
### Block Diagram of J-K Flip Flop
Given Below is Block Diagram of [J-K Flip Flop](https://www.geeksforgeeks.org/digital-logic/what-is-jk-flip-flop/)
![JK-Flip-Flop1](assets/JK-Flip-Flop1-5b6875a769.png)
J-K Flip Flop
### Circuit Diagram and Truth Table of J-K Flip Flop
Given Below is the Diagram of J-K Flip Flop with its Truth Table
![JK_flip](assets/JK_flip-32d23bb8a5.png)
### Operations of J-K Flip Flop
Given Below is the Operations of J-K Flip Flop
- **Case 1 (PR=CLR=0 ):**This condition is in its invalid state.
- **Case 2 (PR=0 and CLR=1):**The PR is activated which means the output in the Q is set to 1. Therefore, the flip flop is in the set state.
- **Case 3 (PR=1 and CLR=0):**The CLR is activated which means the output in the Q’ is set to 1. Therefore, the flip flop is in the reset state.
- **Case 4 (PR=CLR=1):**In this condition the flip flop works in its normal way whereas the PR and CLR gets deactivated.
### Race Around Condition in J-K Flip Flop
When the J and K both are set to 1, the input remains high for a longer duration of time, then the output keeps on toggling. Toggle means that switching in the output instantly i.e. Q=0, Q’=1 will immediately change to Q=1 and Q’=0 and this continuation keeps on changing. This change in output leads to race around condition.
> Characteristics Equation for JK Flip Flop
>
> **Q**N+1** **= JQ'**N** **+ K'Q**N**
## D Flip Flop
The D Flip Flop Consists a single data input(D), a clock input(CLK),and two outputs: Q and Q' (the complement of Q).
### Block Diagram of D Flip Flop
Given Below is the Block Diagram of [D Flip Flop](https://www.geeksforgeeks.org/digital-logic/d-flip-flop/)
![D-Flip-Flop](assets/D-Flip-Flop-781c0d9337.png)
D FLIP FLOP
### Circuit Diagram and Truth Table of D Flip Flop
Given Below is the Diagram of D Flip Flop with its Truth Table
![D- logic diag](assets/D-logic-diag-300x123-c56b36f022.png) ![D flip flop](assets/D-flip-flop-653dad264e.png)
### Operation of the D Flip-Flop
Given Below is the operation of D Flip-Flip
- **Case 1 (PR=CLR=0):**This conditions is represents as invalid state where both PR(present) and CLR(clear) inputs are inactive.
- **Case 2 (PR=0 and CLR=1)**:This state is set state in which PR is inactive (0) and CLR is active(1) and the output Q is set to 1.
- **Case 3 (PR=1 and CLR=0):**This state is reset state in which PR is active (1) and CLR is inactive (0) and the complementary output Q' is set to 1.
- **Case 4 (PR=CLR=1):**In This state the flip flop behaves as normal, both PR and CLR inputs are active(1).
> Characteristics Equation for D Flip Flop
>
> **Q**N+1** **= D**
## T Flip Flop
The T Flip Flop consists of data input (T), a clock input (CLK), and two outputs: Q and Q' (the complement of Q).
### Block Diagram of T Flip Flop
Given Below is the Block Diagram of [T Flip Flop](https://www.geeksforgeeks.org/digital-logic/t-flip-flop/)
![T-Flip-Flop](assets/T-Flip-Flop-4f372072c2.png)
T FLIP FLOP
### Circuit Diagram and Truth Table of T Flip Flop
Given Below is the Circuit Diagram and Truth Table of T Flip Flop
### T- logic diag T flip flop Operation of the T Flip-Flop
Given Below is the Operation of T Flip-Flop
- **Case 1 (T=0):**In this condition the **fl**ip-flop remains in its current state regardless of clock input,Also the Output Q will remain unchanged unit the value of T will not change.
- **Case 2 (T=1):**In this condition the flip flop will change when T input is 1,At each rising or falling edge of the clock signal the output Q will be in complementary state.
> Characteristics Equation for T Flip Flop
>
> **Q**N+1** **= Q'**N**T + Q**N**T' = Q**N** **XOR T**
## Conversion for Flip Flops
The Excitation Table of the Flip Flop can be given as
**EXCITATION TABLE**:
![flip_1](assets/flip_1-73ab8d3daa.png)
### **Steps To Convert from One Flip Flop to Other**
Let there be required flipflop to be constructed using sub-flipflop:
1. Draw the truth table of the required flip-flop.
2. Write the corresponding outputs of sub-flipflop to be used from the excitation table.
3. Draw K-Maps using required flipflop inputs and obtain excitation functions for sub-flipflop inputs.
4. Construct a logic diagram according to the functions obtained.
**Convert SR To JK Flip Flop**
The Table for the SR To JK is given as
![flip_2](assets/flip_2-f17abae300.png)
### **Excitation Functions and Logic Diagram**
Function and Logic Diagram for the conversion is given below
![flip_3](assets/flip_3-d462c56205.png) 
**Convert SR To D Flip Flop**
The Table for the SR To JK is given as
![flip_4](assets/flip_4-b863e2f1fc.png)
**Excitation Functions and Logic Diagram**
Function and Logic Diagram for the conversion is given below
## flip_5 flip_6Applications of Flip-Flops
These are the various types of flip-flops being used in digital electronic circuits and the applications of Flip-flops are as specified below.
- **Counters:** The Flip Flop are used in the [Counter](https://www.geeksforgeeks.org/digital-logic/counters-in-digital-logic/) Circuits for Counting pulse or events.
- **Frequency Dividers:** The Flip Flop are used in [Frequency Dividers](https://www.geeksforgeeks.org/computer-networks/frequency-division-and-time-division-multiplexing/) to divide the frequency of a input signal by a specific factor.
- **Shift Registers:** The [Shift registers](https://www.geeksforgeeks.org/digital-logic/shift-registers-in-digital-logic/) consist of interconnected flip-flops that shift data serially.
- **Storage Registers:** The Storage Resistor uses Flip Flop to store data in binary information.
- **Bounce elimination switch:** The Flip Flop are used in Bounce elimination switch to eliminate the contact bounce.
- **Data storage:** The Flip Flop are used in the Data Storage to store binary data temporarily or permanently.
- **Data transfer:** The Flip Flops are used for data transfer in different [electronic parts](https://www.geeksforgeeks.org/electrical-engineering/electronic-components/).
- **Latch:** The Latches are the [Sequential circuit](https://www.geeksforgeeks.org/digital-logic/introduction-of-sequential-circuits/) which uses Flip Flop for temporary storage of data
- **Registers:** The [Registers](https://www.geeksforgeeks.org/digital-logic/registers-vs-counters/) are mode from the array of flip flop which are used to store data temporarily**.**
- **Memory:** The Flip Flops are the main components in the [memory unit](https://www.geeksforgeeks.org/computer-organization-architecture/introduction-to-memory-and-memory-units/) for data storage.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/flip-flop-types-their-conversion-and-applications/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Sequential Circuit

> [!note] Related notes
>
> - [[Amortized analysis for increment in counter]]
> - [[Asynchronous Sequential Circuits]]
> - [[Counters]]
> - [[D Flipflop]]
> - [[Design 101 sequence detector]]
> - [[Design counter for given sequence]]
> - [[Introduction of Sequential Circuits]]
> - [[Master Slave JK Flip Flop]]
> - [[n-bit Johnson Counter]]
> - [[Ring Counter]]
