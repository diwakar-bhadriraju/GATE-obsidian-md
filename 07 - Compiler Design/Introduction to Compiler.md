---
title: "Single Pass vs Two-Pass (Multi-Pass) Compilers"
subject: "Compiler Design"
topic: "Lexical Analysis, Parsing, Syntax-directed"
source: "https://www.geeksforgeeks.org/compiler-design/single-pass-two-pass-and-multi-pass-compilers/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Lexical Analysis, Parsing, Syntax-directed"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/lexical-analysis-parsing-syntax-directed
---


> [!abstract] Single Pass vs Two-Pass (Multi-Pass) Compilers
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Lexical Analysis, Parsing, Syntax-directed`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/single-pass-two-pass-and-multi-pass-compilers/)

---

# Single Pass vs Two-Pass (Multi-Pass) Compilers

The compilation process can be organized in different ways based on how the source program is analyzed and translated. One common classification depends on the number of times the compiler processes the source code during compilation. Each complete traversal of the source program or its intermediate representation is called a compiler pass. Based on the number of passes performed, compilers are categorized into :
- Single-pass compilers
- Multi-pass compilers
## Types of Compiler Passes
Compiler passes are classified based on how many times the source program is processed during compilation.
### **1. Single Pass Compiler**
Reads the source code only once and performs all compilation phases in that single scan.
![1](assets/1-65117be1b1.webp)
Single pass Compiler
### Key Characteristics:
- Processes source code only once
- Faster compilation
- Simple design
- Less memory usage
- Limited optimization capability
### Limitations:
- Difficult to handle forward references
- Limited error detection
- Requires simpler grammar
- Poor optimization
### **2. Two-Pass compiler / Multi-Pass compiler**
- A Two-Pass Compiler processes the source program twice.
- A Multi-Pass Compiler processes it more than two times.
Typically divided into:
![2](assets/2-998f6d22d9.webp)
Multi-Pass Compiler
**First Pass (Front-End / Analysis Phase)**
- Lexical Analysis
- Syntax Analysis
- Semantic Analysis
- Intermediate Code Generation
- Platform Independent
**Second Pass (Back-End / Synthesis Phase)**
- Code Optimization
- Code Generation
- Machine-dependent tasks
- Platform Dependent
## Difference Between One Pass and Two Pass Compiler
| One-Pass Compiler | Two-Pass Compiler |
| --- | --- |
| Compiles source code in a single pass | Compiles source code in two passes |
| Scans source code once | Scans source code twice |
| Faster | Slower |
| Limited optimization | Better optimization |
| Limited error detection | Better error detection |
| Simple design | More complex design |
| Less memory required | More memory required |
| May not generate intermediate code | Usually generates intermediate code |
| Suitable for simple languages | Suitable for complex languages |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/single-pass-two-pass-and-multi-pass-compilers/)

## GATE CS

- Subject: Compiler Design
- Topic: Lexical Analysis, Parsing, Syntax-directed

> [!note] Related notes
>
> - [[Ambiguous Grammar]]
> - [[Backtracking]]
> - [[Bottom Up or Shift Reduce Parsers]]
> - [[Classification of Context Free Grammars]]
> - [[Classification of top down parsers]]
> - [[Error detection and Recovery in Compiler]]
> - [[Error Handling in Compiler Design]]
> - [[Fast Lexical Analyzer Generator]]
> - [[FIRST Set in Syntax Analysis]]
> - [[FOLLOW Set in Syntax Analysis]]
