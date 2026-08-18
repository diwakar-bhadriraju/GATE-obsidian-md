---
title: "Recursive Descent Parser"
subject: "Compiler Design"
topic: "Lexical Analysis, Parsing, Syntax-directed"
source: "https://www.geeksforgeeks.org/compiler-design/recursive-descent-parser/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Lexical Analysis, Parsing, Syntax-directed"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/lexical-analysis-parsing-syntax-directed
---


> [!abstract] Recursive Descent Parser
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Lexical Analysis, Parsing, Syntax-directed`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/recursive-descent-parser/)

---

# Recursive Descent Parser

A **recursive descent parser** is a top-down parser that processes input based on a set of recursive functions, where each function corresponds to a grammar rule. It parses the input from left to right, constructing a parse tree by matching the grammar's production rules. This parser is simple to implement and is suitable for LL(1) grammars, where decisions can be made based on a single lookahead token. While straightforward, recursive descent parsers struggle with left-recursive grammars and may require grammar transformations to handle such cases effectively.
A [**Predictive Parser**](https://www.geeksforgeeks.org/compiler-design/predictive-parser-in-compiler-design/) is a special case of Recursive Descent Parser, where no Back Tracking is required. 
By carefully writing a grammar, means eliminating left recursion and left factoring from it, the resulting grammar will be a grammar that can be parsed by a recursive descent parser.
By carefully writing a grammar means eliminating left recursion and left factoring from it, the resulting grammar will be a grammar that can be parsed by a recursive descent parser.
**Example:**
| Before removing left recursion | After removing left recursion |
| --- | --- |
| E –> E + T | T  T –> T \* F | F  F –> ( E ) | id | E –> T E’  E’ –> + T E’ | e  T –> F T’  T’ –> \* F T’ | e  F –> ( E ) | id |
## Algorithm for Recursive Descent Parser
```
S(){     Choose any S production, S ->X1X2…..Xk;      for (i = 1 to k)      {          If ( Xi is a non-terminal)          Call procedure Xi();          else if ( Xi equals the current input, increment input)          Else /* error has occurred, backtrack and try another possibility */      }}
```
Let's understand it better with an example:
The given grammar is:
```
E  → i E'E' → + i E' | ε
```
**Function** **`E()`**
```
E(){        if (input == 'i') {  // If the input is 'i' (identifier)            input++;        // Consume 'i' }            E'();     // Call E' to check for further expressions}
```
- It checks for `i` (identifier).
- If found, it moves the input pointer ahead.
- Calls `E'()` to check if a `+` operation exists.
**Function** **`E'()`**
```
void E`() {    if (input == '+') {        input++;           // Consume the '+'                if (input == 'i') {            input++;       // Consume the 'i'        }                E`();           // Recursively process more additions    } else {        return;            // If no '+', return (ε production)    }}
```
- It checks for `+ i`.
- If found, it consumes them and calls `E'()` recursively.
- If no `+`, it returns (ε production).
**Main Function**
```
Main(){        E();              // Start parsing from E        if (input == '$') // If we reach end of input            Parsing Successful;}
```
- Calls `E()` to start parsing.
- Checks if the input ends with `$`, which indicates a successful parse.
**Example Input Parsing**
Let’s consider the example input:
```
i + i $
```
Processing step by step:
1. `E()` starts → `input == i`, so consume `i`
2. Call `E'()` → `input == +`, so consume `+`
3. `input == i`, so consume `i`
4. Call `E'()` again → no `+`, so return.
5. Back to `Main()`, input == `$` → Parsing Successful
## Important points about **recursive descent parsers**
1. [**Top-Down Parsing**](https://www.geeksforgeeks.org/compiler-design/classification-of-top-down-parsers/): It starts from the start symbol and recursively applies grammar rules to break down the input.
2. **One Function per Non-Terminal**: Each grammar rule has a corresponding function in the parser, making the implementation straightforward.
3. **Uses Recursion**: The parser calls functions within themselves to process different parts of the input, matching the recursive nature of grammar rules.
4. **Works Best with** [**LL(1)**](https://www.geeksforgeeks.org/compiler-design/ll1-parsing-algorithm/) **Grammars**: It’s most effective for grammars that can be parsed with a single token lookahead, typically simple, non-left-recursive grammars.
5. **Easy to Implement**: The structure is easy to follow and implement, making it a good choice for small compilers or interpreters.
6. **Error Handling**: It can detect syntax errors and report them, making it useful for debugging input strings.
## Code I**mplementation** of a R**ecursive Descent Parser**
````cpp
#include <stdio.h>
#include <string.h>
#define SUCCESS 1
#define FAILED 0
// Function prototypes
int E(), Edash(), T(), Tdash(), F();
const char *cursor;
char string[64];
int main()
{
    puts("Enter the string");
    scanf("%s", string); // Read input from the user
    cursor = string;
    puts("");
    puts("Input          Action");
    puts("--------------------------------");
    // Call the starting non-terminal E
    if (E() && *cursor == '\0')
    { // If parsing is successful and the cursor has reached the end
        puts("--------------------------------");
        puts("String is successfully parsed");
        return 0;
    }
    else
    {
        puts("--------------------------------");
        puts("Error in parsing String");
        return 1;
    }
}
// Grammar rule: E -> T E'
int E()
{
    printf("%-16s E -> T E'\n", cursor);
    if (T())
    { // Call non-terminal T
        if (Edash())
        { // Call non-terminal E'
            return SUCCESS;
        }
        else
        {
            return FAILED;
        }
    }
    else
    {
        return FAILED;
    }
}
// Grammar rule: E' -> + T E' | $
int Edash()
{
    if (*cursor == '+')
    {
        printf("%-16s E' -> + T E'\n", cursor);
        cursor++;
        if (T())
        { // Call non-terminal T
            if (Edash())
            { // Call non-terminal E'
                return SUCCESS;
            }
            else
            {
                return FAILED;
            }
        }
        else
        {
            return FAILED;
        }
    }
    else
    {
        printf("%-16s E' -> $\n", cursor);
        return SUCCESS;
    }
}
// Grammar rule: T -> F T'
int T()
{
    printf("%-16s T -> F T'\n", cursor);
    if (F())
    { // Call non-terminal F
        if (Tdash())
        { // Call non-terminal T'
            return SUCCESS;
        }
        else
        {
            return FAILED;
        }
    }
    else
    {
        return FAILED;
    }
}
// Grammar rule: T' -> * F T' | $
int Tdash()
{
    if (*cursor == '*')
    {
        printf("%-16s T' -> * F T'\n", cursor);
        cursor++;
        if (F())
        { // Call non-terminal F
            if (Tdash())
            { // Call non-terminal T'
                return SUCCESS;
            }
            else
            {
                return FAILED;
            }
        }
        else
        {
            return FAILED;
        }
    }
    else
    {
        printf("%-16s T' -> $\n", cursor);
        return SUCCESS;
    }
}
// Grammar rule: F -> ( E ) | i
int F()
{
    if (*cursor == '(')
    {
        printf("%-16s F -> ( E )\n", cursor);
        cursor++;
        if (E())
        { // Call non-terminal E
            if (*cursor == ')')
            {
                cursor++;
                return SUCCESS;
            }
            else
            {
                return FAILED;
            }
        }
        else
        {
            return FAILED;
        }
    }
    else if (*cursor == 'i')
    {
        printf("%-16s F -> i\n", cursor);
        cursor++;
        return SUCCESS;
    }
    else
    {
        return FAILED;
    }
}
````
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/recursive-descent-parser/)

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
