---
title: "Buddy Memory Allocation Program | Set 2 (Deallocation)"
subject: "Operating System"
topic: "Main Memory Management"
source: "https://www.geeksforgeeks.org/operating-systems/buddy-memory-allocation-program-set-2-deallocation/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Operating System/Main Memory Management"
tags:
  - gate/cs
  - subject/operating-system
  - topic/main-memory-management
---


> [!abstract] Buddy Memory Allocation Program | Set 2 (Deallocation)
> 
> **Subject:** `Operating System` &nbsp;|&nbsp; **Topic:** `Main Memory Management`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/buddy-memory-allocation-program-set-2-deallocation/)

---

# Buddy Memory Allocation Program | Set 2 (Deallocation)

Prerequisite - [Buddy Allocation | Set 1](https://www.geeksforgeeks.org/operating-systems/buddy-memory-allocation-program-set-1-allocation/) 
**Question:** Write a program to implement the buddy system of memory allocation and deallocation in Operating Systems.
**Explanation -** 
As we already know from Set 1, the allocation is done via the usage of free lists. Now, for deallocation, we will maintain an extra data structure-a Map (unordered\_set in C++, HashMap in Java) with the starting address of segment as key and size of the segment as value and update it whenever an allocation request comes. Now, when a deallocation request comes, we will first check the map to see if it is a valid request. If so, we will then add the block to the free list tracking blocks of their sizes. Then, we will search the free list to see if its **buddy** is free-if so, we will merge the blocks and place them on the free list above them (which tracks blocks of double the size), else we will not coalesce and simply return after that.
How to know which block is a given block's buddy?
Let us define two terms-**buddyNumber** and **buddyAddress**. The **buddyNumber** of a block is calculated by the formula: 
```
(base_address-starting_address_of_main_memory)/block_size
```
We note that this is always an integer, as both numerator and denominator are powers of 2. Now, a block will be another block's buddy if both of them were formed by the splitting of the same bigger block. For example, if 4 consecutive allocation requests of 16 bytes come, we will end up with blocks 0-15, 16-31, 32-47, 48-63 where blocks 0-15 and 16-31 are buddies (as they were formed by splitting block 0-32) but 0-15 and 32-47 aren't. The **buddyAddress** of a block is the starting index of its buddy block, given by the formula: 
```
block_starting_address+block_size (if buddyNumber is even)block_starting_address-block_size (if buddyNumber is odd)
```
Thus, all we have to do is find this **buddyAddress** in the free list (by comparing with all the starting addresses in that particular list), and if present, coalescing can be done.
**Examples:** 
Let us see how the algorithm proceeds by tracking a memory block of size 128 KB. Initially, the free list is: {}, {}, {}, {}, {}, {}, {}, { (0, 127) } 
- **Allocation Request:** 16 bytes 
  No such block found, so we traverse up and split the 0-127 block into 0-63, 64-127; we add 64-127 to list tracking 64-byte blocks and pass 0-63 downwards; again it is split into 0-31 and 32-63; we add 32-63 to list tracking 32-byte blocks, passing 0-31 downwards; one more splits done and 0-15 is returned to the user while 16-31 is added to free list tracking 16-byte blocks. 
  List is: {}, {}, {}, {}, { (16, 31) }, { (32, 63) }, { (64, 127) }, {}
- **Allocation Request:** 16 bytes 
  Straight-up memory segment 16-31 will be allocated as it already exists. 
  List is: {}, {}, {}, {}, {}, { (32, 63) }, { (64, 127) }, {}
- **Allocation Request:** 16 bytes 
  No such block was found, so we will traverse up to block 32-63 and split it into blocks 32-47 and 48-63; we will add 48-63 to list tracking 16-byte blocks and return 32-47 to a user. 
  List is: {}, {}, {}, {}, { (48, 63) }, {}, { (64, 127) }, {}
- **Allocation Request:** 16 bytes 
  Straight-up memory segment 48-63 will be allocated as it already exists. 
  List is: {}, {}, {}, {}, {}, {}, { (64, 127) }, {}
- **Deallocation Request:** StartIndex = 0 
  Deallocation will be done but no coalescing is possible as its **buddyNumber** is 0 and **buddyAddress** is 16 (via the formula), none of which is in the free list. 
  List is: {}, {}, {}, {}, { (0, 15) }, {}, { (64, 127) }, {}
- **Deallocation Request:** StartIndex = 9 
  Result: Invalid request, as this segment was never allocated. 
  List is: {}, {}, {}, {}, { (0, 15) }, {}, { (64, 127) }, {}
- **Deallocation Request:** StartIndex = 32 
  Deallocation will be done but no coalescing is possible as the **buddyNumber** of the blocks are 0 and 2 **buddyAddress** of the blocks are 16 and 48, respectively, none of which is in the free list. 
  List is: {}, {}, {}, {}, { (0, 15), (32-47) }, {}, { (64, 127) }, {}
- **Deallocation Request:** StartIndex = 16 
  Deallocation will be done and coalescing of the blocks 0-15 and 16-31 will also be done as the **buddyAddress** of block 16-31 is 0, which is present in the free list tracking 16-byte blocks. 
  List is: {}, {}, {}, {}, { (32-47) }, { (0, 31) }, { (64, 127) }, {}
![](assets/GFG-21-cec3f9fe87.png)
**Figure -** Buddy algorithm-allocation and deallocation
**Implementation -** 
Below is the complete program. 
````cpp
#include<bits/stdc++.h>
using namespace std;
// Size of vector of pairs
int size;
// Global vector of pairs to track all
// the free nodes of various sizes
vector<pair<int, int>> arr[100000];
// Map used as hash map to store the
// starting address as key and size
// of allocated segment key as value
map<int, int> mp;
void Buddy(int s)
{
    // Maximum number of powers of 2 possible
    int n = ceil(log(s) / log(2));
    size = n + 1;
    for(int i = 0; i <= n; i++)
        arr[i].clear();
    // Initially whole block of specified
    // size is available
    arr[n].push_back(make_pair(0, s - 1));
}
void allocate(int s)
{
    // Calculate index in free list
    // to search for block if available
    int x = ceil(log(s) / log(2));
    // Block available
    if (arr[x].size() > 0)
    {
        pair<int, int> temp = arr[x][0];
        // Remove block from free list
        arr[x].erase(arr[x].begin());
        cout << "Memory from " << temp.first
             << " to " << temp.second
             << " allocated" << "\n";
        // Map starting address with
        // size to make deallocating easy
        mp[temp.first] = temp.second -
                         temp.first + 1;
    }
    else
    {
        int i;
        // If not, search for a larger block
        for(i = x + 1; i < size; i++)
        {
            // Find block size greater
            // than request
            if (arr[i].size() != 0)
                break;
        }
        // If no such block is found
        // i.e., no memory block available
        if (i == size)
        {
            cout << "Sorry, failed to allocate memory\n";
        }
        // If found
        else
        {
            pair<int, int> temp;
            temp = arr[i][0];
            // Remove first block to split
            // it into halves
            arr[i].erase(arr[i].begin());
            i--;
            for(;i >= x; i--)
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
                arr[i].push_back(pair1);
                // Push them in free list
                arr[i].push_back(pair2);
                temp = arr[i][0];
                // Remove first free block to
                // further split
                arr[i].erase(arr[i].begin());
            }
            cout << "Memory from " << temp.first
                 << " to " << temp.second
                 << " allocate" << "\n";
            mp[temp.first] = temp.second -
                             temp.first + 1;
        }
    }
}
void deallocate(int id)
{
    // If no such starting address available
    if(mp.find(id) == mp.end())
    {
        cout << "Sorry, invalid free request\n";
        return;
    }
    // Size of block to be searched
    int n = ceil(log(mp[id]) / log(2));
    int i, buddyNumber, buddyAddress;
    // Add the block in free list
    arr[n].push_back(make_pair(id,
                               id + pow(2, n) - 1));
    cout << "Memory block from " << id
         << " to "<< id + pow(2, n) - 1
         << " freed\n";
    // Calculate buddy number
    buddyNumber = id / mp[id];
    if (buddyNumber % 2 != 0)
        buddyAddress = id - pow(2, n);
    else
        buddyAddress = id + pow(2, n);
    // Search in free list to find it's buddy
    for(i = 0; i < arr[n].size(); i++)
    {
        // If buddy found and is also free
        if (arr[n][i].first == buddyAddress)
        {
            // Now merge the buddies to make
            // them one large free memory block
            if (buddyNumber % 2 == 0)
            {
                arr[n + 1].push_back(make_pair(id,
                   id + 2 * pow(2, n) - 1));
                cout << "Coalescing of blocks starting at "
                     << id << " and " << buddyAddress
                     << " was done" << "\n";
            }
            else
            {
                arr[n + 1].push_back(make_pair(
                    buddyAddress, buddyAddress +
                    2 * pow(2, n) - 1));
                cout << "Coalescing of blocks starting at "
                     << buddyAddress << " and "
                     << id << " was done" << "\n";
            }
            arr[n].erase(arr[n].begin() + i);
            arr[n].erase(arr[n].begin() +
            arr[n].size() - 1);
            break;
        }
    }
    // Remove the key existence from map
    mp.erase(id);
}
// Driver code
int main()
{
    // Uncomment following code for interactive IO
    /*
    int total,c,req;
    cout<<"Enter Total Memory Size (in Bytes) => ";
    cin>>total;
    initialize(total);
    label:
    while(1)
    {
        cout<<"\n1. Add Process into Memory\n
        2. Remove Process \n3. Allocation Map\n4. Exit\n=> ";
        cin>>c;
        switch(c)
        {
            case 1:
            cout<<"Enter Process Size (in Bytes) => ";
            cin>>req;
            cout<<"\n===>";
            allocate(req);
            break;
            case 2:
            cout<<"Enter Starting Address => ";
            cin>>req;
            cout<<"\n===>";
            deallocate(req);
            break;
            case 3:
            print();
            break;
            case 4:
            exit(0);
            break;
            default:
            goto label;
        }
    }*/
    Buddy(128);
    allocate(16);
    allocate(16);
    allocate(16);
    allocate(16);
    deallocate(0);
    deallocate(9);
    deallocate(32);
    deallocate(16);
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
    class Pair {
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
    // Hashmap to store the starting
    // address and size of allocated segment
    // Key is starting address, size is value
    HashMap<Integer, Integer> hm;
    // Else compiler will give warning
    // about generic array creation
    @SuppressWarnings("unchecked")
    Buddy(int s)
    {
        size = s;
        hm = new HashMap<>();
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
        if (arr[x].size() > 0) {
            // Remove from free list
            // as it will be allocated now
            temp = (Pair)arr[x].remove(0);
            System.out.println("Memory from " + temp.lb
                            + " to " + temp.ub + " allocated");
            // Store in HashMap
            hm.put(temp.lb, temp.ub - temp.lb + 1);
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
        if (i == arr.length) {
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
                                    + (temp.ub - temp.lb + 1) / 2,
                                    temp.ub);
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
        // Store in HashMap
        hm.put(temp.lb, temp.ub - temp.lb + 1);
    }
    void deallocate(int s)
    {
        // Invalid reference, as this was never allocated
        if (!hm.containsKey(s)) {
            System.out.println("Sorry, invalid free request");
            return;
        }
        // Get the list which will track free blocks
        // of this size
        int x = (int)Math.ceil(Math.log(hm.get(s))
                                        / Math.log(2));
        int i, buddyNumber, buddyAddress;
        // Add it to the free list
        arr[x].add(new Pair(s, s + (int)Math.pow(2, x) - 1));
        System.out.println("Memory block from " + s + " to "
                           + (s + (int)Math.pow(2, x) - 1) + " freed");
        // Calculate it's buddy number and buddyAddress. The
        // base address is implicitly 0 in this program, so no
        // subtraction is necessary for calculating buddyNumber
        buddyNumber = s / hm.get(s);
        if (buddyNumber % 2 != 0) {
            buddyAddress = s - (int)Math.pow(2, x);
        }
        else {
            buddyAddress = s + (int)Math.pow(2, x);
        }
        // Search in the free list for buddy
        for (i = 0; i < arr[x].size(); i++) {
            // This indicates the buddy is also free
            if (arr[x].get(i).lb == buddyAddress) {
                // Buddy is the block after block
                // with this base address
                if (buddyNumber % 2 == 0) {
                    // Add to appropriate free list
                    arr[x + 1].add(new Pair(s, s
                                  + 2 * ((int)Math.pow(2, x)) - 1));
                    System.out.println("Coalescing of blocks starting at "
                                            + s + " and "
                                            + buddyAddress + " was done");
                }
                // Buddy is the block before block
                // with this base address
                else {
                    // Add to appropriate free list
                    arr[x + 1].add(new Pair(buddyAddress,
                                    buddyAddress + 2 * ((int)Math.pow(2, x))
                                                                         - 1));
                    System.out.println("Coalescing of blocks starting at "
                                                + buddyAddress + " and "
                                                + s + " was done");
                }
                // Remove the individual segments
                // as they have coalesced
                arr[x].remove(i);
                arr[x].remove(arr[x].size() - 1);
                break;
            }
        }
        // Remove entry from HashMap
        hm.remove(s);
    }
    public static void main(String args[]) throws IOException
    {
        int initialMemory = 0, type = -1, val = 0;
        // Uncomment below section for interactive I/O
        /*Scanner sc=new Scanner(System.in);
        initialMemory = sc.nextInt();
        Buddy obj=new Buddy(initialMemory);
        while(true)
        {
            type = sc.nextInt();
            if(type==-1)
            break;
            else if(type==1)
            {
                val=sc.nextInt();
                obj.allocate(val);
            }
            else
            {
                val=sc.nextInt();
                obj.deallocate(val);
            }
        }*/
        initialMemory = 128;
        Buddy obj = new Buddy(initialMemory);
        obj.allocate(16);
        obj.allocate(16);
        obj.allocate(16);
        obj.allocate(16);
        obj.deallocate(0);
        obj.deallocate(9);
        obj.deallocate(32);
        obj.deallocate(16);
    }
}
````
````python3
import math
# Size of list of pairs
size = 0
# Global list of pairs to track all
# the free nodes of various sizes
arr = [None] * 100000
# Dictionary used as hash map to store the
# starting address as key and size
# of allocated segment key as value
mp = {}
def Buddy(s):
    global size
    # Maximum number of powers of 2 possible
    n = math.ceil(math.log(s, 2))
    size = n + 1
    for i in range(0, n+1):
        arr[i] = []
    # Initially whole block of specified
    # size is available
    arr[n].append((0, s - 1))
def allocate(s):
    # Calculate index in free list
    # to search for block if available
    x = math.ceil(math.log(s, 2))
    # Block available
    if len(arr[x]) > 0:
        temp = arr[x][0]
        # Remove block from free list
        arr[x].remove(temp)
        print(f"Memory from {temp[0]} to {temp[1]} allocated")
        # Map starting address with
        # size to make deallocating easy
        mp[temp[0]] = temp[1] - temp[0] + 1
    else:
        i = 0
        # If not, search for a larger block
        for i in range(x + 1, size):
            # Find block size greater
            # than request
            if len(arr[i]) != 0:
                break
        # If no such block is found
        # i.e., no memory block available
        if i == size:
            print("Sorry, failed to allocate memory")
        else:
            temp = arr[i][0]
            # Remove first block to split
            # it into halves
            arr[i].remove(temp)
            i -= 1
            while i >= x:
                # Divide block into two halves
                pair1, pair2 = (temp[0], temp[0] + (temp[1] - temp[0]) // 2), (temp[0] + (temp[1] - temp[0] + 1) // 2, temp[1])
                arr[i].append(pair1)
                # Push them in free list
                arr[i].append(pair2)
                temp = arr[i][0]
                # Remove first free block to
                # further split
                arr[i].remove(temp)
                i -= 1
            print(f"Memory from {temp[0]} to {temp[1]} allocated")
            mp[temp[0]] = temp[1] - temp[0] + 1
def deallocate(id):
    # If no such starting address available
    if id not in mp:
        print("Sorry, invalid free request")
        return
    # Size of block to be searched
    n = math.ceil(math.log(mp[id], 2))
    i = 0
    buddyNumber = 0
    buddyAddress = 0
    # Add the block in free list
    arr[n].append((id, id + 2**n - 1))
    print(f"Memory block from {id} to {id + 2**n - 1} freed")
    # Calculate buddy number
    buddyNumber = id // mp[id]
    if buddyNumber % 2 != 0:
        buddyAddress = id - 2**n
    else:
        buddyAddress = id + 2**n
    # Search in free list to find it's buddy
    for i in range(0, len(arr[n])):
        # If buddy found and is also free
        if arr[n][i][0] == buddyAddress:
            # Now merge the buddies to make
            # them one large free memory block
            if buddyNumber % 2 == 0:
                arr[n + 1].append((id, id + 2 * 2**n - 1))
                print(f"Coalescing of blocks starting at {id} and {buddyAddress} was done")
            else:
                arr[n + 1].append((buddyAddress, buddyAddress + 2 * 2**n - 1))
                print(f"Coalescing of blocks starting at {buddyAddress} and {id} was done")
            arr[n].remove(arr[n][i])
            arr[n].remove(arr[n][-1])
            break
    # Remove the key existence from map
    del mp[id]
# Driver code
def main():
    Buddy(128)
    allocate(16)
    allocate(16)
    allocate(16)
    allocate(16)
    deallocate(0)
    deallocate(9)
    deallocate(32)
    deallocate(16)
if __name__ == "__main__":
    main()
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
    // Hashmap to store the starting
    // address and size of allocated segment
    // Key is starting address, size is value
    Dictionary<int, int> hm;
    // Else compiler will give warning
    // about generic array creation
    Buddy(int s)
    {
        size = s;
        hm = new Dictionary<int, int>();
        // Gives us all possible powers of 2
        int x = (int)Math.Ceiling(Math.Log(s) /
                                  Math.Log(2));
        // One extra element is added
        // to simplify arithmetic calculations
        arr = new List<Pair>[x + 1];
        for (int i = 0; i <= x; i++)
            arr[i] = new List<Pair>();
        // Initially, only the largest block is
        // free and hence is on the free list
        arr[x].Add(new Pair(0, size - 1));
    }
    void allocate(int s)
    {
        // Calculate which free list to
        // search to get the smallest block
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
            // Store in Dictionary
            hm.Add(temp.lb, temp.ub - temp.lb + 1);
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
            // Add them to next list
            // which is tracking blocks of
            // smaller size
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
        // Store in Dictionary
        hm.Add(temp.lb, temp.ub - temp.lb + 1);
    }
    void deallocate(int s)
    {
        // Invalid reference,
        // as this was never allocated
        if (!hm.ContainsKey(s))
        {
            Console.WriteLine("Sorry, invalid free request");
            return;
        }
        // Get the list which will track free blocks
        // of this size
        int x = (int)Math.Ceiling(Math.Log(hm[s]) /
                                  Math.Log(2));
        int i, buddyNumber, buddyAddress;
        // Add it to the free list
        arr[x].Add(new Pair(s, s +
                  (int)Math.Pow(2, x) - 1));
        Console.WriteLine("Memory block from " + s +
                                       " to " + (s +
               (int)Math.Pow(2, x) - 1) + " freed");
        // Calculate it's buddy number and
        // buddyAddress. The base address is
        // implicitly 0 in this program,
        // so no subtraction is necessary for
        // calculating buddyNumber
        buddyNumber = s / hm[s];
        if (buddyNumber % 2 != 0)
        {
            buddyAddress = s - (int)Math.Pow(2, x);
        }
        else
        {
            buddyAddress = s + (int)Math.Pow(2, x);
        }
        // Search in the free list for buddy
        for (i = 0; i < arr[x].Count; i++)
        {
            // This indicates the buddy is also free
            if (arr[x][i].lb == buddyAddress)
            {
                // Buddy is the block after block
                // with this base address
                if (buddyNumber % 2 == 0)
                {
                    // Add to appropriate free list
                    arr[x + 1].Add(new Pair(s, s + 2 *
                                 ((int)Math.Pow(2, x)) - 1));
                    Console.WriteLine("Coalescing of blocks starting at " +
                                 s + " and " + buddyAddress + " was done");
                }
                // Buddy is the block before block
                // with this base address
                else
                {
                    // Add to appropriate free list
                    arr[x + 1].Add(new Pair(buddyAddress,
                                            buddyAddress +
                                  2 * ((int)Math.Pow(2, x)) - 1));
                    Console.WriteLine("Coalescing of blocks starting at " +
                                 buddyAddress + " and " + s + " was done");
                }
                // Remove the individual segments
                // as they have coalesced
                arr[x].RemoveAt(i);
                arr[x].RemoveAt(arr[x].Count - 1);
                break;
            }
        }
        // Remove entry from Dictionary
        hm.Remove(s);
    }
    // Driver Code
    public static void Main(String []args)
    {
        int initialMemory = 0;
        initialMemory = 128;
        Buddy obj = new Buddy(initialMemory);
        obj.allocate(16);
        obj.allocate(16);
        obj.allocate(16);
        obj.allocate(16);
        obj.deallocate(0);
        obj.deallocate(9);
        obj.deallocate(32);
        obj.deallocate(16);
    }
}
// This code is contributed by 29AjayKumar
````
**Output**
```
Memory from 0 to 15 allocate
Memory from 16 to 31 allocated
Memory from 32 to 47 allocate
Memory from 48 to 63 allocated
Memory block from 0 to 15 freed
Sorry, invalid free request
Memory block from 32 to 47 freed
Memory block from 16 to 31 freed
Coalescing of blocks starting at 0 and 16 was done
```
**Time Complexity -** 
As already discussed in set 1, the time complexity of allocation is **O(log(n))**. For deallocation, in the worst case, all the allocated blocks can be of size 1 unit, which will then require **O(n)** time to scan the list for coalescing. However, in practice, it is highly unlikely that such an allocation will happen so it is generally much faster than linear time.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/operating-systems/buddy-memory-allocation-program-set-2-deallocation/)

## GATE CS

- Subject: Operating System
- Topic: Main Memory Management

> [!note] Related notes
>
> - [[Allocating kernel memory]]
> - [[Buddy System]]
> - [[Buddy System Memory Allocation]]
> - [[Demand Paging]]
> - [[Fixed (or static) Partitioning]]
> - [[Inverted Page Table]]
> - [[Logical vs Physical Address in Operating System]]
> - [[Mapping virtual address to physical addresses]]
> - [[Memory Management Partition Allocation Method]]
> - [[Multilevel Paging]]
