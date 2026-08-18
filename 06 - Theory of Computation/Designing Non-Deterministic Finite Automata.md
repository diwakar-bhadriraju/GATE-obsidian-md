---
title: "Designing Non-Deterministic Finite Automata (Set 1)"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/designing-non-deterministic-finite-automata-set-1/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Designing Non-Deterministic Finite Automata (Set 1)
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/designing-non-deterministic-finite-automata-set-1/)

---

# Designing Non-Deterministic Finite Automata (Set 1)

**Prerequisite:**
[Finite Automata Introduction](https://www.geeksforgeeks.org/theory-of-computation/introduction-of-finite-automata/)
In this article, we will see some designing of Non-Deterministic Finite Automata (NFA).
**Problem-1:**
Construction of a minimal NFA accepting a set of strings over {a, b} in which each string of the language starts with 'a'.
**Explanation:**
The desired language will be like:
```
L1 = {ab, abba, abaa, ...........}
```
Here as we can see that each string of the above language starts with 'a' and end with any alphabet either 'a' or 'b'. But the below language is not accepted by this NFA because none of the string of below language starts with 'a'.
```
L2 = {ba, ba, babaaa..............}
```
The state transition diagram of the desired language will be like below:
![](assets/P12-49c64759b6.jpg)
In the above NFA, the initial state 'X' on getting 'a' as the input it transits to a final state 'Y'. The final state 'Y' on getting either 'a' or 'b' as the input it remains in the state of itself.
### Python Implementation:
````cpp
#include <iostream>
#include <string>
void stateX(const std::string& n);
void stateY(const std::string& n);
void stateX(const std::string& n) {
    // if length of n becomes 0
    // then print not accepted
    if (n.empty()) {
        std::cout << "String not accepted" << std::endl;
    } else {
        // if at zero index
        // 'a' found call
        // stateY function
        if (n[0] == 'a') {
            stateY(n.substr(1));
        }
        // if at zero index
        // 'b' then print
        // not accepted
        else if (n[0] == 'b') {
            std::cout << "String not accepted" << std::endl;
        }
    }
}
void stateY(const std::string& n) {
    // if length of n becomes 0
    // then print accepted
    if (n.empty()) {
        std::cout << "String accepted" << std::endl;
    } else {
        // if at zero index
        // 'a' found call
        // stateY function
        if (n[0] == 'a') {
            stateY(n.substr(1));
        }
        // if at zero index
        // 'b' found call
        // stateY function
        else if (n[0] == 'b') {
            stateY(n.substr(1));
        }
    }
}
int main() {
    // take input
    std::string inputString="ababa";
    // call stateX function
    // to check the input
    stateX(inputString);
    return 0;
}
//This code is contributed by utkarsh
````
````java
public class StateMachine {
    public static void stateX(String n) {
        // if length of n becomes 0
        // then print not accepted
        if (n.isEmpty()) {
            System.out.println("String not accepted");
        } else {
            // if at zero index
            // 'a' found call
            // stateY function
            if (n.charAt(0) == 'a') {
                stateY(n.substring(1));
            }
            // if at zero index
            // 'b' then print
            // not accepted
            else if (n.charAt(0) == 'b') {
                System.out.println("String not accepted");
            }
        }
    }
    public static void stateY(String n) {
        // if length of n becomes 0
        // then print accepted
        if (n.isEmpty()) {
            System.out.println("String accepted");
        } else {
            // if at zero index
            // 'a' found call
            // stateY function
            if (n.charAt(0) == 'a') {
                stateY(n.substring(1));
            }
            // if at zero index
            // 'b' found call
            // stateY function
            else if (n.charAt(0) == 'b') {
                stateY(n.substring(1));
            }
        }
    }
    public static void main(String[] args) {
        // take input
        String inputString = "ababa";
        // call stateX function
        // to check the input
        stateX(inputString);
    }
}
````
````python3
def stateX(n):
    #if length of n become 0
    #then print not accepted
    if(len(n)==0):
        print(&quot;string not accepted&quot;)
    else:
        #if at zero index
        #'a' found call
        #stateY function
        if (n[0]=='a'):
            stateY(n[1:])
        #if at zero index
        #'b' then print
        #not accepted
        elif (n[0]=='b'):
            print(&quot;string not accepted&quot;)
def stateY(n):
    #if length of n become 0
    #then print accepted
    if(len(n)==0):
        print(&quot;string accepted&quot;)
    else:
        #if at zero index
        #'a' found call
        #stateY function
        if (n[0]=='a'):
            stateY(n[1:])
        #if at zero index
        #'b' found call
        #stateY function
        elif (n[0]=='b'):
            stateY(n[1:])
#take input
n=input()
#call stateA function
#to check the input
stateX(n)
````
````csharp
using System;
class StateMachine
{
    static void StateX(string n)
    {
        // if length of n becomes 0
        // then print not accepted
        if (string.IsNullOrEmpty(n))
        {
            Console.WriteLine("String not accepted");
        }
        else
        {
            // if at zero index
            // 'a' found call
            // StateY function
            if (n[0] == 'a')
            {
                StateY(n.Substring(1));
            }
            // if at zero index
            // 'b' then print
            // not accepted
            else if (n[0] == 'b')
            {
                Console.WriteLine("String not accepted");
            }
        }
    }
    static void StateY(string n)
    {
        // if length of n becomes 0
        // then print accepted
        if (string.IsNullOrEmpty(n))
        {
            Console.WriteLine("String accepted");
        }
        else
        {
            // if at zero index
            // 'a' found call
            // StateY function
            if (n[0] == 'a')
            {
                StateY(n.Substring(1));
            }
            // if at zero index
            // 'b' found call
            // StateY function
            else if (n[0] == 'b')
            {
                StateY(n.Substring(1));
            }
        }
    }
    static void Main()
    {
        // take input
        string inputString = "ababa";
        // call StateX function
        // to check the input
        StateX(inputString);
    }
}
````
**output:**
```
String accepted
```
**Problem-2:**
Construction of a minimal NFA accepting a set of strings over {a, b} in which each string of the language is not starting with 'a'.
**Explanation:**
The desired language will be like:
```
L1 = {ba, bba, bbaa, ...........}
```
Here as we can see that each string of the above language is not starting with 'a' but can end with either 'a' or 'b'. But the below language is not accepted by this NFA because some of the string of below language starts with 'a'.
```
L2 = {ab, aba, ababaab..............}
```
The state transition diagram of the desired language will be like below:
![](assets/jpg-db61d4e51a.jpg)
In the above NFA, the initial state 'X' on getting 'b' as the input it transits to a final state 'Y'. The final state 'Y' on getting either 'a' or 'b' as the input it remains in the state of itself.
### Python Implementation:
````python3
def stateX(n):
    #if length of n become 0
    #then print not accepted
    if(len(n)==0):
        print(&quot;string not accepted&quot;)
    else:
        #if at zero index
        #'b' found call
        #stateY function
        if (n[0]=='b'):
            stateY(n[1:])
        #if at zero index
        #'a' then print
        #not accepted
        elif (n[0]=='a'):
            print(&quot;string not accepted&quot;)
def stateY(n):
    #if length of n become 0
    #then print accepted
    if(len(n)==0):
        print(&quot;string accepted&quot;)
    else:
        #if at zero index
        #'a' found call
        #stateY function
        if (n[0]=='a'):
            stateY(n[1:])
        #if at zero index
        #'b' found call
        #stateY function
        elif (n[0]=='b'):
            stateY(n[1:])
#take input
n=input()
#call stateA function
#to check the input
stateX(n)
````
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/designing-non-deterministic-finite-automata-set-1/)

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
> - [[Designing Non-Deterministic Finite Automata (2)]]
> - [[DFA for accepting the language L = {anbm n+m=even}]]
