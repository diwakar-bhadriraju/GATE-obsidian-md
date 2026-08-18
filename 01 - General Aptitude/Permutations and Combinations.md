---
title: "Permutations and Combinations"
subject: "General Aptitude"
topic: "Quantitative Aptitude"
source: "https://www.geeksforgeeks.org/maths/permutations-and-combinations/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "General Aptitude/Quantitative Aptitude"
tags:
  - gate/cs
  - subject/general-aptitude
  - topic/quantitative-aptitude
---


> [!abstract] Permutations and Combinations
> 
> **Subject:** `General Aptitude` &nbsp;|&nbsp; **Topic:** `Quantitative Aptitude`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/permutations-and-combinations/)

---

# Permutations and Combinations

Permutation and Combination are the most fundamental concepts in mathematics related to picking items from a group or set.
- Permutation is the arrangement of items in which the order of selection matters.
- Combination is the selection of items without considering their order.
For example, in the diagram below, PQ and QP are different in permutation but the same in combination. Therefore, we have more permutations than combinations.
![Permutation-an-Combination](assets/Permutation-an-Combination-01dbc0c4c2.webp)
### Permutation
[Permutation](https://www.geeksforgeeks.org/maths/permutation/) is used to find the number of ways to pick ‘r’ things out of ‘n’ different things in a specific order and replacement is not allowed.
It is represented as n Pr , where,
- **r** : how many components you have to choose.
- **n** : total number of components present.
> For example, let n = 3 (A, B and C) and r = 2 (All permutations of size 2).
> Then there are 3P2 such permutations, i.e. 6.
> These six permutations are AB, AC, BA, BC, CA and CB.
>
> ![Permutation of Two elements out of A, B, and C](assets/Permutation-Combination-4-ad3bcdde2b.webp)
### Formula
Permutation is the way of arranging items where order is important.
![Permutation Formula](assets/Permutation-Combination-1-75048a4ec2.webp)
**For example**:
> If there are three different numerals 1, 2 and 3 and to permute the numerals
> Taking r = 2, it gives (1, 2), (1, 3), (2, 1), (2, 3), (3, 1) and (3, 2) - 6 ways
> Here, (1, 2) and (2, 1) are distinct.
> Putting the third left numeral to each cases we get
> (1, 2, 3), (1, 3, 2), (2, 1, 3), (2, 3, 1), (3, 1, 2) and (3, 2, 1) - 6 ways
In general, n distinct things can be set taking r (r < n) at a time in n(n - 1)(n - 2)...(n - r + 1) ways. In fact, the first thing can be any of the n things.
Now, after choosing the first thing, the second thing will be any of the remaining n - 1 things. Likewise, the third thing can be any of the remaining n - 2 things. Alike, the rth thing can be any of the remaining n - (r - 1) things. 
![pnc](assets/pnc-eb3216dad8.webp)
Hence, the entire number of permutations of n distinct things carrying r at a time is n(n - 1)(n - 2)...[n - (r - 1)], which is written as n Pr. Or, in other words, 
>
$$
\bold{{}^nP_r = \frac{n!}{(n-r)!} }
$$
### Combination
It is the way of arranging given number of components, where order is not given importance. For example, if there are two components A and B, then there is only one way to select two things, i.e. AB and BA represents the same combination.
> For example, let n = 3 (A, B and C) and r = 2 (All combinations of size 2). Then there are **3**C**2** such combinations, which is equal to 3. These three combinations are AB, AC and BC.
>
> Here, the [combination](https://www.geeksforgeeks.org/maths/combinations/) of any two letters out of three letters A, B and C is shown below, the order in which A and B are taken is not important as AB and BA represent the same combination.
>
> ![what is combination](assets/Permutation-Combination-3-03f596bccf.webp)
**Note:** In the example of selecting 2 items among A and B, we can say that,
- AB and BA are two distinct items i.e., two distinct permutation.
- AB and BA are the same i.e., same combination.
### Formula
Combination Formula is used to choose ‘r’ components out of a total number of ‘n’ components and is given by:
![Combination Formula](assets/Permutation-Combination-2-a5cfca7006.webp)
Combination Formula
Using the above formula for r and (n-r), we get the same result. Thus,
>
$$
\bold{{}^nC_r = {}^nC_{(n-r)}}
$$
> Combination, on the further hand, is a type of pack. Again, out of those three numbers 1, 2 and 3 if sets are created with two numbers, then the combinations are (1, 2), (1, 3) and (2, 3). 
>
> Here, (1, 2) and (2, 1) are identical, unlike permutations where they are distinct. This is written as 3C2. In general, the number of combinations of n distinct things taken r at a time is, 
>
>
$$
\bold{{}^nC_r = \frac{n!}{r!\times(n-r)!} = \frac{{}^nP_r}{r!}}
$$
## Derivation of Permutation and Combination Formulas
We can derive these Permutation and Combination formulas using the basic counting methods, as these formulas represent the same thing. Derivation of these formulas is as follows:
### Derivation of Permutations Formula
Permutation is selecting r distinct objects from n objects without replacement and where the order of selection is important. By the fundamental theorem of counting and the definition of permutation, we get
> P (n, r) = n (n-1) (n-2) (n-3).  . . .  .(n-(r+1))
By multiplying and dividing above with (n-r)! = (n-r)(n-r-1)(n-r-2).  . . .  .3. 2. 1, we get
> P (n, r) =
>
>
$$
\frac{n(n-1)\cdots(n-r+1)(n-r)!}{(n-r)!}
$$
>
> ⇒ P (n, r) = n!/(n−r)!
Thus, the formula for P (n, r) is derived.
### Derivation of Combinations Formula
[Combination](https://www.geeksforgeeks.org/maths/combinations-formula-with-examples/) is choosing r items out of n items when the order of selection is of no importance. Its formula is calculated as,
> C(n, r) = Total Number of Permutations /Number of ways to arrange r different objects. 
> [Since by the fundamental theorem of counting, we know that number of ways to arrange r different objects = r!]
>
> C(n,r) = P (n, r)/ r!
>
> **⇒ C(n,r) = n!/(n−r)!r!**
Thus, the formula for Combination i.e., C(n, r) is derived.
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/aptitude/permutation-and-combination-questions/)
### Related Articles
> - [Tricks](https://www.geeksforgeeks.org/maths/tricks-to-solve-permutation-and-combination-questions/)
> - [Quiz](https://www.geeksforgeeks.org/quizzes/permutation-and-combination-gq/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/permutations-and-combinations/)

## GATE CS

- Subject: General Aptitude
- Topic: Quantitative Aptitude

> [!note] Related notes
>
> - [[Bar Graph]]
> - [[Elementary Statistics and Probability]]
> - [[Exponents]]
> - [[Line Graphs]]
> - [[Logarithms]]
> - [[Mensuration and Geometry]]
> - [[Percentages]]
> - [[Pie Chart]]
> - [[Powers]]
> - [[Ratio and Proportion]]
