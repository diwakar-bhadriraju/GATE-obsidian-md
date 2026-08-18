---
title: "Program for Binary To Decimal Conversion"
subject: "Digital Logic and Design"
topic: "Number Representation and Computer Arithmetic"
source: "https://www.geeksforgeeks.org/dsa/program-binary-decimal-conversion/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Number Representation and Computer Arithmetic"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/number-representation-and-computer-arithmetic
---


> [!abstract] Program for Binary To Decimal Conversion
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Number Representation and Computer Arithmetic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/program-binary-decimal-conversion/)

---

# Program for Binary To Decimal Conversion

Given a binary number as input, we need to write a program to convert the given [binary number](https://www.geeksforgeeks.org/maths/binary-number-system/) into an equivalent [decimal number.](https://www.geeksforgeeks.org/digital-logic/decimal-number-system/)
**Examples :** 
> **Input :** 111
> **Output :** 7
> **Explanation** : The output of 7 for input 111 represents the decimal equivalent of the binary number 111.
>
> **Input :** 1010
> **Output :** 10
> **Explanation** : The output of 10 for input 1010 represents the decimal equivalent of the binary number 1010.
>
> **Input:** 100001
> **Output:** 33
> **Explanation** : The output of 33 for input 100001 represents the decimal equivalent of the binary number 100001.
**Check:** [Binary to Decimal Converter](https://www.geeksforgeeks.org/utilities/binary-to-decimal/)
The idea is to extract the digits of a given binary number starting from the rightmost digit and keep a variable dec\_value. At the time of extracting digits from the binary number, multiply the digit with the proper base (Power of 2) and add it to the variable dec\_value. In the end, the variable dec\_value will store the required decimal number.
For Example: 
If the binary number is 111. 
dec\_value = 1\*(2^2) + 1\*(2^1) + 1\*(2^0) = 7
The below diagram explains how to convert ( 1010 ) to equivalent decimal value: 
![binary2decimal](assets/binary2decimal-90bd96e9ed.png)
Below is the implementation of the above idea : 
````cpp
// C++ program to convert binary to decimal
#include <iostream>
using namespace std;
// Function to convert binary to decimal
int binaryToDecimal(int n)
{
    int num = n;
    int dec_value = 0;
    // Initializing base value to 1, i.e 2^0
    int base = 1;
    int temp = num;
    while (temp) {
        int last_digit = temp % 10;
        temp = temp / 10;
        dec_value += last_digit * base;
        base = base * 2;
    }
    return dec_value;
}
// Driver program to test above function
int main()
{
    int num = 10101001;
    cout << binaryToDecimal(num) << endl;
}
````
````java
// Java program to convert
// binary to decimal
// Function to convert
// binary to decimal
class GFG {
    static int binaryToDecimal(int n)
    {
        int num = n;
        int dec_value = 0;
        // Initializing base
        // value to 1, i.e 2^0
        int base = 1;
        int temp = num;
        while (temp > 0) {
            int last_digit = temp % 10;
            temp = temp / 10;
            dec_value += last_digit * base;
            base = base * 2;
        }
        return dec_value;
    }
    // Driver Code
    public static void main(String[] args)
    {
        int num = 10101001;
        System.out.println(binaryToDecimal(num));
    }
}
// This code is contributed by mits.
````
````python3
# Python3 program to convert
# binary to decimal
# Function to convert
# binary to decimal
def binaryToDecimal(n):
    num = n
    dec_value = 0
    # Initializing base
    # value to 1, i.e 2 ^ 0
    base = 1
    temp = num
    while(temp):
        last_digit = temp % 10
        temp = int(temp / 10)
        dec_value += last_digit * base
        base = base * 2
    return dec_value
# Driver Code
num = 10101001
print(binaryToDecimal(num))
````
````csharp
// C# program to convert
// binary to decimal
// Function to convert
// binary to decimal
class GFG {
    public static int binaryToDecimal(int n)
    {
        int num = n;
        int dec_value = 0;
        // Initializing base1
        // value to 1, i.e 2^0
        int base1 = 1;
        int temp = num;
        while (temp > 0) {
            int last_digit = temp % 10;
            temp = temp / 10;
            dec_value += last_digit * base1;
            base1 = base1 * 2;
        }
        return dec_value;
    }
    // Driver Code
    public static void Main()
    {
        int num = 10101001;
        System.Console.Write(binaryToDecimal(num));
    }
}
// This code is contributed by mits.
````
````javascript
<script>
// JavaScript program to convert binary to decimal
// Function to convert binary to decimal
function binaryToDecimal(n)
{
    let num = n;
    let dec_value = 0;
    // Initializing base value to 1, i.e 2^0
    let base = 1;
    let temp = num;
    while (temp) {
        let last_digit = temp % 10;
        temp = Math.floor(temp / 10);
        dec_value += last_digit * base;
        base = base * 2;
    }
    return dec_value;
}
// Driver program to test above function
    let num = 10101001;
    document.write(binaryToDecimal(num) + "<br>");
// This code is contributed by Surbhi Tyagi
</script>
````
**Output**
```
169
```
**Time complexity :** O( log n) We can also say time complexity as O(d) where d is number of digits.
**Auxiliary Space :** O(1)
**Note:** The program works only with binary numbers in the range of integers. In case you want to work with long binary numbers like 20 bits or 30 bit, you can use a string variable to store the binary numbers.
Below is a similar program which uses string variable instead of integers to store binary value: 
````cpp
// C++ program to convert binary to decimal
// when input is represented as binary string.
#include <iostream>
#include <string>
using namespace std;
// Function to convert binary to decimal
int binaryToDecimal(string n)
{
    string num = n;
    int dec_value = 0;
    // Initializing base value to 1, i.e 2^0
    int base = 1;
    int len = num.length();
    for (int i = len - 1; i >= 0; i--) {
        if (num[i] == '1')
            dec_value += base;
        base = base * 2;
    }
    return dec_value;
}
// Driver program to test above function
int main()
{
    string num = "10101001";
    cout << binaryToDecimal(num) << endl;
}
````
````java
// Java program to convert binary to
// decimal when input is represented
// as binary string.
import java.io.*;
class GFG {
    // Function to convert binary to decimal
    static int binaryToDecimal(String n)
    {
        String num = n;
        int dec_value = 0;
        // Initializing base value to 1,
        // i.e 2^0
        int base = 1;
        int len = num.length();
        for (int i = len - 1; i >= 0; i--) {
            if (num.charAt(i) == '1')
                dec_value += base;
            base = base * 2;
        }
        return dec_value;
    }
    // Driver program to test above function
    public static void main(String[] args)
    {
        String num = new String("10101001");
        System.out.println(binaryToDecimal(num));
    }
}
// This code is contributed by Prerna Saini
````
````python3
# Python3 program to convert binary
# to decimal when input is
# represented as binary string.
# Function to convert
# binary to decimal
def binaryToDecimal(n):
    num = n
    dec_value = 0
    # Initializing base
    # value to 1, i.e 2 ^ 0
    base1 = 1
    len1 = len(num)
    for i in range(len1 - 1, -1, -1):
        if (num[i] == '1'):
            dec_value += base1
        base1 = base1 * 2
    return dec_value
# Driver Code
num = "10101001"
print(binaryToDecimal(num))
````
````csharp
// C# program to convert binary to
// decimal when input is represented
// as binary string.
using System;
class GFG {
    // Function to convert binary to decimal
    static int binaryToDecimal(String n)
    {
        String num = n;
        int dec_value = 0;
        // Initializing base value to 1,
        // i.e 2^0
        int base1 = 1;
        int len = num.Length;
        for (int i = len - 1; i >= 0; i--) {
            if (num[i] == '1')
                dec_value += base1;
            base1 = base1 * 2;
        }
        return dec_value;
    }
    // Driver Code
    public static void Main()
    {
        String num = "10101001";
        Console.WriteLine(binaryToDecimal(num));
    }
}
// This code is contribute by mits
````
````javascript
<script>
// Javascript program to convert binary to decimal
// when input is represented as binary string.
// Function to convert binary to decimal
function binaryToDecimal(n)
{
    let num = n;
    let dec_value = 0;
    // Initializing base value to 1, i.e 2^0
    let base = 1;
    let len = num.length;
    for (let i = len - 1; i >= 0; i--) {
        if (num[i] == '1')
            dec_value += base;
        base = base * 2;
    }
    return dec_value;
}
// Driver program to test above function
    let num = "10101001";
    document.write(binaryToDecimal(num) + "<br>");
// This code is contributed by Mayank Tyagi
</script>
````
**Output**
```
169
```
**Time complexity :** O(n) where n is the length of the string.
**Auxiliary Space :** O(1)
Here is another way to convert decimal to binary numbers which is more intuitive and faster. At every iteration we extract the last digit (or a character in case of string input), check if it is a 1, if it is then multiply by the power of 2(where the power depends on which bit we are currently on ) and add it to the decimal number( initially = 0 ) .If it is a 0, then we don't need to add anything to our decimal value since that bit is not contributing, so just increase the power and move to the next bit.
If we left shift 1 by n times ( 1<<n ), we basically get 2^n. Hence we use left shift operator( << ) to find the powers of two since it is faster.
1) If the input is of int type :
````cpp
// C++ program to convert binary to decimal
#include <iostream>
using namespace std;
// Function to convert binary to decimal
int binaryToDecimal(int n)
{
    int dec_num = 0 ;
      int power = 0 ;
      while(n>0){
      if(n%10 == 1){ // extracting the last digit
        dec_num += (1<<power) ;
      }
      power++ ;
      n = n / 10 ;
    }
      return dec_num ;
}
// Driver program to test above function
int main()
{
    int num = 10101001;
    cout << binaryToDecimal(num) << endl;
}
````
````java
public class BinaryToDecimal {
  public static int binaryToDecimal(int n)
  {
    int dec_num = 0;
    int power = 0;
    while (n > 0) {
      if (n % 10 == 1) {
        dec_num += (1 << power);
      }
      power++;
      n = n / 10;
    }
    return dec_num;
  }
  public static void main(String[] args)
  {
    int num = 10101001;
    System.out.println(binaryToDecimal(num));
  }
}
// This code is contributed by aadityamaharshi21.
````
````python3
# Python program to convert binary to decimal
import math
def binaryToDecimal(n):
    dec_num = 0
    power = 0
    while (n > 0):
        if (n % 10 == 1): # extracting the last digit
            dec_num += (1 << power)
        power = power + 1
        n = math.floor(n / 10)
    return dec_num
# Driver program to test the function
num = 10101001
print(binaryToDecimal(num))
````
````csharp
using System;
public class Program
{
  // Function to convert binary to decimal
  public static int BinaryToDecimal(int n)
  {
    int dec_num = 0;
    int power = 0;
    while (n > 0)
    {
      if (n % 10 == 1) // extracting the last digit
      {
        dec_num += (1 << power);
      }
      power++;
      n = n / 10;
    }
    return dec_num;
  }
  // Driver program to test above function
  public static void Main()
  {
    int num = 10101001;
    Console.WriteLine(BinaryToDecimal(num));
  }
}
````
````javascript
// JavaScript program to convert binary to decimal
function binaryToDecimal(n) {
    let dec_num = 0;
    let power = 0;
    while (n > 0) {
        if (n % 10 === 1) { // extracting the last digit
            dec_num += (1 << power);
        }
        power++;
        n = Math.floor(n / 10);
    }
    return dec_num;
}
// Driver program to test the function
let num = 10101001;
console.log(binaryToDecimal(num));
// This code is contributed by adityamaharshi21.
````
**Output**
```
169
```
**Time complexity :** O(log n)
**Space complexity :** O(1)
2) If the input is of string type :
````cpp
// C++ program to convert binary to decimal
// when input is represented as binary string.
#include <iostream>
#include <string>
using namespace std;
// Function to convert binary to decimal
int binaryToDecimal(string str)
{
    int dec_num = 0;
      int power = 0 ;
    int n = str.length() ;
      for(int i = n-1 ; i>=0 ; i--){
      if(str[i] == '1'){
        dec_num += (1<<power) ;
      }
      power++ ;
    }
    return dec_num;
}
// Driver program to test above function
int main()
{
    string num = "10101001";
    cout << binaryToDecimal(num) << endl;
}
````
````java
// Java program to convert binary to decimal
import java.util.*;
public class BinaryToDecimal {
    public static int binaryToDecimal(String str) {
        int dec_num = 0;
        int power = 0;
        int n = str.length();
        for (int i = n - 1; i >= 0; i--) {
            if (str.charAt(i) == '1') {
                dec_num += (int) Math.pow(2, power);
            }
            power++;
        }
        return dec_num;
    }
    public static void main(String[] args) {
        String num = "10101001";
        System.out.println(binaryToDecimal(num));
    }
}
````
````python3
# Python program to convert binary to decimal
def binaryToDecimal(str):
    dec_num = 0
    power = 0
    n = len(str)
    # Iterate through the string str
    for i in range(n - 1, -1, -1):
        if (str[i] == '1'):
            dec_num += (2 ** power)
        power += 1
    return dec_num
# Driver code
num = "10101001"
print(binaryToDecimal(num))
````
````csharp
using System;
class Program {
    // Function to convert binary to decimal
    static int binaryToDecimal(string str)
    {
        int dec_num = 0;
        int power = 0;
        int n = str.Length;
        // Loop through the string from right to left
        for (int i = n - 1; i >= 0; i--) {
            // If the current character is '1', add 2^power
            // to the decimal number
            if (str[i] == '1') {
                dec_num += (1 << power);
            }
            power++;
        }
        return dec_num;
    }
    // Driver program to test above function
    static void Main(string[] args)
    {
        string num = "10101001";
        Console.WriteLine(binaryToDecimal(num));
    }
}
````
````javascript
// Javascript program to convert binary to decimal
// when input is represented as binary string.
// Function to convert binary to decimal
function binaryToDecimal(str)
{
    let dec_num = 0;
    let power = 0 ;
    let n = str.length;
    for(let i = n-1 ; i>=0 ; i--){
        if(str[i] == '1'){
            dec_num += (1<<power) ;
        }
        power++ ;
    }
    return dec_num;
}
// Driver program to test above function
let num = "10101001";
console.log(binaryToDecimal(num));
// The code is contributed by Arushi Goel.
````
**Output**
```
169
```
**Time complexity**: O(k) [since at max, we will have to process 32 bits which will take 32 iterations.]
**Auxiliary Space** : O(1)
**Using pre-defined function:** 
````cpp
#include <iostream>
using namespace std;
int main()
{
    char binaryNumber[] = "1001";
    cout << stoi(binaryNumber, 0, 2);
    return 0;
}
// This code is contributed by whysodarkbro
````
````c
#include <stdio.h>
#include <math.h>
#include <stdlib.h>
int main()
{
    char binaryNumber[] = "1001";
    int bin, dec = 0;
    bin = atoi(binaryNumber);
    for(int i = 0; bin; i++, bin /= 10)
        if (bin % 10)
            dec += pow(2, i);
    printf("%d", dec);
    return 0;
}
// This code is contributed by whysodarkbro
````
````java
public class GFG {
    public static void main(String args[])
    {
        String binaryNumber = "1001";
        System.out.println(Integer.parseInt(binaryNumber, 2));
    }
}
// This code is contributed
// By Yash Kumar Arora
````
````python3
n = input()
# Convert n to base 2
s = int(n, 2)
print(s)
````
````csharp
using System;
class GFG {
public static void Main()
{
    int value = 1001;
    Console.Write(Convert.ToInt32(value.ToString(), 2));
}
}
// This code is contributed by SoumikMondal
````
````javascript
<script>
var binaryNumber = "1001";
document.write(parseInt(binaryNumber, 2));
// This code contributed by Princi Singh
</script>
````
**Output**
```
9
```
**Time complexity:** O(n) where n is the length of the given string.
**Auxiliary Space:** O(1) 
#### 3) Using Horner's scheme
Horner’s scheme is an efficient approach for computing polynomials and it can be redirected into different other scenarios like converting numbers from one numerical system to another (Binary to decimal, etc.), evaluating the Taylor series, etc.
Given a polynomial of degree n, Cnxn + Cn-1xn-1 + Cn-2 xn-2 +…+C1x + C0, it can be nested such that the solution is achieved with n multiplications and n additions using this scheme. Simply put, starting from the first coefficient, multiply by x and add the next coefficient.
```
Cnxn + Cn-1xn-1 + Cn-2 xn-2 +…+C1x + C0 = (((Cnx + Cn-1)x + Cn-2)x + Cn-3)x +… + C0
```
**Example:**
3x3 + 4x2 + 6x + 3 = ((3x + 4)x + 6)x + 3
Observe that when we expand a binary number, it takes the form of a polynomial:
```
Polynomial: Cnxn + Cn-1xn-1 + Cn-2xn-2 +…+C1x + C0
Binary expansion: digitn(2n) + digitn-1(2n-1) + digitn-2(2n-2) + … + digit0(20)
```
The constants in the polynomial form are replaced by digits of the binary number and x=2. Hence, we can just use the same polynomial trick on this conversion:
**Example:**
**10100**2**
= 1\*24 + 0\*23 + 1\*22 + 0\*21 + 0\*20
= (((1(2) + 0)2 + 1)2 + 0)2 + 0
= 20
````cpp
#include <iostream>
#include <string>
int main() {
    // Create a string to store the binary number
    std::string binaryNumber;
    // Prompt the user to enter a binary number
    std::cout << "Enter Binary number: ";
    // Read the entire line as input
    std::getline(std::cin, binaryNumber);
    // Convert binary to decimal
    int decimalNumber = 0;
    for (size_t i = 0; i < binaryNumber.length(); i++) {
        decimalNumber = decimalNumber * 2 + (binaryNumber[i] - '0');
    }
    // Print the decimal number
    std::cout << "Decimal: " << decimalNumber << std::endl;
    return 0;
}
````
````java
import java.util.Scanner;
public class BinaryToDecimal {
    public static void main(String[] args) {
        // Create a Scanner object to take user input
        Scanner scanner = new Scanner(System.in);
        // Prompt the user to enter a binary number
        System.out.print("Enter Binary number: ");
        // Read the entire line as input
        String binaryNumber = scanner.nextLine();
        // Convert binary to decimal
        int decimalNumber = 1;
        for (int i = 0; i < binaryNumber.length() - 1; i++) {
            decimalNumber = decimalNumber * 2 + Character.getNumericValue(binaryNumber.charAt(i + 1));
        }
        // Print the decimal number
        System.out.print("Decimal: ");
        System.out.println(decimalNumber);
        // Close the Scanner
        scanner.close();
    }
}
````
````python3
n = input("Enter Binary number: ")
dec = 1
for i in range(len(n)-1):
    dec = dec*2 + int(n[i+1])
print("Decimal: ", end = "")
print(dec)
# This code is contributed by Jeevani Anumandla
````
````csharp
using System;
class Program {
    static void Main(string[] args)
    {
        // Create a string to store the binary number
        string binaryNumber;
        // Prompt the user to enter a binary number
        Console.Write("Enter Binary number: ");
        // Read the entire line as input
        binaryNumber = Console.ReadLine();
        // Check if input is empty
        if (string.IsNullOrEmpty(binaryNumber)) {
            Console.WriteLine("Decimal: 0");
            return; // Exit the program
        }
        // Convert binary to decimal
        int decimalNumber = 0;
        for (int i = 0; i < binaryNumber.Length; i++) {
            decimalNumber = decimalNumber * 2
                            + (binaryNumber[i] - '0');
        }
        // Print the decimal number
        Console.WriteLine("Decimal: " + decimalNumber);
    }
}
````
````javascript
// Prompt the user to enter a binary number
var n = prompt("Enter Binary number: ");
// Initialize the decimal variable to store the result
var dec = 1;
// Iterate through each digit of the binary number
for (var i = 0; i < n.length - 1; i++) {
// Update the decimal value using the formula: dec = dec * 2 + currentBinaryDigit
dec = dec * 2 + parseInt(n[i + 1]);
}
// Display the decimal result
console.log("Decimal: " + dec);
````
**Output:**
Enter Binary number: 10010
Decimal: 18
**Time complexity:** O(n)
**Decreased operations:** Horners scheme only takes n multiplications and n additions for the conversion.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/program-binary-decimal-conversion/)

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
> - [[Program for Decimal to Binary Conversion]]
