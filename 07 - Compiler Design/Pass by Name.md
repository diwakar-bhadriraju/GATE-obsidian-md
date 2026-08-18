---
title: "Pass By Name in Compiler Design"
subject: "Compiler Design"
topic: "Runtime Environment"
source: "https://www.geeksforgeeks.org/compiler-design/pass-by-name-in-compiler-design/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Runtime Environment"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/runtime-environment
---


> [!abstract] Pass By Name in Compiler Design
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Runtime Environment`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/pass-by-name-in-compiler-design/)

---

# Pass By Name in Compiler Design

Compiler design is a captivating field that plays a role, in transforming high-level programming languages into machine code enabling computers to perform tasks. One concept that often stands out in compiler design is the idea of "**pass by the name**". We will explore the details of pass-by names, define terms, and provide insights into their significance in compiler design.
## **Introduction**
Compiler design is a discipline that involves processes like parsing, syntax analysis, optimization, and code generation. While not extensively discussed some concepts in compilers pass by name play a vital role in understanding how parameters are passed to functions or procedures within a program.
It's important to explore pass-by-name to gain an understanding of compiler design.
## **Defining Important Terms**
Some of the basic terms that are used in Compiler Design are defined below.
### **1. Pass by Name**
Pass by name refers to a mechanism, for passing parameters where the actual argument (the expression or variable) is directly substituted into the body of the function or procedure at each point where the parameter is used. In terms of the parameter is not evaluated until it is used within the function or procedure.
### **2. Actual Argument**
An actual argument represents the value or expression passed to a function or procedure when it is called.
In the pass by name approach the function or procedure body directly uses the argument without any substitution.
### **3. Formal Parameter**
A formal parameter serves as a placeholder, for the argument when defining a function or procedure. It specifies the arguments type and name.
### **4. Macro Expansion**
In pass by name macro expansion involves substituting the parameter with the argument in the body of a function or procedure. This substitution occurs each time the formal parameter is used.
## **Understanding Pass by Name with Examples**
To better understand pass by name lets consider an example in [python programming language](https://www.geeksforgeeks.org/python/python-programming-language-tutorial/);
````python
def swap(a, b):
    temp = a
    a = b
    b = temp
def main():
    x = 5
    y = 10
    swap(x, y)
    print("After swapping, x =", x)
    print("After swapping, y =", y)
main()
````
### Output
```
('After swapping, x =', 5)('After swapping, y =', 10)
```
In this code we're showcasing the concept of Pass by Name in Python. The swap function has two parameters, a and b. When the swap(x, y) is invoked within the function it directly replaces the values of x and y in the swap function body without evaluating them.
## **Significance in Compiler Design**
Pass by name can significantly impact code generation and optimization in compilers. It allows for flexible parameter passing enabling procedures to directly manipulate their arguments. However it also presents challenges regarding code size and efficiency since multiple expansions of arguments may result in code redundancy.
## **Conclusion**
When it comes to compiler design having a grasp of parameter passing mechanisms, like pass by name is essential for creating effective compilers. This has provided an overview of pass by name defined terms and demonstrated its functionality through examples. While pass by name may not be the utilized method for passing parameters it plays a fundamental role in compiler design enhancing our understanding of how programming languages are transformed into executable code.
To summarize pass by name is an aspect of [compiler design](https://www.geeksforgeeks.org/compiler-design/introduction-of-compiler-design/) that emphasizes the relationship between programming languages and the machine code they generate. Its complex operation showcases the depth of this field making it an engaging subject for those, in compilers.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/pass-by-name-in-compiler-design/)

## GATE CS

- Subject: Compiler Design
- Topic: Runtime Environment

> [!note] Related notes
>
> - [[Pass by Copy-restore]]
> - [[Runtime Environments]]
> - [[Ambiguous Grammar]]
> - [[Backtracking]]
> - [[Bottom Up or Shift Reduce Parsers]]
> - [[Classification of Context Free Grammars]]
> - [[Classification of top down parsers]]
> - [[Code Motion]]
> - [[Code Optimization]]
> - [[Common Sub Expression Elimination]]
