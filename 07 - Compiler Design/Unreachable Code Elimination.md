---
title: "Unreachable Code Elimination"
subject: "Compiler Design"
topic: "Local Optimization"
source: "https://www.geeksforgeeks.org/compiler-design/unreachable-code-elimination/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Local Optimization"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/local-optimization
---


> [!abstract] Unreachable Code Elimination
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Local Optimization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/unreachable-code-elimination/)

---

# Unreachable Code Elimination

Unreachable Code is also known as dead code in Compiler Design that points to the portion of a program that is never executed under any condition or scenario. This dead code doesn't do any functionality in the program but unnecessarily occupies the space in the application memory, and also due to this there are different problems of unnecessary computation, that describe the program's performance. So, to avoid this issue in Compiler Design, we can use the technique of Unreachable Code Elimination. In this Compiler Design article, we will see Unreachable Code Elimination with its techniques, practical examples, and advantages.
## Techniques for Unreachable Code Detection
Below mentioned are the techniques for Unreachable Code Detection.
- Static Analysis Techniques
- Dynamic Analysis Techniques
### Static Analysis Techniques
Static Analysis techniques analyze the program's code or the intermediate outlined representation of code without actually executing it. Static Analysis helps to properly understand the control flow and the data flow of the survey program so that it will be easy to detect the potential Unreachable Code in the program.
- **Control Flow Analysis:** Control Flow Analysis measures the program's control flow graph which traces all possible execution routes. Using the Code Flow Analysis we can identify the route that is not reached while executing the source program. Conditional Statements, Loops, Functional Calls, and branching constructs are taken into consideration in Control Flow Analysis.
- **Data Flow Analysis:** Data Flow Analysis traces variable values and their assignments throughout the program. The main purpose of using the Data Flow analysis is that it helps us to properly identify the variables that are just declared but not used in the source code. By analyzing the data dependencies, Data Flow analysis techniques easily detect dead code and also help to eliminate it from the code.
### Dynamic Analysis Techniques
Dynamic Analysis Techniques are used to analyze the execution of the program with user testing inputs and tracking the test cases. The aim is to observe the behavior during the runtime execution of the program or source code. Dynamic Analysis Techniques detect the Unreachbele Code in the source program according to the execution route and Code Coverage data.
- **Code Coverage Analysis:** Code Code Analysis calculates the extent to which the program's code is trained by a given set of test cases. Code Coverage Analysis identifies the code that is unexecuted in the source program execution. Some of the most used Common Code Coverage Metrics are Statement Coverage, Branch Coverage, and Path Coverage.
- **Program Profiling:** Program Profiling technique consists of collecting runtime data during program execution. This analysis of the execution tracks identifies the Code Routes that are never reached for execution. By Profiling the program's behavior, Unreachable Code can be easily identified and subsequently eliminated.
## Example of Unreachable Code Elimination
Consider the below C++ code snippet as an Example of Unreachable Code Elimination.
### Before Optimization
````cpp
#include <iostream>
void exampleFunction(int x)
{
    if (x > 10) {
        std::cout <<"x is greater than 10" << std::endl;
    }
    else {
        std::cout <<"x is less than or equal to 10" << std::endl;
        return;
        std::cout<<"This line is unreachable" << std::endl;
    }
}
int main()
{
    exampleFunction(15);
    return 0;
}
````
In the above code, there is a function called the example function that takes an integer x as input. It checks if x is greater than 10. If it is, it prints " x is greater than 10 " to the console. Otherwise, it prints "x is less than or equal to 10" and has an extra line that will never be executed due to the return statement before it.
### After Optimization
````cpp
#include <iostream>;
void exampleFunction(int x)
{
    if (x > 10) {
        std::cout << "x is greater than 10" << std::endl;
    }
    else {
        std::cout << "x is less than or equal to 10"
                  << std::endl;
        return;
    }
}
int main()
{
    exampleFunction(15);
    return 0;
}
````
After optimization, the unreachable line of code std::cout << "This line is unreachable" << std::endl; is removed. The resulting optimized code still prints the appropriate message based on the value of x , but it eliminates the unnecessary and unreachable line.
## Advantages/Benefits of Unreachable Code Elimination
- **Performance Improvement:** The compiler reduces pointless computations and instructions, which improves program performance by removing unreachable code. Dead code should be removed because it makes the program work less and completes operations more quickly.
- **Reduced Memory Usage:** The compiled program uses memory to store unreachable code. So if we eliminate this unreachable code, then the memory usage is minimized and we can use the memory for other computations. In some systems, the memory is limited for the operations, so unreachable code elimination is more useful for these systems.
- **Improved Readability and Maintainability:** Removing inaccessible code makes the codebase easier to read and maintain. The program is simpler to comprehend and modify because developers can concentrate on pertinent code.
- **Optimization of Resource Utilisation:** By eliminating unreachable code, less computation, and memory usage is required, which leads to optimized resource use. When aiming for devices with low processing power or memory, or in resource-constrained systems, this optimization is especially beneficial.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/unreachable-code-elimination/)

## GATE CS

- Subject: Compiler Design
- Topic: Local Optimization

> [!note] Related notes
>
> - [[Code Motion]]
> - [[Code Optimization]]
> - [[Common Sub Expression Elimination]]
> - [[Constant Folding]]
> - [[Constant Propagation]]
> - [[Copy Propagation]]
> - [[Dead Code Elimination]]
> - [[Frequency Reduction]]
> - [[Function Inlining]]
> - [[Induction Variable and Strength Reduction]]
