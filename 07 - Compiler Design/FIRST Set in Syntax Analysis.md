---
title: "FIRST Set in Syntax Analysis"
subject: "Compiler Design"
topic: "Lexical Analysis, Parsing, Syntax-directed"
source: "https://www.geeksforgeeks.org/compiler-design/first-set-in-syntax-analysis/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Lexical Analysis, Parsing, Syntax-directed"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/lexical-analysis-parsing-syntax-directed
---


> [!abstract] FIRST Set in Syntax Analysis
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Lexical Analysis, Parsing, Syntax-directed`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/first-set-in-syntax-analysis/)

---

# FIRST Set in Syntax Analysis

The FIRST set is used in syntax analysis to identify which terminal symbols can appear at the start of strings derived from a non-terminal. It is crucial for LL and LR parsers, helping them decide which rules to apply.
To compute the FIRST set:
1. Add the terminal itself to the FIRST set for all terminals.
2. For non-terminals, add the FIRST terminal from the right-hand side of their productions.
3. Repeat until no more symbols can be added.
In LL parsers, if the next input symbol matches the FIRST set of a non-terminal, that rule can be safely applied. The FIRST set is also used in computing the FOLLOW set, which identifies what can come immediately after a non-terminal in a grammar.
## Rules to Compute **FIRST Set**
If x is a terminal, then FIRST(x) = { ‘x’ }
If x-> ε, is a production rule, then add ε to FIRST(x).
If X->Y1 Y2 Y3….Yn is a production, 
- FIRST(X) = FIRST(Y1)
- If FIRST(Y1) contains ε then FIRST(X) = { FIRST(Y1) – ε } U { FIRST(Y2) }
- If FIRST (Yi) contains ε for all i = 1 to n, then add ε to FIRST(X).
**Example 1:** 
```
Production Rules of GrammarE  -> TE’E’ -> +T E’| εT  -> F T’T’ -> *F T’ |  εF  -> (E) | idFIRST setsFIRST(E) = FIRST(T) = { ( , id }FIRST(E’) = { +, ε}FIRST(T) = FIRST(F) = { ( , id }FIRST(T’) = { *, ε }FIRST(F) = { ( , id }
```
**Example 2:** 
```
Production Rules of GrammarS -> ACB | Cbb | BaA -> da | BCB -> g | εC -> h | εFIRST setsFIRST(S) = FIRST(ACB) U FIRST(Cbb) U FIRST(Ba)         = { d, g, h, b, a,  ε}FIRST(A) = { d } U FIRST(BC)          = { d, g, h,  ε }FIRST(B) = { g ,  ε }FIRST(C) = { h ,  ε }
```
**Notes:**
1. The grammar used above is Context-Free Grammar ([CFG](https://www.geeksforgeeks.org/theory-of-computation/what-is-context-free-grammar/)). Syntax of most programming languages can be specified using CFG.
2. CFG is of the form A -> B, where A is a single Non-Terminal, and B can be a set of grammar symbols ( i.e. Terminals as well as Non-Terminals)
## Features of FIRST Sets
- **Definition:** The FIRST set of a nonterminal symbol is the set of terminal symbols that can appear as the first symbol in a string derived from that nonterminal. In other words, it is the set of all possible starting symbols for a string derived from that nonterminal.
- **Calculation:** The FIRST set for each nonterminal symbol is calculated by examining the productions for that symbol and determining which terminal symbols can appear as the first symbol in a string derived from that production.
- **Recursive Descent Parsing:** The FIRST set is often used in recursive descent parsing, which is a [top-down parsing](https://www.geeksforgeeks.org/compiler-design/classification-of-top-down-parsers/) technique that uses the FIRST set to determine which production to use at each step of the parsing process.
- **Ambiguity Resolution:** The FIRST set can help resolve ambiguities in the grammar by providing a way to determine which production to use based on the next input symbol.
- **Follow Set:** The [FOLLOW set](https://www.geeksforgeeks.org/compiler-design/follow-set-in-syntax-analysis/) is another concept used in syntax analysis that represents the set of symbols that can appear immediately after a nonterminal symbol in a derivation. The FOLLOW set is often used in conjunction with the FIRST set to resolve parsing conflicts and ensure that the parser can correctly identify the structure of the input code.
## **Advantages of Using FIRST Set in Syntax Analysis**
- **Improved parsing:** FIRST set can be used to determine which production rule should be used to expand a non-terminal in an LL or LR parser, which helps to improve the accuracy and efficiency of the parsing process.
- **Ambiguity resolution:** FIRST set can be used to resolve ambiguities in the grammar, by determining which production rule should be used in cases where multiple production rules can apply to the same non-terminal.
- **Simplified error handling:** By determining which production rule should be used based on the FIRST set, an LL or LR parser can detect errors in the source code more quickly and accurately.
## **Disadvantages of Using FIRST Set in Syntax Analysis**
- **Complexity:** Computing FIRST set can be a complex process, especially for grammars with many non-terminals and production rules.
- **Limited applicability:** FIRST set is mainly used in [LL and LR](https://www.geeksforgeeks.org/compiler-design/difference-between-ll-and-lr-parser/) parsing algorithms, and may not be applicable to other types of parsing algorithms.
- **Limitations of LL parsing:** LL parsing is limited in its ability to handle certain types of grammars, such as those with left-recursive rules, which can lead to an infinite loop in the parser.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/first-set-in-syntax-analysis/)

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
> - [[FOLLOW Set in Syntax Analysis]]
> - [[Generation of Programming Languages]]
