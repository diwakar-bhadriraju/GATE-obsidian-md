---
title: "Hashing Notes for GATE Exam [2024]"
subject: "Data Structures & C Programming"
topic: "Hashing"
source: "https://www.geeksforgeeks.org/dsa/hashing-notes-for-gate-exam/#introduction-to-hashing"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Hashing"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/hashing
---


> [!abstract] Hashing Notes for GATE Exam [2024]
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Hashing`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/hashing-notes-for-gate-exam/#introduction-to-hashing)

---

# Hashing Notes for GATE Exam [2024]

Hashing is a fundamental concept in computer science and plays a pivotal role in various algorithms and data structures. Aspiring candidates preparing for the GATE Exam 2024 must grasp the intricacies of hashing to tackle complex problem-solving scenarios efficiently. These notes aim to provide a concise yet comprehensive overview of hashing, covering essential concepts that are likely to be tested in the GATE examination.
Table of Content
- [Introduction to Hashing](#introduction-to-hashing)
- [Need for Hash data structure](#need-for-hash-data-structure)
- [Components of Hashing](#components-of-hashing)
- [How does Hashing work?](#how-does-hashing-work)
- [What is a Hash function?](#what-is-a-hash-function)
- [Problem with Hashing](#problem-with-hashing)
- [What is collision?](#what-is-collision)
- [How to handle Collisions?](#how-to-handle-collisions)
- [Separate Chaining](#separate-chaining)
- [Open Addressing](#open-addressing)
- [What is meant by Load Factor in Hashing?](#what-is-meant-by-load-factor-in-hashing)
- [What is Rehashing?](#what-is-rehashing)
- [Applications of Hash Data structure](#applications-of-hash-data-structure)
- [Real-Time Applications of Hash Data structure](#realtime-applications-of-hash-data-structure)
- [Advantages of Hash Data structure](#advantages-of-hash-data-structure)
- [Disadvantages of Hash Data structure](#disadvantages-of-hash-data-structure)
- [MCQ of Hashing](#mcq-of-hashing)
## Introduction to Hashing
> **Hashing** **refers to the process of generating a fixed-size output from an input of variable size using the mathematical formulas known as hash functions. This technique determines an index or location for the storage of an item in a data structure.**
## Need for Hash data structure
> Every day, the data on the internet is increasing multifold and it is always a struggle to store this data efficiently. In day-to-day programming, this amount of data might not be that big, but still, it needs to be stored, accessed, and processed easily and efficiently. A very common data structure that is used for such a purpose is the Array data structure.
>
> Now the question arises if Array was already there, what was the need for a new data structure! The answer to this is in the word “**efficiency**“. Though storing in Array takes O(1) time, searching in it takes at least **O(log n)** time. This time appears to be small, but for a large data set, it can cause a lot of problems and this, in turn, makes the Array data structure inefficient. 
So now we are looking for a data structure that can store the data and search in it in constant time, i.e. in O(1) time. This is how Hashing data structure came into play. With the introduction of the Hash data structure, it is now possible to easily store data in constant time and retrieve them in constant time as well.
## Components of Hashing
There are majorly three components of hashing:
1. **Key**:** A **Key** can be anything string or integer which is fed as input in the hash function the technique that determines an index or location for storage of an item in a data structure.
2. **Hash Function**:**The **hash function** receives the input key and returns the index of an element in an array called a hash table. The index is known as the**hash index**.
3. **Hash Table**:**Hash table is a data structure that maps keys to values using a special function called a hash function. Hash stores the data in an associative manner in an array where each data value has its own unique index.
![](assets/ComponentsofHashing-660x342-95924c2e82.png)
## How does Hashing work?
Suppose we have a set of strings {“ab”, “cd”, “efg”} and we would like to store it in a table. 
Our main objective here is to search or update the values stored in the table quickly in O(1) time and we are not concerned about the ordering of strings in the table. So the given set of strings can act as a key and the string itself will act as the value of the string but how to store the value corresponding to the key? 
- **Step 1:** We know that hash functions (which is some mathematical formula) are used to calculate the hash value which acts as the index of the data structure where the value will be stored.
- **Step 2:** So, let’s assign 
  - “a” = 1,
  - “b”=2, .. etc, to all alphabetical characters.
- **Step 3:**Therefore, the numerical value by summation of all characters of the string:
> - “ab” = 1 + 2 = 3,
> - “cd” = 3 + 4 = 7 ,
> - “efg” = 5 + 6 + 7 = 18
- **Step 4:**Now, assume that we have a table of size 7 to store these strings. The hash function that is used here is the sum of the characters in **key mod Table size**. We can compute the location of the string in the array by taking the **sum(string) mod 7**.
- **Step 5:** So we will then store 
  - “ab” in 3 mod 7 = 3,
  - “cd” in 7 mod 7 = 0, and
  - “efg” in 18 mod 7 = 4.
![](assets/Example-81b63ceb33.png)
The above technique enables us to calculate the location of a given string by using a simple hash function and rapidly find the value that is stored in that location. Therefore the idea of hashing seems like a great way to store (key, value) pairs of the data in a table.
## What is a Hash function?
> The [hash function](https://www.geeksforgeeks.org/dsa/hash-functions-and-list-types-of-hash-functions/) creates a mapping between key and value, this is done through the use of mathematical formulas known as hash functions. The result of the hash function is referred to as a hash value or hash. The hash value is a representation of the original string of characters but usually smaller than the original.
>
> For example: Consider an array as a Map where the key is the index and the value is the value at that index. So for an array A if we have index **i** which will be treated as the key then we can find the value by simply looking at the value at A[i].
> simply looking up A[i]. 
### Types of Hash functions:
There are many hash functions that use numeric or alphanumeric keys. This article focuses on discussing [different hash functions](https://www.geeksforgeeks.org/dsa/hash-functions-and-list-types-of-hash-functions/):
1. [Division Method.](https://www.geeksforgeeks.org/dsa/hash-functions-and-list-types-of-hash-functions/#:~:text=1.%20Division%20Method,the%20remainder%20obtained.)
2. [Mid Square Method.](https://www.geeksforgeeks.org/dsa/introduction-to-hashing-2/)
3. [Folding Method.](https://www.geeksforgeeks.org/dsa/hash-functions-and-list-types-of-hash-functions/#:~:text=3.%20Digit%20Folding,carry%20if%20any.)
4. [Multiplication Method](https://www.geeksforgeeks.org/dsa/hash-functions-and-list-types-of-hash-functions/)
### Properties of a Good hash function
A hash function that maps every item into its own unique slot is known as a perfect hash function. We can construct a perfect hash function if we know the items and the collection will never change but the problem is that there is no systematic way to construct a perfect hash function given an arbitrary collection of items. Fortunately, we will still gain performance efficiency even if the hash function isn’t perfect. We can achieve a perfect hash function by increasing the size of the hash table so that every possible value can be accommodated. As a result, each item will have a unique slot. Although this approach is feasible for a small number of items, it is not practical when the number of possibilities is large.
So, We can construct our hash function to do the same but the things that we must be careful about while constructing our own hash function.
A good hash function should have the following properties:
1. Efficiently computable.
2. Should uniformly distribute the keys (Each table position is equally likely for each.
3. Should minimize collisions.
4. Should have a low load factor(number of items in the table divided by the size of the table).
### Complexity of calculating hash value using the hash function
- Time complexity: O(n)
- Space complexity: O(1)
## Problem with Hashing
If we consider the above example, the hash function we used is the sum of the letters, but if we examined the hash function closely then the problem can be easily visualized that for different strings same hash value is begin generated by the hash function. 
For example: {“ab”, “ba”} both have the same hash value, and string {“cd”,”be”} also generate the same hash value, etc. This is known as **collision** and it creates problem in searching, insertion, deletion, and updating of value. 
## What is collision?
The hashing process generates a small number for a big key, so there is a possibility that two keys could produce the same value. The situation where the newly inserted key maps to an already occupied, and it must be handled using some collision handling technology.
![](assets/Collision-in-Hashing-257da714d5.png)
## How to handle Collisions?
There are mainly two methods to handle collision: 
1. Separate Chaining
2. Open Addressing
![](assets/Collisionresolutiontechnique-d170cc46f1.png)
## [Separate Chaining](https://www.geeksforgeeks.org/dsa/separate-chaining-collision-handling-technique-in-hashing/)
The idea is to make each cell of the hash table point to a linked list of records that have the same hash function value. Chaining is simple but requires additional memory outside the table.
Example: We have given a hash function and we have to insert some elements in the hash table using a separate chaining method for collision resolution technique.
```
Hash function = key % 5, Elements = 12, 15, 22, 25 and 37.
```
Let’s see step by step approach to how to solve the above problem:
- **Step 1:**First draw the empty hash table which will have a possible range of hash values from 0 to 4 according to the hash function provided.
![](assets/step15-62bc4325c4.png)
- **Step 2:** Now insert all the keys in the hash table one by one. The first key to be inserted is 12 which is mapped to bucket number 2 which is calculated by using the hash function 12%5=2.
![](assets/step1-dbc496de2c.png)
- **Step 3:** Now the next key is 22. It will map to bucket number 2 because 22%5=2. But bucket 2 is already occupied by key 12.
![](assets/step2-39027db4e8.png)
- **Step 4:** The next key is 15. It will map to slot number 0 because 15%5=0.
![](assets/step3-bc348095e4.png)
- **Step 5:** Now the next key is 25. Its bucket number will be 25%5=0. But bucket 0 is already occupied by key 25. So separate chaining method will again handle the collision by creating a linked list to bucket 0.
![](assets/step4-3da41c36b1.png)
Hence In this way, the separate chaining method is used as the collision resolution technique.
## [Open Addressing](https://www.geeksforgeeks.org/dsa/open-addressing-collision-handling-technique-in-hashing/)
In open addressing, all elements are stored in the hash table itself. Each table entry contains either a record or NIL. When searching for an element, we examine the table slots one by one until the desired element is found or it is clear that the element is not in the table.
### Linear Probing:
In linear probing, the hash table is searched sequentially that starts from the original location of the hash. If in case the location that we get is already occupied, then we check for the next location. 
**Algorithm:**
> 1. Calculate the hash key. i.e. **key = data % size**
> 2. Check, if **hashTable[key]** is empty
>    - store the value directly by **hashTable[key] = data**
> 3. If the hash index already has some value then
>    1. check for next index using **key = (key+1) % size**
> 4. Check, if the next index is available hashTable[key] then store the value. Otherwise try for next index.
> 5. Do the above process till we find the space.
**Example:** Let us consider a simple hash function as “key mod 5” and a sequence of keys that are to be inserted are 50, 70, 76, 85, 93. 
- **Step 1:**First draw the empty hash table which will have a possible range of hash values from 0 to 4 according to the hash function provided.
![](assets/step14-1a72e7034a.png)
- **Step 2:** Now insert all the keys in the hash table one by one. The first key is 50. It will map to slot number 0 because 50%5=0. So insert it into slot number 0.
![](assets/step21-79a5466f9c.png)
- **Step 3:**The next key is 70. It will map to slot number 0 because 70%5=0 but 50 is already at slot number 0 so, search for the next empty slot and insert it.
![](assets/step31-0715439ada.png)
- **Step 4:**The next key is 76. It will map to slot number 1 because 76%5=1 but 70 is already at slot number 1 so, search for the next empty slot and insert it.
![](assets/step41-6a5ef9e70c.png)
- **Step 5:**The next key is 93 It will map to slot number 3 because 93%5=3, So insert it into slot number 3.
![](assets/step51-89a4c84675.png)
### Quadratic Probing:
Quadratic probing is an open addressing scheme in computer programming for resolving hash collisions in hash tables. Quadratic probing operates by taking the original hash index and adding successive values of an arbitrary quadratic polynomial until an open slot is found.
An example sequence using quadratic probing is:
> **H** + 12, **H** + 22, **H** + 32, **H** + 42…………………. **H** + k2
This method is also known as the mid-square method because in this method we look for i2‘th probe (slot) in i’th iteration and the value of i = 0, 1, . . . n – 1. We always start from the original hash location. If only the location is occupied then we check the other slots.
Let hash(x) be the slot index computed using the hash function and n be the size of the hash table.
> If the slot hash(x) % n is full, then we try (hash(x) + 12) % n.
> If (hash(x) + 12) % n is also full, then we try (hash(x) + 22) % n.
> If (hash(x) + 22) % n is also full, then we try (hash(x) + 32) % n.
> This process will be repeated for all the values of **i** until an empty slot is found
Example: Let us consider table Size = 7, hash function as Hash(x) = x % 7 and collision resolution strategy to be f(i) = i2. Insert = 22, 30, and 50
- **Step 1:** Create a table of size 7.
![](assets/step1-cd9a198be8.png)
- **Step 2** – Insert 22 and 30
  - Hash(22) = 22 % 7 = 1, Since the cell at index 1 is empty, we can easily insert 22 at slot 1.
  - Hash(30) = 30 % 7 = 2, Since the cell at index 2 is empty, we can easily insert 30 at slot 2.
![](assets/step3-142fd2d43d.png)
- **Step 3:** Inserting 50
  - Hash(50) = 50 % 7 = 1
  - In our hash table slot 1 is already occupied. So, we will search for slot 1+12, i.e. 1+1 = 2,
  - Again slot 2 is found occupied, so we will search for cell 1+22, i.e.1+4 = 5,
  - Now, cell 5 is not occupied so we will place 50 in slot 5.
![](assets/step4-16955b103e.png)
### Double Hashing:
Double hashing is a collision resolving technique in [Open Addressed](https://www.geeksforgeeks.org/dsa/open-addressing-collision-handling-technique-in-hashing/) Hash tables. Double hashing make use of two hash function, 
- The first hash function is **h1(k)** which takes the key and gives out a location on the hash table. But if the new location is not occupied or empty then we can easily place our key.
- But in case the location is occupied (collision) we will use secondary hash-function **h2(k)** in combination with the first hash-function **h1(k)** to find the new location on the hash table.
This combination of hash functions is of the form 
```
h(k, i) = (h1(k) + i * h2(k)) % n
```
where 
- i is a non-negative integer that indicates a collision number,
- k = element/key which is being hashed
- n = hash table size.
**Complexity of the Double hashing algorithm:**
```
Time complexity: O(n)
```
**Example:**Insert the keys 27, 43, 692, 72 into the Hash Table of size 7. where first hash-function is**h1​(k) = k mod 7** and second hash-function is **h2(k) = 1 + (k mod 5)**
- **Step 1:**Insert 27
  - 27 % 7 = 6, location 6 is empty so insert 27 into 6 slot.
![](assets/step2-cd9a84d558.png)
- **Step 2:** Insert 43
  - 43 % 7 = 1, location 1 is empty so insert 43 into 1 slot.
![](assets/step2-7d61270de5.png)
- **Step 3:** Insert 692
  - 692 % 7 = 6, but location 6 is already being occupied and this is a collision
  - So we need to resolve this collision using double hashing.
```
hnew = [h1(692) + i * (h2(692)] % 7= [6 + 1 * (1 + 692 % 5)] % 7= 9 % 7= 2Now, as 2 is an empty slot, so we can insert 692 into 2nd slot.
```
![](assets/step3-10a9177978.png)
- **Step 4:** Insert 72
  - 72 % 7 = 2, but location 2 is already being occupied and this is a collision.
  - So we need to resolve this collision using double hashing.
```
hnew = [h1(72) + i * (h2(72)] % 7= [2 + 1 * (1 + 72 % 5)] % 7= 5 % 7= 5, Now, as 5 is an empty slot, so we can insert 72 into 5th slot.
```
![](assets/step4-f6c25d7896.png)
## What is meant by Load Factor in Hashing?
> The [load factor](https://www.geeksforgeeks.org/dsa/load-factor-and-rehashing/) of the hash table can be defined as the number of items the hash table contains divided by the size of the hash table. Load factor is the decisive parameter that is used when we want to rehash the previous hash function or want to add more elements to the existing hash table.
>
> It helps us in determining the efficiency of the hash function i.e. it tells whether the hash function which we are using is distributing the keys uniformly or not in the hash table.
>
> **Load Factor = Total elements in hash table/ Size of hash table**
## What is Rehashing?
> As the name suggests, [rehashing](https://www.geeksforgeeks.org/dsa/load-factor-and-rehashing/#:~:text=Rehashing%3A,and%20low%20complexity.) means hashing again. Basically, when the load factor increases to more than its predefined value (the default value of the load factor is 0.75), the complexity increases. So to overcome this, the size of the array is increased (doubled) and all the values are hashed again and stored in the new double-sized array to maintain a low load factor and low complexity.
## Applications of Hash Data structure
- Hash is used in databases for indexing.
- Hash is used in disk-based data structures.
- In some programming languages like Python, JavaScript hash is used to implement objects.
## Real-Time Applications of Hash Data structure
- Hash is used for cache mapping for fast access to the data.
- Hash can be used for password verification.
- Hash is used in cryptography as a message digest.
- Rabin-Karp algorithm for pattern matching in a string.
- Calculating the number of different substrings of a string.
## Advantages of Hash Data structure
- Hash provides better synchronization than other data structures.
- Hash tables are more efficient than search trees or other data structures
- Hash provides constant time for searching, insertion, and deletion operations on average.
## Disadvantages of Hash Data structure
- Hash is inefficient when there are many collisions.
- Hash collisions are practically not avoided for a large set of possible keys.
- Hash does not allow null values.
## MCQ of Hashing
> **Question 1:** What is the probability of a collision when hashing n keys into a hash table of size m, assuming that the hash function produces a uniform random distribution?
>
> **(A)** O(1/n)
> **(B)** O(n/m)
> **(C)** O(log n)
> **(D)** O(m/n)
>
> **Correct Answer: (C)**
> **Explanation:** The probability of a collision occurring is dependent on the number of items hashed (n) and the size of the hash table (m). As the number of items increases, the probability of a collision also increases. However, as the size of the hash table increases, the probability decreases. Therefore, the probability of a collision can be estimated as O(n/m).
> **Question 2:** How many different insertion sequences of the key values using the hash function **h(k) = k mod 10** and linear probing will result in the hash table shown below? 
>
> ![](assets/gate2010_1-f41cffa553.gif)
>
> **(A)** 10
> **(B)** 20
> **(C)** 30
> **(D)** 40
>
> **Correct Answer: (C)**
> **Explanation:** In a valid insertion sequence, the elements 42, 23 and 34 must appear before 52 and 33, and 46 must appear before 33. 
> Total number of different sequences = 3! x 5 = 30 
> In the above expression, 3! is for elements 42, 23 and 34 as they can appear in any order, and 5 is for element 46 as it can appear at 5 different places.
> **Question 3:** Consider a hash table with 100 slots. Collisions are resolved using chaining. Assuming simple uniform hashing, what is the probability that the first 3 slots are unfilled after the first 3 insertions?
>
> **(A)** (97 × 97 × 97)/1003
> **(B)** (99 × 98 × 97)/1003
> **(C) (**97 × 96 × 95)/1003
> **(D)** (97 × 96 × 95)/(3! × 1003)
>
> **Correct Answer: (A)**
> **Explanation:** Simple Uniform hashing function is a hypothetical hashing function that evenly distributes items into the slots of a hash table. Moreover, each item to be hashed has an equal probability of being placed into a slot, regardless of the other elements already placed. 
>
> ```
Probability that the first 3 slots are unfilled after the first 3 insertions =                 (probability that first item doesn't go in any of the first 3 slots)*                (probability that second item doesn't go in any of the first 3 slots)*                (probability that third item doesn't go in any of the first 3 slots)                 = (97/100) * (97/100) * (97/100)
```
> **Question 4:** Which one of the following hash functions on integers will distribute keys most uniformly over 10 buckets numbered 0 to 9 for i ranging from 0 to 2020?
>
> **(A)** h(i) = (12 ∗ i) mod 10
> **(B)** h(i) = (11 ∗ i2) mod 10
> **(C)** h(i) =i3 mod 10
> **(D)** h(i) =i2 mod 10
>
> **Correct Answer: (C)**
> **Explanation:** Using the concept of power of cycle: 
>
> (a) (0,1,4,9,6,5,6,9,4,1,0) repeated 
> (b) (0,1,8,7,4,5,6,3,2,9) repeated 
> (c) (0,1,4,9,6,5,6,9,4,1,0) repeated 
> (d) (0,2,4,6,8) repeated 
>
> So, only h(i) =i3 mod 10 covers all the digits from 0 to 9. 
> Hence Option **(C)** is correct.
> **Question 5:** Given a hash table T with 25 slots that stores 2000 elements, the load factor α for T is \_\_\_\_\_\_\_\_\_\_
>
> **(A)** 80
> **(B)** 0.0125
> **(C)** 8000
> **(D)** 1.25
>
> **Correct Answer: (A)**
> **Explanation:** load factor = (no. of elements) / (no. of table slots) = 2000/25 = 80.
> **Question 6:** Which of the following statement(s) is TRUE?
>
> 1. A hash function takes a message of arbitrary length and generates a fixed length code.
> 2. A hash function takes a message of fixed length and generates a code of variable length.
> 3. A hash function may give the same hash value for distinct messages.
>
> **(A)** 1 Only
> **(B)** 2 and 3 Only
> **(C)** 1 and 3 Only
> **(D)** 2 Only
>
> **Correct Answer: (C)**
> **Explanation:** Hash function is defined as any function that can be used to map data of arbitrary size of data to a fixed size data.. The values returned by a hash function are called hash values, hash codes, digests, or simply hashes  :  Statement 1 is correct Yes, it is possible that a Hash Function maps a value to a same location in the memory that's why collision occurs and we have different technique to handle  this problem : Statement 3 is correct. eg : we have hash function, h(x) = x mod 3 Acc to Statement 1, no matter what the value of 'x' is h(x) results in a fixed mapping location. Acc. to Statement 3, h(x) can result in same mapping mapping location for different value of 'x' e.g. if x = 4 or x = 7 , h(x) = 1 in both the cases, although collision occurs.   
> **Question 7:** Consider a hash function that distributes keys uniformly. The hash table size is 20. After hashing of how many keys will the probability that any new key hashed collides with an existing one exceed 0.5.
>
> **(A)** 5
> **(B)** 6
> **(C)** 7
> **(D)** 10
>
> **Correct Answer: (D)**
> **Explanation:** For each entry probability of collision is 1/20 {as possible total spaces =20, and an entry will go into only 1 place}
> Say after inserting x values probability becomes 1/2
> => (1/20).x = 1/2
> => X=10
> **Question 8:** Suppose we are given n keys, m has table slots, and two simple uniform hash functions h1 and h2. Further suppose our hashing scheme uses h1 for the odd keys and h2 for the even keys. What is the expected number of keys in a slot?
>
> **(A)** m/n
> **(B)** n/m
> **(C)** 2n/m
> **(D)** n/2m
>
> **Correct Answer: (B)**
> **Question 9:** Consider a hash table with 9 slots. The hash function is h(k) = k mod 9. The collisions are resolved by chaining. The following 9 keys are inserted in the order: 5, 28, 19, 15, 20, 33, 12, 17, 10. The maximum, minimum, and average chain lengths in the hash table, respectively, are
>
> **(A)** 3, 0 and 1
> **(B)** 3, 3 and 3
> **(C)** 4, 0 and 1
> **(D)** 3, 0 and 2
>
> **Correct Answer: (A)**
> **Question 10:** Consider a hash table of size 11 that uses open addressing with linear probing. Let h(k) = k mod 11 be the hash function used. A sequence of records with keys
> 43 36 92 87 11 4 71 13 14 is inserted into an initially empty hash table, the bins of which are indexed from zero to ten. What is the index of the bin into which the last record is inserted?
>
> **(A)** 2
> **(B)** 4
> **(C)** 6
> **(D)** 7
>
> **Correct Answer: (D)**
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/hashing-notes-for-gate-exam/#introduction-to-hashing)

## GATE CS

- Subject: Data Structures & C Programming
- Topic: Hashing

> [!note] Related notes
>
> - [[Double Hashing]]
> - [[Quadratic Probing]]
> - [[1D, 2D and 3D Arrays]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Data Types in C]]
> - [[Enum, Struct & Union in C]]
> - [[Functions in C]]
> - [[I ntroduction to Trees]]
> - [[Introduction to Arrays]]
> - [[Introduction to C Programming]]
