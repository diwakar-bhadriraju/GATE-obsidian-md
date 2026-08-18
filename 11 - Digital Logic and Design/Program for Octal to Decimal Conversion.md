---
title: "Program for Octal to Decimal Conversion"
subject: "Digital Logic and Design"
topic: "Number Representation and Computer Arithmetic"
source: "https://www.geeksforgeeks.org/dsa/program-octal-decimal-conversion/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Number Representation and Computer Arithmetic"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/number-representation-and-computer-arithmetic
---


> [!abstract] Program for Octal to Decimal Conversion
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Number Representation and Computer Arithmetic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/program-octal-decimal-conversion/)

---

# Program for Octal to Decimal Conversion

Given an octal number as input, we need to write a program to convert the given octal number into equivalent decimal number.
**Examples:**
```
Input : 67Output: 55Input : 512Output: 330Input : 123Output: 83
```
The idea is to extract the digits of a given octal number starting from the rightmost digit and keep a variable dec\_value. At the time of extracting digits from the octal number, multiply the digit with the proper base (Power of 8) and add it to the variable dec\_value. In the end, the variable dec\_value will store the required decimal number.
For Example: 
If the octal number is 67. 
dec\_value = 6\*(8^1) + 7\*(8^0) = 55
The below diagram explains how to convert an octal number (123) to an equivalent decimal value:  
![](assets/octToDec-f0983d6da4.png)
Below is the implementation of the above idea. 
````cpp
// C++ program to convert octal to decimal
#include <iostream>
using namespace std;
// Function to convert octal to decimal
int octalToDecimal(int n)
{
    int num = n;
    int dec_value = 0;
    // Initializing base value to 1, i.e 8^0
    int base = 1;
    int temp = num;
    while (temp) {
        // Extracting last digit
        int last_digit = temp % 10;
        temp = temp / 10;
        // Multiplying last digit with appropriate
        // base value and adding it to dec_value
        dec_value += last_digit * base;
        base = base * 8;
    }
    return dec_value;
}
// Driver program to test above function
int main()
{
    int num = 67;
    cout << octalToDecimal(num) << endl;
}
````
````java
// Java program to convert octal to decimal
import java.io.*;
class GFG {
    // Function to convert octal to decimal
    static int octalToDecimal(int n)
    {
        int num = n;
        int dec_value = 0;
        // Initializing base value to 1, i.e 8^0
        int base = 1;
        int temp = num;
        while (temp > 0) {
            // Extracting last digit
            int last_digit = temp % 10;
            temp = temp / 10;
            // Multiplying last digit with appropriate
            // base value and adding it to dec_value
            dec_value += last_digit * base;
            base = base * 8;
        }
        return dec_value;
    }
    // driver program
    public static void main(String[] args)
    {
        int num = 67;
        System.out.println(octalToDecimal(num));
    }
}
// This code is contributed
// by Pramod Kumar
````
````python3
# Python3 program to convert
# octal to decimal
# Function to convert
# octal to decimal
def octalToDecimal(n):
    num = n
    dec_value = 0
    # Initializing base value
    # to 1, i.e 8^0
    base = 1
    temp = num
    while (temp):
        # Extracting last digit
        last_digit = temp % 10
        temp = int(temp / 10)
        # Multiplying last digit
        # with appropriate base
        # value and adding it
        # to dec_value
        dec_value += last_digit * base
        base = base * 8
    return dec_value
# Driver Code
num = 67
print(octalToDecimal(num))
# This code is contributed by mits
````
````csharp
// C# program to convert octal to
// decimal
using System;
class GFG {
    // Function to convert octal
    // to decimal
    static int octalToDecimal(int n)
    {
        int num = n;
        int dec_value = 0;
        // Initializing base value
        // to 1, i.e 8^0
        int b_ase = 1;
        int temp = num;
        while (temp > 0) {
            // Extracting last digit
            int last_digit = temp % 10;
            temp = temp / 10;
            // Multiplying last digit
            // with appropriate base
            // value and adding it to
            // dec_value
            dec_value += last_digit * b_ase;
            b_ase = b_ase * 8;
        }
        return dec_value;
    }
    // driver program
    public static void Main()
    {
        int num = 67;
        Console.WriteLine(octalToDecimal(num));
    }
}
// This code is contributed by vt_m.
````
````javascript
<script>
// JavaScript program to convert octal to decimal
// Function to convert octal to decimal
function octalToDecimal(n)
{
    let num = n;
    let dec_value = 0;
    // Initializing base value to 1, i.e 8^0
    let base = 1;
    let temp = num;
    while (temp) {
        // Extracting last digit
        let last_digit = temp % 10;
        temp = Math.floor(temp / 10);
        // Multiplying last digit with appropriate
        // base value and adding it to dec_value
        dec_value += last_digit * base;
        base = base * 8;
    }
    return dec_value;
}
// Driver program to test above function
    let num = 67;
    document.write(octalToDecimal(num) + "<br>");
// This code is contributed by Surbhi Tyagi
</script>
````
````php
<?php
// PHP program to convert octal to decimal
// Function to convert
// octal to decimal
function octalToDecimal($n)
{
    $num = $n;
    $dec_value = 0;
    // Initializing base value
    // to 1, i.e 8^0
    $base = 1;
    $temp = $num;
    while ($temp)
    {
        // Extracting last digit
        $last_digit = $temp % 10;
        $temp = $temp / 10;
        // Multiplying last digit
        // with appropriate base
        // value and adding it
        // to dec_value
        $dec_value += $last_digit * $base;
        $base = $base * 8;
    }
    return $dec_value;
}
    // Driver Code
    $num = 67;
    echo octalToDecimal($num);
// This code is contributed by anuj_67
?>
````
**Output**
```
55
```
**Time complexity:** O(logN) where N is the given number
**Auxiliary space:** O(1)
### Method: Using look up table method
The function octalToDecimal takes an integer n as input, which represents the octal number that needs to be converted to decimal. It initializes an unordered map lookup that maps each octal digit to its decimal equivalent.
It then uses a loop to extract each digit of the octal number from right to left, starting from the least significant digit. For each digit, it multiplies the decimal equivalent of the digit (retrieved from the lookup table) with the appropriate power of 8 (base) and adds it to the decimal variable. The base variable is updated after each iteration by multiplying it with 8. The loop continues until all digits have been processed.
Finally, the decimal variable is returned as the output of the function.
In the main function, an octal number octal\_num is initialized and passed as an argument to the octalToDecimal function. The resulting decimal value is printed to the console.
````cpp
#include <iostream>
#include <unordered_map>
using namespace std;
int octalToDecimal(int n) {
    unordered_map<int, int> lookup{
        {0, 0}, {1, 1}, {2, 2}, {3, 3},
        {4, 4}, {5, 5}, {6, 6}, {7, 7}
    };
    int decimal = 0;
    int base = 1;
    while (n > 0) {
        int last_digit = n % 10;
        decimal += lookup[last_digit] * base;
        n /= 10;
        base *= 8;
    }
    return decimal;
}
int main() {
    int octal_num = 67;
    cout << octalToDecimal(octal_num) << endl;
    return 0;
}
````
````java
import java.util.HashMap;
public class GFG {
    public static int octalToDecimal(int n) {
        HashMap<Integer, Integer> lookup = new HashMap<>();
        lookup.put(0, 0);
        lookup.put(1, 1);
        lookup.put(2, 2);
        lookup.put(3, 3);
        lookup.put(4, 4);
        lookup.put(5, 5);
        lookup.put(6, 6);
        lookup.put(7, 7);
        int decimal = 0;
        int base = 1;
        while (n > 0) {
            int lastDigit = n % 10;
            decimal += lookup.get(lastDigit) * base;
            n /= 10;
            base *= 8;
        }
        return decimal;
    }
    public static void main(String[] args) {
        int octalNum = 67;
        System.out.println(octalToDecimal(octalNum));
    }
}
````
````python3
def octal_to_decimal(n):
    # Define a dictionary to map octal digits to their decimal equivalents
    lookup = {
        0: 0, 1: 1, 2: 2, 3: 3,
        4: 4, 5: 5, 6: 6, 7: 7
    }
    decimal = 0
    base = 1
    # Convert octal to decimal
    while n > 0:
        last_digit = n % 10  # Get the last digit of the octal number
        decimal += lookup[last_digit] * base  # Add the decimal equivalent to the result
        n //= 10  # Remove the last digit from the octal number
        base *= 8  # Move to the next octal place value (8^0, 8^1, 8^2, ...)
    return decimal
def main():
    octal_num = 67
    print(octal_to_decimal(octal_num))
if __name__ == "__main__":
    main()
````
````csharp
using System;
using System.Collections.Generic;
public class GFG
{
    // Function to convert octal to decimal
    public static int OctalToDecimal(int n)
    {
        // Lookup table for octal values
        Dictionary<int, int> lookup = new Dictionary<int, int>()
        {
            {0, 0}, {1, 1}, {2, 2}, {3, 3},
            {4, 4}, {5, 5}, {6, 6}, {7, 7}
        };
        int decimalNum = 0;
        int baseVal = 1;
        // Extracting digits from the octal number and converting to decimal
        while (n > 0)
        {
            int lastDigit = n % 10; // Get the last digit of the octal number
            decimalNum += lookup[lastDigit] * baseVal; // Convert the last digit to decimal and add to the result
            n /= 10; // Remove the last digit from the octal number
            baseVal *= 8; // Move to the next position in the decimal representation (base 8 -> base 10)
        }
        return decimalNum; // Return the decimal representation of the octal number
    }
    // Driver code
    public static void Main(string[] args)
    {
        int octalNum = 67;
        int decimalValue = OctalToDecimal(octalNum);
        Console.WriteLine("Equivalent Decimal Value = " + decimalValue);
    }
}
````
````javascript
function octalToDecimal(n) {
    let lookup = new Map([
        [0, 0], [1, 1], [2, 2], [3, 3],
        [4, 4], [5, 5], [6, 6], [7, 7]
    ]);
    let decimal = 0;
    let base = 1;
    while (n > 0) {
        let last_digit = n % 10;
        decimal += lookup.get(last_digit) * base;
        n = Math.floor(n/10);
        base *= 8;
    }
    return decimal;
}
let octal_num = 67;
document.write(octalToDecimal(octal_num));
````
**Output**
```
55
```
**Time complexity:** The time complexity of this algorithm is O(log N), where N is the octal number being converted to decimal. This is because we loop through each digit in the octal number once, and the number of digits in an N-digit octal number is log N.
**Auxiliary space:** The space complexity of this algorithm is O(1), as we only store a fixed-size lookup table and a few integer variables for the running sum and base value.
**Using predefined function**
````cpp
// C++ program to convert octal to decimal
#include <iostream>
using namespace std;
int OctToDec(string n)
{
  return stoi(n, 0, 8);
}
int main()
{
  string n = "67";
  cout << OctToDec(n);
  return 0;
}
// This code is contributed by phasing17
````
````java
// Java program to convert octal to decimal
import java.io.*;
class GFG {
    public static int OctToDec(String n)
    {
        return Integer.parseInt(n, 8);
    }
    public static void main(String[] args)
    {
        String n = "67";
        System.out.println(OctToDec(n));
    }
}
````
````python3
# Python program to convert octal to decimal
def OctToDec(n):
    return int(n, 8);
if __name__ == '__main__':
    n = "67";
    print(OctToDec(n));
# This code is contributed by 29AjayKumar
````
````csharp
using System;
public class GFG{
    public static int OctToDec(String n)
    {
        return Convert.ToInt32(n, 8);
    }
    static public void Main (){
        string n = "67";
        Console.WriteLine(OctToDec(n));
    }
}
// THIS CODE IS CONTRIBUTED BY RAG2127
````
````javascript
<script>
// javascript program to convert octal to decimal
   function OctToDec(n)
    {
        return parseInt(n, 8);
    }
   var n = "67";
   document.write(OctToDec(n));
// This code contributed by Princi Singh
</script>
````
**Output**
```
55
```
### Method 3: Using recursion
1. The method uses the fact that each digit of an octal number represents a power of 8, starting from the rightmost digit. 
2. The method extracts the rightmost digit of the octal number by taking the remainder of the number divided by 10 (i.e., octal % 10) and adds it to the product of the remaining digits and the appropriate power of 8 (i.e., 8 \* octal\_to\_decimal(octal // 10)).
3.This recursive step continues until the entire number has been converted to decimal.
````cpp
#include <iostream>
using namespace std;
int octal_to_decimal(int octal) {
    if (octal == 0) {
        return 0;
    } else {
        return (octal % 10) + 8 * octal_to_decimal(octal / 10);
    }
}
int main() {
    int octal = 67;
    cout << octal_to_decimal(octal) << endl;
    return 0;
}
````
````java
public class OctalToDecimal {
    public static int octalToDecimal(int octal) {
        if (octal == 0) {
            return 0;
        } else {
            return (octal % 10) + 8 * octalToDecimal(octal / 10);
        }
    }
    public static void main(String[] args) {
        int octal = 67;
        System.out.println(octalToDecimal(octal));
    }
}
````
````python3
def octal_to_decimal(octal):
    if octal == 0:
        return 0
    else:
        return (octal % 10) + 8 * octal_to_decimal(octal // 10)
octal=67
print(octal_to_decimal(octal))
````
````csharp
using System;
public class Program
{
    public static void Main()
    {
        int octal = 67;
        int decimalNum = OctalToDecimal(octal);
        Console.WriteLine(decimalNum);
    }
    public static int OctalToDecimal(int octal)
    {
        if (octal == 0)
        {
            return 0;
        }
        else
        {
            return (octal % 10) + 8 * OctalToDecimal(octal / 10);
        }
    }
}
````
````javascript
// Javascript program for the above approach
function octal_to_decimal(octal) {
  if (octal == 0) {
    return 0;
  } else {
    return (octal % 10) + 8 * octal_to_decimal(Math.floor(octal / 10));
  }
}
let octal = 67;
console.log(octal_to_decimal(octal));
// This code is contributed by rishabmalhdijo
````
**Output**
```
55
```
**The time complexity of this method is O(log n), where n is the given number**
**Auxiliary space: O(log n), where n is the given number**
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/program-octal-decimal-conversion/)

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
