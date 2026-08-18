---
title: "Asynchronous Sequential Circuits"
subject: "Digital Logic and Design"
topic: "Sequential Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/asynchronous-sequential-circuits/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Sequential Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/sequential-circuit
---


> [!abstract] Asynchronous Sequential Circuits
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Sequential Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/asynchronous-sequential-circuits/)

---

# Asynchronous Sequential Circuits

An asynchronous sequential circuit does not have the clock signal; the transitions between different states occur due to the ‘change of inputs’. This makes them suitable for applications which involve low power input or when a clock signal may not be needed. In this article, we explain how these circuits work and we also have come up with an 8 to 3 line encoder circuit alongside with their advantages and disadvantages.
## What is Asynchronous Sequential Circuits?
[Asynchronous sequential circuits](https://www.geeksforgeeks.org/digital-logic/introduction-of-sequential-circuits/), also known as self-timed or ripple-clock circuits, are digital circuits that do not use a clock signal to determine the timing of their operations. Instead, the state of the circuit changes in response to changes in the inputs.
1. In an asynchronous sequential circuit, each flip-flop has a different set of inputs and outputs, and the state of the circuit is determined by the outputs of the [flip-flops](https://www.geeksforgeeks.org/digital-logic/flip-flop-types-their-conversion-and-applications/). The state transition function, which is a [Boolean function](https://www.geeksforgeeks.org/digital-logic/boolean-functions/) that describes the behavior of the circuit, determines the next state of the circuit based on the current inputs and the previous state stored in the flip-flops.
2. Asynchronous sequential circuits are used in digital systems to implement state machines, which are [digital circuits](https://www.geeksforgeeks.org/digital-logic/digital-electronics-logic-design-tutorials/) that change their output based on the current state and the inputs. They are commonly used in applications that require low power consumption or where a clock signal is not available or practical to use.
3. In summary, asynchronous sequential circuits are digital circuits that do not use a clock signal to determine the timing of their operations. They are used in digital systems to implement state machines and are commonly used in applications that require low power consumption or where a clock signal is not available or practical to use.
**Sequential** circuits are those which use **previous and current input** variables by storing their information and placing them back into the circuit on the next clock (activation) cycle. 
There are two types of input to the combinational logic. **External inputs** which come from outside the circuit design are not controlled by the circuit **Internal inputs** are functions of a previous output state. 
[Asynchronous sequential circuits](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-synchronous-and-asynchronous-sequential-circuits/) **do not use clock signals** as synchronous circuits do. Instead, the circuit is driven by the pulses of the inputs which means the state of the circuit changes when the inputs change. Also, they don’t use clock pulses. The change of internal state occurs when there is a change in the input variable. Their memory elements are either un-clocked flip-flops or time-delay elements. They are similar to combinational circuits with feedback. 
## Design of 8 to 3 Line Encoder
The diagram below depicts the 8 to 3 line [encoder](https://www.geeksforgeeks.org/digital-logic/encoder-in-digital-logic/)
![ENCODER-](assets/ENCODER--3f5147d529.png)
8 to 3 line Encoder
In this encoder there are 8 inputs line(D0 to D7) and 3 Outputs (A, B, C) represents the active input line of the 3 bit binary code. The encoder gives priority to the lowest numbered active input. If multiple inputs are active simultaneously, the encoder outputs the binary code of the lowest numbered active input.
#### Logical Expressions
A = D4 + D5 + D6 + D7
B = D2 + D3 + D6 + D7
C = D1 + D3 + D5 + D7
#### Truth Table
| D7 | D6 | D5 | D4 | D3 | D2 | D1 | D0 | A | B | C |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 1 | X | 0 | 0 | 1 |
| 0 | 0 | 0 | 0 | 0 | 1 | X | X | 0 | 1 | 0 |
| 0 | 0 | 0 | 0 | 1 | X | X | X | 0 | 1 | 1 |
| 0 | 0 | 0 | 1 | X | X | X | X | 1 | 0 | 0 |
| 0 | 0 | 1 | X | X | X | X | X | 1 | 0 | 1 |
| 0 | 1 | X | X | X | X | X | X | 1 | 1 | 0 |
| 1 | X | X | X | X | X | X | X | 1 | 1 | 1 |
'X' here denotes the don't care condition
## **Advantages**
- No clock signal, hence no waiting for a clock pulse to begin processing inputs, therefore fast. Their speed is faster and theoretically limited only by propagation delays of the logic gates.
- Robust handling. Higher performance function units, which provide average-case completion rather than worst-case completion. **Lower power consumption** because no transistor transitions when it is not performing useful computation. The absence of clock drivers reduces power consumption. Less severe [electromagnetic interference](https://www.geeksforgeeks.org/electronics-engineering/electromagnetic-interference/) (EMI).
- More tolerant to process variations and external voltage fluctuations. Achieve high performance while gracefully handling variable input and output rates and mismatched pipeline stage delays. Freedom from difficulties of distributing a high-fan-out, timing-sensitive clock signal. Better modularity.
- **Less assumptions** about the manufacturing process. Circuit speed adapts to changing temperature and voltage conditions. Immunity to transistor-to-transistor variability in the manufacturing process, which is one of the most serious problems faced by the semiconductor industry
- Lower power consumption: Asynchronous sequential circuits do not require a clock signal, which reduces power consumption compared to synchronous sequential circuits.
- More robust: Asynchronous sequential circuits are less sensitive to timing errors, such as clock skew and jitter, which can cause errors in the operation of synchronous sequential circuits.
- Simpler design: Asynchronous sequential circuits do not require the synchronization logic that is required in synchronous sequential circuits, making their design simpler.
- More flexible: Asynchronous sequential circuits can be designed to change their state in response to changes in the inputs, which makes them more flexible and adaptable to changing conditions.
## **Disadvantages**
- Some asynchronous circuits may require extra power for certain operations.
- More **difficult to design** and subject to problems like sensitivity to the relative arrival times of inputs at gates. If transitions on two inputs arrive at almost the same time, the circuit can go into the wrong state depending on slight differences in the propagation delays of the gates which are known as **race condition**.
- The number of circuit elements (transistors) maybe double that of synchronous circuits. Fewer people are trained in this style compared to synchronous design. Difficult to test and debug. Their **output** is **uncertain**.
- The performance of asynchronous circuits may be reduced in architectures that have a complex data path. Lack of dedicated, asynchronous design-focused commercial EDA tools.
- Unpredictable behavior: The lack of a clock signal makes the behavior of asynchronous sequential circuits unpredictable, which can make them harder to design and debug.
- Timing constraints: The timing constraints in asynchronous sequential circuits are more complex and difficult to specify compared to synchronous [sequential circuits](https://www.geeksforgeeks.org/digital-logic/introduction-of-sequential-circuits/).
- Complex design: The design of asynchronous sequential circuits can be complex, especially for large systems with many state transitions.
- Limited use: Asynchronous sequential circuits are not suitable for real-time control applications, where a clock signal is required to ensure predictable behavior.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/asynchronous-sequential-circuits/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Sequential Circuit

> [!note] Related notes
>
> - [[Amortized analysis for increment in counter]]
> - [[Counters]]
> - [[D Flipflop]]
> - [[Design 101 sequence detector]]
> - [[Design counter for given sequence]]
> - [[Flip-flop types and their Conversion]]
> - [[Introduction of Sequential Circuits]]
> - [[Master Slave JK Flip Flop]]
> - [[n-bit Johnson Counter]]
> - [[Ring Counter]]
