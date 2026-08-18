---
title: "Designing Deterministic Finite Automata (Set 3)"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/designing-deterministic-finite-automata-set-3/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Designing Deterministic Finite Automata (Set 3)
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/designing-deterministic-finite-automata-set-3/)

---

# Designing Deterministic Finite Automata (Set 3)

Prerequisite: [Designing finite automata](https://www.geeksforgeeks.org/theory-of-computation/designing-finite-automata-from-regular-expression-set-1/), [Designing Deterministic Finite Automata (Set 2)](https://www.geeksforgeeks.org/theory-of-computation/designing-deterministic-finite-automata-set-2/) 
In this article, we will see some designing of Deterministic Finite Automata (DFA). 
**Problem-1:** Construction of a minimal DFA accepting set of string over {a, b} where each string containing 'a' as the substring. 
**Explanation:** 
The desired language will be like: 
```
L1 = {a, aa, ab, ba, ..............}
```
Here as we can see that each string of the language containing 'a' as the substring but the below language is not accepted by this DFA because some of the string of the below language does not contain 'a' as the substring. 
```
L2 = {b, bb, bbb, ..............}
```
The state transition diagram of the language containing 'a' as the substring will be like: 
![](assets/1-117-4e3352e064.jpg)
Code Implementation:
````cpp
#include <iostream>
#include <string>
class DFA {
public:
    void processInput(const std::string& input) {
        // Flag to track whether 'a' is present in the input
        bool containsA = false;
        // Iterate through each character in the input string
        for (char c : input) {
            // If 'a' is found, set the flag and exit the loop
            if (c == 'a') {
                containsA = true;
                break;
            }
            // If 'b' is found, continue checking for 'a'
            else if (c == 'b') {
                // Continue checking for 'a'
            }
            // If any other character is encountered, print "Not Accepted" and return
            else {
                std::cout << "Not Accepted" << std::endl;
                return;
            }
        }
        // After the loop, check if 'a' is present and print the result
        if (containsA) {
            std::cout << "Accepted" << std::endl;
        } else {
            std::cout << "Not Accepted" << std::endl;
        }
    }
};
int main() {
    // Create an instance of the DFA class
    DFA dfa;
    // Test the DFA with the input string "aba"
    std::string input4 = "aba";
    dfa.processInput(input4);
    return 0;
}
// This code is contributed by Utkarsh
````
````java
public class DFA {
    public void processInput(String input) {
        // Flag to track whether 'a' is present in the input
        boolean containsA = false;
        // Iterate through each character in the input string
        for (char c : input.toCharArray()) {
            // If 'a' is found, set the flag and exit the loop
            if (c == 'a') {
                containsA = true;
                break;
            }
            // If 'b' is found, continue checking for 'a'
            else if (c == 'b') {
                // Continue checking for 'a'
            }
            // If any other character is encountered, print "Not Accepted" and return
            else {
                System.out.println("Not Accepted");
                return;
            }
        }
        // After the loop, check if 'a' is present and print the result
        if (containsA) {
            System.out.println("Accepted");
        } else {
            System.out.println("Not Accepted");
        }
    }
    public static void main(String[] args) {
        // Create an instance of the DFA class
        DFA dfa = new DFA();
        // Test the DFA with the input string "aba"
        String input = "aba";
        dfa.processInput(input);
    }
}
````
**Output:**
```
Accepted
```
In the above DFA, states 'X' and 'Y' are the initial and final state respectively, it accepts all the strings containing 'a' as the substring. Here as we see that on getting input as 'b' it remains in the state of 'X' itself but on getting 'a' as the input it transit to final state 'Y' and hence such string is accepted by above DFA. 
**Problem-2:** Construction of a minimal DFA accepting set of string over {a, b} where each string containing 'ab' as the substring. 
**Explanation:** The desired language will be like: 
```
L1 = {ab, aab, abb, bab, ..............}
```
Here as we can see that each string of the language containing 'ab' as the substring but the below language is not accepted by this DFA because some of the string of the below language does not contain 'ab' as the substring- 
```
L2 = {aba, bba, bbbaaa, ..............}
```
The state transition diagram of the language containing 'ab' as the substring will be like: 
![](assets/3-56-42ddc72ea5.jpg)
In the above DFA, states 'X' and 'Z' are the initial and final state respectively, it accepts all the strings containing 'ab' as the substring. Here as we see that on getting 'b' as the input it remains in the state of initial state itself, on getting 'a' as the input it transit to state 'Y' and then on getting 'b' it finally transit to the final state 'Z' and hence this DFA is accepting all the language containing 'ab' as the substring.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/designing-deterministic-finite-automata-set-3/)

## GATE CS

- Subject: Theory of Computation
- Topic: Regular Expression, Languages,Grammar, and Finite Automata

> [!note] Related notes
>
> - [[Chomsky Hierarchy]]
> - [[Closure properties of Regular languages]]
> - [[Concatenation process in DFA]]
> - [[Conversion from NFA to DFA]]
> - [[Designing Deterministic Finite Automata Set 1]]
> - [[Designing Deterministic Finite Automata Set 2]]
> - [[Designing Finite Automata from Regular Expression]]
> - [[Designing Non-Deterministic Finite Automata]]
> - [[Designing Non-Deterministic Finite Automata (2)]]
> - [[DFA for accepting the language L = {anbm n+m=even}]]
