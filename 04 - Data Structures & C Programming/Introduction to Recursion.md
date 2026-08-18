---
title: "Recursion Notes for GATE Exam [2024]"
subject: "Data Structures & C Programming"
topic: "Recursion"
source: "https://www.geeksforgeeks.org/dsa/recursion-notes-for-gate-exam/#introduction-to-recursion"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Data Structures & C Programming/Recursion"
tags:
  - gate/cs
  - subject/data-structures-c-programming
  - topic/recursion
---


> [!abstract] Recursion Notes for GATE Exam [2024]
> 
> **Subject:** `Data Structures & C Programming` &nbsp;|&nbsp; **Topic:** `Recursion`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/dsa/recursion-notes-for-gate-exam/#introduction-to-recursion)

---

# Recursion Notes for GATE Exam [2024]

This Recursion Notes for the GATE Exam provides a comprehensive guide to one of the fundamental concepts in computer science, recursion, specifically tailored for those preparing for the Graduate Aptitude Test in Engineering (GATE). Recursion is a powerful problem-solving technique where a function calls itself during its execution, and it plays a significant role in algorithm design and programming.
Table of Content
- [Introduction to Recursion](#introduction-to-recursion)
- [Need of Recursion](#need-of-recursion)
- [Types of Recursion](#types-of-recursion)
- [Direct Recursion](#direct-recursion)
- [Indirect Recursion](#indirect-recursion)
- [Gate Previous Year Problems on Recursion](#gate-previous-year-problems-on-recursion)
## Introduction to Recursion
The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called a recursive function. Using a recursive algorithm, certain problems can be solved quite easily. Examples of such problems are [Towers of Hanoi (TOH)](https://www.geeksforgeeks.org/dsa/c-program-for-tower-of-hanoi/), [Inorder/Preorder/Postorder Tree Traversals](https://www.geeksforgeeks.org/dsa/tree-traversals-inorder-preorder-and-postorder/), [DFS of Graph](https://www.geeksforgeeks.org/dsa/depth-first-search-or-dfs-for-a-graph/), etc. A recursive function solves a particular problem by calling a copy of itself and solving smaller subproblems of the original problems. 
## Need of Recursion
Recursion is an amazing technique with the help of which we can reduce the length of our code and make it easier to read and write. It has certain advantages over the iteration technique which will be discussed later. A task that can be defined with its similar subtask, recursion is one of the best solutions for it. For example; The Factorial of a number.
## Types of Recursion
Recursion are mainly of**two types** depending on whether **a function calls itself from within itself** or **more than one function call one another mutually.** The first one is called **direct recursion** and another one is called **indirect recursion**. Thus, the two types of recursion are:
## **Direct Recursion**
Direct recursion occurs when a function directly calls itself within the same function. Direct Recursion can be further categorized into **four types**:
### **Tail Recursion**
If a recursive function calling itself and that recursive call is the last statement in the function then it’s known as **Tail Recursion.** After that call the recursive function performs nothing. The function has to process or perform any operation at the time of calling and it does nothing at returning time.
![tail1](assets/tail1-768-892a383c3d.jpg)
Tail Recursion
**Time Complexity For Tail Recursion : O(n)** 
**Space Complexity For Tail Recursion : O(n)**
### **Head Recursion**
If a recursive function calling itself and that recursive call is the first statement in the function then it’s known as **Head Recursion.** There’s no statement, no operation before the call. The function doesn’t have to process or perform any operation at the time of calling and all operations are done at returning time.
![head3](assets/head3-768-3999dc121f.jpg)
Head Recursion
**Time Complexity For Head Recursion: O(n)** 
**Space Complexity For Head Recursion: O(n)**
### **Tree Recursion**:
To understand **Tree Recursion** let’s first understand **Linear Recursion**. If a recursive function calling itself for one time then it’s known as **Linear Recursion**. Otherwise if a recursive function calling itself for more than one time then it’s known as **Tree Recursion**.
![Lightbox](assets/tree4-4d366a29c2.jpg)
**Time Complexity For Tree Recursion: O(2^n)** 
**Space Complexity For Tree Recursion: O(n)**
### **Nested Recursion**:
In this recursion, a recursive function will pass the parameter as a recursive call. That means **“recursion inside recursion”.** Let see the example to understand this recursion.
![](assets/nested2-d97c5b89d9.jpg)
## **Indirect Recursion**
In this recursion, there may be more than one functions and they are calling one another in a circular manner.
![](assets/Capture34-bf6b6541d2.jpg)
From the above diagram fun(A) is calling for fun(B), fun(B) is calling for fun(C) and fun(C) is calling for fun(A) and thus it makes a cycle.
## Gate Previous Year Problems on Recursion
**Question 1:** In the C language: **[GATE 2002: 2 marks]**
(A). At most one activation record exists between the current activation record and the activation record for the main.
(B). The number of activation records between the current activation record and the activation records from the main depends on the actual function calling sequence.
(C). The visibility of global variables depends on the actual function calling sequence
(D). Recursion requires the activation record for the recursive function to be saved in a different stack before the recursive function can be called.
> **Solution:** Correct answer is (B)
>
> **Explanation:**
>
> A→Incorrect, There is no such restriction in the C language
>
> B→ Correct
>
> C→ Incorrect. In C, variables are statically scoped, not dynamically.
>
> D→Incorrect. The activation records are stored on the same stack.
**Question 2:** Consider the following recursive C function that takes two arguments:
```
unsigned int foo (unsigned int n, unsigned int r) {
if (n > 0) return((n % r) + foo(n/r, r));
else return 0;
}
```
What is the return value of the function foo when it is called as foo (513, 2)? **[GATE 2011: 2 marks]**
(A). 9
(B). 8
(C). 5
(D). 2
> **Solution:** Correct answer is (D)
>
> **Explanation**
>
> The function call foo(513, 2) will return 1 + foo(256, 2). All subsequent recursive function calls (including foo(256, 2)) will return 0 + foo(n/2, 2) except the last function call foo(1, 2) . The last call foo(1, 2) returns 1. So, the value returned by call foo(513, 2) is 1 + 0 + 0…. + 0 + 1.The function call foo(n, 2) returns the sum of bits (or count of set bits) in the number n.
**Question 3:** Choose the correct option to fill ? 1 and ? 2 so that the program below prints an input string in reverse order. Assume that the input string is terminated by a newline character.
```
void recerse (void) {
int c;
if (?1) reverse() ;
?2
}
main {
printf ("Enter Text" ); 
printf("\n");
reverse() ;
printf("\n") ;
}
```
What does f(173) print? **[GATE 2008: 2 marks]**
(A). ?1 is (getchar() != ’\n’)
?2 is getchar(c);
(B).?1 is (c = getchar() ) != ’\n’)
?2 is getchar(c);
(C). ?1 is (c != ’\n’)
?2 is putchar(c);
(D). ?1 is ((c = getchar()) != ’\n’)
?2 is putchar(c);
> **Solution:** Correct answer is (D)
>
> **Explanation:**
>
> As given in the question, the '=' operator has less priority than the '!=' operator in the c program. So (c=getchar()) has to be in brackets and after reversing the string, we use the function putchar(c) for printing the character.
>
> So, option (D) is the correct answer.
**Question 4:** Consider the following recursive C function that takes two arguments.
```
unsigned int foo(unsigned int n, unsigned int r)
{
if(n>0) return((n%r)+foo(n/r,r));
else return 0;
}
```
What is the return value of the function foo when it is called as foo(345,10)? **[GATE 2011: 2 marks]**
(A). 345
(B). 12
(C). 5
(D). 3
> **Solution:** Correct answer is (B)
>
> **Explanation:**
>
> The function  call foo(345, 10) returns sum of decimal digits (because r is 10) in the number n.And Sum of digits for number (n) 345 is 3 + 4 + 5 = 12.
**Question 5:** Consider the following recursive C function:
```
int f(int n)
{
static int r = 0;
if(n <= 0) return 1;
if(n>3)
{
r = n;
return f(n-2)+2;
}
return f(n-1)+r;
}
```
What is the value of f(5)? **[GATE 2008: 2 marks]**
(A). 5
(B). 7
(C). 9
(D). 18
> **Solution:** Correct answer is (D)
>
> **Explanation:**
>
> f(5) = f(3)+2  
>
> The line "r = n" takes the value of r to 5.  Since r is static, its value is shared be all subsequence calls. Also, all subsequent calls don't change r because the statement "r = n" is in a if condition with n > 3.
>
> f(3) = f(2)+5
>
> f(2) = f(1)+5
>
> f(1) = f(0)+5
>
> f(0) = 1
>
> So f(5) = 1+5+5+5+2 = 18 
**Question 6:** Consider the following function written in the C programming language.
```
void foo(char *a){
 if ( *a && *a != ' '){
      foo(a+1);
      putchar(*a);
   }
}
```
The output of the above function on input “ABCD EFGH” is **[GATE 2015: 2 marks]**
(A). ABCD EFGH
(B). ABCD
(C). HGFE DCBA
(D). DCBA
> **Solution:** Correct answer is (D)
>
> **Explanation:** 
>
> The priority of != is greater than that of && in C program. The execution happens as: if ((\*a) && (\*a != ' '))
>
> So, the if condition breaks either when ∗a=0 (not '0' but ASCII 0 or null character'\0'), or when ∗a=' '.
>
> So, the recursive call goes like
>
> 'A' - 'B' - 'C' - 'D' -' ' (breaks) and then starts outputting
>
> DCBA
**Question 7:** What will be the output of the following C program segment?
Char inchar = 'A'; **[GATE 2012: 2 marks]**
```
Switch ( inchar ) {
case 'A' : printf ("Choice A\ n") ;
case 'B' :
case 'C' : printf (“Choice B”) ;
case 'D' :
case 'E' :
default : printf ( " No Choice" ) ; }
```
(A). No Choice
(B). Choice A
(C). Choise A Choise B No Choice
(D). Program gives no output as it is erroneous
> **Solution:** Correct answer is (C)
>
> **Explanation:** 
>
> Since there is no break statement in any case so all the cases will be executed and the answer will be an option(c).
**Question 8:** Which one of the following are essential features of an object-oriented programming language? **[GATE 2005: 2 marks]**
i) Abstraction and encapsulation
ii) Strictly-typedness
iii) Type-safe property coupled with sub-type rule
iv) Polymorphism in the presence of inheritance
(A). (i) and (ii) only
(B). (i) and (iv) only
(C). (i), (ii) and (iv) only
(D). (i), (iii) and (iv) only
> **Solution:** Correct answer is (B)
>
> **Explanation:** Abstraction, Encapsulation, Polymorphism and Inheritance are the essential features of a OOP Language.
**Question 9:** An Abstract Data Type (ADT) is **[GATE 2005: 2 marks]**
(A). Same as an abstract class.
(B). A data type that cannot be instantiated
(C). A data type for which only the operations defined on it can be used, but none else
 (D). All of the above
> **Solution:** Correct answer is (C)
>
> **Explanation:** 
>
> An abstract data type (ADT) supports only the operations which are defined.
>
> An abstract class is one that may not have definitions of all the objects it has. Moreover, it can not be instantiated. To instantiate we have to create a subclass and then instantiate the class.
**Question 10:** Consider the following C function. **[GATE 2003: 2 marks]**
```
float f,(float x, int y) {
float p, s; int i;
for (s=1,p=1,i=1; i < y; i++) {
p *= x/i;
 s+=p;
 }
return s;
}
```
For large values of y, the return value of the function f best approximates
(A). x^y
(B).e^x
(C). ln(1 + x)
(D). x^x
> **Solution:** Correct answer is (B)
>
> **Explanation:**
>
> i=1 then p=x & s=1+x
>
> i=2 then p=x2/2 & s=1+x+x2/2
>
> As y goes to infinity s tends to ex.
>
> Hence the correct answer is option b.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/dsa/recursion-notes-for-gate-exam/#introduction-to-recursion)

## GATE CS

- Subject: Data Structures & C Programming
- Topic: Recursion

> [!note] Related notes
>
> - [[1D, 2D and 3D Arrays]]
> - [[CATEGORY ARCHIVES DATA STRUCTURES]]
> - [[Data Types in C]]
> - [[Double Hashing]]
> - [[Enum, Struct & Union in C]]
> - [[Functions in C]]
> - [[I ntroduction to Trees]]
> - [[Introduction to Arrays]]
> - [[Introduction to C Programming]]
> - [[Introduction to Graphs]]
