---
title: "SLR, CLR and LALR Parsers"
subject: "Compiler Design"
topic: "Lexical Analysis, Parsing, Syntax-directed"
source: "https://www.geeksforgeeks.org/compiler-design/slr-clr-and-lalr-parsers-set-3/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Lexical Analysis, Parsing, Syntax-directed"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/lexical-analysis-parsing-syntax-directed
---


> [!abstract] SLR, CLR and LALR Parsers
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Lexical Analysis, Parsing, Syntax-directed`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/slr-clr-and-lalr-parsers-set-3/)

---

# SLR, CLR and LALR Parsers

Parsing is a fundamental process in compiler design that helps analyze and validate the syntax of programming languages. It converts a sequence of tokens into a structured format, often represented as a parse tree. Among various parsing techniques, LR parsers are widely used due to their efficiency and ability to handle a broad class of grammars.
LR parsers are a type of bottom-up parsers that construct the parse tree from the leaves (tokens) to the root (start symbol). They are deterministic and capable of handling context-free grammars (CFGs) efficiently. The three main types of LR parsers include:
- **SLR (Simple LR) Parser** – The most basic LR parser, using LR(0) items and [FOLLOW](https://www.geeksforgeeks.org/compiler-design/follow-set-in-syntax-analysis/) sets for table construction.
- **CLR (Canonical LR) Parser** – A more powerful parser that utilizes LR(1) items to resolve conflicts and recognize a broader range of grammars.
- **LALR (Look-Ahead LR) Parser** – A memory-optimized version of CLR that merges states to reduce table size while maintaining most of its parsing power.
Each of these parsers differs in terms of complexity, power, and efficiency.
![clr-slr-lalr](assets/clr-slr-lalr-660-070f302144.webp)
Block Diagram of LR Parser
## **Bottom-Up Parsing**
Method used in compilers to analyze and understand code. It starts with the smallest parts of a program (tokens) and gradually builds up to form the complete structure (syntax tree).
In bottom-up parsing:
1. It reads the input from left to right.
2. It groups tokens into larger structures based on grammar rules.
3. It keeps combining these structures until it forms the final result (start symbol).
The most powerful bottom-up parsers are [**LR Parsers**](https://www.geeksforgeeks.org/compiler-design/lr-parser/) (used in programming languages like C and Java). Examples include:
- SLR (Simple LR)
- CLR (Canonical LR)
- LALR (Look-Ahead LR)
Read more about [Bottom-Up Parsing](https://www.geeksforgeeks.org/compiler-design/bottom-up-or-shift-reduce-parsers-set-2/).
![parser_21](assets/Parsing-bc7f1af2ac.jpg)
## SLR(1) Parsing
SLR(1) stands for Simple LR Parsing. It is similar to LR(0) Parsing because LR(0) parsing requires just the canonical items for the construction of a parsing table, The only thing that differentiates the LR(0) parser from the SLR parser is the possibility of a shift reduced conflict because we are entering reduce corresponding to all terminal states in the LR(0) parsing table. In LR(0) Parsing, the parser sometimes mistakenly reduces when it shouldn't, causing shift-reduce conflicts. SLR(1) fixes this issue by only allowing reduce operations in places where they match the FOLLOW set of the left-hand side (LHS) of the production rule. This means that SLR(1) uses FOLLOW sets to make better decisions, reducing conflicts.
### Constructing the SLR(1) parsing Table
> 1. Construct the collection of LR(0) item sets for G′.
>
> 2. For each state i:
>
> - If [A → α . a β] is in Ii and GOTO(Ii, a) = Ij, then
>
> ACTION[i, a] = shift j
>
> - If [A → α .] is in Ii and A ≠ S′, then
>
> ACTION[i, a] = reduce A → α, for all a in FOLLOW(A)
>
> - If [S′ → S .] is in Ii, then
>
> ACTION[i, $] = accept
>
> 3. For each non-terminal A:
>
> - If GOTO(Ii, A) = Ij, then
>
> GOTO[i, A] = j
>
> 4. All remaining entries in ACTION and GOTO are set to error.
>
> 5. Initial state:
>
> - s0 = CLOSURE([S′ → . S])
If in the parsing table we have multiple entries then it is said to be a conflict.
**Example:**
```
Consider the grammar:E → T + E | TT → idAugmented grammar: E’ → EE → T + E | TT → idConstruct the SLR(1) parsing table.Also determine whether the grammar is LR(0) or SLR(1).
```
Given grammar:
```
E → T + E | T  T → id
```
Augment the grammar by adding a new start symbol:
```
E' → E  E  → T + E  E  → T  T  → id
```
Construct the canonical LR(0) items.
The initial state is:
```
I₀:E' → •E  E  → •T + E  E  → •T  T  → •id
```
From I₀:
- On `E`:
```
I₁:E' → E•
```
- On `T`:
```
I₂:E → T• + E  E → T•
```
- On `id`:
```
I₃:T → id•
```
From I₂:
- On `+`:
```
I₄:E → T + •E  E → •T + E  E → •T  T → •id
```
From I₄:
- On `E`:
```
I₅:E → T + E•
```
Now consider state I₂:
```
E → T• + E  E → T•
```
Here, E → T• suggests a reduction, while E → T• + E suggests a shift on symbol +.
This leads to a shift-reduce conflict in LR(0), so the grammar is not LR(0).
Now consider SLR parsing. The FOLLOW sets are:
```
FOLLOW(E) = { $ }  FOLLOW(T) = { +, $ }
```
In SLR parsing, the reduction E → T is applied only on symbols in FOLLOW(E), i.e., $.
Thus, in state I₂:
- On +, shift is performed.
- On $, reduction E → T is performed.
Since the conflict is resolved using FOLLOW sets, no shift-reduce conflict occurs in SLR parsing.
Hence, the grammar is SLR(1) but not LR(0).
Read more about [SLR (1) Parsing](https://www.geeksforgeeks.org/compiler-design/slr-parser-with-examples/).
## **CLR(1) Parsing**
CLR(1) Parsing, also called Canonical LR(1) Parsing, is a type of bottom-up parsing used in compilers to analyze the structure of programming languages. It is an advanced version of SLR(1) Parsing that reduces or resolves conflicts by using look-ahead symbols. These symbols help the parser decide whether to shift or reduce based on what comes next in the input.
Unlike SLR(1), which relies on FOLLOW sets to make reduction decisions, CLR(1) associates a specific look-ahead symbol with each grammar rule. This allows the parser to differentiate between situations where a rule should be applied or postponed, making it more powerful and capable of handling a wider range of grammars.
CLR(1) Parsing works by constructing LR(1) items, which are similar to LR(0) items but include a look-ahead symbol. These items help in building a more accurate parsing table that reduces errors caused by shift-reduce or reduce-reduce conflicts. Because of this, CLR(1) parsing is much more precise than SLR(1), but it also has a drawback—it generates large parsing tables that require more memory and processing time.
### Constructing the LR(1) Parsing Table
> 1. Construct the collection of LR(1) item sets for the augmented grammar G′ using closure₁ and goto₁.
>
> 2. For each state i:
>
> - If [A → α . a β, b] is in Ii and GOTO(Ii, a) = Ij, then
>
> ACTION[i, a] = shift j
>
> - If [A → α . , a] is in Ii and A ≠ S′, then
>
> ACTION[i, a] = reduce A → α
>
> - If [S′ → S . , $] is in Ii, then
>
> ACTION[i, $] = accept
>
> 3. For each non-terminal A:
>
> - If GOTO(Ii, A) = Ij, then
>
> GOTO[i, A] = j
>
> 4. All remaining entries in ACTION and GOTO are set to error.
>
> 5. Initial state:
>
> - s0 = CLOSURE₁([S′ → . S, $])
### Closure₁ and GOTO₁ (CLR(1))
Given Grammar:
```
S → A AA → a A | b
```
Augmented:
```
S′ → S
```
### Closure₁ Example
```
CLOSURE₁([S′ → . S, $])
```
```
[S′ → . S, $][S → . A A, $][A → . a A, a/b][A → . b, a/b]
```
### GOTO₁ Examples
```
GOTO₁([S′ → . S, $], S)[S′ → S ., $]
```
```
GOTO₁([S → . A A, $], A)[S → A . A, $][A → . a A, a/b][A → . b, a/b]
```
**Example:**
```
Consider the following grammar     S -> AaAb | BbBa    A -> a    B -> b    Augmented grammar - S’ -> S    S -> AaAb | BbBa    A -> a    B -> b    Determine whether the grammar is LR(0), SLR(1), or CLR(1).
```
Augmented Grammar
```
S′ → SS → AaAb | BbBaA → aB → b
```
**LR(0) Analysis**
While constructing LR(0) items, we encounter a state containing:
```
S → A • a A bS → B • b B aA → a •B → b •
```
Here:
- A → a • and B → b • indicate reductions
- Multiple reductions appear in the same state
This results in a reduce-reduce conflict
Therefore, the grammar is NOT LR(0)
**SLR(1) Analysis**
Compute FOLLOW sets:
```
FOLLOW(A) = { a, b }FOLLOW(B) = { a, b }
```
Both A and B have the same FOLLOW sets. Hence:
- Reduction A → a applies on {a, b}
- Reduction B → b also applies on {a, b}
This again causes a reduce-reduce conflict
Therefore, the grammar is NOT SLR(1)
**CLR(1) Analysis**
In CLR(1), each item carries a specific lookahead:
```
[A → a • , a][A → a • , b][B → b • , a][B → b • , b]
```
Here, reductions are applied based on exact lookahead symbols, not full FOLLOW sets.
- This removes ambiguity
- No multiple entries in parsing table
Therefore, the grammar is CLR(1)
Read more about [CLR(1) Parsing](https://www.geeksforgeeks.org/compiler-design/clr-parser-with-examples/).
## LALR Parsing
LALR(1) (Look-Ahead LR) Parsing is an optimized version of CLR(1) (Canonical LR(1)) Parsing that reduces the size of the parsing table while maintaining most of its power. In CLR(1), the number of states can become very large because each state keeps look-ahead symbols separately. LALR(1) solves this problem by merging states that have the same LR(0) core items but different look-ahead symbols.
By merging similar states, LALR(1) reduces memory usage while keeping the parsing process efficient. However, in some cases, this merging can lead to shift-reduce or reduce-reduce conflicts, making LALR(1) slightly weaker than CLR(1). Despite this, it is widely used in practical compilers and parser generators like YACC and Bison because it offers a good balance between power and efficiency.
### Constructing the LALR(1) Parsing Table
> 1. Construct the collection of LR(1) item sets for the augmented grammar G′ using closure₁ and goto₁.
>
> 2. Identify all states having the same LR(0) core:
>
> - Merge such states by taking the union of their lookahead symbols.
> - Update the GOTO function accordingly.
>
> 3. For each state i:
>
> - If [A → α . a β, b] is in Ii and GOTO(Ii, a) = Ij, then
>
> ACTION[i, a] = shift j
>
> - If [A → α . , a] is in Ii and A ≠ S′, then
>
> ACTION[i, a] = reduce A → α
>
> - If [S′ → S . , $] is in Ii, then
>
> ACTION[i, $] = accept
>
> 4. For each non-terminal A:
>
> - If GOTO(Ii, A) = Ij, then
>
> GOTO[i, A] = j
>
> 5. All undefined entries in ACTION and GOTO are set to error.
>
> 6. Initial state:
>
> - s0 = CLOSURE₁([S′ → . S, $])
**Example:**
```
Consider the grammar:S → A AA → a A | bAugment the grammar and construct the LALR(1) parsing states.Identify the states that can be merged and conclude whether the grammar is LALR(1).
```
Augmented Grammar
```
S′ → SS → A AA → a A | b
```
Step 1: LR(1) Item Sets (Important States Only)
```
I₀:S′ → . S , $S → . A A , $A → . a A , a/bA → . b , a/b
```
```
I₁:S′ → S . , $
```
```
I₂:S → A . A , $A → . a A , $A → . b , $
```
```
I₃:A → a . A , a/bA → . a A , a/bA → . b , a/b
```
```
I₄:A → b . , a/b
```
```
I₅:S → A A . , $
```
```
I₆:A → a A . , $
```
```
I₇:A → b . , $
```
Step 2: Identify States with Same LR(0) Core
Compare states ignoring lookahead:
```
I₄: A → b . , a/bI₇: A → b . , $
```
Same core → can be merged
```
I₃: A → a . A , a/bI₆: A → a A . , $ (different core, not mergeable)
```
Step 3: Merge States (LALR)
Merge I₄ and I₇:
New state:
```
A → b . , a/b/$
```
Step 4: Final Result
- LR(1) states successfully merged based on same cores
- No conflicts introduced after merging
 Read more about [LALR(1) Parsing](https://www.geeksforgeeks.org/compiler-design/lalr-parser-with-examples/).
### SLR(1) v/s CLR(1) v/s LALR(1)
| Feature | **SLR(1) Parser (Simple LR)** | **CLR(1) Parser (Canonical LR)** | **LALR(1) Parser (Look-Ahead LR)** |
| --- | --- | --- | --- |
| Parsing Table Size | Smallest (fewer states) | Largest (most states) | Medium (states merged to reduce size) |
| Grammar Handling | Limited (only simple grammars) | Most powerful (handles almost all grammars) | Nearly as powerful as CLR but compact |
| Basis for Decisions | Uses FOLLOW sets for reductions | Uses look-ahead symbols to make precise decisions | Uses merged look-ahead symbols, similar to CLR but optimized |
| Conflicts (Shift-Reduce, Reduce-Reduce) | More conflicts due to reliance on FOLLOW sets | Least conflicts because of look-ahead symbols | May introduce reduce-reduce conflicts when merging states |
| Error Detection | Delayed (errors detected later) | Delayed (similar to SLR) | Similar to CLR, not always immediate |
| Time and Space Complexity | Low (fast but limited) | High (slow due to large tables but powerful) | Medium (optimized for efficiency) |
| Ease of Implementation | Easiest (simplest to build) | Most complex (large tables make it harder) | Easier than CLR but slightly more complex than SLR |
| Used In | Simple parsers and educational tools | Strong theoretical compilers (not widely used in practice) | Most real-world compilers (YACC, Bison, etc.) |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/slr-clr-and-lalr-parsers-set-3/)

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
