---
title: "Logic Gates"
subject: "Digital Logic and Design"
topic: "Introduction of Boolean Algebra and Logic Gates"
source: "https://www.geeksforgeeks.org/physics/logic-gates/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Introduction of Boolean Algebra and Logic Gates"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/introduction-of-boolean-algebra-and-logic-gates
---


> [!abstract] Logic Gates
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Introduction of Boolean Algebra and Logic Gates`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/physics/logic-gates/)

---

# Logic Gates

Fundamental building blocks in digital electronics which is used to perform logical operations based on the inputs provided to it and gives a logical output that can be either high(1) or low(0).
- The operation of logic gates is based on [Boolean algebra](https://www.geeksforgeeks.org/digital-logic/boolean-algebra/), or mathematics.
- There are basically seven main types of logic gates that are used to perform various logical operations in digital systems.
- By combining different logic gates, complex operations are performed, and circuits like flip-flops, counters, and processors are designed.
- Logic gates find their uses in our day-to-day lives, such as in the architecture of our telephones, laptops, tablets and memory devices.
## Types
### **AND GATE**
An [AND gate](https://www.geeksforgeeks.org/digital-logic/and-gate/) is used to perform logical multiplication of binary input. The Output state of the AND gate will be high (1) if both the input is high (1), else the output state will be low(0) if any of the input is low (0).
The Boolean Expression or logic for the AND gate is the logical multiplication of inputs denoted by a full stop or single dot as :
> X = A.B
>
> The value of X will be True when both the inputs will be True.
![1](assets/1-436f3362cc.webp)
**Properties**
- AND gate can accept two or more than two input values at a time.
- When all of the inputs are logic 1, the output of this gate is logic 1.
### **OR GATE**
[OR GATE](https://www.geeksforgeeks.org/digital-logic/or-gate/) is most widely used digital logic circuit. The output state of OR gate will be high i.e., (1) if any of the input state is high or 1, else output state will be low i.e., 0.
The Boolean Expression for the OR gate is the logical addition of inputs denoted by plus sign (+) as
> X= A+B
The value of X will be high(true) when one of the inputs is set to high (true).
![2](assets/2-9122847844.webp)
**Properties**
- It can have two or more input lines at a time.
- When all of the inputs to the OR gate are low or logic 0, the output of it is low or logic 0.
### **NOT GATE**
[NOT gate](https://www.geeksforgeeks.org/digital-logic/not-gate/) is one of the basic logic gate having only a single input and a single output. It is also known as inverter or inverting buffer. When the input signal is "low" the output signal is "high" and vice-versa.
The Boolean expression of NOT Gate is as follows:
> Y = Ā or
>
> Y = A’
>
> the value of Y will be high when A will be low.
![3](assets/3-e874e9e6e4.webp)
**Properties**
- The output of a NOT gate is complemented or inverse of the input applied to it.
- NOT gate takes only one output.
### **NOR GATE**
The NOR gate is the type of [universal logic gate](https://www.geeksforgeeks.org/digital-logic/universal-logic-gates/). It takes two or more inputs and gives only one output. The output state of the NOR gate will be high (1) when all the inputs are low (0). [NOR](https://www.geeksforgeeks.org/digital-logic/nor-gate/) gate returns the complement result of the OR gate. It is basically a combination of two basic logic gates i.e., OR gate and NOT gate.
The Boolean expression of NOR gate is as follows:
> **O = (A + B)’**
>
> The value of O will be true when all of its inputs are set to 0.
![4](assets/4-b6787733a7.webp)
**Properties**
- A NOR gate can have two or more inputs and gives an output.
- A NOR gate gives a high or logic 1 output only when it's all inputs are low or logic 0.
### **NAND GATE**
The [NAND Gate](https://www.geeksforgeeks.org/digital-logic/what-is-nand-gate/) is another type of [Universal logic gate](https://www.geeksforgeeks.org/digital-logic/universal-logic-gates/). The NAND gate or "Not AND" is the combination of two basic logic gates AND gate and the NOT gate connected in series. It takes two or more inputs and gives only one output. The output of the NAND gate will give result high (1) when either of its input is high (1) or both of its input are low (0). In simple, it performs the inverted operation of AND gate.
The Boolean Expression of NAND Gate is as follows:
> **X = (A. B)’**
![5](assets/5-431954f5e3.webp)
**Properties**
- NAND gate can take two or more inputs at a time and produces one output based on the combination of inputs applied.
- NAND gate produces a low or logic 0 output only when its all inputs are high or logic 1.
### **XOR GATE**
The [XOR gate](https://www.geeksforgeeks.org/digital-logic/xor-gate/) is a special logic gate used to perform modulo-2 addition. It has two inputs and one output. The output is HIGH (1) only when the inputs are different; otherwise, it is LOW (0). XOR gates are widely used in arithmetic logic circuits, comparators, and error detection systems.
The Boolean expression of XOR Gate is:
> **X = A’B + AB’**
![6](assets/6-5f47ad9a2b.webp)
**Properties**
- It can accept only two inputs at a time. There is nothing like a three or more input XOR gate.
- The output of the XOR gate is logic 1 or high, when its inputs are dissimilar.
### **XNOR GATE**
The [XNOR](https://www.geeksforgeeks.org/digital-logic/xnor-gate/) is the combination of XOR gate and NOT gate. The output of the XNOR gate is high(1) when both the inputs are high (1) or low(0). In other words, the output of the XNOR gate is high(1) when both the inputs are the same. the XNOR gate can sometimes be called as Equivalence gate. In simple words, The XNOR gate is the complement of the XOR gate.
The following is the Boolean expression of the XNOR gate,
> **Y = A ⊙ B**
Here, A and B are the input variables and Y is the output variable.
This expression can also be written as follows,
> **Y = AB + A’B’**
We can also express the operation of an XNOR gate using XOR gate logic as follows:
> **Y = (A ⊕ B)’**
![7](assets/7-9769f5b4e1.webp)
**Properties**
- XNOR gate takes only two inputs and produces one output.
- The output of the XNOR gate is high or logic 1 only when it has similar inputs.
## Logic Gates with Symbols, Boolean Expressions, and Truth Tables
![Introduction-of-Logic-Gates](assets/Introduction-of-Logic-Gates-eecbb08aef.webp)
Logic Gates
## Logic Gates in Programming
- [Program to Implement Logic Gates](https://www.geeksforgeeks.org/c/program-to-implement-logic-gates/)
- [Logic Gates in Python](https://www.geeksforgeeks.org/python/logic-gates-in-python/)
## Logic Gates For Competitive Exams
- [Logic Gates For Aptitude Preparation](https://www.geeksforgeeks.org/digital-logic/digital-logic-design-mcqs/)
- [Logic Gates For GATE](https://www.geeksforgeeks.org/digital-logic/digital-logic-for-gate/)
- [Digital Electronics and Logic Design Tutorials](https://www.geeksforgeeks.org/digital-logic/digital-electronics-logic-design-tutorials/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/physics/logic-gates/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Introduction of Boolean Algebra and Logic Gates

> [!note] Related notes
>
> - [[Boolean functions]]
> - [[Canonical and Standard Form]]
> - [[Consensus Theorem]]
> - [[Functional Completeness]]
> - [[Implicants in K-Map]]
> - [[K-Map]]
> - [[Logic Gates]]
> - [[Minimization of Boolean Functions]]
> - [[PDNF and PCNF]]
> - [[Prime implicants and Explicit implicants]]
