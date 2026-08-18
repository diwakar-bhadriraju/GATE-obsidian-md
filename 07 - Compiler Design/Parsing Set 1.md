---
title: "Introduction to Parsers"
subject: "Compiler Design"
topic: "Lexical Analysis, Parsing, Syntax-directed"
source: "https://www.geeksforgeeks.org/compiler-design/introduction-of-parsing-ambiguity-and-parsers-set-1/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Lexical Analysis, Parsing, Syntax-directed"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/lexical-analysis-parsing-syntax-directed
---


> [!abstract] Introduction to Parsers
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Lexical Analysis, Parsing, Syntax-directed`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/introduction-of-parsing-ambiguity-and-parsers-set-1/)

---

# Introduction to Parsers

Parsing is the process of analyzing a sequence of tokens to determine their grammatical structure according to the rules of a language. It organizes tokens into a parse tree or syntax tree, which represents the structural relationship between different parts of the input.
![Parsing](assets/Parsing-8a084d96ca.webp)
Parsing
- Converts tokens into a structured parse tree
- Helps understand the grammatical structure of text or code
- Ensures the input follows syntax rules
- Used in compilers, interpreters, and NLP applications
- Supports further tasks like semantic analysis and code execution
## Role of Parser
A parser performs syntactic and [semantic analysis](https://www.geeksforgeeks.org/nlp/understanding-semantic-analysis-nlp/) of source code by converting tokens into a structured intermediate representation while identifying errors in the code.
- Checks whether code follows grammar and syntax rules
- Supports context-sensitive analysis such as type checking
- Generates parse trees or Abstract Syntax Trees (ASTs)
- Detects and reports syntax errors clearly
- Attempts basic error recovery during parsing
## Types of Parsing
The parsing is divided into two types
![parsers](assets/parsers-660-ed790ae0bd.webp)
Types of Parsers
## 1. Top-Down Parsing
[Top-down Parsing](https://www.geeksforgeeks.org/compiler-design/what-is-top-down-parsing-with-backtracking-in-compiler-design/) builds the parse tree from the start symbol toward the input symbols.
- Starts from the start symbol
- Expands non-terminals using production rules
- Uses leftmost derivation
- Also known as recursive descent or predictive parsing
- Easier to implement for simple grammars
### Types of Top-Down Parsing
**With Backtracking**
- Tries multiple production rules
- Backtracks if one rule fails
- Flexible but slower
**Without Backtracking**
- Does not retry other rules once a choice is made.
- Faster and more efficient.
- Works only for suitable grammars (e.g., LL grammars).
## 2. Bottom-Up Parsing
[Bottom-up Parsing](https://www.geeksforgeeks.org/compiler-design/bottom-up-or-shift-reduce-parsers-set-2/) builds the parse tree from input symbols toward the start symbol.
- Starts from the input string
- Reduces substrings into non-terminals
- Uses rightmost derivation in reverse
- Also known as Shift-Reduce Parsing
- Efficient for complex grammars and compiler design
### Types of Bottom-Up Parsing
- [LR Parsing](https://www.geeksforgeeks.org/compiler-design/lr-parser/)
- [SLR(1) Parsing](https://www.geeksforgeeks.org/compiler-design/slr-parser-with-examples/)
- [LALR Parsing](https://www.geeksforgeeks.org/compiler-design/lalr-parser-with-examples/)
- [CLR Parsing](https://www.geeksforgeeks.org/compiler-design/clr-parser-with-examples/)
- [Operator Precedence Parsing](https://www.geeksforgeeks.org/compiler-design/operator-grammar-and-precedence-parser-in-toc/)
## Bottom-Up vs Top-Down Parser
| Feature | Top-Down Parsing | Bottom-Up Parsing |
| --- | --- | --- |
| Direction | Builds the parse tree from root to leaves | Builds the parse tree from leaves to root |
| Derivation | Uses leftmost derivation | Uses rightmost derivation in reverse |
| Working Approach | Starts from the start symbol | Starts from the input string |
| Efficiency | Simpler but can be slower with backtracking | More efficient for complex grammars |
| Complexity | Easier to implement | More complex to implement |
| Example Parsers | Recursive Descent Parser, LL Parser | Shift-Reduce Parser, LR Parser |
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/introduction-of-parsing-ambiguity-and-parsers-set-1/)

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
