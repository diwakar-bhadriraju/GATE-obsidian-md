---
title: "Power in Mathematics"
subject: "General Aptitude"
topic: "Quantitative Aptitude"
source: "https://www.geeksforgeeks.org/dsa/power-in-mathematics/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "General Aptitude/Quantitative Aptitude"
tags:
  - gate/cs
  - subject/general-aptitude
  - topic/quantitative-aptitude
---


> [!abstract] Power in Mathematics
> 
> **Subject:** `General Aptitude` &nbsp;|&nbsp; **Topic:** `Quantitative Aptitude`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/power-in-mathematics/)

---

# Power in Mathematics

The power of a number says how many times to use the number in a multiplication. Powers are also called Exponents or Indices. For example, 8^2 could be called "8 to the power 2" or "8 to the second power", or simply "8 squared". 
![](assets/12-min-1-5b8e6ff1f8.png)
**Some interesting fact about Power :**
1. If the indices is 1, then you just have the number itself. For example, 5^1 = 5
2. If the indices is 0, then you get 1. For example, 5^0 = 1
3. Exponents make it easier to write and use many multiplications
4. Negative exponent means how many times to divide one by the number.For example, 5^-1 = 1 /5 = 0.2
**How we check if a number is power of y for a given integer x ?**
**Naive solution:** 
Given two positive numbers x and y, check if y is a power of x or not.
**Examples :** 
```
Input:  x = 10, y = 1
Output: True
Input:  x = 10, y = 1000
Output: True
Input:  x = 10, y = 1001
Output: False
```
**Approach :** A simple solution is to repeatedly compute powers of x. If a power becomes equal to y, then y is a power, else not. 
````cpp
// C++ program to check if a number is power of
// another number
#include <bits/stdc++.h>
using namespace std;
/* Returns 1 if y is a power of x */
bool isPower(int x, long int y)
{
    // The only power of 1 is 1 itself
    if (x == 1)
        return (y == 1);
    // Repeatedly compute power of x
    long int pow = 1;
    while (pow < y)
        pow *= x;
    // Check if power of x becomes y
    return (pow == y);
}
/* Driver program to test above function */
int main()
{
    cout << (isPower(10, 1) ? "True" : "False") << endl;
    cout << (isPower(1, 20) ? "True" : "False") << endl;
    cout << (isPower(2, 128) ? "True" : "False") << endl;
    cout << (isPower(2, 30) ? "True" : "False") << endl;
    return 0;
}
````
````Java
// Java program to check if a number is power of
// another number
public class Test {
    // driver method to test power method
    public static void main(String[] args)
    {
        // check the result for true/false and print.
        System.out.println(isPower(10, 1) ? "True" : "False");
        System.out.println(isPower(1, 20) ? "True" : "False");
        System.out.println(isPower(2, 128) ? "True" : "False");
        System.out.println(isPower(2, 30) ? "True" : "False");
    }
    /* Returns true if y is a power of x */
    public static boolean isPower(int x, int y)
    {
        // The only power of 1 is 1 itself
        if (x == 1)
            return (y == 1);
        // Repeatedly compute power of x
        int pow = 1;
        while (pow < y)
            pow = pow * x;
        // Check if power of x becomes y
        return (pow == y);
    }
}
````
````Python3
# Python program to check
# if a number is power of
# another number
# Returns true if y is a
# power of x
def isPower (x, y):
    # The only power of 1
    # is 1 itself
    if (x == 1):
        return (y == 1)
    # Repeatedly compute
    # power of x
    pow = 1
    while (pow < y):
        pow = pow * x
    # Check if power of x
    # becomes y
    return (pow == y)
# Driver Code
# check the result for
# true/false and print.
if(isPower(10, 1)): print("True")
else: print("False")
if(isPower(1, 20)): print("True")
else: print("False")
if(isPower(2, 128)): print("True")
else: print("False")
if(isPower(2, 30)): print("True")
else: print("False")
````
````CSHARP
// C# program to check if a number
// is power of another number
using System;
class GFG
{
    // Returns true if y is a power of x
    public static bool isPower (int x, int y)
    {
        // The only power of 1 is 1 itself
        if (x == 1)
        return (y == 1);
        // Repeatedly compute power of x
        int pow = 1;
        while (pow < y)
        pow = pow * x;
        // Check if power of x becomes y
        return (pow == y);
    }
    // Driver Code
    public static void Main ()
    {
        //check the result for true/false and print.
        Console.WriteLine(isPower(10, 1) ? "True" : "False");
        Console.WriteLine(isPower(1, 20) ? "True" : "False");
        Console.WriteLine(isPower(2, 128) ? "True" : "False");
        Console.WriteLine(isPower(2, 30) ? "True" : "False");
    }
}
````
````php
<?php
// PHP program to check if a
// number is power of another number
/* Returns 1 if y is a power of x */
function isPower($x, $y)
{
    // The only power of 1 is 1 itself
    if ($x == 1)
        return ($y == 1 ? "True" : "False");
    // Repeatedly comput power of x
    $pow = 1;
    while ($pow < $y)
        $pow *= $x;
    // Check if power of x becomes y
    return ($pow == $y ? "True" : "False");
}
// Driver Code
echo isPower(10, 1) . "\n";
echo isPower(1, 20) . "\n";
echo isPower(2, 128) . "\n";
echo isPower(2, 30) . "\n";
?>
````
````javascript
<script>
// Javascript program to check if a number is power of
// another number
/* Returns 1 if y is a power of x */
function isPower( x, y)
{
    // The only power of 1 is 1 itself
    if (x == 1)
        return (y == 1);
    // Repeatedly comput power of x
    let  pow = 1;
    while (pow < y)
        pow *= x;
    // Check if power of x becomes y
    return (pow == y);
}
    // Driver Code
    document.write((isPower(10, 1) ? "True" : "False") + "</br>");
    document.write((isPower(1, 20) ? "True" : "False") + "</br>");
    document.write((isPower(2, 128) ? "True" : "False") + "</br>");
    document.write((isPower(2, 30) ? "True" : "False") + "</br>");
</script>
````
**Output:** 
```
True
False
True
False
```
Time complexity of above solution is O(Logxy)
Auxiliary Space: O(1)
**Basic Program related to Power :** 
- [Find unit digit of x raised to power y](https://www.geeksforgeeks.org/dsa/find-unit-digit-x-raised-power-y/)
- [Check if a number can be expressed as x^y (x raised to power y)](https://www.geeksforgeeks.org/dsa/check-if-a-number-can-be-expressed-as-xy-x-raised-to-power-y/)
- [Find the multiple of x which is closest to a^b](https://www.geeksforgeeks.org/dsa/find-the-multiple-of-x-which-is-closest-to-ab/)
- [All possible numbers of N digits and base B without leading zeros](https://www.geeksforgeeks.org/dsa/all-possible-numbers-of-n-digits-and-base-b-without-leading-zeros/)
- [Check if a number can be expressed as a^b | Set 2](https://www.geeksforgeeks.org/dsa/check-if-a-number-can-be-expressed-as-ab-set-2/)
- [Write you own Power without using multiplication(\*) and division(/) operators](https://www.geeksforgeeks.org/dsa/write-you-own-power-without-using-multiplication-and-division/)
**More problems related to Powers :**
- [Total number of subsets in which the product of the elements is even](https://www.geeksforgeeks.org/dsa/total-number-of-subsets-in-which-the-product-of-the-elements-is-even/)
- [Sum of first N natural numbers which are not powers of K](https://www.geeksforgeeks.org/dsa/sum-of-first-n-natural-numbers-which-are-not-powers-of-k/)
- [GCD of a number raised to some power and another number](https://www.geeksforgeeks.org/dsa/gcd-of-a-number-raised-to-some-power-and-another-number/)
- [Largest N digit number divisible by given three numbers](https://www.geeksforgeeks.org/dsa/largest-n-digit-number-divisible-by-given-three-numbers/)
- [Check whether a given Number is Power-Isolated or not](https://www.geeksforgeeks.org/dsa/check-whether-a-given-number-is-power-isolated-or-not/)
[**Recent Articles on Power!**](https://www.geeksforgeeks.org/tag/maths-power/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/power-in-mathematics/)

## GATE CS

- Subject: General Aptitude
- Topic: Quantitative Aptitude

> [!note] Related notes
>
> - [[Bar Graph]]
> - [[Elementary Statistics and Probability]]
> - [[Exponents]]
> - [[Line Graphs]]
> - [[Logarithms]]
> - [[Mensuration and Geometry]]
> - [[Percentages]]
> - [[Permutations and Combinations]]
> - [[Pie Chart]]
> - [[Ratio and Proportion]]
