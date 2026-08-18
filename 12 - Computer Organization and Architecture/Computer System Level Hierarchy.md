---
title: "Computer System Level Hierarchy"
subject: "Computer Organization and Architecture"
topic: "Machine Instructions and Addressing Modes"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/computer-system-level-hierarchy/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Machine Instructions and Addressing Modes"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/machine-instructions-and-addressing-modes
---


> [!abstract] Computer System Level Hierarchy
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Machine Instructions and Addressing Modes`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-system-level-hierarchy/)

---

# Computer System Level Hierarchy

**Computer System Level Hierarchy** is the combination of different levels that connects the computer with the user and that makes the use of the computer. It also describes how the computational activities are performed on the computer and it shows all the elements used in different levels of system. 
Computer System Level Hierarchy consists of seven levels: 
![](assets/Untitled-Diagram95-449ec16bd2.png)
- **Level-0:** 
  It is related to digital logic. Digital logic is the basis for digital computing and provides a fundamental understanding of how circuits and hardware communicate within a computer. It consists of various circuits and gates etc.
- **Level-1:** 
  This level is related to control. Control is the level where microcode is used in the system. Control units are included in this level of the computer system.
- **Level-2:** 
  This level consists of machines. Different types of hardware are used in the computer system to perform different types of activities. It contains instruction set architecture.
- **Level-3:** 
  System software is a part of this level. System software is of various types. System software mainly helps in operating the process and it establishes the connection between hardware and user interface. It may consist operating system, library code, etc.
- **Level-4:** 
  Assembly language is the next level of the computer system. The machine understands only the assembly language and hence in order, all the high-level languages are changed in the assembly language. Assembly code is written for it.
- **Level-5:** 
  This level of the system contains high-level language. High-level language consists of C++, Java, FORTRAN, and many other languages. This is the language in which the user gives the command.
- **Level-6:** 
  This is the last level of the computer system hierarchy. This consists of users and executable programs.
### The different levels in the hierarchy are:
**Hardware level:** This is the lowest level in the hierarchy and includes all the physical components of the computer system such as the CPU, memory, storage devices, input/output devices, and other peripherals.
**Firmware level:** This level includes the software that is stored in non-volatile memory, such as the BIOS or firmware on other devices, and is responsible for initializing and controlling the hardware.
**Operating system level:** This level includes the software that manages the resources of the computer system, provides a user interface, and runs application programs. Examples of operating systems include Windows, macOS, and Linux.
**Application level:** This level includes the software applications that run on the operating system and perform specific tasks such as word processing, spreadsheet calculations, or playing games.
### features of the computer system level hierarchy are:
**Abstraction:** Each level in the hierarchy provides a level of abstraction from the underlying hardware, allowing software developers to write programs that are independent of the specific hardware components in the system.
**Modularity:** Each level in the hierarchy can be designed and developed independently, allowing for easier maintenance and upgrades.
**Interoperability:** The different levels in the hierarchy are designed to work together seamlessly, allowing for software applications to run on different hardware platforms and operating systems.
**Scalability:** The hierarchical design allows for the addition of new components and functionality, making it possible to scale up or down the system as needed.
**Security:** The different levels in the hierarchy can be isolated from each other, providing a layered approach to security and reducing the risk of security breaches.
### Advantages of the computer system level hierarchy:
**Modularity:** The hierarchical approach to organizing computer systems allows for greater modularity, which can make it easier to develop, test, and maintain individual components.
**Standardization:** The use of standard interfaces and protocols between layers of the hierarchy can make it easier to integrate new components into a system and to reuse existing components in new contexts.
**Abstraction:** Each layer of the hierarchy can provide a higher level of abstraction, allowing programmers and users to interact with the system at a higher level of complexity without having to deal with the details of lower-level components.
**Scalability:** The hierarchical approach can make it easier to scale a system to handle larger workloads by adding more resources or components at different levels of the hierarchy.
### Disadvantages of the computer system level hierarchy:
**Overhead:** The additional layers of abstraction and communication between components can introduce additional overhead and complexity, which can reduce overall system performance.
**Dependencies:** Changes to one layer of the hierarchy can have ripple effects on other layers, which can make it difficult to modify or update a system without causing unintended consequences.
**Inefficiency:** In some cases, the hierarchical approach can lead to inefficiencies in the use of system resources, as components at different levels may not be optimized to work together efficiently.
**Complexity:** The hierarchical approach can make it difficult for users and developers to understand and navigate the system, especially as the number of components and layers increases.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/computer-system-level-hierarchy/)

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
> - [[Difference between CALL and JUMP instructions]]
> - [[Flynn’s taxonomy]]
> - [[General Register based CPU Organization]]
> - [[Generations of computer]]
> - [[Hardware architecture]]
