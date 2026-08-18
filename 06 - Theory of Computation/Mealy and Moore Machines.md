---
title: "Mealy and Moore Machines in TOC"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/mealy-and-moore-machines-in-toc/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Mealy and Moore Machines in TOC
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/mealy-and-moore-machines-in-toc/)

---

# Mealy and Moore Machines in TOC

Moore and Mealy Machines are Transducers that help in producing outputs based on the input of the current state or previous state. In this article we are going to discuss Moore Machines and Mealy Machines, the difference between these two machines as well as Conversion from Moore to Mealy and Conversion from Mealy to Moore Machines.
## **Moore Machines**
Moore Machines are finite state machines with output value and its output depends only on the present state. It can be defined as (Q, q0, **∑,**O, δ, λ) where:
> - Q is a finite set of states.
> - q0 is the initial state.
> - **∑**is the input alphabet.
> - O is the output alphabet.
> - δ is the transition function which maps Q×**∑**→ Q.
> - λ is the output function which maps Q → O.
![Figure 1: Moore Machines](assets/1-43-214a03f750.jpg)
Figure 1: Moore Machines
In the Moore machine shown in Figure 1, the output is represented with each input state separated by /. The length of output for a Moore Machine is greater than input by 1.
- **Input:**  1,1
- **Transition:** δ(q0,1) = q2 || δ(q2,1) = q2
- **Output:**  000 (0 for q0, 0 for q2 and again 0 for q2)
## **Mealy Machines**
Mealy machines are also finite state machines with output value and their output depends on the present state and current input symbol. It can be defined as (Q, q0, **∑,**O, δ, λ’) where:
> - Q is a finite set of states.
> - q0 is the initial state.
> - **∑**is the input alphabet.
> - O is the output alphabet.
> - δ is the transition function which maps Q×**∑**→ Q.
> - 'λ’ is the output function that maps Q×**∑**→ O.
![Figure 2:Mealy Machines](assets/2-39-ed4121f198.jpg)
Figure 2:Mealy Machines
In the mealy machine shown in Figure 1, the output is represented with each input symbol for each state separated by /.  The length of output for a mealy machine is equal to the length of input.
- **Input:**  1,1
- **Transition:**  δ(q0,1) = q2 || δ(q2,1) = q2
- **Output:**  00 (q0 to q2 transition has Output 0 and q2 to q2 transition also has Output 0)
> **NOTE:** If there are n inputs in the Mealy machine then it generates n outputs while if there are n inputs in the Moore machine then it generates n + 1 outputs. 
## Moore Machines vs Mealy Machines
The Mealy and Moore machines form the backbone of state-based systems and are integral to automata theory in TOC. These machines, though conceptually similar, have key differences in how outputs are determined. Understanding their practical applications, particularly in system design and digital circuits, is crucial for learners. For those looking to grasp the nuances of these machines and see how they are implemented in real systems, this [GATE Computer Science & Information Technology - 2025 course](https://www.geeksforgeeks.org/courses/category/gate) offers a well-structured guide that covers theoretical and practical aspects in depth.
| **Moore Machine** | **Mealy Machine** |
| --- | --- |
| Output depends only on the **current state** | Output depends on **current state and input** |
| Output is associated with **states** | Output is associated with **transitions** |
| Output changes only on **state change** | Output changes **immediately with input** |
| Requires **more states** | Requires **fewer states** |
| Output is **more stable (no glitches)** | Output may have **glitches** |
| **Slower response** to input changes | **Faster response** to input changes |
For more differences, refer to [Difference Between Moore and Mealy Machines](https://www.geeksforgeeks.org/theory-of-computation/difference-between-mealy-machine-and-moore-machine/).
## **Conversion From Mealy to Moore Machine**
Let us take the transition table of the mealy machine shown in Figure 2.
|  | **Input=0** | | **Input=1** | |
| --- | --- | --- | --- | --- |
| **Present State** | **Next State** | **Output** | **Next State** | **Output** |
| q0 | q1 | 0 | q2 | 0 |
| q1 | q1 | 0 | q2 | 1 |
| q2 | q1 | 1 | q2 | 0 |
**Table 1**
**Step 1.** First, find out those states which have more than 1 output associated with them. q1 and q2 are the states which have both output 0 and 1 associated with them.
**Step 2** Create two states for these states. For q1, two states will be q10 (a state with output 0) and q11 (a state with output 1). Similarly, for q2, two states will be q20 and q21.
**Step 3:** Create an empty Moore machine with a newly generated state. For more machines, Output will be associated with each state irrespective of inputs.
|  | Input=0 | Input=1 |  |
| Present State | Next State | Next State | Output |
| q0 |  |  |  |
| q10 |  |  |  |
| q11 |  |  |  |
| q20 |  |  |  |
| q21 |  |  |  |
**Table 2**
**Step 4:** Fill in the entries of the next state using the mealy machine transition table shown in Table 1. 
- For q0 on input 0, the next state is q10 (q1 with output 0).
- For q0 on input 1, the next state is q20 (q2 with output 0).
- For q1 (both q10 and q11) on input 0, the next state is q10.
- For q1(both q10 and q11), next state is q21.
- For q10, the output will be 0 and for q11, the output will be 1.
Similarly, other entries can be filled following same logic.
|  | Input=0 | Input=1 |  |
| --- | --- | --- | --- |
| Present State | Next State | Next State | Output |
| q0 | q10 | q20 | 0 |
| q10 | q10 | q21 | 0 |
| q11 | q10 | q21 | 1 |
| q20 | q11 | q20 | 0 |
| q21 | q11 | q20 | 1 |
**Table 3**
This is the transition table of the Moore machine shown in Figure 1.
## **Conversion From Moore Machine to Mealy Machine**
Let us take the Moore machine of Figure 1 and its [transition table](https://www.geeksforgeeks.org/theory-of-computation/transition-table-in-automata/) is shown in Table 3.
**Step 1.**Construct an empty mealy machine using all states of the Moore machine as shown in Table 4.
|  | **Input=0** | | **Input=1** | |
| **Present State** | **Next State** | **Output** | **Next State** | **Output** |
| q0 |  |  |  |  |
| q10 |  |  |  |  |
| q11 |  |  |  |  |
| q20 |  |  |  |  |
| q21 |  |  |  |  |
**Table 4**
**Step 2:** Next state for each state can also be directly found from Moore machine transition Table as:
|  | **Input=0** | | **Input=1** | |
| --- | --- | --- | --- | --- |
| **Present State** | **Next State** | **Output** | **Next State** | **Output** |
| q0 | q10 |  | q20 |  |
| q10 | q10 |  | q21 |  |
| q11 | q10 |  | q21 |  |
| q20 | q11 |  | q20 |  |
| q21 | q11 |  | q20 |  |
**Table 5**
**Step 3:**As we can see output corresponds to each input in the Moore machine transition table. Use this to fill the Output entries. 
**Example:** Output corresponding to q10, q11, q20 and q21 are 0, 1, 0 and 1 respectively.  
|  | **Input=0** | | **Input=1** | |
| --- | --- | --- | --- | --- |
| **Present State** | **Next State** | **Output** | **Next State** | **Output** |
| q0 | q10 | 0 | q20 | 0 |
| q10 | q10 | 0 | q21 | 1 |
| q11 | q10 | 0 | q21 | 1 |
| q20 | q11 | 1 | q20 | 0 |
| q21 | q11 | 1 | q20 | 0 |
**Table 6**
**Step 4:** As we can see from Table 6, q10 and q11 are similar to each other (same value of next state and Output for different Inputs). Similarly, q20 and q21 are also similar. So, q11 and q21 can be eliminated.
|  | **Input=0** | | **Input=1** | |
| --- | --- | --- | --- | --- |
| **Present State** | **Next State** | **Output** | **Next State** | **Output** |
| q0 | q10 | 0 | q20 | 0 |
| q10 | q10 | 0 | q21 | 1 |
| q20 | q11 | 1 | q20 | 0 |
**Table 7**
This is the same mealy machine shown in Table 1. So we have converted Mealy to Moore machine and converted back [Moore to Mealy](https://www.geeksforgeeks.org/theory-of-computation/conversion-of-moore-to-mealy-machine-set-10/).
> **Note:** Number of statAes in the mealy machine can’t be greater than number  of states in moore machine.
**Example:** The Finite state machine is described by the following state diagram with A as starting state, where an arc label is x / y and x stands for 1-bit input and y stands for 2-bit output.
![](assets/3-28-9c7a657668.jpg)
Moore to Mealy Machines
Outputs the sum of the present and the previous bits of the input.
1. Outputs 01 whenever the input sequence contains 11.
2. Outputs 00 whenever the input sequence contains 10.
3. None of these.
**Solution:** Let us take different inputs and its output and check which option works:
**Input:** 01
**Output:** 00 01  (For 0, Output is 00 and state is A. Then, for 1, Output is 01 and state will be B)
**Input:**11
**Output:** 01 10 (For 1, Output is 01 and state is B. Then, for 1, Output is 10 and state is C)
As we can see, it is giving the binary sum of the present and previous bit. For the first bit, the previous bit is taken as 0.
##
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/mealy-and-moore-machines-in-toc/)

## GATE CS

- Subject: Theory of Computation
- Topic: Regular Expression, Languages,Grammar, and Finite Automata

> [!note] Related notes
>
> - [[Chomsky Hierarchy]]
> - [[Closure properties of Regular languages]]
> - [[Concatenation process in DFA]]
> - [[Conversion from NFA to DFA]]
> - [[Designing Deterministic Finite Automata]]
> - [[Designing Deterministic Finite Automata Set 1]]
> - [[Designing Deterministic Finite Automata Set 2]]
> - [[Designing Finite Automata from Regular Expression]]
> - [[Designing Non-Deterministic Finite Automata]]
> - [[Designing Non-Deterministic Finite Automata (2)]]
