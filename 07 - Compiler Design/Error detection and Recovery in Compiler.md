---
title: "Error Detection and Recovery in Compiler"
subject: "Compiler Design"
topic: "Lexical Analysis, Parsing, Syntax-directed"
source: "https://www.geeksforgeeks.org/compiler-design/error-detection-recovery-compiler/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Lexical Analysis, Parsing, Syntax-directed"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/lexical-analysis-parsing-syntax-directed
---


> [!abstract] Error Detection and Recovery in Compiler
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Lexical Analysis, Parsing, Syntax-directed`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/error-detection-recovery-compiler/)

---

# Error Detection and Recovery in Compiler

Error detection and recovery are essential functions of a compiler to ensure that a program is correctly processed. **Error detection** refers to identifying mistakes in the source code, such as syntax, semantic, or logical errors. When an error is found, the compiler generates an error message to help the programmer fix it.
**Error recovery** allows the compiler to handle errors gracefully without abruptly stopping the compilation process. It ensures that minor errors do not prevent the compiler from analyzing the rest of the program. Common recovery techniques include skipping incorrect parts, suggesting corrections, and continuing compilation.
Effective error handling improves the debugging process, enhances code reliability, and helps developers write error-free programs efficiently.
## Classification of Errors
![Error-Handling-3](assets/Error-Handling-3-660-844c1737c3.webp)
### Compile-time errors
Compile-time errors are of three types:- 
![Error-Handling-2](assets/Error-Handling-2-660-0d2b530984.webp)
**1. Lexical phase errors**
These errors are detected during the lexical analysis phase. Typical [lexical errors](https://www.geeksforgeeks.org/compiler-design/lexical-error/) are:
- Exceeding length of identifier or numeric constants.
- The appearance of illegal characters
- Unmatched string
> Example 1 : **printf("Geeksforgeeks");$**
> This is a lexical error since an illegal character $ appears at the end of statement.
>
> Example 2 : **This is a comment \*/**
> This is an lexical error since end of comment is present but beginning is not present
**Error recovery for lexical phase errors**
Panic Mode Recovery 
- In this method, successive characters from the input are removed one at a time until a designated set of synchronizing tokens is found. Synchronizing tokens are delimiters such as; or }
- The advantage is that it is easy to implement and guarantees not to go into an infinite loop.
- The disadvantage is that a considerable amount of input is skipped without checking it for additional errors.
**2. Syntactic phase errors**
These errors are detected during the syntax analysis phase. Typical syntax errors are:
- Errors in structure
- Missing operator
- Misspelled keywords
- Unbalanced parenthesis
> **Example :** swich(ch)
>  {
>  .......
>  .......
>  }
The keyword **switch** is incorrectly written as a swich. Hence, an **"Unidentified keyword/identifier"** error occurs. 
**Error recovery for syntactic phase error:**
**Panic Mode Recovery** 
- In this method, successive characters from the input are removed one at a time until a designated set of synchronizing tokens is found. Synchronizing tokens are deli-meters such as; or }
- The advantage is that it's easy to implement and guarantees not to go into an infinite loop.
- The disadvantage is that a considerable amount of input is skipped without checking it for additional errors.
**Statement Mode recovery** 
- In this method, when a [parser](https://www.geeksforgeeks.org/compiler-design/introduction-of-parsing-ambiguity-and-parsers-set-1/) encounters an error, it performs the necessary correction on the remaining input so that the rest of the input statement allows the parser to parse ahead.
- The correction can be deletion of extra semicolons, replacing the comma with semicolons, or inserting a missing semicolon.
- While performing correction, utmost care should be taken for not going in an infinite loop.
- A disadvantage is that it finds it difficult to handle situations where the actual error occurred before pointing of detection.
**Error production** 
- If a user has knowledge of common errors that can be encountered then, these errors can be incorporated by augmenting the grammar with error productions that generate erroneous constructs.
- If this is used then, during parsing appropriate error messages can be generated and parsing can be continued.
- The disadvantage is that it's difficult to maintain.
**Global Correction** 
- The parser examines the whole program and tries to find out the closest match for it which is error-free.
- The closest match program has less number of insertions, deletions, and changes of tokens to recover from erroneous input.
- Due to high time and space complexity, this method is not implemented practically.
**3. Semantic errors**
These errors are detected during the semantic analysis phase. Typical semantic errors are :
- Incompatible type of operands
- Undeclared variables
- Not matching of actual arguments with a formal one
> **Example :** int a[10], b;
>  .......
>  .......
>  a = b;
It generates a semantic error because of an incompatible type of a and b. 
**Error recovery for Semantic errors**
- If the error **"Undeclared Identifier"** is encountered then, to recover from this a symbol table entry for the corresponding identifier is made.
- If data types of two operands are incompatible then, automatic type conversion is done by the compiler.
## **Advantages of Error Detection and Recovery in Compiler**
1. **Better Code Quality** – Detects and fixes errors early, preventing bigger issues.
2. **Increased Productivity** – Allows compilation to continue after errors, saving time.
3. **Improved Debugging** – Provides clear error messages, helping developers fix bugs quickly.
4. **Consistent Error Handling** – Ensures uniform handling of errors for better reliability.
5. **Lower Maintenance Costs** – Fixing errors early reduces time and effort in later stages.
6. **Better Software Performance** – Helps identify inefficient code that may affect performance.
7. **Enhanced User Experience** – Well-handled errors make applications more stable and user-friendly.
## **Disadvantages of Error Detection and Recovery in Compiler**
1. **Slower Compilation** – Error handling adds extra processing, increasing compile time.
2. **Increased Complexity** – Makes the compiler harder to develop and maintain.
3. **Silent Errors** – Some errors may be masked, leading to unnoticed issues.
4. **Incorrect Recovery** – Poor error handling may introduce new bugs.
5. **Over-Reliance on Recovery** – Developers may neglect proper debugging.
6. **Difficult Error Diagnosis** – Recovery mechanisms can make it harder to pinpoint the root cause.
7. **Compatibility Issues** – Some error recovery methods may not work across all platforms.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/error-detection-recovery-compiler/)

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
> - [[Error Handling in Compiler Design]]
> - [[Fast Lexical Analyzer Generator]]
> - [[FIRST Set in Syntax Analysis]]
> - [[FOLLOW Set in Syntax Analysis]]
> - [[Generation of Programming Languages]]
