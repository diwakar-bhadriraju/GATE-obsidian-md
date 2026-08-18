---
title: "Synchronous Sequential Circuits in Digital Logic"
subject: "Digital Logic and Design"
topic: "Sequential Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/synchronous-sequential-circuits-in-digital-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Sequential Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/sequential-circuit
---


> [!abstract] Synchronous Sequential Circuits in Digital Logic
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Sequential Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/synchronous-sequential-circuits-in-digital-logic/)

---

# Synchronous Sequential Circuits in Digital Logic

## What is Sequential Circuit?
A [sequential circuit](https://www.geeksforgeeks.org/digital-logic/introduction-of-sequential-circuits/) is a digital circuit, whose output depends not only on the current inputs but also on the history of past inputs. This places sequential circuits in a different category than the combinational circuits, whose outputs depend merely on the current inputs, and which have no "memory" of what happened previously. Sequential circuits use memory elements like [flip-flops](https://www.geeksforgeeks.org/digital-logic/flip-flop-types-their-conversion-and-applications/) or latches that retain their past state; therefore they can perform functions that involve a sequence of operations over time.
- In a synchronous sequential circuit, the state of the circuit changes only on the rising or falling edge of the clock signal, and all changes in the circuit are synchronized to this clock. This makes the behavior of the circuit predictable and ensures that all elements of the circuit change at the same time, preventing race conditions and making the circuit easier to design and debug.
- Synchronous sequential circuits can be implemented using flip-flops, which are circuits that store binary values and maintain their state even when the inputs change. The output of the flip-flops is determined by the current inputs and the previous state stored in the flip-flops, and the next state is determined by the state transition function, which is a [Boolean function](https://www.geeksforgeeks.org/digital-logic/boolean-functions/) that describes the behavior of the circuit.
- In summary, synchronous sequential circuits are digital circuits that use clock signals to determine the timing of their operations. They are commonly used in digital systems to implement timers, [counters](https://www.geeksforgeeks.org/digital-logic/counters-in-digital-logic/), and memory elements and are essential components in digital systems design.
### Steps to solve a problem
**1.** Draw the state diagram from the problem statement or from the given state table. **Example:** Serial Adder. The functioning of serial adder can be depicted by the following state diagram. X1 and X2 are inputs, A and B are states representing carry. ![State diagram](assets/synchronous_1-9b45368d66.png) 
**2.** Draw the state table. If there is any redundant state then reduce the state table. ![state table](assets/synchronous_2-3b7ef2a574.png) 
**3.** Select **state assignment** i.e. assign binary numbers to the states according to total number states. Also decide the memory element (flip-flops) for the circuit. A -> 0 B -> 1 **4.** Replace the assignments in the state table to obtain Transition table: ![state assignment](assets/synchronous_3-ca59b617c0.png) 
**5.** Separate the output table from the transition table. ![Separation of  the output table from the transition table](assets/synchronous_4-129830bdb0.png)
z = x1x'2y+x'1x2y'+x1x2y+x1x'2y'
**6.** Excitation table for the flip-flop is obtained from the transition table using the output of flip-flop. **Excitation table for D flip-flop:** ![](assets/synchronous_5-7dc2e9e486.png)
D = x1 x2 +x1 y+x2 y
**7.** Draw the circuit diagram using gates and flip-flops. ![circuit diagram of Synchronous Sequential Circuits](assets/synchronous_6-67b4194187.png)
## Advantages of Synchronous Sequential Circuits
- **Predictable behavior**: The use of a clock signal makes the behavior of a synchronous sequential circuit predictable and deterministic, which is important for real-time control applications.
- **Synchronization**: Synchronous sequential circuits ensure that all elements of the circuit change at the same time, preventing race conditions and making the circuit easier to design and debug.
- **Timing constraints**: The timing constraints in a synchronous sequential circuit are well-defined, making it easier to design and test the circuit.
- **Easy to implement**: Synchronous sequential circuits can be implemented using flip-flops, which are simple and widely available digital components.
## Disadvantages of Synchronous Sequential Circuits
1. **Clock skew**: Clock skew is a timing error that occurs when the clock signal arrives at different flip-flops at different times. This can cause errors in the operation of the circuit.
2. **Timing jitter**: Timing jitter is a variation in the arrival time of the clock signal that can cause errors in the operation of the circuit.
3. **Complex design**: The design of synchronous sequential circuits can be complex, especially for large systems with many state transitions.
4. **Power consumption**: The use of a clock signal increases the power consumption of a synchronous sequential circuit compared to asynchronous sequential circuits.
## Applications of Synchronous Sequential Circuits
- **Finite State Machines (FSMs)**: Applied in control logics for a variety of applications, including traffic light control, vending machines, and industrial automation.
- **Memory Devices**: Applied in storing data and instructions in computers and other electronic devices, particularly in [RAM](https://www.geeksforgeeks.org/computer-science-fundamentals/random-access-memory-ram/) and [ROM](https://www.geeksforgeeks.org/computer-organization-architecture/read-only-memory-rom/).
- **Signal Processing**: Applied in DSPs to filter and manipulate signals in audio and video applications.
- **Data Transfer Protocols**: It has applications in communication systems; so, it controls the transfer of data from one device to another in relation to the synchronizing clock and mechanisms for error handling.
- **Clock Division Circuits**: These circuits convert a high-frequency clock to produce lower frequency signals, which is used to control many digital systems for their timing arrangements.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/synchronous-sequential-circuits-in-digital-logic/)

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
> - [[Flip-flop types and their Conversion]]
> - [[Introduction of Sequential Circuits]]
> - [[Master Slave JK Flip Flop]]
> - [[n-bit Johnson Counter]]
