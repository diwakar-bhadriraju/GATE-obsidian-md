---
title: "Introduction to Memory and Memory Units"
subject: "Computer Organization and Architecture"
topic: "Cache Memory"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/introduction-to-memory-and-memory-units/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Cache Memory"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/cache-memory
---


> [!abstract] Introduction to Memory and Memory Units
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Cache Memory`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/introduction-to-memory-and-memory-units/)

---

# Introduction to Memory and Memory Units

Memory is an essential component of a computer system, responsible for storing data and instructions needed for processing. It enables the CPU to execute programs efficiently and ensures smooth system operation.
- **Memory Cell:** Smallest storage unit that holds 1 bit of data. Each address in memory typically refers to a byte.
- **Word & Byte:** A word is a group of bits; 1 byte = 8 bits.
- **Capacity**: Total number of bits a memory can hold.
![memory](assets/memory-0d5b7ceb06.webp)
## Classification of Memory
Memory is classified into primary and secondary types based on speed, accessibility, and volatility.
- **Primary Memory**: Directly accessible by the CPU; fast but limited in capacity.
- **Secondary Memory**: Used for long-term storage; slower but larger in capacity.
![types_of_computer_memory_](assets/types_of_computer_memory_-c6edea163c.webp)
## RAM (Random Access Memory)
[RAM](https://www.geeksforgeeks.org/computer-science-fundamentals/random-access-memory-ram/) is the computer’s main memory used for temporary storage of active programs and data. Data is lost when power is off. It provides fast CPU access, improving multitasking and performance.
![RAM](assets/RAM-0dba7fe93d.webp)
### Types of RAM
- **SRAM (Static RAM)**: Fast, used in cache, retains data while powered.
- **DRAM (Dynamic RAM)**: Slower, needs periodic refresh; main memory. Includes SDRAM and DDR series.
## ROM (Read-Only Memory)
[ROM](https://www.geeksforgeeks.org/computer-organization-architecture/read-only-memory-rom/) is non-volatile memory that stores essential instructions permanently. It holds system firmware and boot instructions.
![ROMFind-It](assets/ROMFind-It-124e5cde62.webp)
### Types of ROM
Following are types of ROM:
- **MROM**: Pre-programmed at manufacture
- **PROM**: User-programmable once
- **EPROM**: UV-erasable
- **EEPROM**: Electrically erasable
- **Flash Memory**: Fast, used in SSDs and USB drives
## Secondary Memory
[Secondary memory](https://www.geeksforgeeks.org/computer-science-fundamentals/secondary-memory/) provides long-term data storage and is not directly accessed by the CPU.
- **Examples:** HDD, SSD, optical discs (CD/DVD/Blu-ray), USB drives, flash cards, magnetic tapes, cloud storage.
- **Characteristics**: Non-volatile, slower, high capacity, used for storing operating systems, software, and user files.
## Memory Unit
A memory unit is a standard unit used to measure the amount of data that can be stored, processed, or transferred in a computer system. It represents the storage capacity of memory and storage devices.
- The smallest memory unit is a Bit (0 or 1) and larger units are KB, MB, GB, TB, PB, EB, ZB, and YB.
- A Byte is the basic unit of storage and equals 8 bits.
- Memory units are used to measure file sizes, RAM capacity, and storage device capacity.
- Computers use the binary number system, so memory units are typically based on powers of 2 (1024).
- **Example:** A computer with 8 GB RAM can store approximately 8 gigabytes of data in its main memory.
```
Please refer Understanding file sizes for more details.
```
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/introduction-to-memory-and-memory-units/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Cache Memory

> [!note] Related notes
>
> - [[2D and 2.5D Memory organization]]
> - [[Cache Memory]]
> - [[Cache Organization Introduction]]
> - [[Different Types of RAM]]
> - [[Locality and Cache friendly code]]
> - [[Memory Hierarchy Design and its Characteristics]]
> - [[Memory Interleaving]]
> - [[RAM vs ROM]]
> - [[Read and Write operations in memory]]
> - [[Types of computer memory]]
