---
title: "Concatenation Process in DFA"
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/concatenation-process-in-dfa/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Concatenation Process in DFA
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/concatenation-process-in-dfa/)

---

# Concatenation Process in DFA

In the context of Deterministic Finite Automata (DFA), concatenation refers to the process of combining two regular languages (or strings) together to form a new language.
- **DFA** is a model used to recognize patterns or decide if a string belongs to a particular language.
- **Concatenation** is simply taking two strings, one after the other. If you have a string A and a string B, the concatenation of these two strings results in AB (the first string followed by the second string).
## How Concatenation Works in DFA
When you concatenate two [regular languages](https://www.geeksforgeeks.org/theory-of-computation/regular-expressions-regular-grammar-and-regular-languages/) (represented by DFAs), you essentially want to combine the DFAs that recognize each of the individual languages into one [DFA](https://www.geeksforgeeks.org/theory-of-computation/introduction-of-finite-automata/) that can recognize the concatenated language.
**1. Initial Setup**: Start with two separate DFAs, i.e. DFA1 and DFA2, where:
- **DFA1** recognizes the first part of the string.
- **DFA2** recognizes the second part of the string.
**2. Modify the Final States**: In the concatenation process, the final state of DFA1 is connected to the start state of DFA2. This means:
- Once **DFA1** reaches its final state (after reading the first part of the string), the machine then transitions into **DFA2** and starts reading the second part of the string.
**3. Accepting States**: The new DFA should accept the concatenated string if:
- The string is accepted by DFA1 (after processing the first part).
- Then, DFA2 should accept the second part of the string.
**4. Final Automaton**: After these adjustments, the new DFA recognizes the concatenation of both languages and can accept any string that is a valid combination of the two languages.
**Example:** Designing a DFA for the set of string over {a, b} such that string of the language start with "a" and end with "b". There two desired language will be formed: 
> L1 = {a, aab, aabab, ...}
> L2 = {b, bbab, bbabab, ...}
### **1. Designing a DFA for Strings That Start with 'a' and End with 'b'**
- The string starts with a
- The string ends with b
**Examples of valid strings:**
- ab
- aab
- aabab
- aaabbb
**Examples of invalid strings:**
- baba (does not start with a)
- aaba (ends with a)
- b (starts with b)
### **2. Defining Sub-Languages L1 and L2**
**2.1 Language L1: Strings that start with a**
This DFA accepts any string that begins with the letter a. As soon as it sees the first character, if it's not a, it moves to a dead state (where no accepted string is possible anymore). After seeing an initial a, it can accept any combination of as and bs.
**Examples:** a, ab, aab, aaba, aaabb
**Rejected:** b, ba, bb
![](assets/TOC10-783ff3f8fb.png)
**2.2 Language L2: Strings that end with b**
This DFA accepts any string as long as its last character is b. It keeps track of the last symbol. If the last input symbol was b, the string is accepted. If the string ends in a, it's rejected.
**Examples:** b, ab, aab, bab
**Rejected:** a, aa, aba
![](assets/TOC6-2-2dd2817014.png)
### **3. Concatenation L1.L2**
Now, to create the final DFA, we combine the logic of L1 and L2. We want a string that:
- Starts with a (L1)
- Ends with b (L2)
This means the DFA must first verify that the first letter is a, and after that, it must watch for the last letter to be b. Both conditions must be satisfied.
**Examples of accepted strings:**
- ab (starts with a, ends with b)
- aab
- aaabb
- aabab
**Examples of rejected strings:**
- aaba (ends with a)
- b (starts with b)
- baab (starts with b)
- a (ends with a)
![](assets/TOC11-2-39ddc309c0.png)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/concatenation-process-in-dfa/)

## GATE CS

- Subject: Theory of Computation
- Topic: Regular Expression, Languages,Grammar, and Finite Automata

> [!note] Related notes
>
> - [[Chomsky Hierarchy]]
> - [[Closure properties of Regular languages]]
> - [[Conversion from NFA to DFA]]
> - [[Designing Deterministic Finite Automata]]
> - [[Designing Deterministic Finite Automata Set 1]]
> - [[Designing Deterministic Finite Automata Set 2]]
> - [[Designing Finite Automata from Regular Expression]]
> - [[Designing Non-Deterministic Finite Automata]]
> - [[Designing Non-Deterministic Finite Automata (2)]]
> - [[DFA for accepting the language L = {anbm n+m=even}]]
