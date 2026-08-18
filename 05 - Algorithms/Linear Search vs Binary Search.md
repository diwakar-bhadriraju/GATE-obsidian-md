---
title: "Linear Search vs Binary Search"
subject: "Algorithms"
topic: "Searching, Sorting, Technique-based Theorem and Hashing"
source: "https://www.geeksforgeeks.org/dsa/linear-search-vs-binary-search/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Algorithms/Searching, Sorting, Technique-based Theorem and Hashing"
tags:
  - gate/cs
  - subject/algorithms
  - topic/searching-sorting-technique-based-theorem-and-hashing
---


> [!abstract] Linear Search vs Binary Search
> 
> **Subject:** `Algorithms` &nbsp;|&nbsp; **Topic:** `Searching, Sorting, Technique-based Theorem and Hashing`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/linear-search-vs-binary-search/)

---

# Linear Search vs Binary Search

#### Prerequisites:
- [Linear Search](https://www.geeksforgeeks.org/dsa/linear-search/)
- [Binary Search](https://www.geeksforgeeks.org/dsa/binary-search/)
### **Important Differences**
| **Linear Search** | **Binary Search** |
| In linear search input data need not to be in sorted. | In binary search input data need to be in sorted order. |
| It is also called sequential search. | It is also called half-interval search. |
| The time complexity of linear search **O(n)**. | The time complexity of binary search **O(log n)**. |
| Multidimensional array can be used. | Only single dimensional array is used. |
| Linear search performs equality comparisons. | Binary search performs ordering comparisons. |
| It is less complex. | It is more complex. |
| It is very slow process. | It is very fast process. |
### LINEAR SEARCH
> Suppose we are searching a target element in an array. In linear search we begin with the first position of the array, and traverse the whole array in order to find the target element. If we find the target element we return the index of the element. Otherwise, we will move to the next position. If we arrive at the last position of an array and still can not find the target, we return -1. This is called the Linear search or Sequential search.
**Working :**
````cpp
#include <iostream>
#include <vector>
using namespace std;
int search(vector<int> &arr, int target){
    int n = arr.size();
    // Iterate linearly through the array
    for (int i = 0; i < n; i++)
        if (arr[i] == target)
            return i;
    return -1;
}
int main() {
    vector<int> arr = {2, 3, 4, 7, 1, 5};
    int target = 7;
    int index = search(arr, target);
    cout<<index<<endl;
    return 0;
}
````
````c
#include <stdio.h>
int search(int arr[], int n, int target) {
    // Iterate linearly through the array
    for (int i = 0; i < n; i++)
        if (arr[i] == target)
            return i;
    return -1;
}
int main() {
    int arr[] = {2, 3, 4, 7, 1, 5};
    int n = sizeof(arr) / sizeof(arr[0]);
    int target = 7;
    int index = search(arr, n, target);
    printf("%d\n", index);
    return 0;
}
````
````java
public class GFG {
    public static int search(int[] arr, int target) {
        int n = arr.length;
        // Iterate linearly through the array
        for (int i = 0; i < n; i++)
            if (arr[i] == target)
                return i;
        return -1;
    }
    public static void main(String[] args) {
        int[] arr = {2, 3, 4, 7, 1, 5};
        int target = 7;
        int index = search(arr, target);
        System.out.println(index);
    }
}
````
````python
def search(arr, target):
    n = len(arr)
    # Iterate linearly through the array
    for i in range(n):
        if arr[i] == target:
            return i
    return -1
if __name__ == "__main__":
    arr = [2, 3, 4, 7, 1, 5]
    target = 7
    index = search(arr, target)
    print(index)
````
````csharp
using System;
class GFG{
    static int search(int[] arr, int target) {
        int n = arr.Length;
        // Iterate linearly through the array
        for (int i = 0; i < n; i++)
            if (arr[i] == target)
                return i;
        return -1;
    }
    static void Main() {
        int[] arr = {2, 3, 4, 7, 1, 5};
        int target = 7;
        int index = search(arr, target);
        Console.WriteLine(index);
    }
}
````
````javascript
function search(arr, target) {
    const n = arr.length;
    // Iterate linearly through the array
    for (let i = 0; i < n; i++)
        if (arr[i] === target)
            return i;
    return -1;
}
// Driver Code
const arr = [2, 3, 4, 7, 1, 5];
const target = 7;
const index = search(arr, target);
console.log(index);
````
**Output**
```
3
```
**Time Complexity:** O(n), where n is the size of the input array. The worst-case scenario is when the target element is not present in the array, and the function has to go through the entire array to figure that out.
**Auxiliary Space:** O(1), the function uses only a constant amount of extra space to store variables. The amount of extra space used does not depend on the size of the input array.
### BINARY SEARCH
> Binary Search is a more optimized form of searching algorithm. It cuts down the search space in halves achieving logarithmic time complexity on a sorted data. We take two extremes lower bound and upper bound and compare our target element with the middle element. In the process we discard one half where we are sure our target element can not be found and update our lower and upper bound accordingly.
**Working :**
````cpp
#include <iostream>
#include <vector>
using namespace std;
int binarySearch(vector<int> &arr, int target, int low, int high) {
    // Repeat until the pointers low and
    // high meet each other
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == target)
            return mid;
        if (arr[mid] < target)
            low = mid + 1;
        else
            high = mid - 1;
    }
    return -1;
}
int main(){
    vector<int> arr = {2, 3, 4, 7, 9, 10};
    int n = arr.size();
    int target = 7;
    int low = 0;
    int high = n;
    int index = binarySearch(arr, target, low, high);
    cout<<index<<endl;
    return  0;
}
````
````c
#include <stdio.h>
int binarySearch(int arr[], int target, int low, int high) {
    // Repeat until the pointers low and
    // high meet each other
    while (low <= high) {
        int mid = low + (high - low) / 2;
        if (arr[mid] == target)
            return mid;
        if (arr[mid] < target)
            low = mid + 1;
        else
            high = mid - 1;
    }
    return -1;
}
int main() {
    int arr[] = {2, 3, 4, 7, 9,10};
    int n = sizeof(arr) / sizeof(arr[0]);
    int target = 7;
    int low = 0;
    int high = n;
    int index = binarySearch(arr, target, low, high);
    printf("%d\n", index);
    return 0;
}
````
````java
public class GFG {
    // Repeat until the pointers low and
    // high meet each other
    public static int binarySearch(int[] arr, int target, int low, int high) {
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (arr[mid] == target)
                return mid;
            if (arr[mid] < target)
                low = mid + 1;
            else
                high = mid - 1;
        }
        return -1;
    }
    public static void main(String[] args) {
        int[] arr = {2, 3, 4, 7, 9, 10};
        int n = arr.length;
        int target = 7;
        int low = 0;
        int high = n;
        int index = binarySearch(arr, target, low, high);
        System.out.println(index);
    }
}
````
````python
def binarySearch(arr, target, low, high):
    # Repeat until the pointers low and
    # high meet each other
    while low <= high:
        mid = low + (high - low) // 2
        if arr[mid] == target:
            return mid
        if arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1
if __name__ == "__main__":
    arr = [2, 3, 4, 7, 9, 10]
    n = len(arr)
    target = 7
    low = 0
    high = n
    index = binarySearch(arr, target, low, high)
    print(index)
````
````csharp
using System;
class GFG {
    static int binarySearch(int[] arr, int target, int low, int high) {
        // Repeat until the pointers low and
        // high meet each other
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (arr[mid] == target)
                return mid;
            if (arr[mid] < target)
                low = mid + 1;
            else
                high = mid - 1;
        }
        return -1;
    }
    static void Main() {
        int[] arr = {2, 3, 4, 7, 9, 10};
        int n = arr.Length;
        int target = 7;
        int low = 0;
        int high = n;
        int index = binarySearch(arr, target, low, high);
        Console.WriteLine(index);
    }
}
````
````javascript
function binarySearch(arr, target, low, high) {
    // Repeat until the pointers low and
    // high meet each other
    while (low <= high) {
        const mid = low + Math.floor((high - low) / 2);
        if (arr[mid] === target)
            return mid;
        if (arr[mid] < target)
            low = mid + 1;
        else
            high = mid - 1;
    }
    return -1;
}
// Driver Code
const arr = [2, 3, 4, 7, 9, 10];
const n = arr.length;
const target = 7;
const low = 0;
const high = n;
const index = binarySearch(arr, target, low, high);
console.log(index);
````
**Output**
```
3
```
**Time Complexity:** O(log n) - Binary search algorithm divides the input array in half at every step, reducing the search space by half, and hence has a time complexity of logarithmic order.
**Auxiliary Space:** O(1) - Binary search algorithm requires only constant space for storing the low, high, and mid indices, and does not require any additional data structures, so its auxiliary space complexity is O(1).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/linear-search-vs-binary-search/)

## GATE CS

- Subject: Algorithms
- Topic: Searching, Sorting, Technique-based Theorem and Hashing

> [!note] Related notes
>
> - [[Binary Search]]
> - [[Introduction to Searching Algorithms]]
> - [[Linear Search]]
> - [[Applications of Depth First Search]]
> - [[Asymptotic Notations]]
> - [[Breadth First Traversal or BFS for a Graph]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Dijkstra’s Algorithm for Adjacency List Representation]]
> - [[Efficient Huffman Coding for Sorted Input]]
> - [[Fractional Knapsack Problem]]
