---
title: "Cartesian Product of Two Sets"
subject: "Discrete Mathematics"
topic: "Algebraic and Set-Theoretic Structures"
source: "https://www.geeksforgeeks.org/dsa/cartesian-product-two-sets/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Algebraic and Set-Theoretic Structures"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/algebraic-and-set-theoretic-structures
---


> [!abstract] Cartesian Product of Two Sets
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Algebraic and Set-Theoretic Structures`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/cartesian-product-two-sets/)

---

# Cartesian Product of Two Sets

Let A and B be two sets, Cartesian product**A × B** is the set of all ordered pair of elements from A and B 
**A × B = {{x, y} : x ? A, y ? B}**
> Let A = {a, b, c} and B = {d, e, f} 
> The Cartesian product of two sets is 
> A x B = {a, d}, {a, e}, {a, f}, {b, d}, {b, e}, {b, f}, {c, d}, {c, e}, {c, f}}
> A has 3 elements and B also has 3 elements. The Cartesian Product has 3 x 3 = 9 elements.
> In general, if there are m elements in set A and n elements in B, the number of elements in the Cartesian Product is **m x n**
**Given two finite non-empty sets, write a program to print** [**Cartesian Product**](https://www.geeksforgeeks.org/maths/cartesian-product-of-sets/)**.**
**Examples :**
> **Input :** A = {1, 2}, B = {3, 4}
> **Output :** A × B = {{1, 3}, {1, 4}, {2, 3}, {2, 4}}
>
> **Input :** A = {1, 2, 3} B = {4, 5, 6}
> **Output :** A × B = {{1, 4}, {1, 5}, {1, 6}, {2, 4}, 
>                    {2, 5}, {2, 6}, {3, 4}, {3, 5}, {3, 6}} 
````cpp
// C++ Program to find the Cartesian Product of Two Sets
#include <stdio.h>
void findCart(int arr1[], int arr2[], int n, int n1)
{
    for (int i = 0; i < n; i++)
        for (int j = 0; j < n1; j++)
            printf("{%d, %d}, ", arr1[i], arr2[j]);
}
int main()
{
    int arr1[] = { 1, 2, 3 }; // first set
    int arr2[] = { 4, 5, 6 }; // second set
    int n1 = sizeof(arr1) / sizeof(arr1[0]);
    int n2 = sizeof(arr2) / sizeof(arr2[0]);
    findCart(arr1, arr2, n1, n2);
    return 0;
}
````
````java
// Java Program to find the
// Cartesian Product of Two Sets
import java.io.*;
import java.util.*;
class GFG {
    static void findCart(int arr1[], int arr2[], int n,
                         int n1)
    {
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n1; j++)
                System.out.print("{" + arr1[i] + ", "
                                 + arr2[j] + "}, ");
    }
    // Driver code
    public static void main(String[] args)
    {
        // first set
        int arr1[] = { 1, 2, 3 };
        // second set
        int arr2[] = { 4, 5, 6 };
        int n1 = arr1.length;
        int n2 = arr2.length;
        findCart(arr1, arr2, n1, n2);
    }
}
// This code is contributed by Nikita Tiwari.
````
````python3
# Python3 Program to find the
# Cartesian Product of Two Sets
def findCart(arr1, arr2, n, n1):
    for i in range(0, n):
        for j in range(0, n1):
            print("{", arr1[i], ", ", arr2[j], "}, ", sep="", end="")
# Driver code
arr1 = [1, 2, 3]  # first set
arr2 = [4, 5, 6]  # second set
n1 = len(arr1)  # sizeof(arr1[0])
n2 = len(arr2)  # sizeof(arr2[0]);
findCart(arr1, arr2, n1, n2)
# This code is contributed
# by Smitha Dinesh Semwal
````
````csharp
// C# Program to find the
// Cartesian Product of Two Sets
using System;
class GFG {
    static void findCart(int[] arr1, int[] arr2, int n,
                         int n1)
    {
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n1; j++)
                Console.Write("{" + arr1[i] + ", " + arr2[j]
                              + "}, ");
    }
    // Driver code
    public static void Main()
    {
        // first set
        int[] arr1 = { 1, 2, 3 };
        // second set
        int[] arr2 = { 4, 5, 6 };
        int n1 = arr1.Length;
        int n2 = arr2.Length;
        findCart(arr1, arr2, n1, n2);
    }
}
// This code is contributed by vt_m.
````
````javascript
<script>
// JavaScript Program to find the
// Cartesian Product of Two Set
    function findCart(arr1, arr2, n, n1)
    {
        for (let i = 0; i < n; i++)
          for (let j = 0; j < n1; j++)
            document.write("{"+ arr1[i]+", "
                             + arr2[j]+"}, ");
    }
// Driver Code
        // first set
        let arr1 = [ 1, 2, 3 ];
        // second set
        let arr2 = [4, 5, 6 ];
        let n1 = arr1.length;
        let n2 = arr2.length;
        findCart(arr1, arr2, n1, n2);
       // This code is contributed by chinmoy1997pal.
</script>
````
````php
<?php
// PHP Program to find the
// Cartesian Product of Two Sets
function findCart($arr1, $arr2, $n, $n1)
{
    for ($i = 0; $i < $n; $i++)
        for ( $j = 0; $j < $n1; $j++)
            echo "{", $arr1[$i] ," , ",
                      $arr2[$j], "}",",";
}
// Driver Code
// first set
$arr1 = array ( 1, 2, 3 );
// second set
$arr2 = array ( 4, 5, 6 );
$n1 = sizeof($arr1) ;
$n2 = sizeof($arr2);
findCart($arr1, $arr2, $n1, $n2);
// This code is contributed by m_kit.
?>
````
**Output**
```
{1, 4}, {1, 5}, {1, 6}, {2, 4}, {2, 5}, {2, 6}, {3, 4}, {3, 5}, {3, 6},
```
**Time complexity:** O(M\*N) where M and N are size of given sets
**Auxiliary space:** O(1) because it is using constant space for variables
**Practical Examples:** 
1) A set of playing cards is Cartesian product of a four element set to a set of 13 elements.
2) A two dimensional coordinate system is a Cartesian product of two sets of real numbers.
**Reference:** 
<https://en.wikipedia.org/wiki/Cartesian_product>
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/cartesian-product-two-sets/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Algebraic and Set-Theoretic Structures

> [!note] Related notes
>
> - [[Classes of Functions]]
> - [[Closure of Relations]]
> - [[Composition of Functions]]
> - [[Equivalence Relations]]
> - [[Groups]]
> - [[Hasse Diagrams]]
> - [[Introduction to Set Theory]]
> - [[Inverse Functions]]
> - [[Modular Addition]]
> - [[Multiplication Modulo]]
