---
title: "Ambiguous Grammar"
subject: "Compiler Design"
topic: "Lexical Analysis, Parsing, Syntax-directed"
source: "https://www.geeksforgeeks.org/compiler-design/ambiguous-grammar/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Lexical Analysis, Parsing, Syntax-directed"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/lexical-analysis-parsing-syntax-directed
---


> [!abstract] Ambiguous Grammar
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Lexical Analysis, Parsing, Syntax-directed`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/ambiguous-grammar/)

---

# Ambiguous Grammar

A Context-Free Grammar (CFG) describes the structure of a language using production rules. Based on the number of parse trees generated for a string, CFGs are classified as:
1. Ambiguous Grammar
2. Unambiguous Grammar
## **Ambiguous grammar**
A [CFG](https://www.geeksforgeeks.org/theory-of-computation/what-is-context-free-grammar/) is ambiguous if at least one string has more than one parse tree or derivation.
A CFG G = (V, T, P, S) is ambiguous if a string in T\* can be derived in more than one way.
 Where:
 V = set of non-terminals
 T = set of terminals
 P = set of production rules
 S = start symbol.
Example 1. Let us consider this grammar: E-> E + E | E\*E | id, We can create two parse tree from this grammar to obtain a string **id + id \* id.**
![ambiguous_grammar](assets/ambiguous_grammar-660-07a55e95cc.jpg)
Both the above parse trees are derived from the same grammar rules but both parse trees are different. Hence the grammar is ambiguous.    
Example 2. Let us now consider the following grammar:  
```
Set of symbols Σ = {0, …, 9, +, *, (, )}E -> I        E -> E + EE -> E * EE -> (E)I -> ε | 0 | 1 | … | 9 
```
From the above grammar, the string 3\*2+5 can be derived in two ways
```
I) First leftmost derivation                   II) Second leftmost derivation        E=>E*E                                                        E=>E+E         =>I*E                                                             =>E*E+E         =>3*E+E                                                        =>I*E+E         =>3*I+E                                                         =>3*E+E         =>3*2+E                                                        =>3*I+E         =>3*2+I                                                         =>3*2+I         =>3*2+5                                                        =>3*2+5
```
  Following are some examples of ambiguous grammar:  
- S -> aS | Sa | ε
- E-> E +E | E\*E| id
- A -> AA | (A) | a
- S -> SS | AB
- A -> Aa | a
- B -> Bb | b
## Unambiguous Grammar
A CFG is unambiguous if every string has only one parse tree (one leftmost and one rightmost derivation).
Example:
E → E + T | T
 T → T \* F | F
 F → (E) | id
This grammar defines operator precedence (multiplication before addition), so each string has only one valid parse tree.
## Removal of Ambiguity in Grammar
To remove ambiguity from a grammar, follow these simple steps:
1. **Simplify production rules**: Break down complex rules into smaller and simpler ones. This way, the grammar won't allow multiple interpretations for the same string.
2. **Set precedence and associativity**: For things like math operations, make sure the order in which they are applied is clear. For example, define that multiplication happens before addition, or how to group operations (left-to-right or right-to-left).
3. **Fix left recursion**: Left recursion occurs when a rule refers to itself in a way that causes infinite loops. To fix it, change the rules so that recursion happens at the end, not at the start.
4. **Factor out common parts**: If two rules start the same way, combine the common part. For example, instead of having rules like **A → αβ** and **A → αγ**, make it **A → αA'** and **A' → β | γ**.
Read more about [Removal of Ambiguity in Grammar](https://www.geeksforgeeks.org/theory-of-computation/removal-of-ambiguity-converting-an-ambiguos-grammar-into-unambiguos-grammar/).
## **Inherent Ambiguity**
A Context-Free Language (CFL) is said to be inherently ambiguous if every possible grammar for the language is ambiguous. This means no matter how you write the grammar for the language, there will always be strings in that language that can be parsed in more than one way.
### Example:
Consider the language **L** defined as:
L = { **aⁿbⁿcᵐdᵐ : n ≥ 1, m ≥ 1** } ∪ { **aⁿbᵐcᵐdⁿ : n ≥ 1, m ≥ 1** }
A grammar for this language could be:
- **S → AB | C**
- **A → aAb | ab**
- **B → cBd | cd**
- **C → aCd | aDd**
- **D → bDc | bc**
Let’s see how the string **aabbccdd** can be parsed. This string has two possible leftmost derivations:
Using **S → AB**:
- **S ⇒ AB**
- **A → aAb** ⇒ **aAbB**
- **A → ab** ⇒ **aabbB**
- **B → cBd** ⇒ **aabbcBd**
- **B → cd** ⇒ **aabbccdd**
Using **S → C**:
- **S ⇒ C**
- **C → aCd** ⇒ **aCd**
- **C → aDd** ⇒ **aaDdd**
- **D → bDc** ⇒ **aabDcdd**
- **D → bc** ⇒ **aabbccdd**
![ambiguous_grammar_2](assets/ambiguous_grammar_2-660-245ae32699.jpg)
Both derivations result in the same string **aabbccdd**, but they come from different rules and paths, showing that there is more than one way to parse the string.
Since there are multiple ways to parse the string **aabbccdd** and this pattern holds for all grammars of **L**, we can conclude that **L** is inherently ambiguous. This means no grammar for **L** can avoid ambiguity for all strings in the language.
## **Important Points on Ambiguous Grammar**
**1)** A grammar is ambiguous if a string has more than one parse tree or derivation. This combination can lead to multiple ways of deriving the same string, creating more than one parse tree.
**Example**: **S → SaS | ε**
Here, the grammar has both **left recursion** (S → SaS) and **right recursion** (S → ε), making it ambiguous. This allows multiple derivations for the same string, such as **{aa}**, leading to more than one parse tree.
![ambiguous_grammar_4](assets/ambiguous_grammar_4-660-c89a5d8da6.webp)
**2)** Even if a grammar does not have both **left** and **right recursion**, it can still be **ambiguous**. The absence of recursion does not guarantee that the grammar is unambiguous.
**Example: S → aB | ab , A → AB | a , B → Abb | b**
In this example, there is no left or right recursion, but the grammar is still ambiguous. For the string **{ab}**, we can derive it in multiple ways, resulting in more than one parse tree. This shows that even without recursion, a grammar can still be ambiguous.
![ambiguous_grammar_3](assets/ambiguous_grammar_3-660-a58696c461.jpg)
From the above example, we can see that even if both left and right recursion are not present in grammar, the grammar can be ambiguous.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/ambiguous-grammar/)

## GATE CS

- Subject: Compiler Design
- Topic: Lexical Analysis, Parsing, Syntax-directed

> [!note] Related notes
>
> - [[Backtracking]]
> - [[Bottom Up or Shift Reduce Parsers]]
> - [[Classification of Context Free Grammars]]
> - [[Classification of top down parsers]]
> - [[Error detection and Recovery in Compiler]]
> - [[Error Handling in Compiler Design]]
> - [[Fast Lexical Analyzer Generator]]
> - [[FIRST Set in Syntax Analysis]]
> - [[FOLLOW Set in Syntax Analysis]]
> - [[Generation of Programming Languages]]
