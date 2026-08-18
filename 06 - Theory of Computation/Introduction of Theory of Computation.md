---
title: "Introduction to Theory of Computation"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/introduction-of-theory-of-computation/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Introduction to Theory of Computation
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/introduction-of-theory-of-computation/)

---

# Introduction to Theory of Computation

Automata theory, also known as the Theory of Computation, is a field within computer science and mathematics that focuses on studying abstract machines to understand the capabilities and limitations of computation by analyzing mathematical models of how machines can perform calculations.
### 1. Symbol
A symbol (often also called a character) is the smallest building block, which can be any alphabet, letter, or picture. 
![1](assets/1-752f8b012c.webp)
### 2. Alphabets (Σ)
A finite, non-empty set of symbols used to construct strings and languages. For example, Σ = {a, b}.
![3815826](assets/3815826-d5d3961738.webp)
### 3. String
A string is a **finite** sequence of symbols from some alphabet. A string is generally denoted as **w** and the length of a string is denoted as **|w|**. Empty string is the string with zero occurrence of symbols, represented as ε.
> **Number of Strings (of length 2)**
> **that can be generated over the alphabet {a, b}:**
>  **- -**
>  a a
>  a b
>  b a
>  b b
>
> Length of String |w| = 2
> Number of Strings = 4
>
> **Conclusion:**
> For alphabet {a, b} with length **n**, number of
> strings can be generated = **2**n**.
Automata theory is used in modeling computational problems hence enhancing the understanding and design of systems such as compilers, interpreters among others.
## Closure Representation in TOC
**1. L**+**: It is a **Positive Closure** that represents a set of all strings except Null or ε-strings.
**2. L**\**: It is "**Kleene Closure**", that represents the occurrence of certain alphabets for given language alphabets from zero to the infinite number of times. In which ε-string is also included.
From the above two statements, it can be concluded that: **L\* = εL**+**
**Example:**
> **(a) Regular expression for language accepting all combination of g's over Σ={g}:**
> **R = g**\**
> R={ε,g,gg,ggg,gggg,ggggg,...}
>
> **(b) Regular Expression for language accepting all combination of g's over Σ={g} :**
> **R = g**+**
> R={g,gg,ggg,gggg,ggggg,gggggg,...}
Kleene Star is also called a **"Kleene Operator"** or **"Kleene Closure"**. Engineers and IT professionals make use of Kleene Star to achieve all set of strings which is to be included from a given set of characters or symbols. It is one kind of Unary operator. In Kleene Star methodology all individual elements of a given string must be present but additional elements or combinations of these alphabets can be included to any extent.
**Example:**
> **Input String: "GFG".**
> Σ\* = { ε,"GFG","GGFG","GGFG","GFGGGGGGGG","GGGGGGGGFFFFFFFFFGGGGGGGG",...}
> (Kleene Star is an infinite set but if we provide any grammar rules then it can work as a finite set.
> Please note that we can include ε string also in given Kleene star representation.)
## Language
- A language is a set of strings formed using the symbols of a given alphabet Σ\SigmaΣ.
- Formally, a language is a subset of Σ∗\Sigma^\*Σ∗, where Σ∗\Sigma^\*Σ∗ is the set of all possible strings (including ε) over the alphabet Σ\SigmaΣ.
**Examples of Languages:**
> Finite Language:
>  L1 = { set of string of 2 }
>  L1 = { xy, yx, xx, yy }
>
> Infinite Language:
>  L1 = { set of all strings starts with 'b' }
>  L1 = { babb, baa, ba, bbb, baab, ....... }
## Types of Languages in TOC
Languages are classified based on the computational model or grammar generating them:
1. **Regular Languages:** Defined using regular expressions or finite automata. Example:
$$
L=a^n∣n≥0.
$$
2. **Context-Free Languages:** Defined using context-free grammars or pushdown automata. Example:
$$
L=a^n b^n ∣n≥0.
$$
3. **Context-Sensitive Languages:** Defined using context-sensitive grammars or linear-bounded automata.
4. **Recursive and Recursively Enumerable Languages:** Defined using Turing machines.
## Core Areas of the Theory of Computation
The field of computation theory can be broadly divided into three major areas:
### 1. Automata Theory
Automata theory studies abstract computational models and their applications. It forms the basis for understanding how machines process inputs and produce outputs. Key components include:
- **Finite Automata**: Used to model simple systems like lexical analyzers in compilers.
- **Pushdown Automata**: A more powerful model capable of recognizing context-free languages, essential for parsing programming languages.
- **Turing Machines**: The most powerful automata, used as a standard for defining what is computable.
### 2. Formal Languages and Grammars
This area examines the syntax and structure of languages used in computation.
- **Regular Languages**: Described by regular expressions and finite automata, representing simple patterns.
- **Context-Free Languages**: Defined by context-free grammars, crucial for designing compilers.
- **Chomsky Hierarchy**: A classification of languages into regular, context-free, context-sensitive, and recursively enumerable languages.
### 3. Computability and Decidability
Computability theory addresses the question: What problems can a computer solve? It studies concepts like:
- **Decidable Problems**: Problems with an algorithmic solution.
- **Undecidable Problems**: Problems, such as the Halting Problem, for which no algorithm can determine a solution for all inputs.
### 4. Complexity Theory
Complexity theory focuses on the efficiency of algorithms by analyzing the time and space resources they require. It categorizes problems into classes such as:
- **P (Polynomial Time)**: Problems solvable in polynomial time.
- **NP (Nondeterministic Polynomial Time)**: Problems whose solutions can be verified in polynomial time.
- **NP-Complete and NP-Hard**: The most challenging problems in NP, with applications in cryptography, optimization, and artificial intelligence.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/introduction-of-theory-of-computation/)

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
