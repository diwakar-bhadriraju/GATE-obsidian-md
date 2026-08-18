---
title: "Cache Organization | Set 1 (Introduction)"
subject: "Computer Organization and Architecture"
topic: "Cache Memory"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/cache-organization-set-1-introduction/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Cache Memory"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/cache-memory
---


> [!abstract] Cache Organization | Set 1 (Introduction)
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Cache Memory`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/cache-organization-set-1-introduction/)

---

# Cache Organization | Set 1 (Introduction)

Cache is close to CPU and faster than main memory. But at the same time is smaller than main memory. The cache organization is about mapping data in memory to a location in cache. **A Simple Solution:** One way to go about this mapping is to consider last few bits of long memory address to find small cache address, and place them at the found address. **Problems With Simple Solution:** The problem with this approach is, we lose the information about high order bits and have no way to find out the lower order bits belong to which higher order bits. ![CacheOrg](assets/cache-55e113c7d1.jpg) **Solution is Tag:** To handle above problem, more information is stored in cache to tell which block of memory is stored in cache. We store additional information as **Tag** ![tags](assets/cache-tag-a70ea97908.jpg) **What is a Cache Block?** Since programs have Spatial Locality (Once a location is retrieved, it is highly probable that the nearby locations would be retrieved in near future). So a cache is organized in the form of blocks. Typical cache block sizes are 32 bytes or 64 bytes. ![cache-tag-3-copy](assets/cache-tag-3-copy-25b006d258.webp)
 **The above arrangement is Direct Mapped Cache and it has following problem** We have discussed above that last few bits of memory addresses are being used to address in cache and remaining bits are stored as tag. Now imagine that cache is very small and addresses of 2 bits. Suppose we use the last two bits of main memory address to decide the cache (as shown in below diagram). So if a program accesses 2, 6, 2, 6, 2, ..., every access would cause a hit as 2 and 6 have to be stored in same location in cache. ![blocks](assets/cache-problem-7e7d65d1bf.jpg) **Solution to above problem - Associativity** What if we could store data at any place in cache, the above problem won't be there? That would slow down cache, so we do something in between. ![cache](assets/cache-solution-47de7eb004.jpg) **Source:** [https://www.youtube.com/sg4CmZ-p8rU](https://www.youtube.com/)
We will soon be discussing more details of cache organization. This article is contributed **Ankur Gupta**.
### Advantages and downsides of different cache employer techniques:
#### Direct-Mapped Cache:
**Advantages:**
1. Simple and easy to put into effect
2. Low hardware overhead
3. Fast hit time
**Disadvantages:**
1. High pass over fee because of restrained wide variety of cache blocks
2. Increased war misses because of block collisions
3. Limited flexibility in phrases of block placement
### Set-Associative Cache:
**Advantages:**
1. Higher hit fee than direct-mapped cache because of more than one blocks being saved in each set
2. More bendy block placement than direct-mapped cache
3. Lower struggle misses as compared to direct-mapped cache
**Disadvantages:**
1. Higher hardware overhead than direct-mapped cache
2. Longer hit time than direct-mapped cache because of looking multiple blocks
3. Limited scalability due to fixed quantity of ways in step with set
### Fully-Associative Cache:
**Advantages:**
1. Highest hit rate amongst cache businesses
2. Most flexible block placement
3. No struggle misses because of fully-associative mapping
**Disadvantages:**
1. Highest hardware overhead among cache agencies
2. Longest hit time due to searching all blocks in cache
3. Limited scalability because of constrained physical area and huge tag storage necessities
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/cache-organization-set-1-introduction/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Cache Memory

> [!note] Related notes
>
> - [[2D and 2.5D Memory organization]]
> - [[Cache Memory]]
> - [[Different Types of RAM]]
> - [[Introduction to memory and memory units]]
> - [[Locality and Cache friendly code]]
> - [[Memory Hierarchy Design and its Characteristics]]
> - [[Memory Interleaving]]
> - [[RAM vs ROM]]
> - [[Read and Write operations in memory]]
> - [[Types of computer memory]]
