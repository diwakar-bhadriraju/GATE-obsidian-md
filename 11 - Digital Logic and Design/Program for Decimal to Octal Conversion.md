---
title: "Program for Decimal to Octal Conversion"
subject: "Digital Logic and Design"
topic: "Number Representation and Computer Arithmetic"
source: "https://www.geeksforgeeks.org/dsa/program-decimal-octal-conversion/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Number Representation and Computer Arithmetic"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/number-representation-and-computer-arithmetic
---


> [!abstract] Program for Decimal to Octal Conversion
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Number Representation and Computer Arithmetic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/program-decimal-octal-conversion/)

---

# Program for Decimal to Octal Conversion

Given a decimal number as input, we need to write a program to convert the given decimal number into an equivalent octal number. i.e convert the number with base value 10 to base value 8. The base value of a number system determines the number of digits used to represent a numeric value. For example, the binary number system uses two digits 0 and 1, the [octal number system](https://www.geeksforgeeks.org/maths/octal-number-system/) uses 8 digits from 0-7 and the decimal number system uses 10 digits 0-9 to represent any numeric value.
**Examples:** 
```
Input : 16Output: 20Input : 10Output: 12Input : 33Output: 41
```
### **Algorithm**:
1. Store the remainder when the number is divided by 8 in an array.
2. Divide the number by 8 now
3. Repeat the above two steps until the number is not equal to 0.
4. Print the array in reverse order now.
For Example: 
If the given decimal number is 16. 
**Step 1**: Remainder when 16 is divided by 8 is 0. Therefore, arr[0] = 0. 
**Step 2**: Divide 16 by 8. New number is 16/8 = 2. 
**Step 3**: Remainder, when 2 is divided by 8, is 2. Therefore, arr[1] = 2. 
**Step 4**: Divide 2 by 8. New number is 2/8 = 0. 
**Step 5**: Since number becomes = 0. 
Stop repeating steps and print the array in reverse order. Therefore, the equivalent octal number is 20.
The below diagram shows an example of converting the decimal number 33 to an equivalent octal number.  
![decToOctal](assets/decToOctal-0cd5c64428.png)
Below is the implementation of the above idea.  
````cpp
// C++ program to convert a decimal
// number to octal number
#include <iostream>
using namespace std;
// function to convert decimal to octal
void decToOctal(int n)
{
    // array to store octal number
    int octalNum[100];
    // counter for octal number array
    int i = 0;
    while (n != 0) {
        // storing remainder in octal array
        octalNum[i] = n % 8;
        n = n / 8;
        i++;
    }
    // printing octal number array in reverse order
    for (int j = i - 1; j >= 0; j--)
        cout << octalNum[j];
}
// Driver Code
int main()
{
    int n = 33;
    // Function Call
    decToOctal(n);
    return 0;
}
````
````c
// C program to convert decimal
// number to octal number
#include <stdio.h>
// function to convert decimal to octal
void decToOctal(int n)
{
    // array to store octal number
    int octalNum[100];
    // counter for octal number array
    int i = 0;
    while (n != 0) {
        // storing remainder in octal array
        octalNum[i] = n % 8;
        n = n / 8;
        i++;
    }
    // printing octal number array in reverse order
    for (int j = i - 1; j >= 0; j--)
        printf("%d", octalNum[j]);
}
// Driver Code
int main()
{
    int n = 33;
    // Function Call
    decToOctal(n);
    return 0;
}
````
````java
// Java program to convert a decimal
// number to octal number
import java.io.*;
class GFG {
    // Function to convert decimal to octal
    static void decToOctal(int n)
    {
        // array to store octal number
        int[] octalNum = new int[100];
        // counter for octal number array
        int i = 0;
        while (n != 0) {
            // storing remainder in octal array
            octalNum[i] = n % 8;
            n = n / 8;
            i++;
        }
        // Printing octal number array in reverse order
        for (int j = i - 1; j >= 0; j--)
            System.out.print(octalNum[j]);
    }
    // Driver Code
    public static void main(String[] args)
    {
        int n = 33;
        // Function Call
        decToOctal(n);
    }
}
// Contributed by Pramod Kumar
````
````python3
# Python3 program to convert
# a decimal number to
# octal number
# function to convert
# decimal to octal
def decToOctal(n):
    # array to store
    # octal number
    octalNum = [0] * 100
    # counter for octal
    # number array
    i = 0
    while (n != 0):
        # storing remainder
        # in octal array
        octalNum[i] = n % 8
        n = int(n / 8)
        i += 1
    # printing octal number
    # array in reverse order
    for j in range(i - 1, -1, -1):
        print(octalNum[j], end="")
# Driver Code
n = 33
# Function Call
decToOctal(n)
# This code is contributed
# by mits
````
````csharp
// C# program to convert a decimal
// number to octal number
using System;
class GFG {
    // Function to convert decimal to octal
    static void decToOctal(int n)
    {
        // array to store octal number
        int[] octalNum = new int[100];
        // counter for octal number array
        int i = 0;
        while (n != 0) {
            // storing remainder in octal array
            octalNum[i] = n % 8;
            n = n / 8;
            i++;
        }
        // Printing octal number array in
        // reverse order
        for (int j = i - 1; j >= 0; j--)
            Console.Write(octalNum[j]);
    }
    // Driver Code
    public static void Main()
    {
        int n = 33;
        // Function Call
        decToOctal(n);
    }
}
// This code is contributed by nitin mittal.
````
````javascript
<script>
// JavaScript program to convert a decimal
// number to octal number
// function to convert decimal to octal
function decToOctal(n)
{
    // array to store octal number
    let octalNum = new Array(100);
    // counter for octal number array
    let i = 0;
    while (n != 0) {
        // storing remainder in octal array
        octalNum[i] = n % 8;
        n = Math.floor(n / 8);
        i++;
    }
    // printing octal number array in reverse order
    for (let j = i - 1; j >= 0; j--)
        document.write(octalNum[j]);
}
// Driver Code
    let n = 33;
    // Function Call
    decToOctal(n);
// This code is contributed by Surbhi Tyagi
</script>
````
````php
<?php
// PHP program to convert
// a decimal number to
// octal number
// function to convert
// decimal to octal
function decToOctal($n)
{
    // array to store
    // octal number
    $octalNum;
    // counter for octal
    // number array
    $i = 0;
    while ($n != 0)
    {
        // storing remainder
        // in octal array
        $octalNum[$i] = $n % 8;
        $n = (int)($n / 8);
        $i++;
    }
    // printing octal number
    // array in reverse order
    for ( $j = $i - 1; $j >= 0; $j--)
        echo $octalNum[$j];
}
// Driver Code
$n = 33;
// Function Call
decToOctal($n);
// This code is contributed
// by ajit
?>
````
**Output**
```
41
```
#### **Time Complexity:** O(log N)
**Auxiliary Space: O(L)** where L is the number of digits in octal number.
### **Another Approach: (O(1) space Complexity)**
This problem can also be solved without using an array  using the following algorithm:
- Initialize octal num to 0 and countVal to 1 and the decimal number as n
- Find the remainder when decimal number divided by 8
- Update octal number by octalNum + (remainder \* countval)
- Increase countval by countval\*10
- Divide decimal number by 8
- Repeat from the second step until the decimal number is zero
Below is the implementation of the above idea:
````cpp
// C++ program to convert decimal
// number to octal number
#include <iostream>
using namespace std;
// function to calculate the octal value of the given
// decimal number
void decimaltoOctal(int deciNum)
{
    // initializations
    int octalNum = 0, countval = 1;
    int dNo = deciNum;
    while (deciNum != 0) {
        // decimals remainder is calculated
        int remainder = deciNum % 8;
        // storing the octalvalue
        octalNum += remainder * countval;
        // storing exponential value
        countval = countval * 10;
        deciNum /= 8;
    }
    cout << octalNum << endl;
}
// Driver Code
int main()
{
    int n = 33;
    // Function Call
    decimaltoOctal(n);
    return 0;
}
````
````c
// C program to convert decimal
// number to octal number
#include <stdio.h>
// function to calculate the octal value of the given
// decimal number
void decimaltoOctal(int deciNum)
{
    int octalNum = 0, countval = 1;
    int dNo = deciNum;
    while (deciNum != 0) {
        // decimals remainder is calculated
        int remainder = deciNum % 8;
        // storing the octalvalue
        octalNum += remainder * countval;
        // storing exponential value
        countval = countval * 10;
        deciNum /= 8;
    }
    printf("%d", octalNum);
}
// Driver Code
int main()
{
    int n = 33;
    // Function Call
    decimaltoOctal(n);
    return 0;
}
````
````java
// JAVA program to convert decimal
// number to octal number
import java.io.*;
class GFG {
    // function to calculate the octal value of the given
    // decimal number
    static void octaltodecimal(int deciNum)
    {
        int octalNum = 0, countval = 1;
        int dNo = deciNum;
        while (deciNum != 0) {
            // decimals remainder is calculated
            int remainder = deciNum % 8;
            // storing the octalvalue
            octalNum += remainder * countval;
            // storing exponential value
            countval = countval * 10;
            deciNum /= 8;
        }
        System.out.println(octalNum);
    }
    // Driver Code
    public static void main(String[] args)
    {
        int n = 33;
        // Function Call
        octaltodecimal(n);
    }
}
````
````python3
# Python3 program to convert decimal
# number to octal number
# function to calculate the octal value of the given
# decimal number
def decimaltoOctal(deciNum):
    # initializations
    octalNum = 0
    countval = 1
    dNo = deciNum
    while (deciNum != 0):
        # decimals remainder is calculated
        remainder = deciNum % 8
        # storing the octalvalue
        octalNum += remainder * countval
        # storing exponential value
        countval = countval * 10
        deciNum //= 8
    print(octalNum)
# Driver Code
if __name__ == '__main__':
    n = 33
    # Function Call
    decimaltoOctal(n)
# This code is contributed by pratham76
````
````csharp
// C# program to convert decimal
// number to octal number
using System;
class GFG {
    // function to calculate
    // the octal value of the given
    // decimal number
    static void octaltodecimal(int deciNum)
    {
        int octalNum = 0, countval = 1;
        while (deciNum != 0) {
            // decimals remainder is
            // calculated
            int remainder = deciNum % 8;
            // storing the octalvalue
            octalNum += remainder * countval;
            // storing exponential value
            countval = countval * 10;
            deciNum /= 8;
        }
        Console.Write(octalNum);
    }
    // Driver Code
    public static void Main(string[] args)
    {
        int n = 33;
        // Function Call
        octaltodecimal(n);
    }
}
// This code is contributed by rutvik_56
````
````javascript
<script>
// Javascript program to convert decimal
// number to octal number
// function to calculate the octal value of the given
// decimal number
function decimaltoOctal(deciNum)
{
    // initializations
    let octalNum = 0, countval = 1;
    let dNo = deciNum;
    while (deciNum != 0) {
        // decimals remainder is calculated
        let remainder = Math.floor(deciNum % 8);
        // storing the octalvalue
        octalNum += remainder * countval;
        // storing exponential value
        countval = countval * 10;
        deciNum = Math.floor(deciNum/8);
    }
    document.write(octalNum + "<br>");
}
// Driver Code
    let n = 33;
    // Function Call
    decimaltoOctal(n);
//This code is contributed by Mayank Tyagi
</script>
````
**Output**
```
41
```
**Time Complexity:** O(log N)
**Auxiliary Space:** O(1)
**Using a predefined function**
````cpp
#include <bits/stdc++.h>
using namespace std;
string intToOctal(int n)
{
    stringstream st;
    st << oct << n;
    return st.str();
}
int main()
{
    int n = 43;
    cout << intToOctal(n);
    return 0;
}
````
````java
// JAVA program to convert decimal
// number to octal number
import java.io.*;
class GFG {
    public static void decToOct(int n)
    {
        System.out.println(Integer.toOctalString(n));
    }
    public static void main(String[] args)
    {
        int n = 33;
        decToOct(n);
    }
}
````
````python3
# Python program to convert decimal
# number to octal number
def decToOct(n):
    print(oct(n));
if __name__ == '__main__':
    n = 33;
    decToOct(n);
# This code is contributed by Amit Katiyar
````
````csharp
// C# program to convert decimal
// number to octal number
using System;
public class GFG
{
    public static void decToOct(int n)
    {
        Console.WriteLine(Convert.ToString(n, 8));
    }
    public static void Main(String[] args)
    {
        int n = 33;
        decToOct(n);
    }
}
// This code is contributed by 29AjayKumar
````
````javascript
<script>
// Javascript program to convert decimal
// number to octal number
function decToOct(n)
{
    document.write(n.toString(8));
}
var n = 33;
decToOct(n);
// This code contributed by Princi Singh
</script>
````
**Output**
```
41
```
**Time complexity: O(1).**
**Space complexity: O(1).**
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/program-decimal-octal-conversion/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Number Representation and Computer Arithmetic

> [!note] Related notes
>
> - [[Booth’s Algorithm]]
> - [[Code Converters – BCD(8421) to from Excess-3]]
> - [[Code Converters – Binary to from Gray Code]]
> - [[Computer Arithmetic Set – 1]]
> - [[Computer Arithmetic Set – 2]]
> - [[Floating Point Representation]]
> - [[Last Minute Notes – Digital Electronics]]
> - [[Non-Restoring Division For Unsigned Integer]]
> - [[Number System and base conversions]]
> - [[Program for Binary To Decimal Conversion]]
