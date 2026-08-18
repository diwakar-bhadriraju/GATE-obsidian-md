---
title: "D Flip Flop"
subject: "Digital Logic and Design"
topic: "Sequential Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/d-flip-flop/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Sequential Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/sequential-circuit
---


> [!abstract] D Flip Flop
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Sequential Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/d-flip-flop/)

---

# D Flip Flop

Prerequisite : [Introduction to Sequential Circuit]( https://www.geeksforgeeks.org/digital-logic/introduction-of-sequential-circuits/)
Flip Flop is an electronic device or to be precise a kind of memory component that can hold one bit of data. A flip flop has two states, that is "SET" and "RESET". Those states are represented with the binary values 0 and 1. The flip flop remains in its current state until its receives a signal that switches it to opposite state. A clock or pulse signal may "trigger" the flip flop to change state.
## **D Flip Flop**
D flip flop is an electronic devices that is known as "delay flip flop" or "data flip flop" which is used to store single bit of data.
- D flip flops can be either synchronous or asynchronous.
- The clock signal is required for the synchronous version of D flip flops but not for the asynchronous one.
- The D flip flop has two inputs, data  and clock input which controls the flip flop.
- When clock input is high, the data is transferred to the output of the flip flop.
- When the clock input is low, the output of the flip flop is held in its previous state.
![](assets/lu-6c1e663917.png)
Block Diagram of D Flip Flop
A D flip-flop is created by modifying an SR flip-flop. The S input is connected to the D input, and the R input is connected to the inverted D input. As a result, a D flip-flop functions similarly to an SR flip-flop, but with complementary inputs, preventing any possibility of an invalid intermediate state. One major issue with the SR flip-flop is the race around condition, which is eliminated in the D flip-flop due to the inverted inputs. The circuit diagram of the D flip-flop is shown in the figure below:
![22](assets/22-c7f9239a19.webp)
Logic Circuit of D Flip Flop
## **Working of D Flip Flop**
D flip flop consist of a single input D and two outputs (Q and Q'). The basic working of D Flip Flop is as follows:
- When the clock signal is low, the flip flop holds its current state and ignores the D input.
- When the clock signal is high, the flip flop samples and stores D input.
- The value that was previously fed into the D input is reflected at the flip flop's Q output.
  - If D = 0 then Q will be 0.
  - If D = 1 then Q will be 1.
- The Q' output of the flip flop is complemented by the Q output. 
  - If Q = 0 then Q' will be 1.
  - If Q = 1 then Q' will be 0.
![Truth Table of D Flip Flop](assets/fin-9059bf113b.png)
Truth Table of D Flip Flop
## **Characteristic Table of D Flip Flop**
The characteristic table of the D flip flop displays the behavior of the flip flop for each combination of input and current state. The characteristic table for a D flip flop is as follows.
![Characteristics table of D Flip Flop](assets/hioja-c84e5b344c.png)
Characteristics table of D Flip Flop
- D is the input, and Q is current state, Q(n+1) is the next state outputs.
- Q(n+1) will always be zero when D is 0, irrespective of current state of flip flop.
- When the input of the flip flop is 1,  next state of  flip flop will always be 1, regardless of the current state of flip flop.
## **Characteristic Equation of D Flip Flop**
The characteristics equation of D flip flop consist of a Boolean expression that explains the relationship between the input and output of the flip flop. The characteristic equation for a D flip flop is :
```
Q(n+1) =D(n)
```
- Q(n+1) represents the output of flip flop at the next clock cycle.
- D(n) is the input to the flip flop at the current clock cycle, and n represents the current clock cycle.
- This characteristic equation of D flip flop states "**that the output of the flip flop at the next clock cycle will be equal to the input at the current clock cycle**".
## **D Flip Flop Excitation Table**
Her, Q(n) represents the current state of the flip flop, and D(n) represents the current input of the flip flop. Where as Q(n+1) represents the next state of the flipflop.
- When the Q(n) is 0 and the D(n) is also 0, then the Q(n+1) becomes 0. This situation explains the condition of "hold" state.
- When the Q(n) is 0 but D(n) is 1, then the Q(n+1) becomes 1. This situation explains the condition of "set" state.
- When the Q(n) is 1 but D(n) is 0, then the Q(n+1) becomes 0. This situation explains the condition of "reset" state.
- When the Q(n) is 1 and the D(n) is also 1, then the Q(n+1) becomes 1. This situation explains the condition of "hold" state.
![](assets/chl-fa8537dc30.png)
## **Advantages of D Flip Flop**
- D flip flop is very simple to design.
- The computation speed of D flip flop is very fast compared to other flip flops.
- D flip flop requires very few components to design which makes it simple to understand.
**Note:** D flip flops are glitch prone. When input varies fast, flip flop output may glitch. Digital circuit glitches are hard to identify and fix.
## **Application of D Flip Flop**
D flip flop has numerous applications in digital system is described as follows:
- **Memory:** D flip flop is used to create memory circuit for holding the data.
- **Registers:** D flip flop is used to create register, which can hold data in digital system. By using the D flip flop the designer can built any size of register as per the requirement.
- **Counters:** D flip flops are used to create the counters which counts the number of event occurred in the digital system.
- **Synchronous System:** D flip flop is having in developing the synchronous system.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/d-flip-flop/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Sequential Circuit

> [!note] Related notes
>
> - [[Amortized analysis for increment in counter]]
> - [[Asynchronous Sequential Circuits]]
> - [[Counters]]
> - [[Design 101 sequence detector]]
> - [[Design counter for given sequence]]
> - [[Flip-flop types and their Conversion]]
> - [[Introduction of Sequential Circuits]]
> - [[Master Slave JK Flip Flop]]
> - [[n-bit Johnson Counter]]
> - [[Ring Counter]]
