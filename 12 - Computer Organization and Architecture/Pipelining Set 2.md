---
title: "Pipelining | Set 2 (Dependencies and Data Hazard)"
subject: "Computer Organization and Architecture"
topic: "Instruction Pipelining"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-pipelining-set-2-dependencies-and-data-hazard/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Instruction Pipelining"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/instruction-pipelining
---


> [!abstract] Pipelining | Set 2 (Dependencies and Data Hazard)
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Instruction Pipelining`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-pipelining-set-2-dependencies-and-data-hazard/)

---

# Pipelining | Set 2 (Dependencies and Data Hazard)

Please see [**Set 1**](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-pipelining-set-1-execution-stages-and-throughput/) for Execution, Stages and Performance (Throughput) and [**Set 3**](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-pipelining-set-3-types-and-stalling/) for Types of Pipeline and Stalling.   
## Dependencies in a pipelined processor
There are mainly three types of dependencies possible in a pipelined processor.
- Structural Dependency
- Control Dependency
- Data Dependency
These dependencies may introduce stalls in the pipeline.
- **Stall :** A stall is a cycle in the pipeline without new input.
- **Structural dependency** This dependency arises due to the resource conflict in the pipeline. A resource conflict is a situation when more than one instruction tries to access the same resource in the same cycle. A resource can be a register, memory, or ALU.
**Example**
| Instruction / Cycle | 1 | 2 | 3 | 4 | 5 |
| --- | --- | --- | --- | --- | --- |
| I1 | IF(Mem) | ID | EX | Mem |  |
| I2 |  | IF(Mem) | ID | EX |  |
| I3 |  |  | IF(Mem) | ID | EX |
| I4 |  |  |  | IF(Mem) | ID |
In the above scenario, in Cycle 4, instructions I1 and I4 are trying to access same resource (Memory) which introduces a resource conflict. To avoid this problem, we have to keep the instruction on wait until the required resource (memory in our case) becomes available.
This wait will introduce stalls in the pipeline as shown below:
| Cycle | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| I1 | IF(Mem) | ID | EX | Mem | WB |  |  |  |
| I2 |  | IF(Mem) | ID | EX | Mem | WB |  |  |
| I3 |  |  | IF(Mem) | ID | EX | Mem | WB |  |
| I4 |  |  |  | - | - | - | IF(Mem) |  |
**Solution for structural dependency:** To minimize structural dependency stalls in the pipeline, we use separate instruction and data memory (Harvard architecture) or duplicate resources
**Renaming :** Renaming: It is a technique used to eliminate false data dependencies (WAR and WAW) by assigning different physical registers to logical registers.
| Instruction/ Cycle | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| I1 | IF(CM) | ID | EX | DM | WB |  |  |
| I2 |  | IF(CM) | ID | EX | DM | WB |  |
| I3 |  |  | IF(CM) | ID | EX | DM | WB |
| I4 |  |  |  | IF(CM) | ID | EX | DM |
| I5 |  |  |  |  | IF(CM) | ID | EX |
| I6 |  |  |  |  |  | IF(CM) | ID |
| I7 |  |  |  |  |  |  | IF(CM) |
**Control Dependency (Branch Hazards):** This type of dependency occurs during the transfer of control instructions such as BRANCH, CALL, JMP, etc. On many instruction architectures, the processor will not know the target address of these instructions when it needs to insert the new instruction into the pipeline. Due to this, unwanted instructions are fed to the pipeline.
Consider the following sequence of instructions in the program:
- 100: I1
- 101: I2 (JMP 250)
- 102: I3
- ...
- 250: BI1
Expected output: I1 -> I2 -> BI1
**NOTE:** Generally, the target address of the JMP instruction is known after ID stage only.
| Instruction/ Cycle | 1 | 2 | 3 | 4 | 5 | 6 |
| --- | --- | --- | --- | --- | --- | --- |
| I1 | IF | ID | EX | MEM | WB |  |
| I2 |  | IF | ID (PC:250) | EX | Mem | WB |
| I3 |  |  | IF | ID | EX | Mem |
| BI1 |  |  |  | IF | ID | EX |
**Output Sequence:** I1 -> I2 -> I3 -> BI1
- Since this output sequence is not equal to the expected output, this happens due to control hazards in the pipeline.
- To correct this problem, we need to stall the instruction fetch until the target address of the branch instruction is known. This can be implemented by introducing a delay slot until the target address is obtained.
| Instruction/ Cycle | 1 | 2 | 3 | 4 | 5 | 6 |
| --- | --- | --- | --- | --- | --- | --- |
| I1 | IF | ID | EX | MEM | WB |  |
| I2 |  | IF | ID (PC:250) | EX | Mem | WB |
| Delay | - | - | - | - | - | - |
| BI1 |  |  |  | IF | ID | EX |
**Output Sequence:** I1 -> I2 -> Delay (Stall) -> BI1
- As the delay slot performs no operation, this output sequence is equal to the expected output sequence. But this slot introduces stall in the pipeline.
- **Solution for Control dependency:** In branch prediction, the processor predicts the outcome of a branch instruction to reduce stalls. Branch prediction reduces the branch penalty, but it is not always zero. The penalty becomes zero only if the prediction is always correct.
- **Branch penalty :** The number of stalls introduced during the branch operations in the pipelined processor is known as branch penalty.
**NOTE :** As we see that the target address is available after the ID stage, so the number of stalls introduced in the pipeline is 1. Suppose, the branch target address would have been present after the ALU stage, there would have been 2 stalls. Generally, if the target address is present after the kth stage, then there will be (k – 1) stalls in the pipeline.
Total number of stalls introduced in the pipeline due to branch instructions:
```
Branch frequency x Branch Penalty     
```
**Data Dependency (Data Hazard)**
Let us consider an ADD instruction S, such that
- S : ADD R1, R2, R3
- Addresses read by S = I(S) = {R2, R3}
- Addresses written by S = O(S) = {R1}
Now, we say that instruction S2 depends in instruction S1, when ![pipelining 7](assets/formula-41-7a7262381f.jpg)
This condition is called Bernstein condition. Three cases exist:
1. Flow (data) dependence / True Dependence:
O(S1) ∩ I(S2) ≠ ∅, S1 → S2 and S2 reads a value written by S1.
2. Anti-dependence:
I(S1) ∩ O(S2) ≠ ∅, S1 → S2 and S1 reads a value before S2 overwrites it.
3. Output dependence:
O(S1) ∩ O(S2) ≠ ∅, S1 → S2 and both write to the same memory location.
**Example:** Let there be two instructions I1 and I2 such that:
- I1 : ADD R1, R2, R3
- I2 : SUB R4, R1, R2
When the above instructions are executed in a pipelined processor, then data dependency condition will occur, which means that I2 tries to read the data before I1 writes it, therefore, I2 incorrectly gets the old value from I1.
| Instruction / Cycle | 1 | 2 | 3 | 4 |
| --- | --- | --- | --- | --- |
| I1 | IF | ID | EX | DM |
| I2 |  | IF | ID(Old value) | EX |
To minimize data dependency stalls in the pipeline,operand forwardingis used.
**Operand Forwarding :** In operand forwarding, we use the interface registers present between the stages to hold intermediate output so that dependent instruction can access new value from the interface register directly. Operand Forwarding can avoid stalls only if the dependent instructions are ALU type instructions.
Considering the same example:
- I1 : ADD R1, R2, R3
- I2 : SUB R4, R1, R2
| Instruction / Cycle | 1 | 2 | 3 | 4 |
| --- | --- | --- | --- | --- |
| I1 | IF | ID | EX | DM |
| I2 |  | IF | ID | EX |
## Data Hazards
Data hazards occur when instructions that exhibit data dependence, modify data in different stages of a pipeline. Hazard cause delays in the pipeline.
There are mainly three types of data hazards:
- RAW (Read after Write) [Flow/True data dependency]
- WAR (Write after Read) [Anti-Data dependency]
- WAW (Write after Write) [Output data dependency]
Let there be two instructions I and J, such that J follow I. Then,
- Instruction depend on result of prior instruction still in the pipeline.
- It can occur among the operands in the instruction at the pipeline stages.
- It occur when instructions read or write registers that are used by other instructions.
- RAW hazard occurs when instruction J tries to read data before instruction I writes it. Ex: I: R2 <- R1 + R3 J: R4 <- R2 + R3
- WAR hazard occurs when instruction J tries to write data before instruction I reads it. Ex: I: R2 <- R1 + R3 J: R3 <- R4 + R5
- WAW hazard occurs when instruction J tries to write output before instruction I writes it. Ex: I: R2 <- R1 + R3 J: R2 <- R4 + R5
WAR and WAW hazards occur during the out-of-order execution of the instructions.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-pipelining-set-2-dependencies-and-data-hazard/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Instruction Pipelining

> [!note] Related notes
>
> - [[Different Instruction Cycles]]
> - [[Micro-Operation]]
> - [[Performance of Computer]]
> - [[Pipelining]]
> - [[Pipelining Set 3]]
> - [[RISC and CISC]]
> - [[RISC and CISC Set 2]]
> - [[2D and 2.5D Memory organization]]
> - [[A simple understanding of Computer]]
> - [[Addressing Modes]]
