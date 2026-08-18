---
title: "Buddy Memory Allocation Program | Set 1 (Allocation)"
subject: "Operating System"
topic: "Main Memory Management"
source: "https://www.geeksforgeeks.org/operating-systems/buddy-memory-allocation-program-set-1-allocation/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Main Memory Management"
tags:
  - gate/cs
  - subject/operating-system
  - topic/main-memory-management
---


> [!abstract] Buddy Memory Allocation Program | Set 1 (Allocation)
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Main Memory Management`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/buddy-memory-allocation-program-set-1-allocation/)

---

# Buddy Memory Allocation Program | Set 1 (Allocation)

Prerequisite - [Buddy System](https://www.geeksforgeeks.org/operating-systems/buddy-system-memory-allocation-technique/) 
**Question:** Write a program to implement the buddy system of memory allocation in Operating Systems.
**Explanation -** 
The buddy system is implemented as follows- A list of free nodes, of all the different possible powers of 2, is maintained at all times (So if total memory size is 1 MB, we'd have 20 free lists to track-one for blocks of size 1 byte, 1 for 2 bytes, next for 4 bytes and so on). 
When a request for allocation comes, we look for the smallest block bigger than it. If such a block is found on the free list, the allocation is done (say, the request is of 27 KB and the free list tracking 32 KB blocks has at least one element in it), else we traverse the free list **upwards** till we find a big enough block. Then we keep splitting it in two blocks-one for adding to the next free list (of smaller size), one to traverse **down** the tree till we reach the target and return the requested memory block to the user. If no such allocation is possible, we simply return null.
**Example:** 
Let us see how the algorithm proceeds by tracking a memory block of size 128 KB. Initially, the free list is: {}, {}, {}, {}, {}, {}, {}, { (0, 127) } 
- **Request:** 32 bytes 
  No such block found, so we traverse up and split the 0-127 block into 0-63, 64-127; we add 64-127 to list tracking 64 byte blocks and pass 0-63 downwards; again it is split into 0-31 and 32-63; since we have found the required block size, we add 32-63 to list tracking 32 byte blocks and return 0-31 to user. 
  List is: {}, {}, {}, {}, {}, { (32, 63) }, { (64, 127) }, {}
- **Request:** 7 bytes 
  No such block found-split block 32-63 into two blocks, namely 32-47 and 48-63; then split 32-47 into 32-39 and 40-47; finally, return 32-39 to user (internal fragmentation of 1 byte occurs) 
  List is: {}, {}, {}, { (40, 47) }, { (48, 63) }, {}, { (64, 127) }, {}
- **Request:** 64 bytes 
  Straight up memory segment 64-127 will be allocated as it already exists. 
  List is: {}, {}, {}, { (40, 47) }, { (48, 63) }, {}, {}, {}
- Request: 56 bytes 
  Result: Not allocated
The result will be as follows:
![](assets/GFG-20-300e2ad5e5.png)
**Figure -** Buddy Allocation-128 shows the starting address of next possible block (if main memory size ever increases)
**Implementation -**  
````cpp
#include<bits/stdc++.h>
using namespace std;
// Size of vector of pairs
int size;
// Global vector of pairs to store
// address ranges available in free list
vector<pair<int, int>> free_list[100000];
// Map used as hash map to store the starting
// address as key and size of allocated segment
// key as value
map<int, int> mp;
void initialize(int sz)
{
    // Maximum number of powers of 2 possible
    int n = ceil(log(sz) / log(2));
    size = n + 1;
    for(int i = 0; i <= n; i++)
        free_list[i].clear();
    // Initially whole block of specified
    // size is available
    free_list[n].push_back(make_pair(0, sz - 1));
}
void allocate(int sz)
{
    // Calculate index in free list
    // to search for block if available
    int n = ceil(log(sz) / log(2));
    // Block available
    if (free_list[n].size() > 0)
    {
        pair<int, int> temp = free_list[n][0];
        // Remove block from free list
        free_list[n].erase(free_list[n].begin());
        cout << "Memory from " << temp.first
             << " to " << temp.second << " allocated"
             << "\n";
        // map starting address with
        // size to make deallocating easy
        mp[temp.first] = temp.second -
                         temp.first + 1;
    }
    else
    {
        int i;
        for(i = n + 1; i < size; i++)
        {
            // Find block size greater than request
            if(free_list[i].size() != 0)
                break;
        }
        // If no such block is found
        // i.e., no memory block available
        if (i == size)
        {
            cout << "Sorry, failed to allocate memory \n";
        }
        // If found
        else
        {
            pair<int, int> temp;
            temp = free_list[i][0];
            // Remove first block to split it into halves
            free_list[i].erase(free_list[i].begin());
            i--;
            for(; i >= n; i--)
            {
                // Divide block into two halves
                pair<int, int> pair1, pair2;
                pair1 = make_pair(temp.first,
                                  temp.first +
                                  (temp.second -
                                  temp.first) / 2);
                pair2 = make_pair(temp.first +
                                  (temp.second -
                                  temp.first + 1) / 2,
                                  temp.second);
                free_list[i].push_back(pair1);
                // Push them in free list
                free_list[i].push_back(pair2);
                temp = free_list[i][0];
                // Remove first free block to
                // further split
                free_list[i].erase(free_list[i].begin());
            }
            cout << "Memory from " << temp.first
                 << " to " << temp.second
                 << " allocated" << "\n";
            mp[temp.first] = temp.second -
                             temp.first + 1;
        }
    }
}
// Driver code
int main()
{
    // Uncomment following code for interactive IO
    /*
    int total,c,req;
    cin>>total;
    initialize(total);
    while(true)
    {
        cin>>req;
        if(req < 0)
            break;
        allocate(req);
    }*/
    initialize(128);
    allocate(32);
    allocate(7);
    allocate(64);
    allocate(56);
    return 0;
}
// This code is contributed by sarthak_eddy
````
````java
import java.io.*;
import java.util.*;
class Buddy {
    // Inner class to store lower
    // and upper bounds of the allocated memory
    class Pair
    {
        int lb, ub;
        Pair(int a, int b)
        {
            lb = a;
            ub = b;
        }
    }
    // Size of main memory
    int size;
    // Array to track all
    // the free nodes of various sizes
    ArrayList<Pair> arr[];
    // Else compiler will give warning
    // about generic array creation
    @SuppressWarnings("unchecked")
    Buddy(int s)
    {
        size = s;
        // Gives us all possible powers of 2
        int x = (int)Math.ceil(Math.log(s) / Math.log(2));
        // One extra element is added
        // to simplify arithmetic calculations
        arr = new ArrayList[x + 1];
        for (int i = 0; i <= x; i++)
            arr[i] = new ArrayList<>();
        // Initially, only the largest block is free
        // and hence is on the free list
        arr[x].add(new Pair(0, size - 1));
    }
    void allocate(int s)
    {
        // Calculate which free list to search to get the
        // smallest block large enough to fit the request
        int x = (int)Math.ceil(Math.log(s) / Math.log(2));
        int i;
        Pair temp = null;
        // We already have such a block
        if (arr[x].size() > 0)
        {
            // Remove from free list
            // as it will be allocated now
            temp = (Pair)arr[x].remove(0);
            System.out.println("Memory from " + temp.lb
                               + " to " + temp.ub + " allocated");
            return;
        }
        // If not, search for a larger block
        for (i = x + 1; i < arr.length; i++) {
            if (arr[i].size() == 0)
                continue;
            // Found a larger block, so break
            break;
        }
        // This would be true if no such block was found
        // and array was exhausted
        if (i == arr.length)
        {
            System.out.println("Sorry, failed to allocate memory");
            return;
        }
        // Remove the first block
        temp = (Pair)arr[i].remove(0);
        i--;
        // Traverse down the list
        for (; i >= x; i--) {
            // Divide the block in two halves
            // lower index to half-1
            Pair newPair = new Pair(temp.lb, temp.lb
                                     + (temp.ub - temp.lb) / 2);
            // half to upper index
            Pair newPair2 = new Pair(temp.lb
                                  + (temp.ub - temp.lb + 1) / 2, temp.ub);
            // Add them to next list
            // which is tracking blocks of smaller size
            arr[i].add(newPair);
            arr[i].add(newPair2);
            // Remove a block to continue the downward pass
            temp = (Pair)arr[i].remove(0);
        }
        // Finally inform the user
        // of the allocated location in memory
        System.out.println("Memory from " + temp.lb
                            + " to " + temp.ub + " allocated");
    }
    public static void main(String args[]) throws IOException
    {
        int initialMemory = 0, val = 0;
        // Uncomment the below section for interactive I/O
        /*Scanner sc=new Scanner(System.in);
        initialMemory = sc.nextInt();
        Buddy obj = new Buddy(initialMemory);
        while(true)
        {
            val = sc.nextInt();// Accept the request
            if(val <= 0)
                break;
            obj.allocate(val);// Proceed to allocate
        }*/
        initialMemory = 128;
        // Initialize the object with main memory size
        Buddy obj = new Buddy(initialMemory);
        obj.allocate(32);
        obj.allocate(7);
        obj.allocate(64);
        obj.allocate(56);
    }
}
````
````python3
import math
# Size of vector of pairs
size = 0
# Global list of lists to store
# address ranges available in free list
free_list = [[] for _ in range(100000)]
# Dictionary used as a hash map to store the starting
# address as key and size of allocated segment
# as the value
mp = {}
def initialize(sz):
    global size
    # Maximum number of powers of 2 possible
    n = math.ceil(math.log(sz) / math.log(2))
    size = n + 1
    for i in range(size):
        free_list[i].clear()
    # Initially the whole block of specified
    # size is available
    free_list[n].append((0, sz - 1))
def allocate(sz):
    global size
    # Calculate index in free list
    # to search for a block if available
    n = math.ceil(math.log(sz) / math.log(2))
    # Block available
    if len(free_list[n]) > 0:
        temp = free_list[n][0]
        # Remove block from free list
        free_list[n].pop(0)
        print("Memory from", temp[0], "to", temp[1], "allocated")
        # map starting address with
        # size to make deallocating easy
        mp[temp[0]] = temp[1] - temp[0] + 1
    else:
        i = n + 1
        while i < size and not free_list[i]:
            i += 1
        # If no such block is found
        # i.e., no memory block available
        if i == size:
            print("Sorry, failed to allocate memory")
        else:
            temp = free_list[i][0]
            # Remove first block to split it into halves
            free_list[i].pop(0)
            i -= 1
            while i >= n:
                # Divide block into two halves
                pair1 = (temp[0], temp[0] + (temp[1] - temp[0]) // 2)
                pair2 = (temp[0] + (temp[1] - temp[0] + 1) // 2, temp[1])
                # Push them in free list
                free_list[i].append(pair1)
                free_list[i].append(pair2)
                temp = free_list[i][0]
                # Remove first free block to further split
                free_list[i].pop(0)
                i -= 1
            print("Memory from", temp[0], "to", temp[1], "allocated")
            mp[temp[0]] = temp[1] - temp[0] + 1
# Driver code
def main():
    # Uncomment the following code for interactive IO
    '''
    total = int(input())
    initialize(total)
    while True:
        req = int(input())
        if req < 0:
            break
        allocate(req)
    '''
    initialize(128)
    allocate(32)
    allocate(7)
    allocate(64)
    allocate(56)
if __name__ == "__main__":
    main()
    # This code is contributed by utkarshcode1.
````
````csharp
using System;
using System.Collections.Generic;
public class Buddy
{
    // Inner class to store lower
    // and upper bounds of the
    // allocated memory
    class Pair
    {
        public int lb, ub;
        public Pair(int a, int b)
        {
            lb = a;
            ub = b;
        }
    }
    // Size of main memory
    int size;
    // Array to track all
    // the free nodes of various sizes
    List<Pair> []arr;
    // Else compiler will give warning
    // about generic array creation
    Buddy(int s)
    {
        size = s;
        // Gives us all possible powers of 2
        int x = (int)Math.Ceiling(Math.Log(s) /
                                  Math.Log(2));
        // One extra element is added
        // to simplify arithmetic calculations
        arr = new List<Pair>[x + 1];
        for (int i = 0; i <= x; i++)
            arr[i] = new List<Pair>();
        // Initially, only the largest block is free
        // and hence is on the free list
        arr[x].Add(new Pair(0, size - 1));
    }
    void allocate(int s)
    {
        // Calculate which free list to search
        // to get the smallest block
        // large enough to fit the request
        int x = (int)Math.Ceiling(Math.Log(s) /
                                  Math.Log(2));
        int i;
        Pair temp = null;
        // We already have such a block
        if (arr[x].Count > 0)
        {
            // Remove from free list
            // as it will be allocated now
            temp = (Pair)arr[x][0];
                arr[x].RemoveAt(0);
            Console.WriteLine("Memory from " + temp.lb +
                       " to " + temp.ub + " allocated");
            return;
        }
        // If not, search for a larger block
        for (i = x + 1; i < arr.Length; i++)
        {
            if (arr[i].Count == 0)
                continue;
            // Found a larger block, so break
            break;
        }
        // This would be true if no such block
        // was found and array was exhausted
        if (i == arr.Length)
        {
            Console.WriteLine("Sorry, failed to" +
                              " allocate memory");
            return;
        }
        // Remove the first block
        temp = (Pair)arr[i][0];
        arr[i].RemoveAt(0);
        i--;
        // Traverse down the list
        for (; i >= x; i--)
        {
            // Divide the block in two halves
            // lower index to half-1
            Pair newPair = new Pair(temp.lb, temp.lb +
                                   (temp.ub - temp.lb) / 2);
            // half to upper index
            Pair newPair2 = new Pair(temp.lb + (temp.ub -
                              temp.lb + 1) / 2, temp.ub);
            // Add them to next list which is
            // tracking blocks of smaller size
            arr[i].Add(newPair);
            arr[i].Add(newPair2);
            // Remove a block to continue
            // the downward pass
            temp = (Pair)arr[i][0];
            arr[i].RemoveAt(0);
        }
        // Finally inform the user
        // of the allocated location in memory
        Console.WriteLine("Memory from " + temp.lb +
                   " to " + temp.ub + " allocated");
    }
    // Driver Code
    public static void Main(String []args)
    {
        int initialMemory = 0;
        initialMemory = 128;
        // Initialize the object with main memory size
        Buddy obj = new Buddy(initialMemory);
        obj.allocate(32);
        obj.allocate(7);
        obj.allocate(64);
        obj.allocate(56);
    }
}
// This code is contributed by 29AjayKumar
````
````javascript
<script>
// Inner class to store lower
// and upper bounds of the allocated memory
class Pair
{
    constructor(a, b)
    {
        this.lb = a;
        this.ub = b;
    }
}
let size;
let arr;
function Buddy(s)
{
    size = s;
    // Gives us all possible powers of 2
    let x = Math.ceil(Math.log(s) / Math.log(2));
    // One extra element is added
    // to simplify arithmetic calculations
    arr = new Array(x + 1);
    for(let i = 0; i <= x; i++)
        arr[i] =[];
    // Initially, only the largest block is free
    // and hence is on the free list
    arr[x].push(new Pair(0, size - 1));
}
function allocate(s)
{
    // Calculate which free list to search to get the
    // smallest block large enough to fit the request
    let x = Math.floor(Math.ceil(
            Math.log(s) / Math.log(2)));
    let i;
    let temp = null;
    // We already have such a block
    if (arr[x].length > 0)
    {
        // Remove from free list
        // as it will be allocated now
        temp = arr[x].shift();
        document.write("Memory from " + temp.lb +
                       " to " + temp.ub + " allocated<br>");
        return;
    }
    // If not, search for a larger block
    for(i = x + 1; i < arr.length; i++)
    {
        if (arr[i].length == 0)
            continue;
        // Found a larger block, so break
        break;
    }
    // This would be true if no such block was
    // found and array was exhausted
    if (i == arr.length)
    {
        document.write("Sorry, failed to " +
                       "allocate memory<br>");
        return;
    }
    // Remove the first block
    temp = arr[i].shift(0);
    i--;
    // Traverse down the list
    for(; i >= x; i--)
    {
        // Divide the block in two halves
        // lower index to half-1
        let newPair = new Pair(temp.lb,
                               temp.lb +
                               Math.floor(
                                   (temp.ub -
                                    temp.lb) / 2));
        // half to upper index
        let newPair2 = new Pair(temp.lb +
                                Math.floor(
                                    (temp.ub -
                                     temp.lb + 1) / 2),
                                     temp.ub);
        // Add them to next list which is
        // tracking blocks of smaller size
        arr[i].push(newPair);
        arr[i].push(newPair2);
        // Remove a block to continue
        // the downward pass
        temp = arr[i].shift(0);
    }
    // Finally inform the user
    // of the allocated location in memory
    document.write("Memory from " + temp.lb +
                   " to " + temp.ub + " allocated<br>");
}
// Driver code
let initialMemory = 0, val = 0;
// Uncomment the below section for interactive I/O
/*Scanner sc=new Scanner(System.in);
        initialMemory = sc.nextInt();
        Buddy obj = new Buddy(initialMemory);
        while(true)
        {
            val = sc.nextInt();// Accept the request
            if(val <= 0)
                break;
            obj.allocate(val);// Proceed to allocate
        }*/
initialMemory = 128;
// Initialize the object with main memory size
Buddy(initialMemory);
allocate(32);
allocate(7);
allocate(64);
allocate(56);
// This code is contributed by rag2127
</script>
````
**Output**
```
Memory from 0 to 31 allocated
Memory from 32 to 39 allocated
Memory from 64 to 127 allocated
Sorry, failed to allocate memory
```
**Time Complexity -** 
If the main memory size is **n**, we have log(n) number of different powers of 2 and hence log(n) elements in the array (named **arr** in the code) tracking free lists. To allocate a block, we only need to traverse the array once upwards and once downwards, hence time complexity is **O(2log(n))** or simply **O(logn)**
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/buddy-memory-allocation-program-set-1-allocation/)

## GATE CS

- Subject: Operating System
- Topic: Main Memory Management

> [!note] Related notes
>
> - [[Allocating kernel memory]]
> - [[Buddy System]]
> - [[Buddy System Memory Deallocation]]
> - [[Demand Paging]]
> - [[Fixed (or static) Partitioning]]
> - [[Inverted Page Table]]
> - [[Logical vs Physical Address in Operating System]]
> - [[Mapping virtual address to physical addresses]]
> - [[Memory Management Partition Allocation Method]]
> - [[Multilevel Paging]]
