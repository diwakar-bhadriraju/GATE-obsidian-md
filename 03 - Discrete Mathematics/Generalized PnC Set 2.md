---
title: "Mathematics | Generalized PnC Set 2"
subject: "Discrete Mathematics"
topic: "Combinatorics"
source: "https://www.geeksforgeeks.org/engineering-mathematics/mathematics-generalized-pnc-set-2/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Combinatorics"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/combinatorics
---


> [!abstract] Mathematics | Generalized PnC Set 2
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Combinatorics`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-generalized-pnc-set-2/)

---

# Mathematics | Generalized PnC Set 2

**Prerequisite -** [Generalized PnC Set 1](https://www.geeksforgeeks.org/engineering-mathematics/generalized-pnc-set-1/)
Combinatorial problems can be rephrased in several different ways, the most common of which is in terms of distributing balls into boxes. So we must become familiar with the terminology to be able to solve problems.
The balls and boxes can be either **distinguishable** or **indistinguishable** and the distribution can take place either with or without **exclusion**.
The term exclusion means that no box can contain more than one ball, and similarly, if the problem states the distribution is without exclusion it means that a box may contain more than one ball.
Throughout this article consider that there are
$$
m
$$
balls and
$$
n
$$
boxes.
### 1. Distinguishable balls and Distinguishable boxes -
**With Exclusion -** In case of exclusion, distribution is the same as counting
$$
r
$$
-permutations, as there are
$$
n
$$
choices for the first ball,
$$
n-1
$$
for the second and so on.
**Without Exclusion -** When the distribution is without exclusion, i.e. there is no restriction on the minimum number of balls a box has to have, the number of ways -
$$
n^m
$$
. This is because every ball has
$$
n
$$
choices.
**Fixed number of balls -** If the distribution is such that each box should only have a fixed number of balls then the number of ways is-
$$
\frac{m!}{m_1!m_2!...m_k!}
$$
where
$$
m_k
$$
is the number of balls to be put in the
$$
k^{th}
$$
box.
- **Example 1 -** In how many ways can 10 prizes be distributed among 5 people without exclusion?
- **Solution -** This situation is analogous to distributing distinct balls into distinct boxes without exclusion. For every prize there are 5 choices of people who can receive it. So the number of ways of distributing the prizes is-
$$
5^{10}
$$
  .
- **Example 2 -** How many ways are there to distribute hands of 5 cards to each of four players from a standard deck of 52 cards?
- **Solution -** This situation is analogous to distributing distinct balls into distinct boxes where each box must have a certain number of balls.
  The first person can get the cards in C(52,5) ways.
  The second person can get the cards in C(47,5) ways and so on till the fourth person can get the cards in C(37,5) ways. After 20 balls(cards) have been distributed, the remaining cards form the fifth box (or player).
  This can be solved with the product rule, total ways-
  =
$$
C(52,5) * C(47,5) * C(42,5) * C(37,5)
$$
  =
$$
\frac{52!}{47!5!}\frac{47!}{42!5!}\frac{42!}{37!5!}\frac{37!}{32!5!}
$$
  =
$$
\frac{52!}{5!5!5!5!32!}
$$
  This could also be solved using the formula mentioned above using group sizes 5,5,5,5 and 32.
### 2. Indistinguishable balls and Distinguishable boxes -
Counting the number of ways of placing indistinguishable balls into distinguishable boxes with exclusion is the same as counting
$$
r
$$
-combinations without repetition of elements. But if the distribution is without exclusion then the problem is the same as counting the number of
$$
r
$$
-combinations where elements can be repeated. Refer [Generalized PnC Part-1](https://www.geeksforgeeks.org/engineering-mathematics/generalized-pnc-set-1/) for more on this topic.
### 3. Distinguishable balls and Indistinguishable boxes -
There is no simple closed formula for counting the number of ways of distributing distinguishable balls into indistinguishable boxes, but there is a complex one involving Stirling number of the second kind.
The Stirling number is denoted by
$$
S(m,j)
$$
where
$$
m
$$
is the number of balls and
$$
j
$$
is the number of non-empty boxes.
$$
S(m,j) = \frac{1}{j!}\sum\limits_{i=0}^{j-1}(-1)^i \binom{j}{i} (j-i)^m
$$
So the number of ways is-
$$
\sum\limits_{j=1}^{n}S(m,j)
$$
### 4. Indistinguishable balls and Indistinguishable boxes -
Counting the number of ways of distributing indistinguishable balls into indistinguishable objects is analogous to finding the number of partitions of a positive integer. No simple formula exists for finding the number of partitions of a positive integer.
For both of the above cases, enumeration of all ways is sometimes easier than finding a closed formula which gives the same result.
- **Example 1 -** How many ways are there to put four different balls into three indistinguishable offices without exclusion?
- **Solution -** Enumerating all possible scenarios instead of using the Stirling Formula is easier. Let the four balls be
$$
a, b, c\:and\:d
$$
  .
  All balls in one box -
$$
\{\{a,b,c,d\}\}
$$
  3 balls in one box and 1 in another-
$$
\{\{a,c,d\},\{b\}\},\:\{\{a,b,c\},\{d\}\},\:\{\{a,b,d\},\{c\}\},\:\{\{b,c,d\},\{a\}\}
$$
  2 balls in one box and 2 in another-
$$
\{\{a,b\},\{c,d\}\},\:\{\{a,d\},\{b,c\}\},\:\{\{a,c\},\{b,d\}\}
$$
  2 balls in one box and 1 each in the remaining boxes-
$$
\{\{a,b\},\{c\},\{d\}\},\:\{\{a,d\},\{b\},\{c\}\},\:\{\{a,c\},\{b\},\{d\}\},\:\{\{b,c\},\{a\},\{d\}\}
$$
$$
\{\{b,d\},\{a\},\{c\}\},\:\{\{d,c\},\{b\},\{a\}\}
$$
  This gives us a total of- 1 + 3 + 4 + 6 = 14 ways.
- **Example 2 -** How many ways are there to put 4 indistinguishable balls into 3 indistinguishable boxes?
- **Solution -** As mentioned above, the above problem is analogous to finding the number of partitions of the positive integer 4, where the number of partitions is less than or equal to 3.
  Enumerating all possible ways-
  All four balls in one box - 4
  3 balls in one box, 1 ball in one - 3,1
  2 balls in two boxes - 2,2
  2 balls in 1 box, 1 ball in two boxes each - 2,1,1
  Total number of ways = 4
  It is similar to finding the number of partitions of 4-
  4 = 4
  3 + 1 = 4
  2 + 2 = 4
  2 + 1 + 1 = 4
**GATE CS Corner Questions**
Practicing the following questions will help you test your knowledge. All questions have been asked in GATE in previous years or in GATE Mock Tests. It is highly recommended that you practice them.
1. [GATE CS 2003, Question 34](https://www.geeksforgeeks.org/questions/m-identical-balls-are-to-be-placed-in-n/)
2. [GATE CS 2015 Set-3, Question 15](https://www.geeksforgeeks.org/questions/the-number-of-4-digit-numbers-having-their-digits/)
**References-**
[Partition Number Theory - Wikipedia](https://en.wikipedia.org/wiki/Partition_%28number_theory%29)
Discrete Mathematics and its Applications, by Kenneth H Rosen
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematics-generalized-pnc-set-2/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Combinatorics

> [!note] Related notes
>
> - [[Binomial Coefficients]]
> - [[Combinatorics Basics]]
> - [[Corollaries of Binomial Theorem]]
> - [[Generalized PnC Set 1]]
> - [[Generating Functions]]
> - [[Pigeonhole Principle]]
> - [[Principle of Inclusion-Exclusion]]
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Closure of Relations]]
