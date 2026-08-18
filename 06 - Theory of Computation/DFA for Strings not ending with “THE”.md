---
title: "DFA for Strings not ending with \"THE\""
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/dsa/dfa-for-strings-not-ending-with-the/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] DFA for Strings not ending with "THE"
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/dfa-for-strings-not-ending-with-the/)

---

# DFA for Strings not ending with "THE"

**Problem -** Accept Strings that not ending with substring "THE". Check if a given string is ending with "the" or not. The different forms of "the" which are avoided in the end of the string are:
```
"THE", "ThE", "THe", "tHE", "thE", "The", "tHe" and "the"
```
All those strings that are ending with any of the above mentioned forms of "the" are not accepted.
**Deterministic finite automata (DFA) of strings that not ending with "THE" -** 
The initial and starting state in this dfa is Qo
![](assets/22-2-0f3c9da6aa.jpg)
**Approach used in the program -** 
In this program, consider the 4 states to be 0, 1, 2 and 3. Now let us take a variable named DFA which will be initially 0. Whenever any transition takes place, it will update the value of DFA with the number associated with new state.
**Example :** If a transition occurs from state 0 to state 1 then the value of DFA will be updated to 1. If a transition occurs from state 2 to state 3 then the value of dfa will be updated to 3. In this way, apply this algorithm on entire string and if in the end, then reach state 0, 1 or 2 then our string will be accepted otherwise not.
```
Input : XYzabCthe
Output : NOT ACCEPTED
Input :  Themaliktth
Output :  ACCEPTED
```
````cpp
// C++ program to implement DFS that accepts
// all string that do not end with "THE"
#include <iostream>
using namespace std;
// dfa tells the number associated
// with the present state
int dfa = 0;
// This function is for
// the starting state (zeroth) of DFA
void start(char c)
{
    // On receiving 'T' or 't' goto
    // first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;
}
// This function is for the first state of DFA
void state1(char c)
{
    // On receiving 'T' or 't' goto
    // first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;
    // On receiving 'H' or 'h'
    // goto second state (2)
    else if (c == 'h' || c == 'H')
        dfa = 2;
    // Else goto starting state (0)
    else
        dfa = 0;
}
// This function is for the second state of DFA
void state2(char c)
{
    // On receiving 'E' or 'e' goto third state (3)
    // else goto starting state (0)
    if (c == 'e' || c == 'E')
        dfa = 3;
    else if (c == 't' || c == 'T')
        dfa = 1;
      else
        dfa = 0;
}
// This function is for the third state of DFA
void state3(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    // else goto starting state (0)
    if (c == 't' || c == 'T')
        dfa = 1;
    else
        dfa = 0;
}
bool isAccepted(string str)
{
    // Store length of string
    int len = str.length();
    for(int i = 0; i < len; i++)
    {
        if (dfa == 0)
            start(str[i]);
        else if (dfa == 1)
            state1(str[i]);
        else if (dfa == 2)
            state2(str[i]);
        else
            state3(str[i]);
    }
    return (dfa != 3);
}
// Driver code
int main()
{
    string str = "forTHEgeeks";
    if (isAccepted(str) == true)
        cout << "ACCEPTED\n";
    else
        cout << "NOT ACCEPTED\n";
    return 0;
}
// This code is contributed by ShubhamSingh10
````
````c
// C program to implement DFS that accepts
// all string that do not end with "THE"
#include <stdio.h>
#include <string.h>
// dfa tells the number associated
// with the present state
int dfa = 0;
// This function is for
// the starting state (zeroth) of DFA
void start(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;
}
// This function is for the first state of DFA
void state1(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;
    // On receiving 'H' or 'h' goto second state (2)
    else if (c == 'h' || c == 'H')
        dfa = 2;
    // else goto starting state (0)
    else
        dfa = 0;
}
// This function is for the second state of DFA
void state2(char c)
{
    // On receiving 'E' or 'e' goto third state (3)
    // else goto starting state (0)
    if (c == 'e' || c == 'E')
        dfa = 3;
    else if (c == 't' || c == 'T')
        dfa = 1;
      else
        dfa = 0;
}
// This function is for the third state of DFA
void state3(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    // else goto starting state (0)
    if (c == 't' || c == 'T')
        dfa = 1;
    else
        dfa = 0;
}
bool isAccepted(char str[])
{
    // store length of string
    int len = strlen(str);
    for (int i=0; i < len; i++) {
            if (dfa == 0)
                start(str[i]);
            else if (dfa == 1)
                state1(str[i]);
            else if (dfa == 2)
                state2(str[i]);
            else
                state3(str[i]);
    }
    return (dfa != 3);
}
// driver code
int main()
{
    char str[] = "forTHEgeeks";
    if (isAccepted(str) == true)
        printf("ACCEPTED\n");
    else
        printf("NOT ACCEPTED\n");
    return 0;
}
````
````JAVA
// Java program to implement DFS that accepts
// all string that do not end with "THE"
import java.util.*;
class GFG
{
// dfa tells the number associated
// with the present state
static int dfa = 0;
// This function is for
// the starting state (zeroth) of DFA
static void start(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;
}
// This function is for the first state of DFA
static void state1(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;
    // On receiving 'H' or 'h' goto second state (2)
    else if (c == 'h' || c == 'H')
        dfa = 2;
    // else goto starting state (0)
    else
        dfa = 0;
}
// This function is for the second state of DFA
static void state2(char c)
{
    // On receiving 'E' or 'e' goto third state (3)
    // else goto starting state (0)
    if (c == 'e' || c == 'E')
        dfa = 3;
    else
        dfa = 0;
}
// This function is for the third state of DFA
static void state3(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    // else goto starting state (0)
    if (c == 't' || c == 'T')
        dfa = 1;
    else
        dfa = 0;
}
static boolean isAccepted(char str[])
{
    // store length of string
    int len = str.length;
    for (int i=0; i < len; i++)
    {
            if (dfa == 0)
                start(str[i]);
            else if (dfa == 1)
                state1(str[i]);
            else if (dfa == 2)
                state2(str[i]);
            else
                state3(str[i]);
    }
    return (dfa != 3);
}
// Driver code
public static void main(String[] args)
{
    char str[] = "forTHEgeeks".toCharArray();
    if (isAccepted(str) == true)
        System.out.println("ACCEPTED\n");
    else
        System.out.println("NOT ACCEPTED\n");
}
}
/* This code is contributed by PrinciRaj1992 */
````
````PYTHON3
# Python3 program to implement DFS that accepts
# all string that do not end with "THE"
# This function is for the starting
# state (zeroth) of DFA
def start(c):
    # On receiving 'T' or 't' goto
    # first state (1)
    if (c == 't' or c == 'T'):
        dfa=1
# This function is for the first state of DFA
def state1(c):
    # On receiving 'T' or 't' goto first state (1)
    if (c == 't' or c == 'T'):
        dfa = 1
    # On receiving 'H' or 'h' goto second state (2)
    elif (c == 'h' or c == 'H'):
        dfa = 2
    # else goto starting state (0)
    else:
        dfa = 0
# This function is for the second state of DFA
def state2(c):
    # On receiving 'E' or 'e' goto third
    # state (3) else goto starting state (0)
    if (c == 'e' or c == 'E'):
        dfa = 3
    else:
        dfa = 0
# This function is for the third state of DFA
def state3(c):
    # On receiving 'T' or 't' goto first
    # state (1) else goto starting state (0)
    if (c == 't' or c == 'T'):
        dfa = 1
    else:
        dfa = 0
def isAccepted(string):
    # store length of string
    length = len(string)
    for i in range(length):
        if (dfa == 0):
            start(string[i])
        elif (dfa == 1):
            state1(string[i])
        elif (dfa == 2):
            state2(string[i])
        else:
            state3(string[i])
    return (dfa != 3)
# Driver Code
if __name__ == "__main__" :
    string="forTHEgeeks"
    # dfa tells the number associated
    # with the present state
    dfa = 0
    if isAccepted(string):
        print("ACCEPTED")
    else:
        print("NOT ACCEPTED")
# This code is contributed by SHUBHAMSINGH10
````
````csharp
// C# program to implement DFS that accepts
// all string that do not end with "THE"
using System;
class GFG
{
// dfa tells the number associated
// with the present state
static int dfa = 0;
// This function is for
// the starting state (zeroth) of DFA
static void start(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;
}
// This function is for the first state of DFA
static void state1(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    if (c == 't' || c == 'T')
        dfa = 1;
    // On receiving 'H' or 'h' goto second state (2)
    else if (c == 'h' || c == 'H')
        dfa = 2;
    // else goto starting state (0)
    else
        dfa = 0;
}
// This function is for the second state of DFA
static void state2(char c)
{
    // On receiving 'E' or 'e' goto third state (3)
    // else goto starting state (0)
    if (c == 'e' || c == 'E')
        dfa = 3;
    else
        dfa = 0;
}
// This function is for the third state of DFA
static void state3(char c)
{
    // On receiving 'T' or 't' goto first state (1)
    // else goto starting state (0)
    if (c == 't' || c == 'T')
        dfa = 1;
    else
        dfa = 0;
}
static bool isAccepted(char []str)
{
    // store length of string
    int len = str.Length;
    for (int i=0; i < len; i++)
    {
            if (dfa == 0)
                start(str[i]);
            else if (dfa == 1)
                state1(str[i]);
            else if (dfa == 2)
                state2(str[i]);
            else
                state3(str[i]);
    }
    return (dfa != 3);
}
// Driver code
static public void Main ()
{
    char []str = "forTHEgeeks".ToCharArray();
    if (isAccepted(str) == true)
        Console.WriteLine("ACCEPTED\n");
    else
        Console.WriteLine("NOT ACCEPTED\n");
}
}
/* This code is contributed by ajit. */
````
````php
<?php
// PHP program to implement DFS
// that accepts all string that
// do not end with "THE"
// dfa tells the number associated
// with the present state
$dfa = 0;
// This function is for the
// starting state (zeroth) of DFA
function start($c)
{
    global $dfa;
    // On receiving 'T' or 't'
    // goto first state (1)
    if ($c == 't' || $c == 'T')
        $dfa = 1;
}
// This function is for
// the first state of DFA
function state1($c)
{
    global $dfa;
    // On receiving 'T' or 't'
    // goto first state (1)
    if ($c == 't' || $c == 'T')
        $dfa = 1;
    // On receiving 'H' or 'h'
    // goto second state (2)
    else if ($c == 'h' || $c == 'H')
        $dfa = 2;
    // else goto starting state (0)
    else
        $dfa = 0;
}
// This function is for
// the second state of DFA
function state2($c)
{
    global $dfa;
    // On receiving 'E' or 'e'
    // goto third state (3) else
    // goto starting state (0)
    if ($c == 'e' || $c == 'E')
        $dfa = 3;
    else
        $dfa = 0;
}
// This function is for
// the third state of DFA
function state3($c)
{
    global $dfa;
    // On receiving 'T' or 't'
    // goto first state (1) else
    // goto starting state (0)
    if ($c == 't' || $c == 'T')
        $dfa = 1;
    else
        $dfa = 0;
}
function isAccepted($str)
{
    global $dfa;
    // store length of string
    $len = strlen($str);
    for ($i=0; $i < $len; $i++)
    {
            if ($dfa == 0)
                start($str[$i]);
            else if ($dfa == 1)
                state1($str[$i]);
            else if ($dfa == 2)
                state2($str[$i]);
            else
                state3($str[$i]);
    }
    return ($dfa != 3);
}
// Driver Code
$str = "forTHEgeeks";
if (isAccepted($str) == true)
    echo "ACCEPTED\n";
else
    echo "NOT ACCEPTED\n";
// This code is contributed by m_kit
?>
````
````javascript
<script>
    // Javascript program to
    // implement DFS that accepts
    // all string that do not end
    // with "THE"
    // dfa tells the number associated
    // with the present state
    let dfa = 0;
    // This function is for
    // the starting state (zeroth) of DFA
    function start(c)
    {
        // On receiving 'T' or 't' goto
        // first state (1)
        if (c == 't' || c == 'T')
            dfa = 1;
    }
    // This function is for the first state of DFA
    function state1(c)
    {
        // On receiving 'T' or 't' goto first state (1)
        if (c == 't' || c == 'T')
            dfa = 1;
        // On receiving 'H' or 'h' goto second state (2)
        else if (c == 'h' || c == 'H')
            dfa = 2;
        // else goto starting state (0)
        else
            dfa = 0;
    }
    // This function is for the second state of DFA
    function state2(c)
    {
        // On receiving 'E' or 'e' goto third state (3)
        // else goto starting state (0)
        if (c == 'e' || c == 'E')
            dfa = 3;
        else
            dfa = 0;
    }
    // This function is for the third state of DFA
    function state3(c)
    {
        // On receiving 'T' or 't' goto first state (1)
        // else goto starting state (0)
        if (c == 't' || c == 'T')
            dfa = 1;
        else
            dfa = 0;
    }
    function isAccepted(str)
    {
        // store length of string
        let len = str.length;
        for (let i=0; i < len; i++)
        {
                if (dfa == 0)
                    start(str[i]);
                else if (dfa == 1)
                    state1(str[i]);
                else if (dfa == 2)
                    state2(str[i]);
                else
                    state3(str[i]);
        }
        return (dfa != 3);
    }
    let str = "forTHEgeeks".split('');
    if (isAccepted(str) == true)
        document.write("ACCEPTED");
    else
        document.write("NOT ACCEPTED");
</script>
````
**Output :** 
```
ACCEPTED
```
**Time Complexity:** O(n)
**Auxiliary Space:** O(1) since it is using constant space
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/dfa-for-strings-not-ending-with-the/)

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
