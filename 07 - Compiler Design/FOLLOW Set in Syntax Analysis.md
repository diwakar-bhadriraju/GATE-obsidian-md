---
title: "FOLLOW Set in Syntax Analysis"
subject: "Compiler Design"
topic: "Lexical Analysis, Parsing, Syntax-directed"
source: "https://www.geeksforgeeks.org/compiler-design/follow-set-in-syntax-analysis/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Lexical Analysis, Parsing, Syntax-directed"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/lexical-analysis-parsing-syntax-directed
---


> [!abstract] FOLLOW Set in Syntax Analysis
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Lexical Analysis, Parsing, Syntax-directed`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/follow-set-in-syntax-analysis/)

---

# FOLLOW Set in Syntax Analysis

The FOLLOW set in Syntax Analysis is a group of symbols that can come right after a non-terminal in a grammar. It helps parsers figure out what should appear next in the input while checking if the grammar is correct. The FOLLOW set is important for building parsing tables, especially in LL(1) parsers, which use it to decide how to process rules during syntax checking.
For example, if you're analyzing a sentence in a programming language, the FOLLOW set tells the parser what valid symbols can follow a specific rule or variable. It also includes the end-of-input symbol (`$`) to show when the input string ends. This makes the FOLLOW set an essential tool in creating reliable parsers for programming languages.
**Example:**
```
S ->Aa | AcA ->b        S                  S       /  \              /   \    A    a            A     c    |                 |    b                 b   Here, FOLLOW (A) = {a, c}
```
## Rules to compute FOLLOW set:
1) FOLLOW(S) = { $ } // where S is the starting Non-Terminal
2) If A -> pBq is a production, where p, B and q are any grammar symbols,
 then everything in FIRST(q) except Є is in FOLLOW(B).
3) If A->pB is a production, then everything in FOLLOW(A) is in FOLLOW(B).
4) If A->pBq is a production and FIRST(q) contains Є,
 then FOLLOW(B) contains { FIRST(q) – Є } U FOLLOW(A)
**Example 1:** 
```
Production Rules:E -> TE’E’ -> +T E’|ЄT -> F T’T’ -> *F T’ | ЄF -> (E) | idFIRST setFIRST(E) = FIRST(T) = { ( , id }FIRST(E’) = { +, Є }FIRST(T) = FIRST(F) = { ( , id }FIRST(T’) = { *, Є }FIRST(F) = { ( , id }FOLLOW SetFOLLOW(E)  = { $ , ) }  // Note  ')' is there because of rule 3 (the propagation of FOLLOW(E) through the non-terminal E’)FOLLOW(E’) = FOLLOW(E) = {  $, ) }  // See 1st production ruleFOLLOW(T)  = { FIRST(E’) – Є } U FOLLOW(E’) U FOLLOW(E) = { + , $ , ) }FOLLOW(T’) = FOLLOW(T) =      { + , $ , ) }FOLLOW(F)  = { FIRST(T’) –  Є } U FOLLOW(T’) U FOLLOW(T) = { *, +, $, ) }
```
**Example 2:** 
```
Production Rules:S -> aBDhB -> cCC -> bC | ЄD -> EFE -> g | ЄF -> f | ЄFIRST setFIRST(S) = { a }FIRST(B) = { c }FIRST(C) = { b , Є }FIRST(D) = FIRST(E) U FIRST(F) = { g, f, Є }FIRST(E) = { g , Є }FIRST(F) = { f , Є }FOLLOW SetFOLLOW(S) = { $ } FOLLOW(B) = { FIRST(D) – Є } U FIRST(h) = { g , f , h }FOLLOW(C) = FOLLOW(B) = { g , f , h }FOLLOW(D) = FIRST(h) = { h }FOLLOW(E) = { FIRST(F) – Є } U FOLLOW(D) = { f , h }FOLLOW(F) = FOLLOW(D) = { h }
```
**Example 3:**  
```
Production Rules:S -> ACB|Cbb|BaA -> da|BCB-> g|ЄC-> h| ЄFIRST setFIRST(S) = FIRST(A) U FIRST(B) U FIRST(C) = { d, g, h, Є, b, a}FIRST(A) = { d } U {FIRST(B)-Є} U FIRST(C) = { d, g, h, Є }FIRST(B) = { g, Є }FIRST(C) = { h, Є }FOLLOW SetFOLLOW(S) = { $ }FOLLOW(A)  = { h, g, $ }FOLLOW(B) = { a, $, h, g }FOLLOW(C) = { b, g, $, h }
```
**Note:**
1. Є as a FOLLOW doesn’t mean anything (Є is an empty string).
2. $ is called end-marker, which represents the end of the input string, hence used while parsing to indicate that the input string has been completely processed.
3. The grammar used above is [Context-Free Grammar](https://www.geeksforgeeks.org/theory-of-computation/what-is-context-free-grammar/) (CFG). The syntax of a programming language can be specified using CFG.
4. CFG is of the form A -> B, where A is a single Non-Terminal, and B can be a set of grammar symbols. ( i.e. Terminals as well as Non-Terminals)
## Features of FOLLOW Set
The FOLLOW set in syntax analysis has several important features that make it essential for parsing algorithms, especially in predictive parsers like LL(1). Here are its key features:
1. **Identifies Valid Successors**: It contains all terminal symbols that can immediately follow a non-terminal in any derivation.
2. **End-of-Input Marker (**`$`**)**: For the start symbol of a grammar, the FOLLOW set always includes the end-of-input marker `$`, indicating the end of parsing.
3. **Assists in Parsing Table Construction**: It is used in [LL(1)](https://www.geeksforgeeks.org/compiler-design/construction-of-ll1-parsing-table/) parsing to decide which production rule to apply based on the next input symbol.
4. **Handles Nullable Productions**: If a non-terminal can derive an empty string (nullable), the FOLLOW set of that non-terminal contributes to its parent non-terminal.
5. **Ensures Predictive Parsing**: By using the FOLLOW set, parsers avoid ambiguity and ensure that only one rule is chosen for a given input.
6. **Closely Linked to FIRST Set**: The FOLLOW set works with the [FIRST set](https://www.geeksforgeeks.org/compiler-design/first-set-in-syntax-analysis/) to resolve grammar rules and predict parsing steps effectively.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/follow-set-in-syntax-analysis/)

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
> - [[Generation of Programming Languages]]
