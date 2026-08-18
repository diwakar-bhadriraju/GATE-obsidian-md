---
title: "Ripple Counter in Digital Logic"
subject: "Digital Logic and Design"
topic: "Sequential Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/ripple-counter-in-digital-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Sequential Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/sequential-circuit
---


> [!abstract] Ripple Counter in Digital Logic
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Sequential Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/ripple-counter-in-digital-logic/)

---

# Ripple Counter in Digital Logic

A ripple counter is an asynchronous counter made by cascading flip-flops, where the output of one flip-flop drives the clock of the next. Only the first flip-flop receives the external clock; others are triggered by the previous stage's output, causing a "ripple" effect.
- Asynchronous operation.
- Flip-flops operate in toggle mode.
- Only one flip-flop receives the external clock (LSB).
- Can be configured as up, down, or up/down counter.
An n-bit ripple counter has 2ⁿ states and is also called a MOD-n counter. Counting sequences repeat after reaching the maximum or minimum count:
- Up counter: 000 → 001 → ... → 111 → 000...
- Down counter: 111 → 110 → ... → 000 → 111...
## 3-bit Ripple counter using a [JK flip-flop](https://www.geeksforgeeks.org/digital-logic/what-is-jk-flip-flop/)
In the circuit shown in the below figure, Q0(LSB) will toggle for every clock pulse because JK flip-flop works in toggle mode when both J and K are applied 1, 1, or high input. The following counter will toggle when the previous one changes from 1 to 0.
![3-bit Ripple Counter](assets/33-3-2eb4052d38.jpg)
### Truth Table
![Truth Table of 3-bit Ripple Counter](assets/countsequence-300x188-2-69e5991b02.png) 
The 3-bit ripple counter used in the circuit above has eight different states, each one of which represents a count value. Similarly, a counter having n flip-flops can have a maximum of 2 to the power n states. The number of states that a counter owns is known as its mod (modulo) number. Hence a 3-bit counter is a mod-8 counter. A mod-n counter may also be described as a divide-by-n counter. This is because the most significant flip-flop (the furthest flip-flop from the original clock pulse) produces one pulse for every n pulses at the clock input of the least significant flip-flop (the one triggers by the clock pulse). Thus, the above counter is an example of a divide-by-4 counter. 
### **Timing diagram**
Let us assume that the clock is negative [edge triggered](https://www.geeksforgeeks.org/digital-logic/edge-triggering-and-level-triggering/) so the above the counter will act as an up counter because the clock is negative edge triggered and output is taken from Q. 
![Timing Diagram](assets/ds54_clip_image004-1-300x127-1-70f6cff5c4.jpg)
Counters are used very frequently to divide clock frequencies and their uses mainly involve digital clocks and in multiplexing. The widely known example of the counter is parallel to serial data conversion logic.
## **Advantages of Ripple Counter in Digital Logic**
- Can be easily designed by T flip-flop or [D flip-flop](https://www.geeksforgeeks.org/digital-logic/d-flip-flop/).
- Can be used in low speed circuits & divide by n-counters.
- Used as Truncated counters to design any mode number counters (i.e. Mod 4, Mod 3)
## **Disadvantages of Ripple Counter in Digital Logic**
- Extra flip-flop are needed to do resynchronization.
- To count the sequence of truncated counters, additional feedback logic is needed.
- Propagation delay of asynchronous counters is very large, while counting the large number of bits.
- Counting errors may occur due to propagation delay for high clock frequencies.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/ripple-counter-in-digital-logic/)

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
