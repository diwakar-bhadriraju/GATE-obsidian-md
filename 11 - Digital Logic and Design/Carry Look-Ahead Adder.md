---
title: "Carry Look-Ahead Adder"
subject: "Digital Logic and Design"
topic: "Combinational Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/carry-look-ahead-adder/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Combinational Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/combinational-circuit
---


> [!abstract] Carry Look-Ahead Adder
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Combinational Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/carry-look-ahead-adder/)

---

# Carry Look-Ahead Adder

The adder produce carry propagation delay while performing other arithmetic operations like multiplication and divisions as it uses several additions or subtraction steps. This is a major problem for the adder and hence improving the speed of addition will improve the speed of all other arithmetic operations. Hence reducing the carry propagation delay of adders is of great importance. There are different logic design approaches that have been employed to overcome the carry propagation problem. One widely used approach is to employ a carry look-ahead which solves this problem by calculating the carry signals in advance, based on the input signals. This type of adder circuit is called a carry look-ahead adder.
Here a carry signal will be generated in two cases:
1. Input bits A and B are 1
2. When one of the two bits is 1 and the carry-in is 1.
In ripple carry adders, for each adder block, the two bits that are to be added are available instantly. However, each adder block waits for the carry to arrive from its previous block. So, it is not possible to generate the sum and carry of any block until the input carry is known. The 
$$
i^{th}
$$
block waits for the 
$$
i-1^{th}
$$
block to produce its carry. So there will be a considerable time delay which is carry propagation delay. 
![](assets/digital_Logic1-fe4c83a399.png)
Consider the above 4-bit ripple carry adder. The sum 
$$
S_{3}
$$
is produced by the corresponding full adder as soon as the input signals are applied to it. But the carry input 
$$
C_{4}
$$
is not available on its final steady-state value until carry 
$$
C_{3}
$$
is available at its steady-state value. Similarly 
$$
C_{3}
$$
depends on 
$$
C_{2}
$$
and 
$$
C_{2}
$$
on 
$$
C_{1}
$$
. Therefore, though the carry must propagate to all the stages in order that output 
$$
S_{3}
$$
and carry 
$$
C_{4}
$$
settle their final steady-state value. 
The propagation time is equal to the propagation delay of each adder block, multiplied by the number of adder blocks in the circuit. For example, if each full adder stage has a propagation delay of 20 nanoseconds, then 
$$
S_{3}
$$
will reach its final correct value after 60 (20 × 3) nanoseconds. The situation gets worse, if we extend the number of stages for adding more number of bits. 
**Carry Look-ahead Adder :** 
A carry look-ahead adder reduces the propagation delay by introducing more complex hardware. In this design, the ripple carry design is suitably transformed such that the carry logic over fixed groups of bits of the adder is reduced to two-level logic. Let us discuss the design in detail. 
![](assets/digital_Logic2-600d80dfb8.png)
![](assets/digital_Logic3-315f94991f.png)Consider the full adder circuit shown above with corresponding truth table. We define two variables as **'carry generate'** 
$$
G_{i}
$$
and **'carry propagate'** 
$$
P_{i}
$$
then, 
$$
P_{i} = A_{i} \oplus B_{i} \newline G_{i} = A_{i} B_{i}
$$
The sum output and carry output can be expressed in terms of carry generate 
$$
G_{i}
$$
and carry propagate 
$$
P_{i}
$$
as
$$
S_{i} = P_{i} \oplus C_{i} \newline C_{i+1} = G_{i} + P_{i} C_{i}
$$
where 
$$
G_{i}
$$
produces the carry when both 
$$
A_{i}
$$
, 
$$
B_{i}
$$
are 1 regardless of the input carry. 
$$
P_{i}
$$
is associated with the propagation of carry from 
$$
C_{i}
$$
to 
$$
C_{i + 1}
$$
. 
The carry output Boolean function of each stage in a 4 stage carry look-ahead adder can be expressed as
$$
C_{1} = G_{0} + P_{0} C_{in} \newline C_{2} = G_{1} + P_{1} C_{1} = G_{1} + P_{1} G_{0} + P_{1} P_{0} C_{in} \newline C_{3} = G_{2} + P_{2} C_{2} = G_{2} + P_{2} G_{1} + P_{2} P_{1} G_{0} + P_{2} P_{1} P_{0} C_{in} \newline C_{4} = G_{3} + P_{3} C_{3} = G_{3} + P_{3} G_{2} + P_{3} P_{2} G_{1} + P_{3} P_{2} P_{1} G_{0} + P_{3} P_{2} P_{1} P_{0} C_{in} \newline
$$
From the above Boolean equations we can observe that 
$$
C_{4}
$$
does not have to wait for 
$$
C_{3}
$$
and 
$$
C_{2}
$$
to propagate but actually 
$$
C_{4}
$$
is propagated at the same time as 
$$
C_{3}
$$
and 
$$
C_{2}
$$
. Since the Boolean expression for each carry output is the sum of products so these can be implemented with one level of AND gates followed by an OR gate.
The implementation of three Boolean functions for each carry output (
$$
C_{2}
$$
, 
$$
C_{3}
$$
and 
$$
C_{4}
$$
) for a carry look-ahead carry generator shown in below figure. 
![](assets/digital_Logic6-4c7fc3ed9a.png)
**Time Complexity Analysis :** 
We could think of a carry look-ahead adder as made up of two "parts" 
1. The part that computes the carry for each bit.
2. The part that adds the input bits and the carry for each bit position.
The 
$$
log(n)
$$
complexity arises from the part that generates the carry, not the circuit that adds the bits. 
Now, for the generation of the 
$$
n^{th}
$$
carry bit, we need to perform a AND between (n+1) inputs. The complexity of the adder comes down to how we perform this AND operation. If we have AND gates, each with a fan-in (number of inputs accepted) of k, then we can find the AND of all the bits in 
$$
log_{k}(n+1)
$$
time. This is represented in asymptotic notation as 
$$
\Theta(log n)
$$
.
**Advantages and Disadvantages:**
| **Advantages** | **Disadvantages** |
| --- | --- |
| Propagation delay is significantly reduced compared to ripple carry adders. | Circuit complexity increases rapidly with increase in number of bits. |
| Provides very fast addition by computing carry signals in advance. | Requires more hardware components, making the circuit expensive. |
| Suitable for high-speed and performance-critical applications. | Consumes more power due to additional logic gates. |
| Improves overall system speed in processors and ALUs. | Not efficient for small bit-width adders due to overhead. |
> **NOTE :**For n-bit carry lookahead adder to evaluate all the carry bits it requires [n(n + 1)]/2 AND gates and n OR gates.
**GATE CS Corner Questions** 
Practicing the following questions will help you test your knowledge. All questions have been asked in GATE in previous years or in GATE Mock Tests. It is highly recommended that you practice them. 
1. [GATE CS 2016 (Set-1), Question 43](https://www.geeksforgeeks.org/questions/consider-a-carry-lookahead-adder-for-adding-two-n-bit/)
2. [GATE CS 2004, Question 90](https://www.geeksforgeeks.org/questions/a-4-bit-carry-lookahead-adder-which-adds-two-4-bit/)
3. [GATE CS 2007, Question 85](https://www.geeksforgeeks.org/questions/in-a-look-ahead-carry-generator-the-carry-generate-function/)
4. [GATE CS 2006, Question 85](https://www.geeksforgeeks.org/questions/given-two-three-bit-numbers-a2a1a0-and-b2b1b0-and/)
5. [GATE CS 1997, Question 15](https://www.geeksforgeeks.org/questions/an-n-bit-carry-look-ahead-adder-where-n-is/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/carry-look-ahead-adder/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Combinational Circuit

> [!note] Related notes
>
> - [[BCD Adder]]
> - [[BCD to 7 Segment Decoder]]
> - [[Binary Decoder]]
> - [[Combinational circuits using Decoder]]
> - [[De-MUX]]
> - [[Encoder]]
> - [[Encoders and Decoders]]
> - [[Full Adder]]
> - [[Full Subtractor]]
> - [[Grey Code]]
