---
title: "Introduction of Sequential Circuits"
subject: "Digital Logic and Design"
topic: "Sequential Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/introduction-of-sequential-circuits/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Sequential Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/sequential-circuit
---


> [!abstract] Introduction of Sequential Circuits
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Sequential Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/introduction-of-sequential-circuits/)

---

# Introduction of Sequential Circuits

Sequential circuits are digital circuits that store and use previous state information to determine their next state. They are commonly used in digital systems to implement state machines, timers, counters, and memory elements and are essential components in digital systems design.
- Sequential circuits are commonly used in digital systems to implement state machines, timers, counters, and memory elements.
- The memory elements in sequential circuits can be implemented using [flip-flops](https://www.geeksforgeeks.org/digital-logic/flip-flop-types-their-conversion-and-applications/), which are circuits that store binary values and maintain their state even when the inputs change.
- Unlike combinational circuits, which only depend on the current input values to produce outputs, sequential circuits depend on both the current inputs and the previous state stored in memory elements.
Sequential circuit is a [combinational logic circuit](https://www.geeksforgeeks.org/digital-logic/what-is-combinational-circuit/) that consists of inputs variable (X), logic gates (Computational circuit), and output variable (Z). 
![](assets/111-d8cbb3e82e.png)
A combinational circuit produces an output based on input variables only, but a **sequential circuit** produces an output based on **current input and previous output variables**. That means sequential circuits include memory elements that are capable of storing binary information. That binary information defines the state of the sequential circuit at that time. A [latch](https://www.geeksforgeeks.org/digital-logic/latches-in-digital-logic/) capable of storing one bit of information.
![](assets/1111-1-0b1f080ecc.png)
As shown in the figure, there are two types of input to the combinational logic : 
1. External inputs which are not controlled by the circuit.
2. Internal inputs, which are a function of a previous output state.
Secondary inputs are state variables produced by the storage elements, whereas secondary outputs are excitations for the storage elements. 
## **Types of Sequential Circuits**
There are two types of sequential circuits
### Asynchronous Sequential Circuit
These circuits **do not use a clock signal** but uses the pulses of the inputs. These circuits are **faster** than synchronous sequential circuits because there is clock pulse and change their state immediately when there is a change in the input signal. We use asynchronous sequential circuits when speed of operation is important and **independent** of internal clock pulse. 
![](assets/11212-5d8b7f1604.png)
But these circuits are more **difficult** to design and their output is **uncertain**.  
## Synchronous Sequential Circuit
These circuits **uses clock signal** and level inputs (or pulsed) (with restrictions on pulse width and circuit propagation). The output pulse is the same duration as the clock pulse for the clocked sequential circuits. Since they wait for the next clock pulse to arrive to perform the next operation, so these circuits are bit **slower** compared to asynchronous. Level output changes state at the start of an input pulse and remains in that until the next input or clock pulse. 
![](assets/11-1-96d4b313f2.png)
We use synchronous sequential circuit in synchronous counters, flip flops, and in the design of MOORE-MEALY state management machines. We use sequential circuits to design Counters, Registers, RAM, MOORE/MEALY Machine and other state retaining machines. 
## Clock Signal and Triggering
Clock signal is a kind of control signal that allows the elements of synchronous circuits to be in phase or phenomena that occur in circuits. It is derived from the square wave that has a high and a low level, it helps in measuring the sequential changes in the circuit states. The clock signal also makes a pulse simultaneously on all the circuit parts that are needed for the proper work of synchronous sequential circuits.
## Types of Triggering
In Sequential circuits, triggering denotes the way, in terms of which the state changes take place. There are two main types of triggering
### Level Triggering
Level triggering happens when the change of state is from the level of the clock signal is high or low. The circuit depends on the level of the clock signal rather than the rising or the falling edge of it. There are two types of level triggering:
1. **Positive Level Triggering:**  The circuit changes state when it is high time in the clock cycle i.e. when the clock signal is high.
2. **Negative Level Triggering:**  The circuit changes state when the clock signal is in the low state.
![Level-Triggering](assets/Level-Triggering-4422e61954.png)
### Edge Triggering
Edge triggering occurs when the state change is initiated by the transition (rising or falling edge) of the clock signal. The circuit responds to the clock signal's edges rather than its levels. There are two types of edge triggering:
1. **Positive Edge Triggering:**  The circuit changes state on the rising edge (transition from low to high) of the clock signal.
2. **Negative Edge Triggering:**  The circuit changes state on the falling edge (transition from high to low) of the clock signal.
![Edge-Triggering-](assets/Edge-Triggering--d00894ebb4.png)
Edge Triggering
## Applications
Sequential circuits find application in virtually almost every digital system today because of their capacity to handle state information. Some common applications include:
- Counters: Appearing in commonly in digital clocks, frequency counters, and event counters.
- Registers: Found in microprocessors and digital systems as a storage medium, a transfer medium and a medium for manipulating data.
- Memory Elements: Used in [RAM](https://www.geeksforgeeks.org/computer-organization-architecture/different-types-ram-random-access-memory/) and other storage devices to keep data in a temporary hold.
- State Machines: Made use in [control systems](https://www.geeksforgeeks.org/electronics-engineering/control-system/) , communication processes, and different digital devices for state control.
- Timers: It is applied in time measurement, delay production, and scheduling functions in digital circuits.
1. [GATE CS 2010, Question 65](https://www.geeksforgeeks.org/questions/in-the-sequential-circuit-shown-belowif-the-initial-value/)
2. [GATE CS 1999, Question 33](https://www.geeksforgeeks.org/questions/consider-the-circuit-shown-below-in-a-certain/)
3. [GATE CS 2014 (Set 3), Question 65](https://www.geeksforgeeks.org/questions/the-above-sequential-circuit-is-built-using-jk-flip-flops/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/introduction-of-sequential-circuits/)

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
> - [[Master Slave JK Flip Flop]]
> - [[n-bit Johnson Counter]]
> - [[Ring Counter]]
