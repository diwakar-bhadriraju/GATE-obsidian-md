---
title: "Difference between CALL and JUMP instructions"
subject: "Computer Organization and Architecture"
topic: "Machine Instructions and Addressing Modes"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/difference-call-jump-instructions/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Machine Instructions and Addressing Modes"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/machine-instructions-and-addressing-modes
---


> [!abstract] Difference between CALL and JUMP instructions
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Machine Instructions and Addressing Modes`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/difference-call-jump-instructions/)

---

# Difference between CALL and JUMP instructions

In assembly language as well as in low level programming CALL and JUMP are the two major control transfer instructions. Both instructions enable a program to go to different other parts of the code but both are different. CALL is mostly used to direct calls to subroutine or a function and regresses to the main program after function call only. On the other hand, JUMP cause the control to jump to another part of code and does not return. CALL and JUMP you need to understand well especially when operating at low levels and the optimizations to the control flow of a program.
## What is CALL Instruction?
The CALL instruction involves in calling up a subroutine or a function used in [assembly language](https://www.geeksforgeeks.org/computer-organization-architecture/what-is-assembly-language/). During CALL, the address of the instruction after the CALL instruction is stored on the stack since after a subroutine has been executed, the control flows back to the main program. This feature makes CALL suitable in areas, where a given line of code can be run several times for instance in function calls.
### Advantages of CALL Instruction
- **Code Reusability**: The CALL instruction is used to call subroutines thus making the codes reusable. This eliminates repetition, and has the added benefits of making the overall structure of the program easier to develop.
- **Ease of Maintenance**: It is easy to alter the program because the same subroutine is used many times. Any modifications that are done in the subroutine are implemented wherever its CALL instruction is employed.
- **Program Control**: CALL allows to come back to the point of the program where execution was interrupted with less interruptions, more controlled and less random program flow.
### Disadvantages of CALL Instruction
- **Performance Overhead**: The CALL instruction also include pushing the address of the next instruction to the stack which is not serious but may cause some performance degrade in cases where time is of high essence.
- **Stack Management**: Various problems such as stack overflow or memory problems can occur because of improper stack management (wrong disposing of a call, for example).
## What is JUMP Instruction?
The unconditioned branch instruction is called the JUMP or JMP for short where it is able to transfer control to a different part of the program. Like CALL, after JUMP executes the jump the program moves to the target address, the only difference is that there are no RETURN information needed to return back to the starting point. Basically, JUMP is utilized to do branching operations within the given code or to omit instructions liking certain code further.
### Advantages of JUMP Instruction
- **Efficiency**: This implies that JUMP instructions are usually faster than CALL instructions since the latter necessitate the saving and managing of return addresses.
- **Simpler Control Flow**: For loops, conditions, and for exiting some parts of the code without coming back are best suited to be used in JUMP.
- **Lower Overhead**: In this way, unlike in the case of CALL, no return address is pushed on the stack, and, therefore, JUMP has lesser overhead.
### Disadvantages of JUMP Instruction
- **No Return Mechanism**: There are no means to go back to the position where the JUMP instruction was executed which may prove problematic in some cases especially when one is debugging.
- **Risk of Unstructured Code**: This is especially because the use of JUMP instructions in a program’s code can result in generation of what is known as spaghetti code.
| SERIAL NO. | JUMP | CALL |
| --- | --- | --- |
| 1. | Program control is transferred to a memory location which is in the main program | Program Control is transferred to a memory location which is not a part of main program |
| 2. | Immediate Addressing Mode | Immediate Addressing Mode + Register Indirect Addressing Mode |
| 3. | Initialization of SP(Stack Pointer) is not mandatory | Initialization of SP(Stack Pointer) is mandatory |
| 4. | Value of [Program Counter](https://www.geeksforgeeks.org/operating-systems/what-is-program-counter/)(PC) is not transferred to stack | Value of Program Counter(PC) is transferred to stack |
| 5. | After JUMP, there is no return instruction | After CALL, there is a return instruction |
| 6. | Value of SP does not changes | Value of SP is decremented by 2 |
| 7. | 10 T states are required to execute this instruction | 18 T states are required to execute this instruction |
| 8. | 3 Machine cycles are required to execute this instruction | 5 Machine cycles are required to execute this instruction |
## Conclusion
The CALL and JUMP statements are used commonly in the Assembly language to control flow of programs, though they exhibit different functionalities. CALL is used for calling subroutines with the option or privilege of the get back to the main program while JUMPs pass control unconditionally to other part without return. CALL is more rigid yet it incorporates code reuse as compared to JUMP that is highly optimized especially to work with small SCPs but lacks backtrack mechanism. Orientation in the applicative need can make the difference of using CALL and JUMP in effectivity and maintainability of the code.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/difference-call-jump-instructions/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Machine Instructions and Addressing Modes

> [!note] Related notes
>
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
> - [[Amdahl’s law and its proof]]
> - [[Basic Computer Instructions]]
> - [[Computer Architecture and Computer Organization]]
> - [[Computer System Level Hierarchy]]
> - [[Flynn’s taxonomy]]
> - [[General Register based CPU Organization]]
> - [[Generations of computer]]
> - [[Hardware architecture]]
