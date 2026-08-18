---
title: "Difference between RISC and CISC Processor | Set 2"
subject: "Computer Organization and Architecture"
topic: "Instruction Pipelining"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-risc-and-cisc-processor-set-2/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Instruction Pipelining"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/instruction-pipelining
---


> [!abstract] Difference between RISC and CISC Processor | Set 2
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Instruction Pipelining`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-risc-and-cisc-processor-set-2/)

---

# Difference between RISC and CISC Processor | Set 2

The **microprocessor** is a processing unit on the single chip. It is the integrated circuit that performs the core functions of the computer CPU. It is the multipurpose programmable silicon chip constructed using a Metal Oxide Semiconductor (MOS) technology which is clock driven and register based. It accepts a binary data as a input and provides output after processing it as per a specification of instructions stored in a memory. These microprocessors are capable of the processing the 128 bits at the time at the speed of a one billion instructions per second.
## Characteristics of a Microprocessor
1. **Instruction Set** : The set of complete instructions that the microprocessor executes is termed the instruction set.
2. **Word Length** : The number of bits processed in a single instruction is called word length or word size. The Greater the word size is the larger the processing power of the [CPU](https://www.geeksforgeeks.org/computer-organization-architecture/what-are-the-functions-of-a-cpu/).
3. **System Clock Speed** : A Clock speed determines how fast the single instruction can be executed in the processor. The microprocessor is controlled by the System Clock. A Clock speeds are generally measured in the millions of a cycles per second (MHz) and thousand million cycles per second GHz. A Clock speed is considered to be the very important aspect of predicting a performance of the processor.
## **What is** Reduced Instruction Set Computer**(RISC)?**
It stands for Reduced Instruction Set Computer. It is a type of microprocessor architecture that uses a small set of instructions of uniform length. These are simple instructions that are generally executed in one clock cycle. [RISC](https://www.geeksforgeeks.org/computer-organization-architecture/advanced-risc-machine-arm-processor/) chips are relatively simple to design and inexpensive. The setback of this design is that the computer has to repeatedly perform simple operations to execute a larger program having a large number of processing operations. 
**Examples:** [SPARC](https://www.geeksforgeeks.org/computer-organization-architecture/sparc-full-form/), POWER PC, etc.
### Advantages of Reduced Instruction Set Computer (RISC)
- Faster execution speed RISC processors use the simpler instructions that can be executed more quickly leading to improved overall performance in the many tasks.
- Lower power consumption The simpler design of a RISC processors often results in the lower power usage making them the ideal for mobile devices and energy efficient computing.
- Easier to design and manufacture RISC processors have a simpler architecture which can make them the easier and potentially cheaper to design and produce.
### Disadvantages of Reduced Instruction Set Computer (RISC)
- Larger code size RISC processors often require more lines of code to perform complex tasks, which can lead to larger program sizes and increased memory usage.
- More work for compilers The simpler instruction set means compilers for RISC processors need to do more work to translate high-level programming languages into machine code.
- Limited built-in functionality RISC processors have fewer complex instructions built into hardware, which can make certain specialized tasks less efficient without additional software support.
## **What is** Complex Instruction Set Computer **(CISC)?**
It stands for Complex Instruction Set Computer. These processors offer the users, hundreds of instructions of variable sizes. CISC architecture includes a complete set of special-purpose circuits that carry out these instructions at a very high speed. These instructions interact with memory by using complex addressing modes. [CISC](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-risc-and-cisc/) processors reduce the program size and hence lesser number of memory cycles are required to execute the programs. This increases the overall speed of execution. 
**Examples:** Intel architecture, AMD
### Advantages of Complex Instruction Set Computer (CISC)
- Smaller code size CISC processors can perform complex operations with single instructions, often resulting in more compact code and reduced memory usage.
- Rich instruction set The diverse set of complex instructions can make programming easier and more intuitive for certain tasks, especially in assembly language.
- Backwards compatibility CISC architectures, like x86, often maintain compatibility with older software, making system upgrades easier for users and businesses.
### Disadvantages of Complex Instruction Set Computer (CISC)
- Slower execution speed Complex instructions typically take longer to execute, potentially resulting in slower overall performance compared to RISC processors.
- Higher power consumption The more complex hardware required for the CISC processors often leads to a increased power usage making them less suitable for the mobile devices.
- More complex hardware design a CISC processors require more complex circuitry to handle their varied the instructions which can make them a more challenging and expensive to design and manufacture.
## **What is EPIC?**
It stands for Explicitly Parallel Instruction Computing. The best features of RISC and CISC processors are combined in the architecture. It implements parallel processing of instructions rather than using fixed-length instructions. The working of EPIC processors is supported by using a set of complex instructions that contain both basic instructions as well as the information of execution of parallel instructions. It substantially increases the efficiency of these [processors](https://www.geeksforgeeks.org/computer-organization-architecture/dual-core-vs-quad-core-processor/).
## Difference between RISC and CISC processor
| CISC | RISC |
| --- | --- |
| A large number of a instructions are present in the architecture. | Very few instructions are present. The number of instructions is generally less than 100. |
| Some instructions with long execution times. These include instructions that copy an entire block from one part of memory to another and others that copy multiple registers to and from memory. | No instruction with a long execution time due to a very simple instruction set. Some early RISC machines did not even have an integer multiply instruction, requiring compilers to implement multiplication as a sequence of additions. |
| Variable-length encodings of the instructions.  **Example:** IA32 instruction size can range from 1 to 15 bytes. | Fixed-length encodings of the instructions are used.  **Example:** In IA32, generally all instructions are encoded as 4 bytes. |
| Multiple formats are supported for specifying operands. A memory operand specifier can have many different combinations of displacement, base, and index register. | Simple addressing formats are supported. Only base and displacement addressing is allowed. |
| CISC supports array. | RISC does not support an array. |
| Arithmetic and logical operations can be applied to both memory and register operands. | Arithmetic and logical operations only use register operands. Memory referencing is only allowed by loading and storing instructions, i.e. reading from memory into a register and writing from a register to memory respectively. |
| Implementation programs are hidden from machine-level programs. The ISA provides a clean abstraction between programs and how they get executed. | Implementation programs exposed to machine-level programs. Few RISC machines do not allow specific instruction sequences. |
| Condition codes are used. | No condition codes are used. |
| The stack is being used for procedure arguments and returns addresses. | Registers are being used for procedure arguments and return addresses. Memory references can be avoided by some procedures. |
| Successful pipeline with one instruction per cycle | Unsuccessful pipeline |
| Heavy use of RAM | More efficient use of [RAM](https://www.geeksforgeeks.org/computer-science-fundamentals/random-access-memory-ram/) |
> Refer for Set-1: [RISC and CISC](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-risc-and-cisc/)
## Conclusion
The Reduced Instruction Set Computing and a Complex Instruction Set Computing are the method of a processor design. The RISC processors use the fewer and simpler instructions that execute quickly while the CISC processors have the complex instructions that can perform the multiple operations. The RISC focuses on a efficiency and speed using a simpler hardware and relying on the software. CISC aims for a versatility with more built in functionality in the hardware. RISC is a generally faster and more energy efficient while a CISC can be more compact in a terms of code size.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-risc-and-cisc-processor-set-2/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Instruction Pipelining

> [!note] Related notes
>
> - [[Different Instruction Cycles]]
> - [[Micro-Operation]]
> - [[Performance of Computer]]
> - [[Pipelining]]
> - [[Pipelining Set 2]]
> - [[Pipelining Set 3]]
> - [[RISC and CISC]]
> - [[2D and 2.5D Memory organization]]
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
