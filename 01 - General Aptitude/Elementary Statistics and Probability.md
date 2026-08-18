---
title: "Probability - Solved Questions and Answers"
subject: "General Aptitude"
topic: "Quantitative Aptitude"
source: "https://www.geeksforgeeks.org/aptitude/probability-questions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "General Aptitude/Quantitative Aptitude"
tags:
  - gate/cs
  - subject/general-aptitude
  - topic/quantitative-aptitude
---


> [!abstract] Probability - Solved Questions and Answers
> 
> **Subject:** `General Aptitude` &nbsp;|&nbsp; **Topic:** `Quantitative Aptitude`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/aptitude/probability-questions/)

---

# Probability - Solved Questions and Answers

[Probability](https://www.geeksforgeeks.org/maths/basic-concepts-of-probability/) measures how likely an event is to occur, expressed as a value between 0 and 1.
**Formula:**
>
$$
P(E)=\frac{Number of favorable outcomes}{Total possible outcome}
$$
**Probability questions and answers are provided below for you to learn and practice.**
**Question 1:** Three unbiased coins are tossed. What is the probability that at most one head occurred? 
**Solution**: 
> S = {HHH, HHT, HTH, THH, HTT, THT, TTH, TTT}
> Favorable outcomes = {HTT, THT, TTH, TTT}
> Total number of outcomes = 8
> Number of favorable outcomes = 4
> Required probability = 4 / 8 = **0.50**
**Question 2:** Find the probability of getting a red card when a card is drawn from a well-shuffled pack of cards. 
**Solution**: 
> Total number of outcomes = 52
> Number of favorable outcomes = Number of red cards = 26
> Required probability = 26 / 52 = **0.50**
**Question 3:** A bag contains 6 white and 4 black balls. Two balls are drawn at random from the bag. Find the probability that both the balls are of the same color. 
**Solution**: 
> Outcome will be favorable if the two balls drawn are of the same color. => Number of favorable outcomes = 6C2 + 4C2 = 21
> Total number of outcomes = 10C2 = 45
> Therefore, required probability = 21 / 45 = **7 / 15** 
**Question 4:** An unbiased die is tossed. Find the probability of getting an even number. 
**Solution**: 
> S = {1, 2, 3, 4, 5, 6}
> Favorable outcomes = {2, 4, 6}
> Required probability = 3 / 6 = **0.50**
**Question 5:** From a bag containing red and blue balls, 10 each, 2 balls are drawn at random. Find the probability that one of them is red and the other is blue. 
**Solution**: 
> Total number of outcomes = 20C2 = 190
> Number of favorable outcomes = 10C1 x 10C1 = 100
> Therefore, required probability = 100 / 190 = **10 / 19**
**Question 6:**If a coin is thrown two times, what is the probability that at least one tail is obtained?
A) 3/4
B) 1/4
C) 1/3
D) 2/3
E) None of these 
```
Answer: A
```
**Solution:** 
> Sample space = [TT, TH, HT, HH]
> Total number of ways = 2 × 2  = 4.  
> Favourite Cases = 3
> P (A) = **3/4**
**Question 7**: There are 7 purple clips and 5 brown clips. Two clips are selected one by one without replacement. Find the probability that the first is brown and the second is purple.
A) 1/35
B) 35/132
C) 1/132
D) 35/144
E) None of these 
```
Answer: B
```
**Solution:**
> P (B) × P (P) = (5/12) x (7/11) = **35/132**
**Question 8:** Find the probability of getting a sum of 8 when two dice are thrown.
A) 1/8
B) 1/5
C) 1/4
D) 5/36
E) 1/3 
```
Answer: D
```
**Solution:**
> Total number of ways = 6 × 6 = 36 ways. 
> Favorable cases = (2, 6) (6, 2) (3, 5) (5, 3) (4, 4)  --- 5 ways. 
> P (A) = 5/36 = **5/36**
**Question 9**: If two dice are rolled together then find the probability of getting at least one '3'.
A) 11/36
B) 1/12
C) 1/36
D) 13/25
E) 13/36 
```
Answer: A
```
**Solution:**
> Total number of ways = 6 × 6 = 36. 
> Probability of getting number ‘3' at least one time
> = 1 – (Probability of getting no number 3) 
> = 1 – (5/6) × (5/6)
> = 1 - 25/36
> = **11/36**
**Question 10**: A container contains 1 red, 3 black, 2 pink, and 4 violet gems. If a single gem is chosen at random from the container, then find the probability that it is violet or black.
A) 1/10
B) 3/10
C) 7/10
D) 9/10
E) None of these
```
Answer: C
```
**Solution:**
> Total gems =( 1 + 3 + 2 + 4 ) = 10
> probability of getting a violet gem = 4/10
> The probability of getting a black gem = 3/10
> Now, P ( Violet or Black) = P(violet) + P(Black)
>                                            = 4/10 + 3/10
>                                            = **7/10**
**Question 11**: A jar contains 63 balls ( 1, 2, 3,......., 63). Two balls are picked at random from the jar one after one and without any replacement. What is the probability that the sum of both balls drawn is even?
A) 5/21
B) 3/23
C) 5/63
D) 19/63
E) None of these
```
Answer: E
```
**Solution:**
> The sum of numbers can be even if we add either two even numbers or two odd numbers.
>
> Number of even numbers from 1 to 63 = 31
> Number of odd numbers from 1 to 63 = 32
>
> Probability of getting **two even** numbers = (32/63) \* (31/62) = **16/63**
> Probability of getting **two odd** numbers = (31/63) \* (30/62) = **5/21**
>
> P(two even numbers **OR** two odd numbers) = 16/63 + 5/21 = **31/63**
**Question 12**: There are 30 students in a class, 15 are boys and 15 are girls. In the final exam, 5 boys and 4 girls made an A grade. If a student is chosen at random from the class, what is the probability of choosing a girl or an 'A-grade student?
A) 1/4
B) 3/10
C) 1/3
D) 2/3
E) None of these
```
Answer: D
```
**Solution:**
> Here, the total number of boys = 15 and the total number of girls = 15
>
> Also, girls getting A grade = 4 and boys getting an A grade = 5 
> Probability of choosing a girl = 15/30
>
> Probability of choosing A grade student= 9/30
>
> Now, an A-grade student chosen can be a girl.
> So the probability of choosing it = 4/30
>
> Required probability of choosing a girl or an A-grade student 
> = 15/30 + 9/30 - 4/30
> = 1/2 + 3/10 - 2/15
> = **2/3**
**Question 13:** If P(A) = 7/13, P(B) = 9/13 and P(A∩B) = 4/13, find the value of P(A|B).
A) 1/9
B) 2/9
C) 3/9
D) 4/9
E) None of these
```
Answer: D
```
**Solution:**
> P(A|B) = P(A∩B)/P(B) = (4/13)/(9/13) = **4/9.**
**Question 14**: A one-rupee coin and a two-rupee coin are tossed once, and then calculate a sample space.
A) [ HH, HT, TH, TT]
B) [ HH, TT]
C) [ TH, HT]
D) [HH, TH, TT]
E) None of these
```
Answer: A
```
**Solution:**
> The outcomes are either Head (H) or tail(T).
> Now,heads on both coins = (H, H) = HH
> Tails on both coins = ( T, T) = TT
>
> Probability of head on one rupee coin and Tail on the two rupee coins = (H, T) = HT
> And Tail on one rupee coin and Head on the two rupee coin = (T, H) = TH
>
> Thus, the sample space,**S = [HH, HT, TH, TT]**
**Question 15**: There are 20 tickets numbered 1 to 20. These tickets are mixed up and then a ticket is drawn at random. Find the probability that the ticket drawn has a number that is a multiple of 4 or 5.
A) 1/4
B) 2/13
C) 8/15
D) 9/20
E) None of these
```
Answer: E
```
**Solution:**
> Here, S = {1, 2, 3, 4, ...., 19, 20} = 20
>
> **Multiples of 4:** 4, 8, 12, 16, 20 (5 tickets)
> **Multiples of 5:** 5, 10, 15, 20 (4 tickets)
>
> Notice that ticket number 20 is a multiple of both 4 and 5, so we have counted it twice. Therefore, we need to subtract one from the total count.
>
> Total number of tickets with numbers that are multiples of 4 or 5: 5 + 4 - 1 = 8
> The total number of tickets is 20, so the probability of drawing a ticket with a number that is a multiple of 4 or 5 is:
>
> P = 8/20 = 2/5 = 0.4
>
> Therefore, the probability that the ticket drawn has a number that is a multiple of 4 or 5 is 0.4 or **40%.**
**Direction ( 16 - 18):**
In a school the total number of students is 300, 95 students like chicken only, 120 students like fish only, 80 students like mutton only and 5 students do not like anything above. If randomly one student is chosen, find the probability that**.**
23) The student likes mutton.
24) He likes either chicken or mutton
25) He likes neither fish nor mutton.
**Solution ( 16 - 18):**
> The total number of favorable outcomes = 300 (Since there are 300 students altogether).
>
> The number of times a chicken liker is chosen = 95 (Since 95 students like chicken).
> The number of times a fish liker is chosen = 120.
> The number of times a mutton liker is chosen = 80.
> The number of times a student is chosen who likes none of these = 5.
**Question 19:** Find the probability that the student likes mutton.
A) 3/10
B) 4/15
C) 1/10
D) 1/15
E) None of these
```
Answer: B
```
**Solution:**
> Therefore, the probability of getting a student who likes mutton
>
> = 80/300
> = **4/15**
**Question 20**: What is the probability that the student likes either chicken or mutton?
A) 7/12
B) 5/12
C) 3/4
D) 1/12
E) None of these
```
Answer: A
```
**Solution:**
> The probability of getting a student who likes either chicken or mutton
> = (95+80)/300
> = 175/300
> = **7/12**
**Question 21**: Find the probability that the student likes neither fish nor mutton.
A) 1/2
B) 1/5
C) 1/3
D) 1/4
E) 1/6
```
Answer: C
```
**Solution:**
> The probability of getting a student who likes neither fish nor mutton 
> = (300–120−80)/300
> = 100/300
> = **1/3**
**Direction ( 22-24):**
A box contains 90 number plates numbered 1 to 90. If one number plate is drawn at random from the box then find out the probability that
26) The number is a two-digit number
27) The number is a perfect square
28) The number is a multiply of 5
**Question 22**: Find the probability that the number is a two-digit number.
A) 1/9
B) 1/10
C) 9/10
D) 7/10
E) None of these
```
Answer: C
```
**Solution :**
> Total possible outcomes = 90 (Since the number plates are numbered from 1 to 90).
>
> Number of favorable outcomes
> = 90 - 9 = 81 (  here, except 1 to 9, other numbers are two-digit number.)
>
> Thus required probability 
> = Number of Favourable Outcomes /Total Number of Possible Outcomes
> = 81/90
> = **9/10.**
**Question 23**: What is the probability that the number is a perfect square?
A) 1/9
B) 1/10
C) 9/10
D) 1/7
E) None of these
```
Answer: B
```
**Solution:**
> Total possible outcomes = 90.
> Number of favorable outcomes = 9      [here 1, 4, 9, 16, 25, 36, 49, 64, and 81 are the perfect squares]
> Thus the required probability = 9/90   =**1/10**                                       
**Question 24:** Find the probability that the number is a multiple of 5.
A) 1/5
B) 1/6
C) 1/10
D) 1/8
E) 9/10
```
Answer: A
```
**Solution:**
> Total possible outcomes = 90.
> Number of favourable outcomes = 18       (here, 5 × 1, 5 × 2, 5 × 3, ....,  5 × 18 are multiple of 5).                                          
>  Thus, the required probability= 18/90 =**1/5**
### Also Check**:**
> [Tricks To Solve Probability Questions](https://www.geeksforgeeks.org/ssc-banking/tricks-to-solve-probability-questions/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/aptitude/probability-questions/)

## GATE CS

- Subject: General Aptitude
- Topic: Quantitative Aptitude

> [!note] Related notes
>
> - [[Bar Graph]]
> - [[Exponents]]
> - [[Line Graphs]]
> - [[Logarithms]]
> - [[Mensuration and Geometry]]
> - [[Percentages]]
> - [[Permutations and Combinations]]
> - [[Pie Chart]]
> - [[Powers]]
> - [[Ratio and Proportion]]
