---
title: "Symbol Table in Compiler"
subject: "Compiler Design"
topic: "Lexical Analysis, Parsing, Syntax-directed"
source: "https://www.geeksforgeeks.org/compiler-design/symbol-table-compiler/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Lexical Analysis, Parsing, Syntax-directed"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/lexical-analysis-parsing-syntax-directed
---


> [!abstract] Symbol Table in Compiler
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Lexical Analysis, Parsing, Syntax-directed`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/symbol-table-compiler/)

---

# Symbol Table in Compiler

A symbol table is a data structure used by a compiler to store information about identifiers such as variables, functions, constants, and parameters in a program.
- Stores information such as the name, type, scope, and memory location of each identifier.
- The symbol table is built during the early phases of compilation and is used throughout all compiler phases for error detection, scope resolution, optimization, and code generation.
## Role of Symbol Table in Compiler Phases
It is used by various [phases of the compiler](https://www.geeksforgeeks.org/compiler-design/phases-of-a-compiler/) as follows:-
### Lexical Analysis
- Inserts identifiers into the symbol table.
- Records token attributes like identifier names.
### Syntax Analysis
- Updates attribute information such as scope and structure.
- Maintains hierarchical scope information.
### Semantic Analysis
- Performs type checking.
- Verifies declarations before use.
- Validates function parameters and return types.
### Intermediate Code Generation
- Uses type and size information.
- Adds temporary variables into the symbol table.
### Code Optimization
- Uses scope and type information.
- Assists in memory and register optimization.
### Target Code Generation
- Uses memory location and offset information.
- Generates correct machine instructions.
### **Example of Using Symbol Table**
Let us consider the following program
````c
#include <stdio.h>
const float pi = 3.14159f;
float calculateArea(float radius) {
    return pi * radius * radius;
}
int main() {
    float distance = 5;
    float area = calculateArea(distance);
    printf("Area of circle with radius %.2f = %.5f\n", distance, area);
    return 0;
}
````
Key identifiers involved:
- **distance** (variable in `main`)
- **pi** (constant)
- **radius** (parameter in `calculateArea`)
- **calculateArea** (function)
A symbol table of this program would look like the following.
| Name | Type | Scope | Category | Additional Info |
| --- | --- | --- | --- | --- |
| pi | float | Global | Constant | Read-only |
| calculateArea | float | Global | Function | Returns float |
| radius | float | Local (Function) | Parameter | Scope: calculateArea |
| distance | float | Local (main) | Variable | Stack allocated |
| area | float | Local (main) | Variable | Stack allocated |
## **Implementation**
Symbol tables can be implemented using various data structures, each with its trade-offs:
- **Hash Tables**: Offer fast lookup times, making them suitable for large programs.
- **Binary Search Trees**: Maintain sorted order, which can be beneficial for certain compiler operations.
- **Linear Lists**: Simpler to implement but less efficient for large numbers of identifiers.
## Applications
- **Name Resolution:** Identifies variables and functions with their types and memory locations.
- **Scope Management:** Resolves naming conflicts and manages local/global scopes.
- **Code Optimization:** Provides information useful for improving execution efficiency.
- **Code Generation:** Supplies data types and storage details for machine code generation.
- **Error Detection:** Helps detect undeclared variables, type mismatches, and duplicate declarations.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/symbol-table-compiler/)

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
