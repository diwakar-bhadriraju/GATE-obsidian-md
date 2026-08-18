---
title: "Array Notes for GATE Exam [2024]"
subject: "Data Structures & C Programming"
topic: "Arrays"
source: "https://www.geeksforgeeks.org/dsa/array-notes-for-gate-exam/#introduction-to-arrays"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Arrays"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/arrays
---


> [!abstract] Array Notes for GATE Exam [2024]
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Arrays`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/array-notes-for-gate-exam/#introduction-to-arrays)

---

# Array Notes for GATE Exam [2024]

**Arrays** are fundamental data structures in computer science, and mastering them is crucial for success in the **GATE exam**. This article aims to provide concise yet comprehensive notes on **arrays**, covering essential concepts and strategies to help you tackle array-related questions in the **GATE 2024 exam**.
Table of Content
- [Introduction to Arrays](#introduction-to-arrays)
- [Basic terminologies of the array](#basic-terminologies-of-the-array)
- [Representation of Array](#representation-of-array)
- [Types of arrays](#types-of-arrays)
- [Finding Adress of an Element in Array](#finding-adress-of-an-element-in-array)
- [Calculating the address of any element In the 1-D array](#calculating-the-address-of-any-element-in-the-1d-array)
- [Calculate the address of any element in the 2-D array](#calculate-the-address-of-any-element-in-the-2d-array)
- [Calculate the address of any element in the 3-D Array](#calculate-the-address-of-any-element-in-the-3d-array)
- [Previously Asked GATE Questions on Arrays](#previously-asked-gate-questions-on-arrays)
## Introduction to Arrays:
> **An** **array** **is a collection of items of the same variable type that are stored at contiguous memory locations. It’s one of the most popular and simple data structures and is often used to implement other data structures. Each item in an array is indexed starting with 0.**
## **Basic terminologies of the array:**
- **Array Index:** In an array, elements are identified by their indexes. Array index starts from 0.
- **Array element:**Elements are items stored in an array and can be accessed by their index.
- **Array Length:** The length of an array is determined by the number of elements it can contain.
## **Representation of Array**:
The representation of an array can be defined by its declaration. A declaration means allocating memory for an array of a given size.
![](assets/array-95b1c08dfb.png)
Representation of Array
Arrays can be declared in various ways in different languages. For better illustration, below are some language-specific array declarations.
![](assets/Arraydeclaration-660x168-266a6e5baa.png)
````cpp
int arr[5]; // This array will store integer type element
char arr[10]; // This array will store char type element
float arr[20]; // This array will store float type element
````
````c
int arr[5]; // This array will store integer type element
char arr[10]; // This array will store char type element
float arr[20]; // This array will store float type element
````
````java
/* Static Arrays are arrays that are declared before runtime
and are assigned values while writing the code.
*/
// The syntax of declaring a static array is:
<data type><variable name>[]
    = {<data1>, <data2>,…..<dataN> };
// Example:
int arr[] = { 2, 5, 6, 9, 7, 4, 3 };
````
````python3
# Python code
arr = [10, 20, 30]  # This array will store integer
arr2 = ['c', 'd', 'e']  # This array will store characters
arr3 = [28.5, 36.5, 40.2]  # This array will store floating elements
````
````csharp
int[] arr = new int[5]; // This array will store integer
                        // type element
````
````javascript
// JS code
let arr=[10,20,30]; // This array will store integer
let arr2 = ['c', 'd', 'e'] // This array will store characters
let arr3 = [28.5, 36.5, 40.2] // This array will store floating elements
````
However, the above declaration is **static** or **compile-time** memory allocation, which means that the array element’s memory is allocated when a program is compiled. Here only a fixed size (i,e. the size that is mentioned in square brackets **[]**) of memory will be allocated for storage, but don’t you think it will not be the same situation as we know the size of the array every time, there might be a case where we don’t know the size of the array. If we declare a larger size and store a lesser number of elements will result in a wastage of memory or either be a case where we declare a lesser size then we won’t get enough memory to store the rest of the elements. In such cases, static memory allocation is not preferred.
## **Types of arrays:**
There are mainly three types of arrays:
1. One Dimensional Array
2. Two Dimensional Array
3. Three-Dimensional Array
### **1.** [**One Dimensional Array**](https://www.geeksforgeeks.org/c/c-arrays/)**:**
- It is a list of the variable of similar [data types](https://www.geeksforgeeks.org/cpp/cpp-data-types/).
- It allows random access and all the elements can be accessed with the help of their index.
- The size of the array is fixed.
- For a dynamically sized array, [vector](https://www.geeksforgeeks.org/cpp/vector-in-cpp-stl/) can be used in [C++](https://www.geeksforgeeks.org/cpp/c-plus-plus/)
Representation of 1D array:
![](assets/array-2-88831db4e4.png)
Representation of the 1D array
### **2. Two Dimensional Array:**
- It is a list of lists of the variable of the same data type.
- It also allows random access and all the elements can be accessed with the help of their index.
- It can also be seen as a collection of 1D arrays. It is also known as the Matrix.
- Its dimension can be increased from 2 to 3 and 4 so on.
- They all are referred to as a [multi-dimension](https://www.geeksforgeeks.org/c/multidimensional-arrays-in-c/) array.
- The most common multidimensional array is a 2D array.
Representation of 2 D array:
![](assets/two-d-fa7af94feb.png)
Representation of 2D Array
### **3. Three-Dimensional Array:**
A **Three Dimensional Array** or **3D** array in C is a collection of two-dimensional arrays. It can be visualized as multiple 2D arrays stacked on top of each other.
![](assets/3D-array-60659d6c42.jpg)
Representation of 3D array
**Declaration of Three-Dimensional Array:**
We can declare a 3D array with **x** 2D arrays each having **y** rows and **z** columns using the syntax shown below.
**Syntax:**
```
data_type array_name[x][y][z];
```
- **data\_type:** Type of data to be stored in each element.
- **array\_name:** name of the array
- **x:** Number of 2D arrays.
- **y:** Number of rows in each 2D array.
- **z:**Number of columns in each 2D array.
## Finding Adress of an Element in Array
When it comes to organizing and accessing elements in a multi-dimensional array, two prevalent methods are **Row Major Order** and **Column Major Order**.
### **1. Row Major Order**
Row major ordering assigns successive elements, moving across the rows and then down the next row, to successive memory locations. In simple language, the elements of an array are stored in a Row-Wise fashion.
To find the address of the element using row-major order uses the following formula:
> **Address of A[I][J] = B + W \* ((I – LR) \* N + (J – LC))**
>
> I = Row Subset of an element whose address to be found, 
> J = Column Subset of an element whose address to be found, 
> B = Base address, 
> W = Storage size of one element store in an array(in byte), 
> LR = Lower Limit of row/start row index of the matrix(If not given assume it as zero), 
> LC = Lower Limit of column/start column index of the matrix(If not given assume it as zero), 
> N = Number of column given in the matrix.
### **2. Column Major Order**
If elements of an array are stored in a column-major fashion means moving across the column and then to the next column then it’s in column-major order. To find the address of the element using column-major order use the following formula:
> **Address of A[I][J] = B + W \* ((J – LC) \* M + (I – LR))**
>
> I = Row Subset of an element whose address to be found, 
> J = Column Subset of an element whose address to be found, 
> B = Base address, 
> W = Storage size of one element store in any array(in byte), 
> LR = Lower Limit of row/start row index of matrix(If not given assume it as zero), 
> LC = Lower Limit of column/start column index of matrix(If not given assume it as zero), 
> M = Number of rows given in the matrix.
## [**Calculating the address of any element In the 1-D array:**](https://www.geeksforgeeks.org/dsa/calculation-of-address-of-element-of-1-d-2-d-and-3-d-using-row-major-and-column-major-order/)
A 1-dimensional array (or single-dimension array) is a type of [linear array](https://www.geeksforgeeks.org/dsa/array-data-structure-guide/). Accessing its elements involves a single subscript that can either represent a row or column index. 
**Example:**
![](assets/1darray-9a099139b7.jpg)
1D array
**To find the address of an element in an array the following formula is used:**
> **Address of A[I] = B + W \* (I – LB)**
>
> I = Subset of element whose address to be found, 
> B = Base address, 
> W = Storage size of one element store in any array(in byte), 
> LB = Lower Limit/Lower Bound of subscript(If not specified assume zero).
**Example**:** Given the base address of an array **A[1300 ………… 1900]** as **1020** and the size of each element is 2 bytes in the memory, find the address of **A[1700].** 
**Solution**:**
> **Given:**
> Base address B = 1020
> Lower Limit/Lower Bound of subscript LB = 1300
> Storage size of one element store in any array W = 2 Byte
> Subset of element whose address to be found I = 1700
>
> **Formula used:**
> Address of A[I] = B + W \* (I – LB)
>
> **Solution:**
> Address of A[1700] = 1020 + 2 \* (1700 – 1300)
>                               = 1020 + 2 \* (400)
>                               = 1020 + 800
> Address of A[1700] = 1820
## [**Calculate the address of any element in the 2-D array:**](https://www.geeksforgeeks.org/dsa/calculation-of-address-of-element-of-1-d-2-d-and-3-d-using-row-major-and-column-major-order/)
The 2-dimensional array can be defined as an array of arrays. The 2-Dimensional arrays are organized as matrices which can be represented as the collection of rows and columns as array[M][N] where M is the number of rows and N is the number of columns. 
**Example**:**
![](assets/Matrix-4412d32c6a.jpg)
2-D Array
**Finding address of an element using Row Major Order**:**
Given an array, **arr[1………10][1………15]** with base value **100** and the size of each element is **1 Byte** in memory. Find the address of **arr[8][6]** with the help of row-major order.
**Solution**:**
> **Given:**
> Base address B = 100
> Storage size of one element store in any array W = 1 Bytes
> Row Subset of an element whose address to be found I = 8
> Column Subset of an element whose address to be found J = 6
> Lower Limit of row/start row index of matrix LR = 1 
> Lower Limit of column/start column index of matrix = 1
> Number of column given in the matrix N = Upper Bound – Lower Bound + 1
>                                                                             = 15 – 1 + 1
>                                                                             = 15
>
> **Formula:**
> Address of A[I][J] = B + W \* ((I – LR) \* N + (J – LC)) 
>
> **Solution:**
> Address of A[8][6] = 100 + 1 \* ((8 – 1) \* 15 + (6 – 1))
>                                    = 100 + 1 \* ((7) \* 15 + (5))
>                                   = 100 + 1 \* (110)
> Address of A[I][J] = 210
**Finding address of an element using Column Major Order**:**
Given an array **arr[1………10][1………15]** with a base value of **100** and the size of each element is **1 Byte** in memory find the address of arr[8][6] with the help of column-major order.
**Solution**:**
> **Given:**
> Base address B = 100
> Storage size of one element store in any array W = 1 Bytes
> Row Subset of an element whose address to be found I = 8
> Column Subset of an element whose address to be found J = 6
> Lower Limit of row/start row index of matrix LR = 1
> Lower Limit of column/start column index of matrix = 1
> Number of Rows given in the matrix M = Upper Bound – Lower Bound + 1
>                                                                             = 10 – 1 + 1
>                                                                            = 10
>
> **Formula: used**
> Address of A[I][J] = B + W \* ((J – LC) \* M + (I – LR))
> Address of A[8][6] = 100 + 1 \* ((6 – 1) \* 10 + (8 – 1))
>                                   = 100 + 1 \* ((5) \* 10 + (7))
>                                  = 100 + 1 \* (57)
> Address of A[I][J] = 157 
From the above examples, it can be observed that for the same position two different address locations are obtained that’s because in row-major order movement is done across the rows and then down to the next row, and in column-major order, first move down to the first column and then next column. So both the answers are right.
## [**Calculate the address of any element in the 3-D Array:**](https://www.geeksforgeeks.org/dsa/calculation-of-address-of-element-of-1-d-2-d-and-3-d-using-row-major-and-column-major-order/)
A **3-Dimensional** array is a collection of 2-Dimensional arrays. It is specified by using three subscripts:
1. Block size
2. Row size
3. Column size
More dimensions in an array mean more data can be stored in that array. 
**Example:**
![](assets/3darray-ac8aba305b.jpg)
3-D Array
To find the address of any element in 3-Dimensional arrays there are the following two ways:
- Row Major Order
- Column Major Order
**Row Major Order:**
To find the address of the element using row-major order, use the following formula:
> **Address of A[i][j][k] = B + W \*(M \* N \* (i-x) + N \*(j-y) + (k-z))**
>
> Here:
>
> B = Base Address (start address)
> W = Weight (storage size of one element stored in the array)
> M = Row (total number of rows)
> N = Column (total number of columns)
> P = Width (total number of cells depth-wise)
> x = Lower Bound of Row
> y = Lower Bound of Column
> z = Lower Bound of Width
**Example**:** Given an array, **arr[1:9, -4:1, 5:10]** with a base value of **400** and the size of each element is **2 Bytes** in memory find the address of element **arr[5][-1][8]** with the help of row-major order?
**Solution**:**
> **Given:**
> Block Subset of an element whose address to be found I = 5
> Row Subset of an element whose address to be found J = -1 
> Column Subset of an element whose address to be found K = 8
> Base address B = 400
> Storage size of one element store in any array(in Byte) W = 2
> Lower Limit of blocks in matrix x = 1
> Lower Limit of row/start row index of matrix y = -4 
> Lower Limit of column/start column index of matrix z = 5
> M(row) = Upper Bound – Lower Bound + 1 = 1 – (-4) + 1 = 6
> N(Column)= Upper Bound – Lower Bound + 1 = 10 – 5 + 1 = 6
>  
>
> **Formula used:**                                            
> Address of[I][J][K] =B + W (M \* N(i-x) + N \*(j-y) + (k-z))
>
> **Solution:**
> Address of arr[5][-1][8] = 400 + 2 \* {[6 \* 6 \* (5 – 1)] + 6 \* [(-1 + 4)]} + [8 – 5]
>                              = 400 + 2 \* (6\*6\*4)+(6\*3)+3
>                             = 400 + 2 \* (165)
>                            = 730
**Column Major Order:**
To find the address of the element using column-major order, use the following formula:1
> **Address of A[i][j][k]= B + W(M \* N(i – x) + M \*(k – z) + (j – y))**
>
> Here:
>
> B = Base Address (start address)
> W = Weight (storage size of one element stored in the array)
> M = Row (total number of rows)
> N = Column (total number of columns)
> P = Width (total number of cells depth-wise)
> x = Lower Bound of block (first subscipt)
> y = Lower Bound of Row
> z = Lower Bound of Column
**Example**:** Given an array **arr[1:8, -5:5, -10:5]** with a base value of **400** and the size of each element is **4 Bytes** in memory find the address of element **arr[3][3][3]** with the help of column-major order ?
**Solution**:**
> **Given:**
> Row Subset of an element whose address to be found I = 3
> Column Subset of an element whose address to be found J = 3
> Block Subset of an element whose address to be found K = 3
> Base address B = 400
> Storage size of one element store in any array(in Byte) W = 4
> Lower Limit of blocks in matrix x = 1
> Lower Limit of row/start row index of matrix y = -5
> Lower Limit of column/start column index of matrix z = -10
> M (row)= Upper Bound - Lower Bound + 1 = 8 - 1 + 1 = 8
> N (column)= Upper Bound - Lower Bound + 1 = 5 - (-5 ) + 1 = 11
>
> **Formula used:**
> Address of A[i][j][k]=B+W×(M×P×(k−z)+M×(j−y)+(i−x))
>
> **Solution:**
> Address of arr[3][3][3] = 400 + 4 \* ((11\*8\*(3-(-10)+ 8\*(3-(-5)+ (3-1))
>                                     = 400 + 4 \* ((88 \* 13+ 8 \* 8 + 2)
>                                    = 400 + 4 \* (1210)
>                                   = 400 + 4840                        
>                                  = 5240
## Previously Asked GATE Questions on Arrays:
**Question 1:** A program **P** reads in 500 integers in the range [0..100] representing the scores of 500 students. It then prints the frequency of each score above 50. What would be the best way for **P** to store the frequencies?
(a) An array of 50 numbers.
(b) An array of 100 numbers.
(c) An array of 500 numbers.
(d) A dynamically allocated array of 550 numbers
> **Answer**: (a)
> **Explanation:** An array of 50 numbers is correct.
**Question 2:** What will the output of the below code?
````cpp
#include <iostream>
using namespace std;
int main()
{
    int arr[2] = { 1, 2 };
    cout << 0 [arr] << ", " << 1 [arr] << endl;
    return 0;
}
````
````java
public class Main {
    public static void main(String[] args) {
        // Declare and initialize an array
        int[] arr = { 1, 2 };
        // Access array elements using the index directly in Java
        System.out.println(arr[0] + ", " + arr[1]);
    }
}
````
````python3
# Equivalent Python code
arr = [1, 2]
print(arr[0], ", ", arr[1])
````
````csharp
using System;
class Program
{
    static void Main()
    {
        // Declare and initialize an array of integers
        int[] arr = { 1, 2 };
        // Print the values using array indexing
        Console.WriteLine(arr[0] + ", " + arr[1]);
    }
}
````
````javascript
// Declare an array with two elements
const arr = [1, 2];
// Access and print the first element using array indexing
console.log(arr[0]);
// Print a comma separator
console.log(', ');
// Access and print the second element using array indexing
console.log(arr[1]);
````
(a) 1, 2
(b) Syntax error
(c) Run time error
(d) None
> **Answer**: (a)
> **Explanation:** 0[arr]] is a different way to represent array element, which represents the first element of the array.
> similarly, 1[arr] is a different way to represent array element, which represents the second element of the array.
**Question 3:** The minimum number of comparisons required to determine if an integer appears more than **n/2** times in a sorted array of **n** integers is
(a) O(n)
(b) O(log(n))
(c) O(nlog(n))
(d) O(1)
> **Answer**: (b)
> **Explanation:**If you answered Theta(1), then think of examples {1, 2, 2, 2, 4, 4}, {1, 1, 2, 2, 2, 2, 3, 3} The Best way to find out whether an integer appears more than n/2 times in a sorted array(Ascending Order) of n integers, would be binary search approach.
>
> 1. The First occurrence of an element can be found out in O(log(n)) time using divide and conquer technique,lets say it is i.
> 2. The Last occurrence of an element can be found out in O(log(n)) time using divide and conquer technique,lets say it is j.
> 3. Now number of occurrence of that element(count) is (j-i+1). Overall time complexity = log n +log n +1 = O(log(n)).
**Question 4:** Let **A** be a square matrix of size n x n. Consider the following program. What is the expected output? 
```
C = 100for i = 1 to n do    for j = 1 to n do    {        Temp = A[i][j] + C        A[i][j] = A[j][i]        A[j][i] = Temp - C    } for i = 1 to n do    for j = 1 to n do        Output(A[i][j]);
```
> **Answer**: 1
> **Explanation:** If we take look at the inner statements of first loops, we can notice that the statements swap A[i][j] and A[j][i] for all i and j. Since the loop runs for all elements, every element A[l][m] would be swapped twice, once for i = l and j = m and then for i = m and j = l. Swapping twice means the matrix doesn’t change.
**Question 5:** An algorithm performs **(logN)**1/**2 find operations, **N** insert operations, **(logN)**1/2** delete operations, and **(logN)**1/2** decrease-key operations on a set of data items with keys drawn from a linearly ordered set. For a delete operation, a pointer is provided to the record that must be deleted. For the decrease-key operation, a pointer is provided to the record that has its key decreased. Which one of the following data structures is the most suited for the algorithm to use, if the goal is to achieve the best total asymptotic complexity considering all the operations?
(a) Unsorted array
(b) Min-heap
(c) Sorted array
(d) Sorted doubly linked list
> **Answer**: (a)
> **Explanation:**The time complexity of insert in unsorted array is O(1), O(Logn) in Min-Heap, O(n) in sorted array and sorted DLL.
>
> - For unsorted array, we can always insert an element at end and do insert in O(1) time
> - For Min Heap, insertion takes O(Log n) time. Refer[Binary Heap operations](https://www.geeksforgeeks.org/quizzes/) for details.
> - For sorted array, insert takes O(n) time as we may have to move all elements worst case.
> - For sorted doubly linked list, insert takes O(n) time to find position of element to be inserted.
**Question 6:** Consider an array consisting of **–ve** and **+ve** numbers. What would be the worst case time complexity of an algorithm to segregate the numbers having same sign altogether i.e all +ve on one side and then all **-ve** on the other ?
(a) O(N)
(b) O(Nlog(N))
(c) O(N\*N)
(d) O(Nlog(log(N)))
> **Answer**: (c)
> **Explanation:** Here we can use the partition algorithm of [quick sort](https://www.geeksforgeeks.org/dsa/quick-sort-algorithm/) for segregation and answer will be O(N\*N). Choose the first element as pivot whatever may be its sign we don’t care and keep an extra index at pivot position.
**Question 7:** Let **A[1...n]** be an array of **n** distinct numbers. If **i < j** and **A[i] > A[j]**, then the pair (i, j) is called an inversion of **A**. What is the expected number of inversions in any permutation on **n** elements ?
(a) n(n-1)/2
(b) n(n-1)/4
(c) n(n+1)/4
(d) 2nlog(n)
> **Answer**: (b)
> **Explanation:**There are n(n-1)/2 pairs such that i < j. For a pair (ai, aj), probability of being inversion is 1/2. Therefore expected value of inversions = 1/2 \* (n(n-1)/2) = n(n-1)/4**.**
**Question 8:** Consider the following array declaration in the 'C' language:
```
int array 1[] = {2, 3};int array2[3]={9};What will be the output of the following print statement?printf(“%d, %d”, array1 [1], array2 [2]);
```
(a) 2, 0
(b) 3, 0
(c) 2, 9
(d) 4, 9
> **Answer**: (b)
**Question 9:** Consider the following C program.
```cpp
#include < stdio.h >int main () {    int a [4] [5] = {{1, 2, 3, 4, 5},                           {6, 7, 8, 9, 10},                           {11, 12, 13, 14, 15},                           {16, 17, 18, 19, 20}};    printf (“%d\n”, *(*(a+**a+2) +3));    return (0);}
```
The output of the program is \_\_\_\_\_\_\_.
> **Answer**: 19
**Question 10:** Which operations can not be done in O(1) for an array of sorted data.
(a) Print the nth largest element
(b) Print the nth smallest element
(c) Delete element
(d) None of the above
> **Answer**: (c)
> **Explanation:** If we have to delete x and its index is last, it would take O(n).
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/array-notes-for-gate-exam/#introduction-to-arrays)

## GATE CS

- Subject: Data Structures & C Programming
- Topic: Arrays

> [!note] Related notes
>
> - [[1D, 2D and 3D Arrays]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Data Types in C]]
> - [[Double Hashing]]
> - [[Enum, Struct & Union in C]]
> - [[Functions in C]]
> - [[I ntroduction to Trees]]
> - [[Introduction to C Programming]]
> - [[Introduction to Graphs]]
> - [[Introduction to Hashing]]
