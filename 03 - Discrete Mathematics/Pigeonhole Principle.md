---
title: "Pigeonhole Principle"
subject: "Discrete Mathematics"
topic: "Combinatorics"
source: "https://www.geeksforgeeks.org/engineering-mathematics/discrete-mathematics-the-pigeonhole-principle/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Combinatorics"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/combinatorics
---


> [!abstract] Pigeonhole Principle
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Combinatorics`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/discrete-mathematics-the-pigeonhole-principle/)

---

# Pigeonhole Principle

The pigeonhole principle states that if **n** items are put into **m** containers, with **n** > **m**, then at least one container must contain more than one item.
The main idea of the principle is if more objects (pigeons) are placed into fewer containers (pigeonholes), at least one container must hold more than one object.
**Example 1:**
> Suppose that a flock of 13 pigeons flies into a set of 12 pigeonholes to roost.
>
> At least one of these 12 pigeonholes must have at least two pigeons in it. At least one of these 12 pigeonholes must have at least two pigeons in it.
> ![Pigeonhole-Principle](assets/Pigeonhole-Principle-b0687244fa.webp)
>
> To see why this is true, note that if each pigeonhole had at most one pigeon, at most 12 pigeons, one per hole, could be accommodated. This illustrates a general principle called the pigeonhole principle, which states that if there are more pigeons than pigeonholes, there must be at least one pigeonhole with at least two pigeons.
**Example 2:** If you have 10 black socks and 12 blue socks mixed in a drawer, how many socks must you pick to guarantee a matching pair?
> n = number of socks picked, k = number of colors (pigeonholes)
> To ensure at least one matching pair, we need: n > k
> n > 2; therefore the least value is 3.
> Therefore at least 3 socks is requiredto get the same value.
The Generalised form of Pigeonhole Principle is given by,
> If **n** items are placed into k containers, then at least one container must contain at least 
>
>
$$
⌈\frac{n}{k}⌉
$$
>
>  items.
**For example:** If there are 100 students, how many students possibly share same birth month?
> Using Generalized form, for 100 students and 12 months, at least 
>
>
$$
⌈\frac{100}{12}⌉ =9
$$
>
>  students share a birth month.
## Pigeonhole Principle Theorem
If “A” is the average number of pigeons per hole, where A is not an integer then
- At least one pigeonhole must contain ≥⌈A⌉ pigeons. (ceiling function)
- The remaining pigeonholes must each contain ≤⌊A⌋ pigeons. (flooring function)
**Example 1:** If (Kn+1) pigeons are kept in n pigeon holes where K is a positive integer, what is the average no. of pigeons per pigeon hole?
**Solution:**
> Average number of pigeons per hole = (Kn+1)/n = K + 1/n
>
> Therefore there will be at least one pigeonhole which will contain at least (K+1) pigeons i.e., ceil[K +1/n] and remaining will contain at most K i.e., floor[k+1/n] pigeons. i.e., the minimum number of pigeons required to ensure that at least one pigeon hole contains (K+1) pigeons is (Kn+1).
**Example 2:** A bag contains 10 red marbles, 10 white marbles and 10 blue marbles. What is the minimum no. of marbles you have to choose randomly from the bag to ensure that we get 4 marbles of same color?
**Solution:**
> Apply pigeonhole principle. No. of colors (pigeonholes) n = 3 No. of marbles (pigeons) K+1 = 4 Therefore the minimum no. of marbles required = Kn+1 By simplifying we get Kn+1 = 10. Verification: ceil[Average] is [Kn+1/n] = 4 [Kn+1/3] = 4 Kn+1 = 10 i.e., 3 red + 3 white + 3 blue + 1(red or white or blue) = 10
## **Pigeonhole Principle Strong Form Theorem**
Let q1, q2, . . . , qn be positive integers. If
> q1+ q2+ . . . + qn - n + 1
objects are put into n boxes, then either the 1st box contains at least q1 objects or the 2nd box contains at least q2 objects, . . ., the nth box contains at least qn objects.
**Example 1:** In a computer science department, a student club can be formed with either 10 members from first year or 8 members from second year or 6 from third year or 4 from final year. What is the minimum no. of students we have to choose randomly from department to ensure that a student club is formed?
**Solution:**
> We can directly apply from the above formula where, q1 = 10, q2 = 8, q3 = 6, q4 = 4 and n = 4
> Therefore the minimum number of students required to ensure department club to be formed is 10 + 8 + 6 + 4 - 4 + 1 = 25
**Example 2:** A box contains 6 red, 8 green, 10 blue, 12 yellow and 15 white balls. What is the minimum no. of balls we have to choose randomly from the box to ensure that we get 9 balls of same color?
**Solution:**
> Here in this we cannot blindly apply pigeon principle. First we will see what happens if we apply above formula directly.
> From the above formula we have get answer 47 because 6 + 8 + 10 + 12 + 15- 5 + 1 = 47. But it is not correct.
> In order to get the correct answer we need to include only blue, yellow and white balls because red and green balls are less than 9.
> But we are picking randomly so we include after we apply pigeon principle. i.e., 9 blue + 9 yellow + 9 white - 3 + 1 = 25
> Since we are picking randomly so we can get all the red and green balls before the above 25 balls. Therefore we add 6 red + 8 green + 25 = 39 .
> We can conclude that in order to pick 9 balls of same color randomly, one has to pick 39 balls from a box.
## Applications of the Pigeonhole Principle
The Pigeonhole Principle is used in various fields to solve problems that involve distributing objects into containers. Here are some notable applications:
- **Computer Science:** In computer science, the Pigeonhole Principle is used in [hashing algorithms](https://www.geeksforgeeks.org/dsa/introduction-to-hashing-2/), where data items (keys) are assigned to hash values (buckets). The principle guarantees that if there are more items than buckets, collisions will occur, necessitating strategies to handle them.
- **Coding Theory:** In coding theory, the Pigeonhole Principle helps in understanding error detection and correction. It implies that if you encode more messages than the number of unique codewords, some messages will share the same codeword, leading to potential errors.
- **Number Theory:** In number theory, the Pigeonhole Principle can prove the existence of certain properties within a set of numbers. For instance, it can show that within any set of n+1 integers, there exists a pair of integers whose difference is divisible by n.
- **Graph Theory:** In graph theory, the Pigeonhole Principle is used to prove properties of graphs, such as the existence of a subgraph with certain characteristics. For example, in any group of people, some subset of individuals will have mutual friendships or mutual non-friendships.
## Solved Examples
**1.** Prove that among any 52 integers, there are always two whose difference is divisible by 51.
**Solution :**
> Consider the remainders when each number is divided by 51. There are 51 possible remainders (0 to 50). With 52 numbers, by the Pigeonhole Principle, at least two numbers must have the same remainder. Their difference will be divisible by 51.
**2.** In a group of 1001 people, show that there are at least two people with the same number of friends within the group.
**Solution :**
> In 1001 people, two have the same number of friends:
> Each person can have between 0 and 1000 friends. However, it is impossible for someone to have 0 friends and someone else to have 1000 friends at the same time. Therefore, the friend counts that actually occur are either among 0–999 or among 1–1000, in either case at most 1000 different values.
> With 1001 people and at most 1000 possible friend counts, the Pigeonhole Principle implies that at least two people have the same number of friends.
**3.** Prove that if 5 points are placed inside a unit square, there must be two points that are at most 1/√2 units apart.
**Solution :**
> 5 points in a unit square, two at most 1/√2 apart:
> Divide the square into four equal squares of side length 1/2. By the Pigeonhole Principle, at least two points must be in the same smaller square. The maximum distance between any two points in a 1/2 × 1/2 square is 1/√2.
**4**. Show that in any sequence of 101 distinct real numbers, there is always an increasing or decreasing subsequence of length at least 11.
**Solution :**
> In 101 distinct reals, increasing/decreasing subsequence of length 11:
> Assign two numbers to each term: its length as a longest increasing subsequence ending at that term and its length as a longest decreasing subsequence starting at that term. If no term has both numbers ≥ 11, the sum of all these numbers would be at most 20 × 101 = 2020. But the sum must be at least 101 × 11 = 1111, a contradiction.
**5.** Prove that for any set of 10 integers, there are always two distinct subsets with the same sum of elements.
**Solution :**
> In 10 integers, two subsets with the same sum:
> There are 2^10 = 1024 possible subsets. The sum of all elements is at most 10 × 9 = 90 (if the set is {0,1,2,...,9}). By the Pigeonhole Principle, among 1024 subsets, two must have the same sum.
### Practice Questions
1. A drawer has 10 black socks and 10 blue socks. How many socks must you pull out (blindly) to guarantee a matching pair?
2. If a class of x students takes an exam with possible scores from 0 to 100, for what x at least two students must share the same score if only integer grades are given?
3. In a city of 500,000 people, show that at least two have the same number of hairs on their head (assuming max hairs = 150,000).
4. In a group of 6 people, show that at least three are mutual friends or mutual strangers.
5. A store sells left and right shoes in 3 different types: sneakers, boots, and sandals. How many shoes must be selected to guarantee at least one matching pair?
**Answer Key:**
> 1. To ensure a pair, pick 3 socks.
> 2. x = 102 students. (0-100 -> 101 pigeonholes)
> 3. Since 500,000>150,001, at least two people must have the same number of hairs.
> 4. Pick any person. They have 5 relationships (friends/strangers). By PHP, at least ⌈5/2⌉=3 are friends or strangers with them.
> 5. 7
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/discrete-mathematics-the-pigeonhole-principle/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Combinatorics

> [!note] Related notes
>
> - [[Binomial Coefficients]]
> - [[Combinatorics Basics]]
> - [[Corollaries of Binomial Theorem]]
> - [[Generalized PnC Set 1]]
> - [[Generalized PnC Set 2]]
> - [[Generating Functions]]
> - [[Principle of Inclusion-Exclusion]]
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
> - [[Closure of Relations]]
