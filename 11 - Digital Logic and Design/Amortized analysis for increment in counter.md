---
title: "Amortized analysis for increment in counter"
subject: "Digital Logic and Design"
topic: "Sequential Circuit"
source: "https://www.geeksforgeeks.org/dsa/amortized-analysis-increment-counter/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Sequential Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/sequential-circuit
---


> [!abstract] Amortized analysis for increment in counter
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Sequential Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/amortized-analysis-increment-counter/)

---

# Amortized analysis for increment in counter

[**Amortized analysis**](https://www.geeksforgeeks.org/dsa/introduction-to-amortized-analysis/) refers to determining the time-averaged running time for a sequence (not an individual) operation. It is different from average case analysis because here, we don't assume that the data arranged in average (not very bad) fashion like we do for average case analysis for [quick sort](https://www.geeksforgeeks.org/dsa/quick-sort-algorithm/). That is, amortized analysis is worst case analysis but for a sequence of operation rather than an individual one. It applies to the method that consists of the sequence of operation, where a vast majority of operations are cheap but some of the operations are expensive. This can be visualized with the help of binary counter which is implemented below.
Let's see this by implementing an increment counter in C. First, let's see how counter increment works. 
Let a variable **i** contains a value 0 and we performs i++ many time. Since on hardware, every operation is performed in binary form. Let binary number stored in 8 bit. So, value is 00000000. Let's increment many time. So, the pattern we find are as :
00000000, 00000001, 00000010, 00000011, 00000100, 00000101, 00000110, 00000111, 00001000 and so on .....
**Steps :** 
**1.** Iterate from rightmost and make all one to zero until finds first zero. 
**2.** After iteration, if index is greater than or equal to zero, then make zero lie on that position to one.
````cpp
#include <bits / stdc++.h>
using namespace std;
int main()
{
    char str[] = "10010111";
    int length = strlen(str);
    int i = length - 1;
    while (str[i] == '1') {
        str[i] = '0';
        i--;
    }
    if (i >= 0)
        str[i] = '1';
    printf("% s", str);
}
````
````java
import java.util.*;
class GFG{
public static void main(String args[])
{
    String st = "10010111";
    char[] str = st.toCharArray();
    int lengthh = st.length();
    int i = lengthh - 1;
    while (str[i] == '1')
    {
        str[i] = '0';
        i--;
    }
    if (i >= 0)
        str[i] = '1';
     System.out.print( str);
}
}
// This code is contributed by sanjoy_62
````
````python3
# Python code for above approach
str = "10010111"
length=len(str)
i=length-1
while(str[i]=='1'):
    str=str[:i]+'0'+str[i+1:]
    i=i-1
if(i>=0):
    str=str[:i]+'1'+str[i+1:]
print(str)
# This code is contributed by Pushpesh Raj.
````
````csharp
using System;
public class GFG{
public static void Main(String []args)
{
    String st = "10010111";
    char[] str = st.ToCharArray();
    int lengthh = st.Length;
    int i = lengthh - 1;
    while (str[i] == '1')
    {
        str[i] = '0';
        i--;
    }
    if (i >= 0)
        str[i] = '1';
     Console.Write( str);
}
}
// This code is contributed by Rajput-Ji
````
````javascript
    // Javascript code for above approach
        let str = "10010111";
        let length = str.length;
        let i = length - 1;
        while (str[i] == '1') {
            str = str.slice(0,i)+'0'+str.slice(i+1,length);
            i--;
        }
        if (i >= 0)
            str=str.slice(0,i)+'1'+str.slice(i+1,length);
        console.log(str);
    // This code is contributed by Aman Kumar
````
**Output:**
```
10011000
```
**Time complexity:** O(n) where n is the length of the string.
**Auxiliary Space:** O(1)
On a simple look on program or algorithm, its running cost looks proportional to the number of bits but in real, it is not proportional to a number of bits. Let's see how!
Let's assume that increment operation is performed k time. We see that in every increment, its rightmost bit is getting flipped. So, the number of flipping for LSB is k. For, second rightmost is flipped after a gap, i.e., 1 time in 2 increments. 3rd rightmost - 1 time in 4 increments. 4th rightmost - 1 time in 8 increments. So, the number of flipping is k/2 for 2nd rightmost bit, k/4 for 3rd rightmost bit, k/8 for 4th rightmost bit and so on ...
Total cost will be the total number of flipping, that is, 
C(k) = k + k/2 + k/4 + k/8 + k/16 + ...... which is Geometric Progression series and also, 
C(k) < k + k/2 + k/4 + k/8 + k/16 + k/32 + ...... up to infinity 
So, C(k) < k/(1-1/2) 
and so, C(k) < 2k 
So, C(k)/k < 2 
Hence, we find that average cost for increment a counter for one time is constant and it does not depend on the number of bit. We conclude that increment of a counter is constant cost operation.
**References :**
1. <https://www.cs.cornell.edu/courses/cs3110/2013sp/supplemental/recitations/rec21.html>
2. <https://people.engr.tamu.edu/andreas-klappenecker/csce411-s17/csce411-amortized3.pdf>
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/amortized-analysis-increment-counter/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Sequential Circuit

> [!note] Related notes
>
> - [[Asynchronous Sequential Circuits]]
> - [[Counters]]
> - [[D Flipflop]]
> - [[Design 101 sequence detector]]
> - [[Design counter for given sequence]]
> - [[Flip-flop types and their Conversion]]
> - [[Introduction of Sequential Circuits]]
> - [[Master Slave JK Flip Flop]]
> - [[n-bit Johnson Counter]]
> - [[Ring Counter]]
