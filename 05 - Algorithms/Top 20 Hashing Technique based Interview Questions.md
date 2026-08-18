---
title: "Hashing Interview Questions"
subject: "Algorithms"
topic: "Misc"
source: "https://www.geeksforgeeks.org/dsa/top-20-hashing-technique-based-interview-questions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Algorithms/Misc"
tags:
  - gate/cs
  - subject/algorithms
  - topic/misc
---


> [!abstract] Hashing Interview Questions
> 
> **Subject:** `Algorithms` &nbsp;|&nbsp; **Topic:** `Misc`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/top-20-hashing-technique-based-interview-questions/)

---

# Hashing Interview Questions

Hashing interview questions are commonly asked to evaluate your understanding of hash tables, hashing techniques, collision handling, and efficient problem-solving. This collection covers the most important questions to help you prepare for coding and technical interviews.
- Covers the most frequently asked Hashing interview questions with concise answers.
- Suitable for both freshers and experienced professionals preparing for technical interviews.
Table of Content
- [Theoretical Questions for Interviews](#theoretical-questions-for-interviews-on-hashing)
- [Coding Interview Questions](#top-coding-interview-questions-on-hashing-1)
- [Easy Problems](#easy-problems)
- [Medium Problems](#medium-and-hard-problems)
- [Hard](#and-hard-problems)
## Theoretical Questions for Interviews
### 1. What is hashing?
[Hashing](https://www.geeksforgeeks.org/dsa/hashing-data-structure/) is a technique used to map data (keys) to a fixed-size value called a hash code using a hash function. The hash code is then used to determine the location where the data is stored, enabling fast lookup, insertion, and deletion operations.
- Uses a hash function to convert keys into hash values.
- Enables average O(1) time complexity for search, insertion, and deletion.
- Commonly used in hash tables, dictionaries, caches, and database indexing.
![Components-of-Hashing](assets/Components-of-Hashing-768-b3efdd7a6a.webp)
Hashing
### 2. What is a Hash Function?
A [hash function](https://www.geeksforgeeks.org/dsa/hash-functions-and-list-types-of-hash-functions/) is an algorithm that takes a key as input and computes a fixed-size value called a hash value or hash code. This hash value is used to determine where the key should be stored or searched in a hash table.
- Converts keys of any size into fixed-size hash values.
- Helps distribute keys across the hash table for efficient operations.
- An ideal hash function minimizes collisions and computes hash values quickly.
> For example, using the modulo method: H(x) = x % 10
![hashf](assets/hashf-6ea8de7de9.webp)
This function converts any large number into a value between 0 and 9, making it suitable for indexing in a hash table. Hashing enables efficient storage and fast retrieval of data.
### 3. What are the properties of a good hash function?
A [good hash function](https://www.geeksforgeeks.org/dsa/what-are-hash-functions-and-how-to-choose-a-good-hash-function/) distributes keys uniformly across the hash table, reducing collisions and ensuring efficient performance.
- **Uniform distribution:** A good hash function spreads values evenly across the hash table to avoid clustering.
- **Efficiency:** It should compute hash values quickly with minimal computational overhead.
- **Deterministic:** The same input should always produce the same hash value.
- **Minimizing collisions:** It should reduce the chances of different inputs mapping to the same hash value.
### 4. What is a hash table? How do you declare it?
A [hash table](https://www.geeksforgeeks.org/dsa/hash-table-data-structure/) is a data structure that stores key-value pairs and uses a hash function to determine where each key-value pair is stored for fast access.
- Stores data as key-value pairs.
- Supports average O(1) search, insertion, and deletion.
- Resolves collisions using techniques like separate chaining or open addressing.
- Can be declared using the language's built-in hash table implementation.
![chain-hashing-11](assets/chain-hashing-11-a3794c39ab.png)
### 5. What is the difference between a hash function and a hash table?
A hash function is an algorithm that computes a hash value from a key, whereas a hash table is a data structure that uses the hash function to store and retrieve key-value pairs efficiently.
| Feature | Hash Function | Hash Table |
| --- | --- | --- |
| Definition | Algorithm that computes a hash value. | Data structure that stores key-value pairs. |
| Purpose | Maps a key to an index. | Stores and retrieves data using hash values. |
| Input | A key or value. | Key-value pairs. |
| Output | A hash value (index). | Stored or retrieved data. |
| Dependency | Used by a hash table. | Relies on a hash function for indexing. |
### 6. What is a collision in hashing?
A collision occurs when two or more different keys produce the same hash value, causing them to map to the same index in a hash table.
- Inevitable because the number of possible keys is usually much larger than the number of table indices.
- Can reduce the performance of hash table operations if not handled properly.
- Common [collision resolution techniques](https://www.geeksforgeeks.org/dsa/collision-resolution-techniques/) include separate chaining and open addressing.
![collision-in-hashing](assets/collision-in-hashing-6926f84331.jpg)
collision in hashing
### 7. What are the different techniques for collision resolution?
[Collision resolution techniques](https://www.geeksforgeeks.org/dsa/collision-resolution-techniques/) are methods used to handle situations where multiple keys map to the same index in a hash table.
![Collision-Resolution-Techniques](assets/Collision-Resolution-Techniques-6bb6c3cc96.jpg)
collision resolution
**1. Separate Chaining:** Stores colliding keys in a linked list or another secondary structure at the same index.
**2. Open Addressing:** Resolves collisions by finding another empty slot within the hash table using probing techniques:
- **Linear Probing:** Checks the next available slot sequentially.
- **Quadratic Probing:** Checks slots using quadratic intervals to reduce clustering.
- **Double Hashing:** Uses a second hash function to determine the probing sequence.
### 8. What is the difference between separate chaining and open addressing?
Both [separate chaining](https://www.geeksforgeeks.org/dsa/separate-chaining-collision-handling-technique-in-hashing/) and [open addressing](https://www.geeksforgeeks.org/dsa/open-addressing-collision-handling-technique-in-hashing/) are collision resolution techniques, but they handle collisions differently.
| Feature | Separate Chaining | Open Addressing |
| --- | --- | --- |
| Storage | Stores colliding keys in a linked list or another secondary structure. | Stores all keys within the hash table itself. |
| Collision Handling | Multiple keys can exist at the same index. | Finds another empty slot using probing techniques. |
| Memory Usage | Requires extra memory for linked lists or secondary structures. | Does not require additional storage outside the table. |
| Performance | Performs well even at high load factors. | Performance degrades as the table becomes full. |
| Examples | Linked list, dynamic array at each bucket. | Linear probing, quadratic probing, double hashing. |
### 9. What is the time complexity of search, insertion, and deletion in a hash table?
The time complexity of hash table operations depends on the quality of the hash function, the load factor, and the collision resolution technique used.
| Operation | Average Case | Worst Case |
| --- | --- | --- |
| Search | **O(1)** | **O(n)** |
| Insertion | **O(1)** | **O(n)** |
| Deletion | **O(1)** | **O(n)** |
- The average case is O(1) when the hash function distributes keys uniformly.
- The worst case becomes O(n) when many keys collide and map to the same location.
- Maintaining a low load factor and using an efficient collision resolution technique helps preserve constant-time performance.
### 10. What is a load factor?
The [load factor](https://www.geeksforgeeks.org/dsa/load-factor-and-rehashing/) is the ratio of the number of stored elements to the total number of slots in a hash table. It indicates how full the hash table is.
> Load Factor = Number of Elements / Number of Slots
- A lower load factor generally results in fewer collisions and better performance.
- A higher load factor increases the likelihood of collisions and slower operations.
- When the load factor exceeds a certain threshold, the hash table is often resized and rehashed.
### 11. Why is rehashing required?
[Rehashing](https://www.geeksforgeeks.org/dsa/load-factor-and-rehashing/) is the process of creating a larger hash table and redistributing all existing elements into it using a new hash function or table size. It is performed to maintain efficient hash table operations.
- Reduces collisions by increasing the number of available slots.
- Improves the performance of search, insertion, and deletion operations.
- Usually triggered when the load factor exceeds a predefined threshold.
### 12. Why does chaining perform better than linear probing at high load factors?
Primary clustering and secondary clustering are collision-related problems that occur in open addressing hash tables.
- **Primary Clustering:** Consecutive occupied slots create long clusters, increasing probe lengths.
- Common in linear probing, where adjacent collisions accumulate into larger clusters.
- Secondary Clustering: Keys with the same initial hash value follow the same probing sequence.
- Common in quadratic probing and can be reduced using double hashing.
### 13. What is a perfect hash function?
A perfect hash function is a hash function that maps each key in a given set to a unique hash value, ensuring that no collisions occur.
- Produces a unique index for every key in the given dataset.
- Eliminates collisions, resulting in faster lookups.
- Best suited for static datasets where the set of keys does not change frequently.
### 14. What is cuckoo hashing?
[Cuckoo hashing](https://www.geeksforgeeks.org/dsa/cuckoo-hashing/) is a collision resolution technique that stores each key in one of two possible locations determined by two different hash functions.
- Uses two hash functions to provide two candidate positions for each key.
- If both positions are occupied, an existing key is displaced and relocated to its alternate position.
- Provides O(1) average-case lookup by ensuring each key can exist in only one of two locations.
### 15. What is a Bloom filter?
A [Bloom filter](https://www.geeksforgeeks.org/python/bloom-filters-introduction-and-python-implementation/) is a space-efficient probabilistic data structure used to test whether an element is a member of a set.
- Uses multiple hash functions to map elements to a bit array.
- Can quickly determine if an element is possibly present or definitely not present.
- May produce false positives, but never false negatives.
### 16. What is the difference between hashing and a self-balancing BST?
Hashing and self-balancing binary search trees (BSTs) are both used for efficient data storage and retrieval, but they differ in how they organize and access data.
| Feature | Hashing | Self-Balancing BST |
| --- | --- | --- |
| Data Organization | Uses a hash function to map keys to indices. | Stores keys in a sorted tree structure. |
| Search Time | O(1) average, O(n) worst case. | O(log n) for search, insertion, and deletion. |
| Data Ordering | Does not maintain sorted order. | Maintains elements in sorted order. |
| Range Queries | Not efficient. | Efficient due to ordered structure. |
| Examples | Hash Table, unordered\_map | AVL Tree, Red-Black Tree |
### 17. What are the different types of hash functions?
Hash functions use [different techniques](https://www.geeksforgeeks.org/dsa/hash-functions-and-list-types-of-hash-functions/) to convert keys into hash values. The choice of hash function affects the distribution of keys and the number of collisions.
- **Division Method:** Computes the hash value using the remainder of division by the table size.
- **Multiplication Method:** Multiplies the key by a constant and extracts a portion of the result.
- **Mid-Square Method:** Squares the key and uses the middle digits as the hash value.
- **Folding Method:** Splits the key into parts and combines them to produce the hash value.
- **Universal Hashing:** Randomly selects a hash function from a family of functions to reduce collisions.
### 18. What are the applications of hashing?
Hashing is widely used in [applications](https://www.geeksforgeeks.org/dsa/applications-advantages-and-disadvantages-of-hash-data-structure/) that require fast storage, retrieval, and lookup of data.
- **Databases:** Enables fast indexing and record retrieval.
- **Hash Tables:** Supports efficient search, insertion, and deletion operations.
- **Caching:** Quickly stores and retrieves frequently accessed data.
- **Password Storage:** Stores hashed passwords for secure authentication.
- **Data Integrity:** Generates checksums and fingerprints to detect data modifications.
- **Compilers:** Implements symbol tables for efficient identifier lookup.
### 19. What is the difference between linear probing, quadratic probing, and double hashing?
These are open addressing techniques used to resolve collisions in a hash table.
| Technique | Probe Sequence | Advantage | Limitation |
| --- | --- | --- | --- |
| Linear Probing | Checks the next slot sequentially. | Simple and cache-friendly. | Suffers from primary clustering. |
| Quadratic Probing | Uses quadratic intervals to find the next slot. | Reduces primary clustering. | Can still suffer from secondary clustering. |
| Double Hashing | Uses a second hash function to determine the step size. | Minimizes clustering and distributes keys more uniformly. | More computationally expensive due to the second hash function. |
- [Linear probing](https://www.geeksforgeeks.org/dsa/implementing-hash-table-open-addressing-linear-probing-cpp/) is the simplest approach but is more prone to clustering.
- [Double hashing](https://) generally provides the best key distribution among the three techniques.
### 20. What are the advantages and disadvantages of hashing?
[Hashing](https://www.geeksforgeeks.org/dsa/applications-advantages-and-disadvantages-of-hash-data-structure/) is widely used for fast data retrieval, but its performance depends on the quality of the hash function and collision handling.
**Advantages**
- Provides O(1) average-case time complexity for search, insertion, and deletion.
- Efficient for implementing dictionaries, sets, and symbol tables.
- Simple to use for key-based data retrieval.
- Scales well for large datasets with a good hash function.
**Disadvantages**
- Performance can degrade to O(n) in the worst case due to collisions.
- Does not maintain elements in sorted order.
- Range queries and ordered traversals are inefficient.
- May require rehashing, which can be expensive for large tables.
## Coding Interview Questions
The following list of 20 coding problems on Hashing that covers a range of difficulty levels, from easy to hard, to help candidates prepare for interviews.
### Easy Problems
- [Subset Check](https://www.geeksforgeeks.org/dsa/find-whether-an-array-is-subset-of-another-array-set-1/)
- [Union and Intersection of two Linked Lists](https://www.geeksforgeeks.org/dsa/union-and-intersection-of-two-linked-lists/)
- [A pair with given sum](https://www.geeksforgeeks.org/dsa/check-if-pair-with-given-sum-exists-in-array/)
- [Two pair sum](https://www.geeksforgeeks.org/dsa/find-four-elements-a-b-c-and-d-in-an-array-such-that-ab-cd/)
- [Missing elements of a range](https://www.geeksforgeeks.org/dsa/find-missing-elements-of-a-range/)
- [Symmetric Pairs](https://www.geeksforgeeks.org/dsa/given-an-array-of-pairs-find-all-symmetric-pairs-in-it/)
- [Duplicates within k distance](https://www.geeksforgeeks.org/dsa/check-given-array-contains-duplicate-elements-within-k-distance/)
### Medium Problems
- [Largest subarray with 0 sum](https://www.geeksforgeeks.org/dsa/find-the-largest-subarray-with-0-sum/)
- [Distinct elements in K-size Window](https://www.geeksforgeeks.org/dsa/count-distinct-elements-in-every-window-of-size-k/)
- [All subarrays with 0 sum](https://www.geeksforgeeks.org/dsa/print-all-subarrays-with-0-sum/)
- [Largest subarray with equal number of 0s and 1s](https://www.geeksforgeeks.org/dsa/largest-subarray-with-equal-number-of-0s-and-1s/)
- [Count Subarrays with XOR](https://www.geeksforgeeks.org/dsa/count-number-subarrays-given-xor/)
- [Longest Consecutive Subsequence](https://www.geeksforgeeks.org/dsa/longest-consecutive-subsequence/)
- [Pair Sum Divisible by K](https://www.geeksforgeeks.org/dsa/check-if-an-array-can-be-divided-into-pairs-whose-sum-is-divisible-by-k/)
- [Separate Chaining for Collision Handling](https://www.geeksforgeeks.org/dsa/separate-chaining-collision-handling-technique-in-hashing/)
- [Open Addressing for Collision Handling](https://www.geeksforgeeks.org/dsa/open-addressing-collision-handling-technique-in-hashing/)
### Hard
- [Find Itinerary from a given list of tickets](https://www.geeksforgeeks.org/dsa/find-itinerary-from-a-given-list-of-tickets/)
- [Palindrome Substring Queries](https://www.geeksforgeeks.org/dsa/palindrome-substring-queries/)
- [Smallest Range from K Lists](https://www.geeksforgeeks.org/dsa/find-smallest-range-containing-elements-from-k-lists/)
- [Internal Working of HashMap in Java](https://www.geeksforgeeks.org/java/internal-working-of-hashmap-java/)
- [Hash Table with Chaining in Java](https://www.geeksforgeeks.org/java/implementing-our-own-hash-table-with-separate-chaining-in-java/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/top-20-hashing-technique-based-interview-questions/)

## GATE CS

- Subject: Algorithms
- Topic: Misc

> [!note] Related notes
>
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[GATE PYQs of CN]]
> - [[Last Minute Notes – Algorithms]]
> - [[Last Minute Notes – C C++]]
> - [[Last Minute Notes – DATA STRUCTURE]]
> - [[Last Minute Notes – DBMS]]
> - [[Last Minute Notes – Engineering Mathematics]]
> - [[Last Minute Notes – Theory of Computation]]
> - [[Applications of Depth First Search]]
> - [[Asymptotic Notations]]
