---
title: "Designing Non-Deterministic Finite Automata (Set 3)"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/designing-non-deterministic-finite-automata-set-3/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Designing Non-Deterministic Finite Automata (Set 3)
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/designing-non-deterministic-finite-automata-set-3/)

---

# Designing Non-Deterministic Finite Automata (Set 3)

**Prerequisite:** Basic Knowledge of Finite Automata
## Problem 1
**Construction of a minimal NFA accepting a set of strings over {a, b} in which each string of the language starts with 'ab'.**
## **Explanation**
The desired language will be like: 
> L1 = {ab, abba, abaa, abbb ...........}
Here as we can see that each string of the above language starts with 'ab' and end with any alphabet either 'a' or 'b'.  But the below language is not accepted by this NFA because none of the string of below language starts with 'ab'. 
> L2 = {ba, ba, babaaa..............}
The state transition diagram of the desired language will be like below: 
![NFA](assets/NFA-5fc0074720.webp)
starting with ab
In the above NFA, the initial state 'X' on getting 'a' as the input it transits to a state 'Y'. The state 'Y' on getting 'b' as the input it transits to a final state 'Z'. The final state 'Z' on getting either 'a' or 'b' as the input it remains in the state of itself. 
### Python Implementation
````python3
def stateX(n):
    #if length of n become 0
    #then print not accepted
    if(len(n)==0):
        print("string not accepted")
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
            print("string not accepted")
def stateY(n):
    #if length of n become 0
    #then print not accepted
    if(len(n)==0):
        print("string not accepted")
    else:
        #if at zero index
        #'a' then print
        #not accepted
        if (n[0]=='a'):
            print("string not accepted")
        #if at zero index
        #'b' found call
        #stateZ function
        elif (n[0]=='b'):
            stateZ(n[1:])
def stateZ(n):
    #if length of n become 0
    #then print accepted
    if(len(n)==0):
        print("string accepted")
    else:
        #if at zero index
        #'b' found call
        #stateZ function
        if (n[0]=='a'):
            stateZ(n[1:])
        #if at zero index
        #'b' found call
        #stateZ function
        elif (n[0]=='b'):
            stateZ(n[1:])
#take input
#n=input()
n="a"
print(n," ")
#call stateX function
#to check the input
stateX(n)
n="ba"
print(n," ")
#call stateX function
#to check the input
stateX(n)
n="abab"
print(n," ")
#call stateX function
#to check the input
stateX(n)
n="ab"
print(n," ")
#call stateX function
#to check the input
stateX(n)
````
**Output:**
> a
> string not accepted
> ba
> string not accepted
> abab
> string accepted
> ab
> string accepted
## **Problem 2**
**Construction of a minimal NFA accepting a set of strings over {a, b} in which each string of the language is not starting with 'ab'.**
## **Explanation**
The desired language will be like: 
> L1 = { 𝝐, a, b, aa, bb, ba, bba, bbaa, ...........}
Here as we can see that each string of the above language is not starting with 'ab' but can end with either 'a' or 'b'. 
But the below language is not accepted by this NFA because some of the string of below language starts with 'ab'. 
> L2 = {ab, aba, ababaab..............}
The state transition diagram of the desired language will be like below: 
![DFA](assets/DFA-404a20fdfa.webp)
not starting with ab
In the above NFA, the initial state 'X' on getting 'b' as the input it transits to a state 'Y' , and on getting 'a' transit to state 'Z' .The state 'Y' on getting either 'a' or 'b' as the input it transits to a final state 'Y' . The final state 'Z' on getting 'a' moves to the state 'Y' and on 'b' moves to the dead state 'S'.
### Python Implementation
````python3
def stateX(n):
    #if length of n is 0
    #then print accepted
    if(len(n)==0):
        print("string accepted")
    else:
        #if at zero index
        #'a' found then
        #stateS function
        if (n[0]=='a'):
             stateS(n[1:])
        #if at zero index
        #'b' then call
        #stateY function
        elif (n[0]=='b'):
            stateY(n[1:])
def stateY(n):
    #if length of n become 0
    #then print accepted
    if(len(n)==0):
        print("string accepted")
    else:
        #if at zero index
        #'a' found call
        #stateZ function
        if (n[0]=='a'):
            stateZ(n[1:])
        #if at zero index
        #'b' found call
        #stateZ function
        elif (n[0]=='b'):
            stateZ(n[1:])
def stateS(n):
    #if length of n become 0
    #then print accepted
    if(len(n)==0):
        print("string accepted")
    else:
        #if at zero index
        #'a' found call
        #stateZ function
        if (n[0]=='a'):
            stateZ(n[1:])
        #if at zero index
        #'b' found call
        #"string not accepted"
        elif (n[0]=='b'):
          print("string not accepted")
def stateZ(n):
    #if length of n become 0
    #then print accepted
    if(len(n)==0):
        print("string accepted")
    else:
        #if at zero index
        #'b' found call
        #stateZ function
        if (n[0]=='a'):
            stateZ(n[1:])
        #if at zero index
        #'b' found call
        #stateZ function
        elif (n[0]=='b'):
            stateZ(n[1:])
#take input
#n=input()
n=""
print("epsilon ")
#call stateX function
#to check the input
stateX(n)
n="a"
print(n," ")
#call stateX function
#to check the input
stateX(n)
n="aa"
print(n," ")
#call stateX function
#to check the input
stateX(n)
n="ab"
print(n," ")
#call stateX function
#to check the input
stateX(n)
n="ba"
print(n," ")
#call stateX function
#to check the input
stateX(n)
````
**Output:**
> epsilon
> string accepted
> a
> string accepted
> aa
> string accepted
> ab
> string not accepted
> ba
> string accepted
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/designing-non-deterministic-finite-automata-set-3/)

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
> - [[DFA for accepting the language L = {anbm n+m=even}]]
