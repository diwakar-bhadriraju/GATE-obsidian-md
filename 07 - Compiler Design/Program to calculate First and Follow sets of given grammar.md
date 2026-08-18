---
title: "Program to Calculate First and Follow Sets of Given Grammar"
subject: "Compiler Design"
topic: "Lexical Analysis, Parsing, Syntax-directed"
source: "https://www.geeksforgeeks.org/compiler-design/program-calculate-first-follow-sets-given-grammar/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Lexical Analysis, Parsing, Syntax-directed"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/lexical-analysis-parsing-syntax-directed
---


> [!abstract] Program to Calculate First and Follow Sets of Given Grammar
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Lexical Analysis, Parsing, Syntax-directed`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/program-calculate-first-follow-sets-given-grammar/)

---

# Program to Calculate First and Follow Sets of Given Grammar

The First and Follow sets are important in syntax analysis, mainly in parsing. All sets help in making predictive parsers and are integral to identifying how a given grammar can be parsed effectively.
- The First Setfor a non-terminal symbol represents all possible terminals that can appear at the beginning of any string derived from that non-terminal.
- The follow **set** contains terminals that can appear immediately after a non-terminal in the derivation of the grammar.
All meaning of First and Follow sets is it allows to define which production rules are implemented in different parsing moment.
## What is the First Set?
The First set of non-terminal in grammar tells us all the possible terminals that can appear at the beginning of any string derived from that non terminal. it gives us a way to know what symbol might come first if we start with a particular non-terminal. For example, if we have a rule like A -> aB | ε, then the First set of A includes the terminal a, as well as ε, which represents the possibility of deriving an empty string. Calculating the First set helps us predict which rules to apply during parsing by knowing which symbols can appear first in a derivation.
## What is a Follow Set?
The Follow set of a non-terminal contains all terminals that can immediately follow it in any derivation of the grammar. This means that if a non-terminal appears in the middle of a sentence, the Follow set tells us what symbol might come right after it. For example, in a rule like S -> AB, the Follow set of A might include anything that can follow B, depending on other rules in the grammar. Follow sets are especially useful for parsers when making decisions about which rule to apply next and ensuring that we’re interpreting the structure of a sentence correctly, especially for [LL(1) parsers](https://www.geeksforgeeks.org/compiler-design/construction-of-ll1-parsing-table/) where we only look one symbol ahead.
**Example:**  
```
Input :E  -> TRR  -> +T R| #T  -> F YY  -> *F Y | #F  -> (E) | iOutput :First(E)= { (, i, }First(R)= { +, #, }First(T)= { (, i, }First(Y)= { *, #, }First(F)= { (, i, }-----------------------------------------------Follow(E) = { $, ),  }Follow(R) = { $, ),  }Follow(T) = { +, $, ),  }Follow(Y) = { +, $, ),  }Follow(F) = { *, +, $, ),  }
```
The functions follow and follow first are both involved in the calculation of the Follow Set of a given Non-Terminal. The follow set of the start symbol will always contain "$". Now the calculation of Follow falls under three broad cases:
- If a Non-Terminal on the R.H.S. of any production is followed immediately by a Terminal then it can immediately be included in the Follow set of that Non-Terminal.
- If a Non-Terminal on the R.H.S. of any production is followed immediately by a Non-Terminal, then the First Set of that new Non-Terminal gets included on the follow set of our original Non-Terminal. In case encountered an epsilon i.e. " # " then, move on to the next symbol in the production. 
  **Note:** "#" is never included in the Follow set of any Non-Terminal.
- If reached the end of a production while calculating follow, then the Follow set of that non-terminal will include the Follow set of the Non-Terminal on the L.H.S. of that production. This can easily be implemented by recursion.
### **Assumptions**
- Epsilon is represented by '#'.
- Productions are of the form A=B, where 'A' is a single Non-Terminal and 'B' can be any combination of Terminals and Non- Terminals.
- L.H.S. of the first production rule is the start symbol.
- Grammar is not left recursive.
- Each production of a non-terminal is entered on a different line.
- Only Upper Case letters are Non-Terminals and everything else is a terminal.
- Do not use '!' or '$' as they are reserved for special purposes.
Below is the implementation:
````c
// C program to calculate the First and
// Follow sets of a given grammar
#include <ctype.h>
#include <stdio.h>
#include <string.h>
// Functions to calculate Follow
void followfirst(char, int, int);
void follow(char c);
// Function to calculate First
void findfirst(char, int, int);
int count, n = 0;
// Stores the final result
// of the First Sets
char calc_first[10][100];
// Stores the final result
// of the Follow Sets
char calc_follow[10][100];
int m = 0;
// Stores the production rules
char production[10][10];
char f[10], first[10];
int k;
char ck;
int e;
int main(int argc, char** argv)
{
    int jm = 0;
    int km = 0;
    int i, choice;
    char c, ch;
    count = 8;
    // The Input grammar
    strcpy(production[0], "X=TnS");
    strcpy(production[1], "X=Rm");
    strcpy(production[2], "T=q");
    strcpy(production[3], "T=#");
    strcpy(production[4], "S=p");
    strcpy(production[5], "S=#");
    strcpy(production[6], "R=om");
    strcpy(production[7], "R=ST");
    int kay;
    char done[count];
    int ptr = -1;
    // Initializing the calc_first array
    for (k = 0; k < count; k++) {
        for (kay = 0; kay < 100; kay++) {
            calc_first[k][kay] = '!';
        }
    }
    int point1 = 0, point2, xxx;
    for (k = 0; k < count; k++) {
        c = production[k][0];
        point2 = 0;
        xxx = 0;
        // Checking if First of c has
        // already been calculated
        for (kay = 0; kay <= ptr; kay++)
            if (c == done[kay])
                xxx = 1;
        if (xxx == 1)
            continue;
        // Function call
        findfirst(c, 0, 0);
        ptr += 1;
        // Adding c to the calculated list
        done[ptr] = c;
        printf("\n First(%c) = { ", c);
        calc_first[point1][point2++] = c;
        // Printing the First Sets of the grammar
        for (i = 0 + jm; i < n; i++) {
            int lark = 0, chk = 0;
            for (lark = 0; lark < point2; lark++) {
                if (first[i] == calc_first[point1][lark]) {
                    chk = 1;
                    break;
                }
            }
            if (chk == 0) {
                printf("%c, ", first[i]);
                calc_first[point1][point2++] = first[i];
            }
        }
        printf("}\n");
        jm = n;
        point1++;
    }
    printf("\n");
    printf("-----------------------------------------------"
           "\n\n");
    char donee[count];
    ptr = -1;
    // Initializing the calc_follow array
    for (k = 0; k < count; k++) {
        for (kay = 0; kay < 100; kay++) {
            calc_follow[k][kay] = '!';
        }
    }
    point1 = 0;
    int land = 0;
    for (e = 0; e < count; e++) {
        ck = production[e][0];
        point2 = 0;
        xxx = 0;
        // Checking if Follow of ck
        // has already been calculated
        for (kay = 0; kay <= ptr; kay++)
            if (ck == donee[kay])
                xxx = 1;
        if (xxx == 1)
            continue;
        land += 1;
        // Function call
        follow(ck);
        ptr += 1;
        // Adding ck to the calculated list
        donee[ptr] = ck;
        printf(" Follow(%c) = { ", ck);
        calc_follow[point1][point2++] = ck;
        // Printing the Follow Sets of the grammar
        for (i = 0 + km; i < m; i++) {
            int lark = 0, chk = 0;
            for (lark = 0; lark < point2; lark++) {
                if (f[i] == calc_follow[point1][lark]) {
                    chk = 1;
                    break;
                }
            }
            if (chk == 0) {
                printf("%c, ", f[i]);
                calc_follow[point1][point2++] = f[i];
            }
        }
        printf(" }\n\n");
        km = m;
        point1++;
    }
}
void follow(char c)
{
    int i, j;
    // Adding "$" to the follow
    // set of the start symbol
    if (production[0][0] == c) {
        f[m++] = '$';
    }
    for (i = 0; i < 10; i++) {
        for (j = 2; j < 10; j++) {
            if (production[i][j] == c) {
                if (production[i][j + 1] != '\0') {
                    // Calculate the first of the next
                    // Non-Terminal in the production
                    followfirst(production[i][j + 1], i,
                                (j + 2));
                }
                if (production[i][j + 1] == '\0'
                    && c != production[i][0]) {
                    // Calculate the follow of the
                    // Non-Terminal in the L.H.S. of the
                    // production
                    follow(production[i][0]);
                }
            }
        }
    }
}
void findfirst(char c, int q1, int q2)
{
    int j;
    // The case where we
    // encounter a Terminal
    if (!(isupper(c))) {
        first[n++] = c;
    }
    for (j = 0; j < count; j++) {
        if (production[j][0] == c) {
            if (production[j][2] == '#') {
                if (production[q1][q2] == '\0')
                    first[n++] = '#';
                else if (production[q1][q2] != '\0'
                         && (q1 != 0 || q2 != 0)) {
                    // Recursion to calculate First of New
                    // Non-Terminal we encounter after
                    // epsilon
                    findfirst(production[q1][q2], q1,
                              (q2 + 1));
                }
                else
                    first[n++] = '#';
            }
            else if (!isupper(production[j][2])) {
                first[n++] = production[j][2];
            }
            else {
                // Recursion to calculate First of
                // New Non-Terminal we encounter
                // at the beginning
                findfirst(production[j][2], j, 3);
            }
        }
    }
}
void followfirst(char c, int c1, int c2)
{
    int k;
    // The case where we encounter
    // a Terminal
    if (!(isupper(c)))
        f[m++] = c;
    else {
        int i = 0, j = 1;
        for (i = 0; i < count; i++) {
            if (calc_first[i][0] == c)
                break;
        }
        // Including the First set of the
        // Non-Terminal in the Follow of
        // the original query
        while (calc_first[i][j] != '!') {
            if (calc_first[i][j] != '#') {
                f[m++] = calc_first[i][j];
            }
            else {
                if (production[c1][c2] == '\0') {
                    // Case where we reach the
                    // end of a production
                    follow(production[c1][0]);
                }
                else {
                    // Recursion to the next symbol
                    // in case we encounter a "#"
                    followfirst(production[c1][c2], c1,
                                c2 + 1);
                }
            }
            j++;
        }
    }
}
````
**Output:**
```
First(X) = { q, n, o, p, #,m}First(T) = { q, #, }First(S) = { p, #, }First(R) = { o, p, q, #, }-----------------------------------------------Follow(X) = { $,  }Follow(T) = { n, m,  }Follow(S) = { $, q, m,  }Follow(R) = { m,  }
```
## Conclusion
Understanding First and Follow sets is crucial for building efficient parsers in [compiler design](https://www.geeksforgeeks.org/compiler-design/introduction-of-compiler-design/). These sets allow us to find which production rules are during parsing to identify the potential starting and following symbols for each non terminal. By calculating First and Follow sets, we ensure accurate [syntax analysis](https://www.geeksforgeeks.org/compiler-design/introduction-to-syntax-analysis-in-compiler-design/), helping to create parsers that are both predictive and [unambiguous](https://www.geeksforgeeks.org/theory-of-computation/difference-between-ambiguous-and-unambiguous-grammar/), which is essential for building reliable compilers.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/program-calculate-first-follow-sets-given-grammar/)

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
