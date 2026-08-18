---
title: "DFA for accepting the language L = { a n b m | n+m =even }"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/dfa-for-accepting-the-language-l-an-bm-nmeven/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] DFA for accepting the language L = { a n b m | n+m =even }
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/dfa-for-accepting-the-language-l-an-bm-nmeven/)

---

# DFA for accepting the language L = { a n b m | n+m =even }

## Problem
**Design a deterministic finite automata(DFA) for accepting the language L = {a**n** **b**m** **| n+m = even}**
### **Examples:**
> **Input:** a a b b , n = 2, m = 2
> 2 + 2 = 4 (even)
> **Output:** ACCEPTED
>
> **Input:** a a a b b b b ,n = 3, m = 4
> 3 + 4 = 7 (odd)
> **Output:** NOT ACCEPTED
>
> **Input:** a a a b b b , n = 3, m = 3
> 3 + 3 = 6 (even)
> **Output:** ACCEPTED
### **Approaches**
**There are 2 cases that result in the acceptance of string:** 
1. If both n and m are even then their sum will be even
2. If both n and m are odd then their sum will be even
### **Description**
Below is a step-by-step explanation and design of a [DFA](https://www.geeksforgeeks.org/theory-of-computation/introduction-of-finite-automata/) that accepts the language **L =** {an bm | n+m =even}, assuming the input [strings](https://www.geeksforgeeks.org/dsa/string-data-structure/) are always of the form zero or more **a**’s followed by zero or more **b**’s. We need to track whether the total number of characters read (n + m) is even or odd.
### **States Explanation**
1. Initially you start in A, where no characters have been read and the total is even. When you read an 'a', you move between A TO B , flipping between even and odd totals without having seen any 'b's yet.
2. Whether the total number of letters read so far (both 'a' and 'b') is even or odd, and whether we’ve started reading 'b's or not.
3. The moment you encounter the first 'b', you move into another set of states—such as C and F, or D and E that are responsible for tracking parity after ‘b’s begin.
4. Each additional 'b' flips the parity, causing you to jump between these states ensuring that at any point the machine knows if the sum of 'a's and 'b's read is even or odd.
5. Some states are shown multiple times or arranged differently to make the diagram clearer, but they all serve the same purpose to keep track of even or odd totals and whether you’re still reading 'a's or have started reading 'b's.
6. If a's come after the b's there is a dead state X where it will go .
## **DFA State Transition Diagram**
![dfa1](assets/dfa1-0d1e61fe2b.webp)
DFA
**Let's see the code for the demonstration:** 
````cpp14
// C++ program to implement DFA that accepts
// all strings which follow the language
// L = { a^n b^m ; n+m=even }
#include <bits/stdc++.h>
using namespace std;
// dfa tells the number associated
// with the present state
int dfa = 0;
// This function is for
// the starting state (zeroth) of DFA
void start(char c)
{
    if (c == 'a')
        dfa = 1;
    else if (c == 'b')
        dfa = 2;
    // -1 is used to check for any invalid symbol
    else
        dfa = -1;
}
// This function is for the first state of DFA
void state1(char c)
{
    if (c == 'a')
        dfa = 0;
    else if (c == 'b')
        dfa = 5;
    else
        dfa = -1;
}
// This function is for the second state of DFA
void state2(char c)
{
    if (c == 'b')
        dfa = 3;
    else
        dfa = -1;
}
// This function is for the third state of DFA
void state3(char c)
{
    if (c == 'b')
        dfa = 4;
    else
        dfa = -1;
}
// This function is for the fourth state of DFA
void state4(char c)
{
    if (c == 'b')
        dfa = 3;
    else
        dfa = -1;
}
// This function is for the fifth state of DFA
void state5(char c)
{
    if (c == 'b')
        dfa = 6;
    else
        dfa = -1;
}
// This function is for the sixth state of DFA
void state6(char c)
{
    if (c == 'b')
        dfa = 5;
    else
        dfa = -1;
}
int isAccepted(char str[])
{
    // Store length of string
    int i, len = strlen(str);
    for (i = 0; i < len; i++)
    {
        if (dfa == 0)
            start(str[i]);
        else if (dfa == 1)
            state1(str[i]);
        else if (dfa == 2)
            state2(str[i]);
        else if (dfa == 3)
            state3(str[i]);
        else if (dfa == 4)
            state4(str[i]);
        else if (dfa == 5)
            state5(str[i]);
        else if (dfa == 6)
            state6(str[i]);
        else
            return 0;
    }
    if (dfa == 3 || dfa == 5)
        return 1;
    else
        return 0;
}
// Driver code
int main()
{
    char str[] = "aaabbb";
    if (isAccepted(str))
        cout << "\nACCEPTED\n";
    else
        cout << "NOT ACCEPTED\n";
    return 0;
}
// This code is contributed by SHUBHAMSINGH10
````
````c
// C program to implement DFA that accepts
// all strings which follow the language
// L = { a^n b^m ; n+m=even }
#include <stdio.h>
#include <string.h>
// dfa tells the number associated
// with the present state
int dfa = 0;
// This function is for
// the starting state (zeroth) of DFA
void start(char c)
{
    if (c == 'a')
        dfa = 1;
    else if (c == 'b')
        dfa = 2;
    // -1 is used to check for any invalid symbol
    else
        dfa = -1;
}
// This function is for the first state of DFA
void state1(char c)
{
    if (c == 'a')
        dfa = 0;
    else if (c == 'b')
        dfa = 5;
    else
        dfa = -1;
}
// This function is for the second state of DFA
void state2(char c)
{
    if (c == 'b')
        dfa = 3;
    else
        dfa = -1;
}
// This function is for the third state of DFA
void state3(char c)
{
    if (c == 'b')
        dfa = 4;
    else
        dfa = -1;
}
// This function is for the fourth state of DFA
void state4(char c)
{
    if (c == 'b')
        dfa = 3;
    else
        dfa = -1;
}
// This function is for the fifth state of DFA
void state5(char c)
{
    if (c == 'b')
        dfa = 6;
    else
        dfa = -1;
}
// This function is for the sixth state of DFA
void state6(char c)
{
    if (c == 'b')
        dfa = 5;
    else
        dfa = -1;
}
int isAccepted(char str[])
{
    // store length of string
    int i, len = strlen(str);
    for (i = 0; i < len; i++)
    {
        if (dfa == 0)
            start(str[i]);
        else if (dfa == 1)
            state1(str[i]);
        else if (dfa == 2)
            state2(str[i]);
        else if (dfa == 3)
            state3(str[i]);
        else if (dfa == 4)
            state4(str[i]);
        else if (dfa == 5)
            state5(str[i]);
        else if (dfa == 6)
            state6(str[i]);
        else
            return 0;
    }
    if (dfa == 3 || dfa == 5)
        return 1;
    else
        return 0;
}
// driver code
int main()
{
    char str[] = "aaabbb";
    if (isAccepted(str))
        printf("\nACCEPTED\n");
    else
        printf("NOT ACCEPTED\n");
    return 0;
}
````
````java
// Java program to implement DFA that accepts
// all strings which follow the language
// L = { a^n b^m ; n+m=even }
class GFG {
    // dfa tells the number associated
    // with the present state.
    static int dfa = 0;
    // This function is for
    // the starting state (Q0)of DFA
    static void start(char c)
    {
        if (c == 'a') {
            dfa = 1;
        }
        else if (c == 'b') {
            dfa = 2;
        }
        // -1 is used to check for any invalid symbol
        else {
            dfa = -1;
        }
    }
    // This function is for
    // the first state (Q1) of DFA
    static void state1(char c)
    {
        if (c == 'a') {
            dfa = 0;
        }
        else if (c == 'b') {
            dfa = 5;
        }
        else {
            dfa = -1;
        }
    }
    // This function is for the
    // second state (Q2) of DFA
    static void state2(char c)
    {
        if (c == 'b') {
            dfa = 3;
        }
        else {
            dfa = -1;
        }
    }
    // This function is for the
    // third state (Q3)of DFA
    static void state3(char c)
    {
        if (c == 'b') {
            dfa = 4;
        }
        else {
            dfa = -1;
        }
    }
    // This function is for the
    // fourth state (Q4) of DFA
    static void state4(char c)
    {
        if (c == 'b') {
            dfa = 3;
        }
        else {
            dfa = -1;
        }
    }
    // This function is for the
    // fifth state (Q5) of DFA
    static void state5(char c)
    {
        if (c == 'b') {
            dfa = 6;
        }
        else {
            dfa = -1;
        }
    }
    // This function is for the
    // sixth state (Q6) of DFA
    static void state6(char c)
    {
        if (c == 'b') {
            dfa = 5;
        }
        else {
            dfa = -1;
        }
    }
    static int isAccepted(char str[])
    {
        // store length of string
        int i, len = str.length;
        for (i = 0; i < len; i++) {
            if (dfa == 0)
                start(str[i]);
            else if (dfa == 1)
                state1(str[i]);
            else if (dfa == 2)
                state2(str[i]);
            else if (dfa == 3)
                state3(str[i]);
            else if (dfa == 4)
                state4(str[i]);
            else if (dfa == 5)
                state5(str[i]);
            else if (dfa == 6)
                state6(str[i]);
            else
                return 0;
        }
        if (dfa == 3 || dfa == 5)
            return 1;
        else
            return 0;
    }
    // Driver code
    public static void main(String[] args)
    {
        char str[] = "aaabbb".toCharArray();
        if (isAccepted(str) == 1)
            System.out.println("ACCEPTED");
        else
            System.out.println("NOT ACCEPTED");
    }
}
````
````python3
# Python3 program to implement DFA that accepts
# all strings which follow the language
# L = a ^ n b ^ m n + m = even
# This function is for the dfa = starting
# dfa = state (zeroth) of DFA
def start(c):
    if (c == 'a'):
        dfa = 1
    elif (c == 'b'):
        dfa = 2
    # -1 is used to check for any
    # invalid symbol
    else:
        dfa = -1
    return dfa
# This function is for the first
# dfa = state of DFA
def state1(c):
    if (c == 'a'):
        dfa = 0
    elif (c == 'b'):
        dfa = 5
    else:
        dfa = -1
    return dfa
# This function is for the second
# dfa = state of DFA
def state2(c):
    if (c == 'b'):
        dfa = 3
    else:
        dfa = -1
    return dfa
# This function is for the third
# dfa = state of DFA
def state3(c):
    if (c == 'b'):
        dfa = 4
    else:
        dfa = -1
    return dfa
# This function is for the fourth
# dfa = state of DFA
def state4(c):
    if (c == 'b'):
        dfa = 3
    else:
        dfa = -1
    return dfa
# This function is for the fifth
# dfa = state of DFA
def state5(c):
    if (c == 'b'):
        dfa = 6
    else:
        dfa = -1
    return dfa
# This function is for the sixth
# dfa = state of DFA
def state6(c):
    if (c == 'b'):
        dfa = 5
    else:
        dfa = -1
    return dfa
def isAccepted(String):
    # store length of String
    l = len(String)
    # dfa tells the number associated
    # with the present dfa = state
    dfa = 0
    for i in range(l):
        if (dfa == 0):
            dfa = start(String[i])
        elif (dfa == 1):
            dfa = state1(String[i])
        elif (dfa == 2):
            dfa = state2(String[i])
        elif (dfa == 3):
            dfa = state3(String[i])
        elif (dfa == 4):
            dfa = state4(String[i])
        elif (dfa == 5):
            dfa = state5(String[i])
        elif (dfa == 6):
            dfa = state6(String[i])
        else:
            return 0
    if (dfa == 3 or dfa == 5):
        return 1
    else:
        return 0
# Driver code
if __name__ == "__main__":
    String = "aaabbb"
    if (isAccepted(String)):
        print("ACCEPTED")
    else:
        print("NOT ACCEPTED")
# This code is contributed by
# Shubham Singh(SHUBHAMSINGH10)
````
````csharp
// C# program to implement DFA that accepts
// all strings which follow the language
// L = { a^n b^m ; n+m=even }
using System;
class GFG {
    // dfa tells the number associated
    // with the present state.
    static int dfa = 0;
    // This function is for
    // the starting state (Q0)of DFA
    static void start(char c)
    {
        if (c == 'a') {
            dfa = 1;
        }
        else if (c == 'b') {
            dfa = 2;
        }
        // -1 is used to check for any invalid symbol
        else {
            dfa = -1;
        }
    }
    // This function is for
    // the first state (Q1) of DFA
    static void state1(char c)
    {
        if (c == 'a') {
            dfa = 0;
        }
        else if (c == 'b') {
            dfa = 5;
        }
        else {
            dfa = -1;
        }
    }
    // This function is for the
    // second state (Q2) of DFA
    static void state2(char c)
    {
        if (c == 'b') {
            dfa = 3;
        }
        else {
            dfa = -1;
        }
    }
    // This function is for the
    // third state (Q3)of DFA
    static void state3(char c)
    {
        if (c == 'b') {
            dfa = 4;
        }
        else {
            dfa = -1;
        }
    }
    // This function is for the
    // fourth state (Q4) of DFA
    static void state4(char c)
    {
        if (c == 'b') {
            dfa = 3;
        }
        else {
            dfa = -1;
        }
    }
    // This function is for the
    // fifth state (Q5) of DFA
    static void state5(char c)
    {
        if (c == 'b') {
            dfa = 6;
        }
        else {
            dfa = -1;
        }
    }
    // This function is for the
    // sixth state (Q6) of DFA
    static void state6(char c)
    {
        if (c == 'b') {
            dfa = 5;
        }
        else {
            dfa = -1;
        }
    }
    static int isAccepted(char[] str)
    {
        // store length of string
        int i, len = str.Length;
        for (i = 0; i < len; i++) {
            if (dfa == 0)
                start(str[i]);
            else if (dfa == 1)
                state1(str[i]);
            else if (dfa == 2)
                state2(str[i]);
            else if (dfa == 3)
                state3(str[i]);
            else if (dfa == 4)
                state4(str[i]);
            else if (dfa == 5)
                state5(str[i]);
            else if (dfa == 6)
                state6(str[i]);
            else
                return 0;
        }
        if (dfa == 3 || dfa == 5)
            return 1;
        else
            return 0;
    }
    // Driver code
    public static void Main(String[] args)
    {
        char[] str = "aaabbb".ToCharArray();
        if (isAccepted(str) == 1)
            Console.WriteLine("ACCEPTED");
        else
            Console.WriteLine("NOT ACCEPTED");
    }
}
/* This code contributed by PrinciRaj1992 */
````
````php
<?php
// PHP program to implement DFA that accepts
// all strings which follow the language
// L = { a^n b^m ; n+m=even }
// This function is for the
// starting state (zeroth) of DFA
function start($c, &$dfa)
{
    if ($c == 'a') $dfa = 1;
    elseif ($c == 'b') $dfa = 2;
    // -1 is used to check for any
    // invalid symbol
    else $dfa = -1;
}
// This function is for the first
// state of DFA
function state1($c, &$dfa)
{
    if ($c == 'a') $dfa = 0;
    elseif ($c == 'b') $dfa = 5;
    else $dfa = -1;
}
// This function is for the second
// state of DFA
function state2($c, &$dfa)
{
    if ($c == 'b') $dfa = 3;
    else $dfa = -1;
}
// This function is for the third
// state of DFA
function state3($c, &$dfa)
{
    if ($c == 'b') $dfa = 4;
    else $dfa = -1;
}
// This function is for the fourth
// state of DFA
function state4($c, &$dfa)
{
    if ($c == 'b') $dfa = 3;
    else $dfa = -1;
}
// This function is for the fifth
// state of DFA
function state5($c, &$dfa)
{
    if ($c == 'b') $dfa = 6;
    else $dfa = -1;
}
// This function is for the sixth
// state of DFA
function state6($c, &$dfa)
{
    if ($c == 'b') $dfa = 5;
    else $dfa = -1;
}
function isAccepted($str, &$dfa)
{
    // store length of string
    $i = 0; $len = sizeof($str);
    for ($i = 0; $i < $len; $i++)
    {
        if ($dfa == 0)
            start($str[$i], $dfa);
        elseif ($dfa == 1)
            state1($str[$i], $dfa);
        elseif ($dfa == 2)
            state2($str[$i], $dfa);
        elseif ($dfa == 3)
            state3($str[$i], $dfa);
        elseif ($dfa == 4)
            state4($str[$i], $dfa);
        elseif ($dfa == 5)
            state5($str[$i], $dfa);
        elseif ($dfa == 6)
            state6($str[$i], $dfa);
        else
            return 0;
    }
    if($dfa == 3 || $dfa == 5)
        return 1;
    else
        return 0;
}
// Driver code
// dfa tells the number associated
// with the present state
$dfa = 0;
$str = array("a", "a", "a", "b", "b", "b");
if (isAccepted($str, $dfa) != 0)
    echo "ACCEPTED";
else
    echo "NOT ACCEPTED";
// This code is contributed by
// Adesh kumar Singh(adeshsingh1)
?>
````
**Output:** 
```
ACCEPTED
```
**Time Complexity:** O(n) where n is the length of the given string
**Auxiliary Space:** O(1)
There is a minimal DFA for the same problem. 
This approach not only helps us understand how to capture parity conditions in a finite automaton but also shows how simple arithmetic properties (like even and odd sums) can be translated into states and transitions in a systematic way.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/dfa-for-accepting-the-language-l-an-bm-nmeven/)

## GATE CS

- Subject: Theory of Computation
- Topic: Regular Expression, Languages,Grammar, and Finite Automata

> [!note] Related notes
>
> - [[Chomsky Hierarchy]]
> - [[Closure properties of Regular languages]]
> - [[Concatenation process in DFA]]
> - [[Conversion from NFA to DFA]]
> - [[Designing Deterministic Finite Automata]]
> - [[Designing Deterministic Finite Automata Set 1]]
> - [[Designing Deterministic Finite Automata Set 2]]
> - [[Designing Finite Automata from Regular Expression]]
> - [[Designing Non-Deterministic Finite Automata]]
> - [[Designing Non-Deterministic Finite Automata (2)]]
