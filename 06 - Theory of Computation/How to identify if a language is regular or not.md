---
title: "Identify a Regular Language."
subject: "Theory of Computation"
topic: "Regular Expression, Languages,Grammar, and Finite Automata"
source: "https://www.geeksforgeeks.org/theory-of-computation/how-to-identify-if-a-language-is-regular-or-not/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Theory of Computation/Regular Expression, Languages,Grammar, and Finite Automata"
tags:
  - gate/cs
  - subject/theory-of-computation
  - topic/regular-expression-languages-grammar-and-finite-automata
---


> [!abstract] Identify a Regular Language.
> 
> **Subject:** `Theory of Computation` &nbsp;|&nbsp; **Topic:** `Regular Expression, Languages,Grammar, and Finite Automata`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/how-to-identify-if-a-language-is-regular-or-not/)

---

# Identify a Regular Language.

There is a well established theorem to identify if a language is regular or not, based on Pigeon Hole Principle, called as Pumping Lemma. But pumping lemma is a negativity test, i.e. if a language doesn't satisfy pumping lemma, then we can definitely say that it is not regular, but if it satisfies, then the language may or may not be regular. Pumping Lemma is more of a mathematical proof, takes more time and it may be confusing sometimes. In exams, we need to address this problem very quickly, so based on common observations and analysis, here are some quick rules that will help: 
1. Every finite set represents a regular language. 
   **Example 1 -** All strings of length = 2 over {a, b}\* i.e. L = {aa, ab, ba, bb} is regular.
2. Given an expression of non-regular language, but the value of parameter is bounded by some constant, then the language is regular (means it has kind of finite comparison). 
   **Example 2 -** L = {
$$
a^n
$$
$$
b^n
$$
   | n <= 101010} is regular, because it is upper bounded and thus a finite language.
3. The pattern of strings form an A.P.(Arithmetic Progression) is regular(i.e. it's power is in form of linear expression), 
   but the pattern with G.P.(Geometric Progression) is not regular(i.e. its power is in form of non-linear expression) and it comes under class of Context Sensitive Language. 
   **Example 3 -** L = { 
$$
a^n
$$
   | n>=2 } is regular. Clearly, it forms an A.P., so we can draw a finite automaton with 3 states. 
   **Example 4 -** L = { a2^n | n>=1 } is not regular. It forms a G.P., so we cannot have a fixed pattern which repeated would generate all strings of this language. 
   In example 4 if 'n' is bounded like n<10000 then it becomes regular as it is finite.
4. No pattern is present, that could be repeated to generate all the strings in language is not regular. Finding prime itself is not possible with FA. 
   **Example 5 -** L = { 
$$
a^p
$$
   | p is prime. } is not regular.
5. A concatenation of pattern(regular) and a non-pattern(not regular) is also not a regular language. 
   **Example 6 -** L1 = { 
$$
a^{n}b^{n}
$$
   | n≥1 }, L2 = {
$$
a^{n}
$$
   n≥1 } then L1.L2 is not regular.
6. Whenever unbounded storage is required for storing the count and then comparison with other unbounded counts, then the language is not regular. 
   **Example 7 -** L = { 
$$
a^n
$$
$$
b^n
$$
   | n>=1 } is not regular, because we need to first store the count of a and then compare it against count of b, but finite automaton has a limited storage, but in L, there can be infinite number of a's coming in, which can't be stored. 
   **Example 8 -** L = { w | na(w) = nb(w) } is not regular. 
   **Example 9 -** L = { w | na(w)%3 > nb(w)%3 } is regular, because modulus operation requires bounded storage i.e. modulus can be only 0, 1 or 2 for %3 operation and then similarly for b, it would be 0, 1 and 2. So, the states represented in DFA would be all combinations of the remainders of a and b.
7. Patterns of **W, W** **r** and **x** , **y** 
   - If **|x|** is bounded to certain length, then not regular. 
     **Example 10 -** L = { W x Wr | W, x belongs to{a, b}\* and |x|=5 } is not regular. If W= abb then Wr = bba and x = aab, so combined string is abb aab bba. Now, x can be expanded to eat away W and Wr , but |x| = 5. So, even in expanded string, W=ab, Wr=ba and x=baabb. So, we don't get any pattern of form (a+b)\*, so not regular.
   - If |x| is unbounded and W belongs to (a+b)\*, then put W as epsilon and W^r as epsilon, if we get (a+b)\* as a result then the language is regular. 
     **Example 11 -** L = { W x Wr | W, x belongs to {a, b}\* } is regular. 
     If W = abb then Wr = bba and X = aab, so combined string is abb aab bba. Now, x can be expanded to eat away W and Wr . So, in expanded string, W=epsilon,Wr =epsilon and X=abb aab bba. We get simple pattern of form (a+b)\* for which finite automaton can be drawn.
   - If |x| is unbounded and W belongs to (a+b)+, then put W as any symbol from alphabet and corresponding Wr , if we can still get some combination of (a+b)\* as a result, with a guarantee that all strings will be of the same form, then the language is regular else not regular. This needs more explanation with an example: 
     **Example 12 -** L = { W x Wr | W, x belongs to {a, b}+ } is regular. 
     If W = abb then Wr = bba and x = aab, so combined string is abbaabbba. Now, X can be expanded to eat away W and Wr , leaving one symbol either a or b. In the expanded string, if W=a then Wr =a and if W=b then Wr =b. In above example, Wr=a. x=bbaabbb. It reduces to the pattern strings starting and ending in same symbol a(a+b)\*a or b(a+b)\*b for which finite automaton can be drawn. 
     **Example 13 -** L = { W Wr Y | W, y belongs to {0, 1}+} is not regular. 
     If W= 101 then Wr = 101 and Y= 0111, then string is 1011010111. If y is expanded, then W=1, Wr =0 and y=11010111. According to this expansion, the string does not belong to the language itself, that is wrong, hence not regular. 
     If W= 110 then Wr = 011 and Y= 0111, then string is 1100110111. If y is expanded, then W=1, Wr=1 and Y=00110111. This string satisfies the language, but we can't generalize based upon this, because strings might start with 01 and 10 as well. 
     **Example 14 -** L = { x WWr y | x, y, W belongs to {a, b}+ } is regular. 
     If X= aaaba, W=ab and Y=aab. The string is aaaba abbaaab. Now, x and y could be expanded such that W and Wr are eaten, but leaving one symbol for + i.e. the new values are X= aaabaa W= b, Wr = b. So, the language gets reduced to set of all strings containing 'bb' or 'aa' as substring, which is regular.
| **Advantages** | **Disadvantages** |
| --- | --- |
| Clear understanding of language structure and rules | Undecidable for general complex languages |
| Fast and efficient processing using automata | Not applicable to higher-level languages |
| Easy implementation in practical applications | May require high time and memory resources |
| Strong theoretical support and properties | Risk of incorrect classification results |
###
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/theory-of-computation/how-to-identify-if-a-language-is-regular-or-not/)

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
