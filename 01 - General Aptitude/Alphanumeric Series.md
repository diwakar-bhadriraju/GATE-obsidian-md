---
title: "Alphanumeric Series"
subject: "General Aptitude"
topic: "Analytical Aptitude"
source: "https://www.geeksforgeeks.org/aptitude/alphanumeric-series/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "General Aptitude/Analytical Aptitude"
tags:
  - gate/cs
  - subject/general-aptitude
  - topic/analytical-aptitude
---


> [!abstract] Alphanumeric Series
> 
> **Subject:** `General Aptitude` &nbsp;|&nbsp; **Topic:** `Analytical Aptitude`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/aptitude/alphanumeric-series/)

---

# Alphanumeric Series

An alphanumeric series is formed by combining both alphabets and numbers. Sometimes it also includes symbols such as @,&,#, etc. So we can say that the Alphanumeric series is the combination of alphabets, numbers, and symbols. This is an important topic that needs to be covered for the [Logical Reasoning](https://www.geeksforgeeks.org/aptitude/logical-reasoning/) section of the Aptitude test asked in the competitive examinations.
Alphanumeric series combine **letters (A-Z) and numbers (0-9)** in a sequence following a hidden pattern.
![alpha_numeric_series](assets/alpha_numeric_series-5679ede7b5.webp)
## **Types of Alphanumeric Series**
### **1. Letter-Number Alternating Series**
**Rule:** Letters and numbers alternate in a fixed pattern.
**Example:**
> **A2, C4, E6, G8, ?**
>
> **Letters:** A (+2) → C (+2) → E (+2) → G (+2) → **I**
>
> **Numbers:** 2 (+2) → 4 (+2) → 6 (+2) → 8 (+2) → **10**
>
> **Answer:** **I10**
### **2. Letter-Number Embedded Series**
**Rule:** Numbers and letters are combined within a single term.
**Example:**
> **3D, 7G, 11J, 15M, ?**
>
> **Numbers:** 3 (+4) → 7 (+4) → 11 (+4) → 15 (+4) → **19**
>
> **Letters:** D (+3) → G (+3) → J (+3) → M (+3) → **P**
>
> **Answer:** **19P**
### **3. Position-Based Series (A=1, B=2, ..., Z=26)**
**Rule:** Letters are converted to their alphabetical positions.
**Example:**
> **2, 6, 12, 20, ?**
>
> **Logic:** 1×2=**2**, 2×3=**6**, 3×4=**12**, 4×5=**20**, 5×6=**30**
>
> **Answer:** **30** (or **E** if letters are expected since E=5)
### **4. Mixed Operations (Letters + Numbers)**
**Rule:** Combines arithmetic operations with letter shifts.
**Example:**
> **Z1, Y4, X9, W16, ?**
>
> **Letters:** Z (-1) → Y (-1) → X (-1) → W (-1) → **V**
>
> **Numbers:** 1²=1, 2²=4, 3²=9, 4²=16, 5²=**25**
>
> **Answer:** **V25**
### **5. Reverse Alphabet Series**
**Rule:** Letters follow reverse alphabetical order (Z=1, Y=2, ..., A=26).
**Example:**
> **V2, R3, N4, J5, ?**
>
> **Letters:** V (-4) → R (-4) → N (-4) → J (-4) → **F**
>
> **Numbers:** 2, 3, 4, 5 → **6**
>
> **Answer:** **F6**
## Sample Questions on Alphanumeric Series
### **Direction (1-5): Answer the following questions based on the arrangement given below:**
**Q1.** **If the symbols followed by consonants interchange their positions within the group, then which element is third from the right end?**
**B @ C 7 N R % 5 $ G 6 K M & 4 S # P U 5**
(a) U 
(b) # 
(c) P 
(d) 5 
(e)  None of these
> **Answer:** **b**
> **Explanation:-**
> **Given series – B** **@ C** **7 N R % 5** **$ G** **6 K M & 4 S** **# P** **U 5**
> **After operation – B** **C @** **7 N R % 5** **G $** **6 K M & 4 S** **P #** **U 5**
> **So, third element from the right end = #**
**Q2. Based on the given arrangement which of the following groups should be next?**
**BC7   R5$   6M&?**
(a) N5G
(b) KS# 
(c) SPU 
(d) C4H 
(e) 4SP
> **Answer:** **c**
> **Explanation:-**
> **Given series – B @ C 7 N R % 5 $ G 6 K M & 4 S # P U 5**
>
> Apply **+5** repeatedly:**So, SPU is the correct answer.**
>
> - **B → R → 6 → S** ⇒ gives **S**
> - **C → 5 → M→ P** ⇒ gives **P**
> - **7 → $ → &** **→** U ⇒ gives **U**
>
> So the next group is formed by taking corresponding elements: SPU
**Q3.** **Which of the following is second to the left of the twelfth from the right end if all the symbols are dropped?**
(a) F 
(b) C
(c) 7 
(d) M 
(e) None of these
> **Answer:** **b**
> **Explanation:-**
> **Given series – B @ C 7 N R % 5 $ G 6 K M & 4 S # P U 5**
> **After dropping symbols – B C 7 N R 5 G 6 K M 4 S P U 5**
> **So, 12th from the right end – N**
> **Hence, second to the left of N is C.**
**Q4. If the numbers which are preceded by letters interchanged their positions and those letters were changed to the next letter in the alphabetical series, then which of the following elements are the fourth from the left end and the eleventh from the right end?**
(a) F and 7 
(b) 6 and D 
(c) A and $ 
(d) D and 6 
(e) None of these
> **Answer:** **d**
> **Explanation:-**
> **Given series – B @ C 7 N R % 5 $ G 6 K M & 4 S # P U 5**
> **After operation – B @ 7 C N R % 5 $ 6 G K M & 4 S # P 5 U**
> **After changing – B @ 7 D N R % 5 $ 6 H K M & 4 S # P 5 V**
> **So, fourth from the left end and eleventh from the right end – D and 6**
> **Therefore, option d is the correct answer.**
**Q5. How many letters are there which are preceded by a symbol and followed by a number within the group in the given arrangement?**
(a) None 
(b) One 
(c) Two 
(d) Three 
(e) More than three
> **Answer:** **c**
> **Explanation:-**
> **Given series – B @ C 7 N R % 5 $ G 6 K M & 4 S # P U 5**
> **So, there are two letters (@C7, $G6). Therefore option c is the correct answer.**
## Tips & Tricks To Solve Alphanumeric Questions
To solve Alphanumeric Questions, follow the tips and tricks given below:
1. **For missing series:** When a series with a pattern is given, containing alphabets and numbers. The candidate is asked to find the missing number in the blank space.
2. **For Alphabet-Number-Symbol Series:** A series with alphabets, numbers, and different types of symbols (like &, \*, $, etc.) are given, and questions are formed on it.
3. **Alphabetic Series:**This type of Series only contains the English alphabet set in a particular pattern. No numbers or symbols are used here.
4. **Numerical Series:**This type of Series only containsnumbers, arranged in a specific pattern. Questions based on this type are usually asked in the form of a rearrangement of numbers in ascending, descending, or any other order.
### Also Check:
> ➣ Alphanumeric Series Solved Question- [Refer Here](https://www.geeksforgeeks.org/aptitude/alphanumeric-series-logical-reasoning-questions-and-answers/)!
>
> ➣ Test your knowledege- [Quiz](https://www.geeksforgeeks.org/quizzes/alphanumeric-series/)!
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/aptitude/alphanumeric-series/)

## GATE CS

- Subject: General Aptitude
- Topic: Analytical Aptitude

> [!note] Related notes
>
> - [[Analogy]]
> - [[Series]]
> - [[Statement and Assumptions]]
> - [[Statement and Conclusions]]
> - [[Syllogisms]]
> - [[Verbal Analogies]]
> - [[Adjectives]]
> - [[Articles]]
> - [[Assembling]]
> - [[Bar Graph]]
