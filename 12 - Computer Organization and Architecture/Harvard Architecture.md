---
title: "Harvard Architecture"
subject: "Computer Organization and Architecture"
topic: "Machine Instructions and Addressing Modes"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/harvard-architecture/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Machine Instructions and Addressing Modes"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/machine-instructions-and-addressing-modes
---


> [!abstract] Harvard Architecture
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Machine Instructions and Addressing Modes`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/harvard-architecture/)

---

# Harvard Architecture

Harvard architecture is a computer design model where program instructions and data are stored in separate memory units that are accessed throughindependent buses. This separation allows the processor to fetch instructions and access data simultaneously, which helps avoid the bottleneck present in traditional Von Neumann systems.
- Eliminates the Von Neumann bottleneck.
- Faster and predictable performance (suitable for real-time systems).
- Parallel access to both instructions and data.
## Working Principle
In Harvard Architecture, fetching an instruction from instruction memory and reading/writing data from/to data memory happen at the same time without waiting for one to finish. Separate buses prevent the bottleneck that occurs when data and instructions share a path. For example, while an instruction is being executed, the next instruction can be fetched simultaneously, speeding up processing.
![central_processing_unit234](assets/central_processing_unit234-82cf8ccc94.webp)
Structure of Harvard Architecture
## **Buses**
Buses are used as signal pathways. In Harvard architecture, there are separate buses for both instruction and data. Types of Buses: 
- **Data Bus:** It carries data among the main memory system, processor, and I/O devices.
- **Data Address Bus:** It carries the address of data from the processor to the main memory system.
- **Instruction Bus:** It carries instructions among the main memory system, processor, and I/O devices.
- **Instruction Address Bus:** It carries the address of instructions from the processor to the main memory system.
## **Components of Harvard Architecture**
Harvard architecture is designed with specific components that handle instruction execution, control, and data communication.
- **Arithmetic and Logic Unit:** The arithmetic logic unit is part of the CPU that operates all the calculations needed. It performs addition, subtraction, comparison, logical Operations, bit Shifting Operations, and various arithmetic operations.
- **Control Unit:** The Control Unit is the part of the CPU that operates all processor control signals. It controls the input and output devices and also controls the movement of instructions and data within the system.
- **The Input/Output (I/O) system** enables communication between the computer and external devices. Input devices provide data and instructions to the system. Output devices display or deliver the processed results to the user.
## Application of Harvard Architecture
Harvard architecture is a type of computer design where the memory for instructions and data are kept separate. Here are the some applications:
**Digital Signal Processors (DSPs):**
- Audio and video processing, telecommunications, radar systems, and image processing.
- Texas Instruments TMS320 for hearing aids.
**Microcontrollers (MCUs):**
- Embedded systems in consumer electronics, automotive systems, IoT devices, and industrial automation**.**
- PIC in automotive ABS
**Network Processors:**
- Routers, switches, and network security appliances.
- Broadcom StrataXGS
**Automotive Systems:**
- Engine control units (ECUs), advanced driver-assistance systems (ADAS), and infotainment systems.
- NXP S32K for engine control
## Related Articles
- [Computer Organization and Architecture Tutorials](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-and-architecture-tutorials/)
- [Difference between Von Neumann and Harvard Architecture](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-von-neumann-and-harvard-architecture/)
- [Computer Organization - Von Neumann Architecture](https://www.geeksforgeeks.org/computer-organization-architecture/computer-organization-von-neumann-architecture/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/harvard-architecture/)

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
> - [[Difference between CALL and JUMP instructions]]
> - [[Flynn’s taxonomy]]
> - [[General Register based CPU Organization]]
> - [[Generations of computer]]
