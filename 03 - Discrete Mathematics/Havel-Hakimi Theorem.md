---
title: "Find if a degree sequence can form a simple graph | Havel-Hakimi Algorithm"
subject: "Discrete Mathematics"
topic: "Graphs"
source: "https://www.geeksforgeeks.org/dsa/find-if-a-degree-sequence-can-form-a-simple-graph-havel-hakimi-algorithm/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Graphs"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/graphs
---


> [!abstract] Find if a degree sequence can form a simple graph | Havel-Hakimi Algorithm
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Graphs`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/find-if-a-degree-sequence-can-form-a-simple-graph-havel-hakimi-algorithm/)

---

# Find if a degree sequence can form a simple graph | Havel-Hakimi Algorithm

Given a sequence of non-negative integers **arr[]**, the task is to check if there exists a simple graph corresponding to this degree sequence. **Note** that a simple graph is a graph with no self-loops and parallel edges.
**Examples:** 
> **Input:** arr[] = {3, 3, 3, 3} 
> **Output:** Yes 
> This is actually a complete graph(K4)
>
> **Input:** arr[] = {3, 2, 1, 0} 
> **Output:** No 
> A vertex has degree n-1 so it's connected to all the other n-1 vertices. 
> But another vertex has degree 0 i.e. isolated. It's a contradiction. 
**Approach:** One way to check the existence of a simple graph is by [Havel-Hakimi algorithm](https://en.wikipedia.org/wiki/Havel%E2%80%93Hakimi_algorithm) given below: 
- Sort the sequence of non-negative integers in non-increasing order.
- Delete the first element(say V). Subtract 1 from the next V elements.
- Repeat 1 and 2 until one of the stopping conditions is met.
Stopping conditions: 
- All the elements remaining are equal to 0 (Simple graph exists).
- Negative number encounter after subtraction (No simple graph exists).
- Not enough elements remaining for the subtraction step (No simple graph exists).
Below is the implementation of the above approach:
````cpp14
// C++ implementation of the approach
#include <bits/stdc++.h>
using namespace std;
// Function that returns true if
// a simple graph exists
bool graphExists(vector<int> &a, int n)
{
    // Keep performing the operations until one
    // of the stopping condition is met
    while (1)
    {
        // Sort the list in non-decreasing order
        sort(a.begin(), a.end(), greater<>());
        // Check if all the elements are equal to 0
        if (a[0] == 0)
            return true;
        // Store the first element in a variable
        // and delete it from the list
        int v = a[0];
        a.erase(a.begin() + 0);
        // Check if enough elements
        // are present in the list
        if (v > a.size())
            return false;
        // Subtract first element from next v elements
        for (int i = 0; i < v; i++)
        {
            a[i]--;
            // Check if negative element is
            // encountered after subtraction
            if (a[i] < 0)
                return false;
        }
    }
}
// Driver Code
int main()
{
    vector<int> a = {3, 3, 3, 3};
    int n = a.size();
    graphExists(a, n) ? cout << "Yes" :
                        cout << "NO" << endl;
    return 0;
}
// This code is contributed by
// sanjeev2552
````
````java
// Java implementation of the approach
import java.util.*;
@SuppressWarnings("unchecked")
class GFG{
// Function that returns true if
// a simple graph exists
static boolean graphExists(ArrayList a, int n)
{
    // Keep performing the operations until one
    // of the stopping condition is met
    while (true)
    {
        // Sort the list in non-decreasing order
        Collections.sort(a, Collections.reverseOrder());
        // Check if all the elements are equal to 0
        if ((int)a.get(0) == 0)
            return true;
        // Store the first element in a variable
        // and delete it from the list
        int v = (int)a.get(0);
        a.remove(a.get(0));
        // Check if enough elements
        // are present in the list
        if (v > a.size())
            return false;
        // Subtract first element from
        // next v elements
        for(int i = 0; i < v; i++)
        {
            a.set(i, (int)a.get(i) - 1);
            // Check if negative element is
            // encountered after subtraction
            if ((int)a.get(i) < 0)
                return false;
        }
    }
}
// Driver Code
public static void main(String[] args)
{
    ArrayList a = new ArrayList();
    a.add(3);
    a.add(3);
    a.add(3);
    a.add(3);
    int n = a.size();
    if (graphExists(a, n))
    {
        System.out.print("Yes");
    }
    else
    {
        System.out.print("NO");
    }
}
}
// This code is contributed by pratham76
````
````python3
# Python3 implementation of the approach
# Function that returns true if
# a simple graph exists
def graphExists(a):
    # Keep performing the operations until one
    # of the stopping condition is met
    while True:
        # Sort the list in non-decreasing order
        a = sorted(a, reverse = True)
        # Check if all the elements are equal to 0
        if a[0]== 0 and a[len(a)-1]== 0:
            return True
        # Store the first element in a variable
        # and delete it from the list
        v = a[0]
        a = a[1:]
        # Check if enough elements
        # are present in the list
        if v>len(a):
            return False
        # Subtract first element from next v elements
        for i in range(v):
            a[i]-= 1
            # Check if negative element is
            # encountered after subtraction
            if a[i]<0:
                return False
# Driver code
a = [3, 3, 3, 3]
if(graphExists(a)):
    print("Yes")
else:
    print("No")
````
````csharp
// C# implementation of the approach
using System;
using System.Collections;
class GFG{
// Function that returns true if
// a simple graph exists
static bool graphExists(ArrayList a, int n)
{
    // Keep performing the operations until one
    // of the stopping condition is met
    while (true)
    {
        // Sort the list in non-decreasing order
        a.Sort();
        a.Reverse();
        // Check if all the elements are equal to 0
        if ((int)a[0] == 0)
            return true;
        // Store the first element in a variable
        // and delete it from the list
        int v = (int)a[0];
        a.Remove(a[0]);
        // Check if enough elements
        // are present in the list
        if (v > a.Count)
            return false;
        // Subtract first element from
        // next v elements
        for(int i = 0; i < v; i++)
        {
            a[i] = (int)a[i] - 1;
            // Check if negative element is
            // encountered after subtraction
            if ((int)a[i] < 0)
                return false;
        }
    }
}
// Driver Code
public static void Main(string[] args)
{
    ArrayList a = new ArrayList(){ 3, 3, 3, 3 };
    int n = a.Count;
    if (graphExists(a, n))
    {
        Console.Write("Yes");
    }
    else
    {
        Console.Write("NO");
    }
}
}
// This code is contributed by rutvik_56
````
````javascript
<script>
// Javascript implementation of the approach
// Function that returns true if
// a simple graph exists
function graphExists(a, n)
{
    // Keep performing the operations until one
    // of the stopping condition is met
    while (1)
    {
        // Sort the list in non-decreasing order
        a.sort((a, b) => b - a)
        // Check if all the elements are equal to 0
        if (a[0] == 0)
            return true;
        // Store the first element in a variable
        // and delete it from the list
        var v = a[0];
        a.shift();
        // Check if enough elements
        // are present in the list
        if (v > a.length)
            return false;
        // Subtract first element from next v elements
        for(var i = 0; i < v; i++)
        {
            a[i]--;
            // Check if negative element is
            // encountered after subtraction
            if (a[i] < 0)
                return false;
        }
    }
}
// Driver Code
var a = [ 3, 3, 3, 3 ];
var n = a.length;
graphExists(a, n) ? document.write("Yes"):
                    document.write("NO");
// This code is contributed by rrrtnx
</script>
````
**Output**
```
Yes
```
**Time Complexity:** O(
$$
N^2*logN
$$
)
**Auxiliary Space:** O(1)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/find-if-a-degree-sequence-can-form-a-simple-graph-havel-hakimi-algorithm/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Graphs

> [!note] Related notes
>
> - [[Euler and Hamiltonian Paths]]
> - [[Graph Isomorphisms and Connectivity]]
> - [[Graph Measurements]]
> - [[Graph Theory Basics]]
> - [[Graph Theory Practice Questions]]
> - [[Independent Sets, Covering, and Matching]]
> - [[Introduction to Graphs]]
> - [[Matching in Graph Theory]]
> - [[Number of Nodes and Height of a Binary Tree]]
> - [[Planar Graphs and Graph Coloring]]
