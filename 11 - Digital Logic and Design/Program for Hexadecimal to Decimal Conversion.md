---
title: "Program for Hexadecimal to Decimal"
subject: "Digital Logic and Design"
topic: "Number Representation and Computer Arithmetic"
source: "https://www.geeksforgeeks.org/dsa/program-for-hexadecimal-to-decimal/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Number Representation and Computer Arithmetic"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/number-representation-and-computer-arithmetic
---


> [!abstract] Program for Hexadecimal to Decimal
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Number Representation and Computer Arithmetic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/program-for-hexadecimal-to-decimal/)

---

# Program for Hexadecimal to Decimal

Given a [hexadecimal number](https://www.geeksforgeeks.org/maths/hexadecimal-number-system/) as input, we need to write a program to convert the given hexadecimal number into an equivalent decimal number.
**Examples:**  
```
Input : 67
Output: 103
Input : 512
Output: 1298
Input : 123
Output: 291
```
## Hexadecimal Number
We know that hexadecimal number uses 16 symbols {0, 1, 2, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F} to represent all numbers. Here, (A, B, C, D, E, F) represents (10, 11, 12, 13, 14, 15). 
The idea is to extract the digits of a given hexadecimal number starting from the rightmost digit and keep a variable dec\_value. At the time of extracting digits from the hexadecimal number, multiply the digit with the proper base (Power of 16) and add it to the variable dec\_value. In the end, the variable dec\_value will store the required decimal number.
For Example: If the hexadecimal number is 1A. 
dec\_value = 1\*(161) + 10\*(160) = 26
### Decimal Number
The number which can be represented using the numbers in the range of (0-9) are termed as decimal number which has the base 10 to it.
For example, The number 123 is a decimal number where:
- 1 represents 100 (10²),
- 2 represents 20 (10¹),
- 3 represents 3 (10⁰).
Thus, 123 = 1×100 + 2×10 + 3×1.
The below diagram explains how to convert a hexadecimal number (1AB) to an equivalent decimal value:  
![](assets/hexaTodeci-0254e3538f.png)
Below is the implementation of the above idea. 
````cpp
// C++ program to convert hexadecimal to decimal
#include <bits/stdc++.h>
using namespace std;
// Function to convert hexadecimal to decimal
int hexadecimalToDecimal(string hexVal)
{
    int len = hexVal.size();
    // Initializing base value to 1, i.e 16^0
    int base = 1;
    int dec_val = 0;
    // Extracting characters as digits from last
    // character
    for (int i = len - 1; i >= 0; i--) {
        // if character lies in '0'-'9', converting
        // it to integral 0-9 by subtracting 48 from
        // ASCII value
        if (hexVal[i] >= '0' && hexVal[i] <= '9') {
            dec_val += (int(hexVal[i]) - 48) * base;
            // incrementing base by power
            base = base * 16;
        }
        // if character lies in 'A'-'F' , converting
        // it to integral 10 - 15 by subtracting 55
        // from ASCII value
        else if (hexVal[i] >= 'A' && hexVal[i] <= 'F') {
            dec_val += (int(hexVal[i]) - 55) * base;
            // incrementing base by power
            base = base * 16;
        }
    }
    return dec_val;
}
// driver program
int main()
{
    string hexNum = "1A";
    cout << (hexadecimalToDecimal(hexNum));
    // This code is contributed by rakeshsahni
    return 0;
}
````
````java
// Java program to convert hexadecimal to decimal
import java.io.*;
class GFG {
    // Function to convert hexadecimal to decimal
    static int hexadecimalToDecimal(String hexVal)
    {
        int len = hexVal.length();
        // Initializing base value to 1, i.e 16^0
        int base = 1;
        int dec_val = 0;
        // Extracting characters as digits from last
        // character
        for (int i = len - 1; i >= 0; i--) {
            // if character lies in '0'-'9', converting
            // it to integral 0-9 by subtracting 48 from
            // ASCII value
            if (hexVal.charAt(i) >= '0'
                && hexVal.charAt(i) <= '9') {
                dec_val += (hexVal.charAt(i) - 48) * base;
                // incrementing base by power
                base = base * 16;
            }
            // if character lies in 'A'-'F' , converting
            // it to integral 10 - 15 by subtracting 55
            // from ASCII value
            else if (hexVal.charAt(i) >= 'A'
                     && hexVal.charAt(i) <= 'F') {
                dec_val += (hexVal.charAt(i) - 55) * base;
                // incrementing base by power
                base = base * 16;
            }
        }
        return dec_val;
    }
    // driver program
    public static void main(String[] args)
    {
        String hexNum = "1A";
        System.out.println(hexadecimalToDecimal(hexNum));
    }
}
````
````python3
# Python3 program to convert
# hexadecimal to decimal
# Function to convert hexadecimal
# to decimal
def hexadecimalToDecimal(hexval):
    # Finding length
    length = len(hexval)
    # Initialize base value to 1,
    # i.e. 16*0
    base = 1
    dec_val = 0
    # Extracting characters as digits
    # from last character
    for i in range(length - 1, -1, -1):
        # If character lies in '0'-'9',
        # converting it to integral 0-9
        # by subtracting 48 from ASCII value
        if hexval[i] >= '0' and hexval[i] <= '9':
            dec_val += (ord(hexval[i]) - 48) * base
            # Incrementing base by power
            base = base * 16
        # If character lies in 'A'-'F',converting
        # it to integral 10-15 by subtracting 55
        # from ASCII value
        elif hexval[i] >= 'A' and hexval[i] <= 'F':
            dec_val += (ord(hexval[i]) - 55) * base
            # Incrementing base by power
            base = base * 16
    return dec_val
# Driver code
if __name__ == '__main__':
    hexnum = '1A'
    print(hexadecimalToDecimal(hexnum))
# This code is contributed by virusbuddah_
````
````csharp
// C# program to convert
// hexadecimal to decimal
using System;
class GFG {
    // Function to convert
    // hexadecimal to decimal
    static int hexadecimalToDecimal(String hexVal)
    {
        int len = hexVal.Length;
        // Initializing base1 value
        // to 1, i.e 16^0
        int base1 = 1;
        int dec_val = 0;
        // Extracting characters as
        // digits from last character
        for (int i = len - 1; i >= 0; i--) {
            // if character lies in '0'-'9',
            // converting it to integral 0-9
            // by subtracting 48 from ASCII value
            if (hexVal[i] >= '0' && hexVal[i] <= '9') {
                dec_val += (hexVal[i] - 48) * base1;
                // incrementing base1 by power
                base1 = base1 * 16;
            }
            // if character lies in 'A'-'F' ,
            // converting it to integral
            // 10 - 15 by subtracting 55
            // from ASCII value
            else if (hexVal[i] >= 'A' && hexVal[i] <= 'F') {
                dec_val += (hexVal[i] - 55) * base1;
                // incrementing base1 by power
                base1 = base1 * 16;
            }
        }
        return dec_val;
    }
    // Driver Code
    static void Main()
    {
        String hexNum = "1A";
        Console.WriteLine(hexadecimalToDecimal(hexNum));
    }
}
// This code is contributed by mits
````
````javascript
<script>
// javascript program to convert hexadecimal to decimal
   // Function to convert hexadecimal to decimal
function hexadecimalToDecimal(hexVal)
{
    var len = hexVal.length;
    // Initializing base value to 1, i.e 16^0
    var base = 1;
    var dec_val = 0;
    // Extracting characters as digits from last
    // character
    for (var i = len - 1; i >= 0; i--) {
        // if character lies in '0'-'9', converting
        // it to integral 0-9 by subtracting 48 from
        // ASCII value
        if (hexVal.charAt(i) >= '0'
            && hexVal.charAt(i) <= '9') {
            dec_val += (hexVal.charAt(i).charCodeAt(0) - 48) * base;
            // incrementing base by power
            base = base * 16;
        }
        // if character lies in 'A'-'F' , converting
        // it to integral 10 - 15 by subtracting 55
        // from ASCII value
        else if (hexVal.charAt(i) >= 'A'
                 && hexVal.charAt(i) <= 'F') {
            dec_val += (hexVal.charAt(i).charCodeAt(0) - 55) * base;
            // incrementing base by power
            base = base * 16;
        }
    }
    return dec_val;
}
// driver program
var hexNum = "1A";
document.write(hexadecimalToDecimal(hexNum));
// This code is contributed by 29AjayKumar
</script>
````
````php
<?php
// PHP program to convert
// hexadecimal to decimal
// Function to convert
// hexadecimal to decimal
function hexadecimalToDecimal($hexVal)
{
    $len = strlen($hexVal);
    // Initializing base value
    // to 1, i.e 16^0
    $base = 1;
    $dec_val = 0;
    // Extracting characters as
    // digits from last character
    for ($i = $len - 1; $i >= 0; $i--)
    {
        // if character lies in '0'-'9',
        // converting it to integral 0-9
        // by subtracting 48 from ASCII value.
        if ($hexVal[$i] >= '0' &&
            $hexVal[$i] <= '9')
        {
            $dec_val += (ord($hexVal[$i]) - 48) *
                                         $base;
            // incrementing base by power
            $base = $base * 16;
        }
        // if character lies in 'A'-'F' ,
        // converting it to integral
        // 10 - 15 by subtracting 55
        // from ASCII value
        else if ($hexVal[$i] >= 'A' &&
                 $hexVal[$i] <= 'F')
        {
            $dec_val += (ord($hexVal[$i]) - 55) *
                                         $base;
            // incrementing base by power
            $base = $base * 16;
        }
    }
    return $dec_val;
}
// Driver Code
$hexNum = "1A";
echo hexadecimalToDecimal($hexNum);
// This code is contributed by mits
?>
````
**Output**
```
26
```
**Time Complexity: O(N)**, where N is the number of digits in the given hexadecimal number.
**Space Complexity: O(1).**
**Using predefined function**
````cpp
// C++ program to convert octal to decimal
#include <bits/stdc++.h>
using namespace std;
int HexToDec(string n) { return stoi(n, 0, 16); }
int main()
{
    string n = "1A";
    cout << HexToDec(n);
    return 0;
}
    // This code is contributed by rakeshsahni
````
````java
// Java program to convert hexadecimal to decimal
import java.io.*;
class GFG {
    public static int HexToDec(String n)
    {
        return Integer.parseInt(n, 16);
    }
    public static void main(String[] args)
    {
        String n = "1A";
        System.out.println(HexToDec(n));
    }
}
````
````python3
# Python program to convert hexadecimal to decimal
def HexToDec(n):
    return int(n, 16);
if __name__ == '__main__':
    n = "1A";
    print(HexToDec(n));
# This code is contributed by 29AjayKumar
````
````csharp
// C# program to convert hexadecimal to decimal
using System;
public class GFG {
    public static int HexToDec(String n)
    {
        return Convert.ToInt32(n, 16);
    }
    public static void Main(String[] args)
    {
        String n = "1A";
        Console.WriteLine(HexToDec(n));
    }
}
// This code is contributed by Amit Katiyar
````
````javascript
<script>
// javascript program to convert octal to decimal
function HexToDec(n)
    {
        return parseInt(n, 16);
    }
var n = "1A";
document.write(HexToDec(n));
// This code is contributed by 29AjayKumar
</script>
````
**Output**
```
26
```
**Time complexity: O(1)** - the conversion of hexadecimal to decimal is done in constant time using the stoi function.
**Auxiliary Space: O(1)** - the only space used is for the string n and the returned integer value, which are constant in size regardless of the input value.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/program-for-hexadecimal-to-decimal/)

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
