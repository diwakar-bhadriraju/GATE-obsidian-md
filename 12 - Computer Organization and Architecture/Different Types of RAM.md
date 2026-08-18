---
title: "Different Types of RAM (Random Access Memory )"
subject: "Computer Organization and Architecture"
topic: "Cache Memory"
source: "https://www.geeksforgeeks.org/computer-organization-architecture/different-types-ram-random-access-memory/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Organization and Architecture/Cache Memory"
tags:
  - gate/cs
  - subject/computer-organization-and-architecture
  - topic/cache-memory
---


> [!abstract] Different Types of RAM (Random Access Memory )
> 
> **Subject:** `Computer Organization and Architecture` &nbsp;|&nbsp; **Topic:** `Cache Memory`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/different-types-ram-random-access-memory/)

---

# Different Types of RAM (Random Access Memory )

In the computer world, memory plays an important component in determining the performance and efficiency of a system. In between various types of memory, Random Access Memory (RAM) stands out as a necessary component that enables computers to process and store data temporarily. In this article, we will explore the world of RAM, exploring its definition, types, and characteristics, as well as its significance in modern computing.
## What is RAM?
Random Access Memory, is a type of computer memory that allows data to be read and written randomly, meaning that the computer can access any location in the memory directly rather than having to read the data in a specific order. This makes RAM an essential component of a computer system, as it enables the CPU to access data quickly and efficiently.
RAM is volatile in nature, which means if the power goes off, the stored information is lost. RAM is used to store the data that is currently processed by the CPU. Most of the programs and data that are modifiable are stored in RAM. 
The block diagram of the RAM chip is given below:
![RAM-chip](assets/RAM-chip-d0bc311a3b.webp)
## **Types of RAM?**
Mainly RAM have 2types
- SRAM (Static RAM)
- DRAM (Dynamic RAM)
![types_of_ram](assets/types_of_ram-396c338883.webp)
## **What is SRAM?**
The SRAM memories consist of circuits capable of retaining the stored information as long as the power is applied. That means this type of memory requires constant power. SRAM memories are used to build [Cache Memory](https://www.geeksforgeeks.org/computer-science-fundamentals/cache-memory/).
### **SRAM Memory Cell**
Static memories(SRAM) are memories that consist of circuits capable of retaining their state as long as power is on. Thus this type of memory is called [**volatile memory**](https://www.geeksforgeeks.org/computer-organization-architecture/what-is-volatile-memory/). The below figure shows a cell diagram of SRAM. A latch is formed by two inverters connected as shown in the figure. Two transistors T1 and T2 are used for connecting the latch with two-bit lines. The purpose of these [transistors](https://www.geeksforgeeks.org/electronics-engineering/what-is-transistor/) is to act as switches that can be opened or closed under the control of the word line, which is controlled by the address decoder. When the word line is at 0-level, the transistors are turned off and the latch remains its information. SRAM does not require refresh time. For example, the cell is at state 1 if the logic value at point A is 1 and at point, B is 0. This state is retained as long as the word line is not activated. 
![SRAM-memory-call](assets/SRAM-memory-call-50bba4f2d8.webp)
For the **Read operation**, the word line is activated by the address input to the address decoder. The activated word line closes both the transistors ([switches](https://www.geeksforgeeks.org/computer-networks/types-of-switches-in-computer-network/)) T1 and T2. Then the bit values at points A and B can transmit to their respective bit lines. The sense/write circuit at the end of the bit lines sends the output to the processor. 
For the **Write operation**, the address provided to the decoder activates the word line to close both switches. Then the bit value that is to be written into the cell is provided through the sense/write circuit and the signals in bit lines are then stored in the cell. 
## **What is DRAM?**
DRAM stores the binary information in the form of electric charges applied to capacitors. The stored information on the capacitors tends to lose over a period of time and thus the capacitors must be periodically recharged to retain their usage. DRAM requires refresh time. The main memory is generally made up of DRAM chips.
### **DRAM Memory Cell**
Though SRAM is very fast, it is expensive because of its every cell requires several transistors. Relatively less expensive RAM is DRAM, due to the use of one transistor and one capacitor in each cell, as shown in the below figure., where C is the [capacitor](https://www.geeksforgeeks.org/physics/applications-of-capacitor/) and T is the transistor. Information is stored in a DRAM cell in the form of a charge on a capacitor and this charge needs to be periodically recharged. 
For storing information in this cell, transistor T is turned on and an appropriate voltage is applied to the bit line. This causes a known amount of charge to be stored in the capacitor. After the transistor is turned off, due to the property of the capacitor, it starts to discharge. Hence, the information stored in the cell can be read correctly only if it is read before the charge on the capacitors drops below some threshold value. 
![DRAM-memory-cell](assets/DRAM-memory-cell-6d69ec14eb.webp)
Understanding the different types of RAM is crucial for grasping how memory works in computers. RAM comes in various forms, including SRAM and DRAM, each serving different purposes within a computer system.
## **Types of DRAM**
There are mainly 5 types of DRAM.
- **Asynchronous DRAM (ADRAM):** The DRAM described above is the asynchronous type of DRAM. The timing of the memory device is controlled asynchronously. A specialized memory controller circuit generates the necessary control signals to control the timing. The [CPU](https://www.geeksforgeeks.org/computer-organization-architecture/what-are-the-functions-of-a-cpu/) must take into account the delay in the response of the memory.
- **Synchronous DRAM (SDRAM):** These RAM chips' access speed is directly synchronized with the CPU's clock. For this, the memory chips remain ready for operation when the CPU expects them to be ready. These memories operate at the CPU-memory bus without imposing wait states. SDRAM is commercially available as modules incorporating multiple SDRAM chips and forming the required capacity for the modules.
- **Double-Data-Rate SDRAM (DDR SDRAM):** This faster version of [SDRAM](https://www.geeksforgeeks.org/computer-organization-architecture/ddr-sdram-full-form/) performs its operations on both edges of the clock signal; whereas a standard SDRAM performs its operations on the rising edge of the clock signal. Since they transfer data on both edges of the clock, the data transfer rate is doubled. To access the data at a high rate, the memory cells are organized into two groups. Each group is accessed separately.
- **Rambus DRAM (RDRAM):** The RDRAM provides a very high data transfer rate over a narrow CPU-memory bus. It uses various speedup mechanisms, like synchronous memory interface, caching inside the DRAM chips and very fast signal timing. The Rambus data bus width is 8 or 9 bits.
- **Cache DRAM (CDRAM):** This memory is a special type of DRAM memory with an on-chip cache memory (SRAM) that acts as a high-speed buffer for the main DRAM.
## **Difference Between SRAM and DRAM**
The below table lists some of the differences between SRAM and DRAM.
| SRAM | DRAM |
| --- | --- |
| SRAM stands for Static Random Access Memory. | DRAM stands for Dynamic Random Access Memory. |
| Uses a flip-flop circuit to store data | Uses a capacitor and a transistor to store data |
| SRAM has a lower access time, so it is faster compared to DRAM. | DRAM has a higher access time, so it is slower than SRAM. |
| SRAM has long data life. | DRAM has short data life. |
| SRAM has a storage capacity of 1 MB to 16 MB in most cases. | DRAM, which is often found in tablets and smartphones, has a capacity of 1 GB to 2 GB |
| SRAM is costlier than DRAM. | DRAM costs less compared to SRAM. |
| SRAM provides faster speed of data read/write. | DRAM provides slower speed of data read/write. |
| SRAM requires a constant power supply, which means this type of memory consumes more power. | DRAM offers reduced power consumption due to the fact that the information is stored in the capacitor. |
| Good choice for applications that may be exposed to extreme temperatures. | Not suitable for such applications. |
| Due to complex internal circuitry, less storage is available compared to the same physical size of a DRAM memory chip. | Due to the small internal circuitry in the one-bit memory cell of DRAM, a large storage capacity is available. |
| SRAM has low packaging capacity. | DRAM has a high packaging density. |
| SRAM is used in cache memories. | DRAM is used in main memories. |
| SRAM does not require refresh time. | DRAM requires periodic refresh time. |
| SRAMs are used as cache memory in computer and other computing devices. | DRAMs are used as main memory in computer systems. |
read more about - [Difference between SRAM and DRAM](https://www.geeksforgeeks.org/computer-organization-architecture/difference-between-sram-and-dram/)
## Conclusion
In conclusion, RAM is a most important component of a computer system that plays a crucial role in storing and retrieving data. Understanding the different types of RAM, including SRAM and DRAM, and their characteristics is essential for building efficient computer systems.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-organization-architecture/different-types-ram-random-access-memory/)

## GATE CS

- Subject: Computer Organization and Architecture
- Topic: Cache Memory

> [!note] Related notes
>
> - [[2D and 2.5D Memory organization]]
> - [[Cache Memory]]
> - [[Cache Organization Introduction]]
> - [[Introduction to memory and memory units]]
> - [[Locality and Cache friendly code]]
> - [[Memory Hierarchy Design and its Characteristics]]
> - [[Memory Interleaving]]
> - [[RAM vs ROM]]
> - [[Read and Write operations in memory]]
> - [[Types of computer memory]]
