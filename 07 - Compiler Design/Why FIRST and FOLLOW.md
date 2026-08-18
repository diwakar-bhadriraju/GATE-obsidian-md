---
title: "FIRST and FOLLOW in Compiler Design"
subject: "Compiler Design"
topic: "Lexical Analysis, Parsing, Syntax-directed"
source: "https://www.geeksforgeeks.org/compiler-design/why-first-and-follow-in-compiler-design/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Lexical Analysis, Parsing, Syntax-directed"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/lexical-analysis-parsing-syntax-directed
---


> [!abstract] FIRST and FOLLOW in Compiler Design
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Lexical Analysis, Parsing, Syntax-directed`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/why-first-and-follow-in-compiler-design/)

---

# FIRST and FOLLOW in Compiler Design

FIRST and FOLLOW are two sets used to help parsers understand how to process a grammar.
- **FIRST Set:** The FIRST set of a non-terminal contains all terminal symbols that can appear at the beginning of strings derived from it (including ε if applicable).
- **FOLLOW Set:** The FOLLOW set of a non-terminal contains all terminal symbols that can appear immediately to its right in any sentential form (including $ for the start symbol).
## FIRST (X)
The FIRST(X) set is a collection of terminal symbols (and possibly ε) that can appear as the leftmost symbol when we expand X in a derivation of a given grammar.
### **When X is a terminal:**
If X is a terminal symbol (for example, 'a' or 'b'), the FIRST(X) set simply contains X itself, since a terminal always starts with itself.
Example: If X = a, then FIRST(a) = {a}.
### **When X has only one production rule of type X** → **aY:**
If a non-terminal has a production that begins with a terminal symbol, then the FIRST set contains that terminal symbol.
Example:
```
A → a B
```
Here, the FIRST set of A contains the first terminal symbol on the right-hand side.
```
FIRST(A) = { a }
```
### **When X has multiple production rules:**
If X is a non-terminal (for example, A or B), the FIRST(X) set includes all the terminal symbols that could be the first symbol of any string derived from X. This means, for each production rule of X, you look at what can be the first symbol of that rule.
Example:
> `A → a B`
> `A → b`
> `A → ε`
Here, FIRST(A) = {a, b, ε} because:
- The first symbol in the first production A → a B is 'a'.
- The first symbol in the second production A → b is 'b'.
- The third production A → ε means A can derive an empty string, so **ε** is included.
### **When X is a string of non-terminals:**
If X is a string made up of terminals and/or non-terminals (like A B C), we start with the leftmost symbol and use its FIRST set.
To compute FIRST(X), you look at FIRST(A). If A can derive ε (i.e., the empty string), then you also look at FIRST(B), and so on. If both A and B can derive ε, you also need to consider FIRST(C).
Example:
> `X → A B C`
> A→a∣ε
> B→b∣ε
> C→c∣d
The FIRST(X) is {a,b,c,d}.
This is because:
- A contributes a and ε.
- B contributes b and ε.
- C contributes c and d. Since A and B can both derive ε, we include the first symbols of C.
Read more about [FIRST Set in Syntax Analysis.](https://www.geeksforgeeks.org/compiler-design/first-set-in-syntax-analysis/)
## FOLLOW (X)
The FOLLOW(X) set contains all the terminal symbols that can appear immediately after the non-terminal X in any valid string derived from the grammar. It is used in parsing to decide what symbols can follow a particular non-terminal in a derivation.
### **When X is the start symbol of the grammar:**
If X is the start symbol (e.g., S), the FOLLOW(S) set always includes the special end-of-input marker `$` to indicate that nothing comes after the start symbol in a complete string.
Example:
> `Start Symbol = S`
> `FOLLOW(S) = { $ }`
### **When X appears before a terminal:**
If X is followed by a terminal symbol in a production rule, that terminal symbol is added to FOLLOW(X).
Example:
> `A → a B c`
Here, B is followed by c, so c is in FOLLOW(B).
### **When X appears before a non-terminal:**
If **X** is followed by a non-terminal (e.g., B), the FIRST(B) set is added to FOLLOW(X). However, if B can derive ε (empty string), then
- FOLLOW(X) include the FIRST of terminal or non-terminal (excluding ε) that is after B.
- If there is nothing after B then FOLLOW(X) include the FOLLOW of left-hand side non-terminal of the production rule.
Example:
> `A → a X B`
> `B → b |` ε
If FIRST(B) = {b, ε}, then:
- b is added to FOLLOW(X).
- Since B can derive ε, FOLLOW(A) will also be included in FOLLOW(X).
### **When X appears at the end of a production rule:**
If X appears at the end of a production rule (e.g., A → B X), then FOLLOW(A) is added to FOLLOW(X) because whatever follows A in the string must also follow X.
Example:
> `A → B X`
Here, everything in FOLLOW(A) must also be included in FOLLOW(X).
Read more about [FOLLOW Set in Syntax Analysis](https://www.geeksforgeeks.org/compiler-design/follow-set-in-syntax-analysis/).
## Importance of FIRST and FOLLOW Set
The FIRST and FOLLOW sets play a crucial role in [LL(1) parsing](https://www.geeksforgeeks.org/compiler-design/ll1-parsing-algorithm/) and grammar analysis, with multiple important applications:
### **Building LL(1) Parsing Tables**
- FIRST and FOLLOW sets help create parsing tables used by LL(1) parsers. These tables guide the parser in selecting the correct production based on the next input symbol.
- Without these sets, it would be impossible to systematically and deterministically decide which rule to apply.
### **Ensuring Grammar is LL(1)**
- By analyzing FIRST and FOLLOW, we can check if a grammar satisfies the LL(1) condition: no overlapping entries in the parsing table for any non-terminal and input symbol.
- This ensures that the grammar is unambiguous and suitable for top-down parsing.
### **Handling ε-Productions**
- The FIRST set includes ε (empty string) when a non-terminal can derive ε.
- The FOLLOW set ensures that after ε, the parser knows which symbols can legally follow.
### **Predictive Parsing**
- These sets allow a parser to predict the correct production to use without backtracking.
- This makes LL(1) parsers efficient, as they don’t need to retry multiple rules.
### **Error Detection and Recovery**
- The FOLLOW set helps the parser identify errors in the input string by showing what symbols are expected at a given point.
- This aids in implementing error recovery mechanisms during parsing.
### **Compiler Design and Syntax Analysis**
- Both sets are foundational in compiler design, enabling systematic analysis of context-free grammars.
- They are used to construct LL(1) parsing tables and enable predictive parsing without backtracking.
> **Related Links:**
> [Quiz on Syntax Analysis](https://www.geeksforgeeks.org/quizzes/parsing-and-syntax-directed-translation-gq/)
> [Program to calculate FIRST and FOLLOW sets of given grammar](https://www.geeksforgeeks.org/compiler-design/program-calculate-first-follow-sets-given-grammar/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/why-first-and-follow-in-compiler-design/)

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
