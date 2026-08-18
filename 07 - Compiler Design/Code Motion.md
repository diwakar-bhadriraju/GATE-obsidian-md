---
title: "What is Code Motion?"
subject: "Compiler Design"
topic: "Local Optimization"
source: "https://www.geeksforgeeks.org/compiler-design/what-is-code-motion/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Compiler Design/Local Optimization"
tags:
  - gate/cs
  - subject/compiler-design
  - topic/local-optimization
---


> [!abstract] What is Code Motion?
> 
> **Subject:** `Compiler Design` &nbsp;|&nbsp; **Topic:** `Local Optimization`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/what-is-code-motion/)

---

# What is Code Motion?

Code motion, a sophisticated compiler optimization technique, plays a pivotal role in enhancing the performance of computer programs. By strategically relocating statements or expressions, code motion reduces the frequency at which they are executed, leading to improved program efficiency. This optimization approach effectively minimizes redundant computations, optimizes cache utilization, and boosts overall program execution. This article explores the concept of code motion, its manifold benefits, and provides insights into its professional application for optimizing program performance.
## **Understanding Code Motion**
Code motion entails identifying and relocating computations or statements that are prone to repeated execution, with the goal of minimizing their overall frequency. It is a [compiler](https://www.geeksforgeeks.org/compiler-design/introduction-to-compilers/) optimization strategy that aims to reduce the redundant execution of computations or statements, improving program efficiency. It primarily focuses on [loop](https://www.geeksforgeeks.org/c/c-loops/) structures because they often account for the majority of a program's execution time and it specifically targets loop structures, as they tend to be the most time-consuming parts of a program.
### **Types of Code Motion**
Following are the types of Code Motion:
- **Loop-Invariant Code Motion (LICM)**
- **Conditional Code Motion**
**Loop-Invariant Code Motion (LICM)**
LICM focuses on recognizing expressions or statements within loops that remain unchanged throughout the loop's execution. These [loop-invariant](https://www.geeksforgeeks.org/dsa/loop-invariant-condition-examples-sorting-algorithms/) computations can be safely moved outside the loop, significantly reducing the number of times they need to be evaluated. This optimization proves especially effective when dealing with loops that encompass a substantial number of iterations.
**Conditional Code Motion**
Conditional code motion emphasizes the relocation of conditional statements or computations from loops whenever possible. By decreasing the frequency of condition evaluations, this optimization minimizes the impact of branching instructions, ultimately resulting in improved program performance.
## **Benefits of Code Motion**
Below are the benefits of Code Motion:
- **Computational Overhead Reduction**: Code motion effectively alleviates the computational workload by relocating computations that are invariant or possess fewer dependencies outside the loop. This eliminates or reduces redundant computations, leading to faster execution.
- **Enhanced Cache Utilization**: Frequent computations within loops can induce cache [thrashing](https://www.geeksforgeeks.org/operating-systems/techniques-to-handle-thrashing/), where data is continuously evicted from the cache. By diminishing the number of computations and memory accesses, code motion optimizes cache utilization, mitigates memory latency, and accelerates program execution.
- **Improved Instruction-Level Parallelism**: Code motion increases the potential for [instruction-level parallelism](https://www.geeksforgeeks.org/computer-organization-architecture/instruction-level-parallelism/) (ILP) by reducing dependencies and enabling more independent instructions to execute simultaneously. This optimization optimizes the utilization of available hardware resources, resulting in superior program throughput.
- **Compiler Optimization Support**: Modern optimizing compilers provide extensive support for code motion and other advanced optimization techniques. These compilers thoroughly analyze program control flow, dependencies, and data flow to identify and exploit opportunities for code motion. By leveraging the capabilities of optimizing compilers, developers can focus on writing clean and maintainable code while relying on the compiler to perform intricate optimizations.
## **Applying Code Motion**
To effectively leverage code motion, adopt the following best practices:
- **Identification of Loop-Invariant Computations**: Carefully examine loops within your program and identify computations that remain unchanged throughout the loop's execution. Relocate these computations outside the loop to minimize redundant evaluations.
- **Evaluation of Conditional Statements**: Thoroughly assess the impact of conditional statements within loops on program performance. Determine if it is feasible to relocate the condition evaluation outside the loop to reduce the frequency of branching instructions.
- **Harness Compiler Optimization Capabilities**: Utilize modern optimizing compilers equipped with robust code motion and other optimization techniques. Configure compiler flags and options to enable optimization during the compilation process.
- **Performance Measurement and Evaluation**: After implementing code motion, meticulously measure the performance of your program using appropriate benchmarks. Compare execution time and resource utilization before and after the optimization to objectively evaluate its effectiveness.
## Conclusion
Code motion, also known as frequency reduction, is an advanced compiler optimization technique that significantly improves program performance. By minimizing redundant computations, optimizing cache utilization, and enhancing instruction-level parallelism, code motion effectively maximizes program efficiency. Familiarity with [loop-invariant](https://www.geeksforgeeks.org/dsa/loop-invariant-condition-examples-sorting-algorithms/) computations, conditional statements, and modern optimizing compilers empowers developers to apply code motion strategically and optimize their programs for peak performance.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/compiler-design/what-is-code-motion/)

## GATE CS

- Subject: Compiler Design
- Topic: Local Optimization

> [!note] Related notes
>
> - [[Code Optimization]]
> - [[Common Sub Expression Elimination]]
> - [[Constant Folding]]
> - [[Constant Propagation]]
> - [[Copy Propagation]]
> - [[Dead Code Elimination]]
> - [[Frequency Reduction]]
> - [[Function Inlining]]
> - [[Induction Variable and Strength Reduction]]
> - [[Loop Jamming]]
