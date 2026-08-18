---
title: "Computer Organization | Locality and Cache friendly code"
subject: "Computer Organization and Architecture"
topic: "Cache Memory"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-locality-and-cache-friendly-code/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Cache Memory"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/cache-memory
---


> [!abstract] Computer Organization | Locality and Cache friendly code
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Cache Memory`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-locality-and-cache-friendly-code/)

---

# Computer Organization | Locality and Cache friendly code

[Caches](https://www.geeksforgeeks.org/computer-science-fundamentals/cache-memory/) are the faster memories that are built to deal with the Processor-Memory gap in data read operation, i.e. the time difference in a data read operation in a CPU register and that in the main memory. Data read operation in registers is generally 100 times faster than in the main memory and it keeps on increasing substantially, as we go down in the memory hierarchy. 
Caches are installed in the middle of CPU registers and the main memory to bridge this time gap in data reading. Caches serve as temporary staging area for a subset of data and instructions stored in relatively slow main memory. Since the size of cache is small, only the data which is frequently used by the processor during the execution of a program is stored in cache. Caching of this frequently used data by CPU eliminates the need of bringing the data from the slower main memory again and again which takes hundreds of CPU cycles. 
The idea of caching the useful data centers around a fundamental property of computer programs known as **locality**. Programs with good locality tend to access the same set of data items over and over again from the upper levels of the memory hierarchy (i.e. cache) and thus run faster. 
**Example:** The run time of different matrix multiplication kernels that perform the same number of arithmetic operations, but have different degrees of locality, can vary by a factor of 20! 
**Types of Locality:** 
- **Temporal locality -** 
  Temporal locality states that the same data objects are likely to be reused multiple times by the CPU during the execution of a program. Once a data object has been written into the cache on the first miss, a number of subsequent hits on that object can be expected. Since the cache is faster than the storage at the next lower level like the main memory, these subsequent hits can be served much faster than the original miss.
- **Spatial locality -** 
  It states that if a data object is referenced once, then there is a high probability that it's neighbor data objects will also be referenced in near future. Memory blocks usually contain multiple data objects. Because of spatial locality, we can expect that the cost of copying a block after a miss will be amortized by subsequent references to other objects within that block.
**Importance of Locality -** 
Locality in programs has an enormous impact on the design and performance of hardware and software systems. In modern computing systems, the locality based advantages are not only confined to the architecture but also, operating systems and application programs are built in a manner that they can exploit the locality to the full extent. 
In operating systems, the principle of locality allows the system to use main memory as a cache of the most recently referenced chunk of virtual address space and also in case of recently used disk blocks in disk file systems. 
Similarly, Application programs like web browsers exploit temporal locality by caching recently referenced documents on a local disk. High-volume web servers hold recently requested documents in the front end disk cache that satisfy requests for these documents without any intervention of server. 
**Cache Friendly Code -** 
Programs with good locality generally run faster as they have lower cache miss rate in comparison with the ones with bad locality. In a good programming practice, cache performance is always counted as one of the important factor when it comes to the analysis of the performance of a program. The basic approach on how a code can be cache friendly is: 
- **Frequently used cases need to be faster:** Programs often invest most of the time in a few core functions and these functions in return have most to do with the loops. So, these loops should be designed in a way that they possess a good locality.
- **Multiple loops:** If a program constitutes of multiple loops then minimize the cache misses in the inner loop to alleviate the performance of the code.
**Example-1:** The above context can be understood by following the simple examples of multi-dimensional array code. Consider the sum\_array() function which sums the elements of a two dimension array in row-major order: 
```
int sumarrayrows(int a[8][4])
{
 int i, j, sum = 0;
 for (i = 0; i < 8; i++)
    for (j = 0; j < 4; j++)
     sum += a[i][j];
 return sum;
}
```
Assuming, the cache has a block size of 4 words each, word size being 4 bytes. It is initially empty and since, C stores arrays in row-major order so the references will result in the following pattern of hits and misses, independent of cache organization. 
![](assets/cache1-1-f2e2dd4323.png)
The block which contains w[0]–w[3] is loaded into the cache from memory and reference to w[0] is a miss but the next three references are all hits. The reference to v[4] causes another miss as a new block is loaded into the cache, the next three references are hits, and so on. In general, three out of four references will hit, which is the best that can be done with a cold cache. Thus, the hit ratio is 3/4\*100 = 75% 
**Example-2:** Now, the sum\_array() function sums the elements of a two dimension array in column-major order. 
```
int sum_array(int a[8][8])
{
 int i, j, sum = 0;
 for (j = 0; j < 8; j++)
   for (i = 0; i < 8; i++)
   sum += a[i][j];
 return sum;
}
```
The cache layout of the program will be as shown in the figure: 
![](assets/cache23-65589f5f9b.png)
As C stores arrays in row-major order but in this case array is being accessed in column major order, so the locality spoils in this case. the references will be made in order: a[0][0], a[1][0], a[2][0] and so on. As the cache size is smaller, with each reference there will be a miss due to poor locality of the program. Hence, the hit ratio will be 0. Poor hit ratio will eventually decrease the performance of a program and will lead to a slower execution. In programming, these type of practices should be avoided.
### Advantages of locality and cache-friendly code:
**Improved performance:** By taking advantage of locality, cache-friendly code can reduce the number of cache misses and improve the overall performance of the system.
**Reduced memory access:** Cache-friendly code can minimize the number of memory accesses required to perform an operation, which can help reduce power consumption and improve energy efficiency.
**Easier to optimize:** Writing cache-friendly code can make it easier to optimize code for specific hardware architectures, as it allows for better use of the cache and other hardware resources.
### Disadvantages of locality and cache-friendly code:
**Increased complexity:** Writing cache-friendly code can be more complex than writing non-cache-friendly code, as it requires careful consideration of the memory layout and access patterns.
**Increased code size:** Cache-friendly code can sometimes result in larger executable sizes, which can affect the overall memory usage of a system.
**Difficulty in debugging:** Cache-friendly code can sometimes be more difficult to debug, as it may not be immediately clear why a particular cache miss is occurring or how to optimize a particular code section for better cache performance.
**Conclusion -** 
When talking about real life application programs and programming realms, optimized cache performance gives a good speedup to a program, even if the runtime complexity of the program is high. A good example is Quick sort. Though it has a worst case complexity of O(n2), it is the most popular sorting algorithm and one of the important factor is the better cache performance than many other sorting algorithms. Codes should be written in a way that they can exploit the cache to the best extent for a faster execution.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-locality-and-cache-friendly-code/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Cache Memory

> [!note] Related notes
>
> - [[2D and 2.5D Memory organization]]
> - [[Cache Memory]]
> - [[Cache Organization Introduction]]
> - [[Different Types of RAM]]
> - [[Introduction to memory and memory units]]
> - [[Memory Hierarchy Design and its Characteristics]]
> - [[Memory Interleaving]]
> - [[RAM vs ROM]]
> - [[Read and Write operations in memory]]
> - [[Types of computer memory]]
