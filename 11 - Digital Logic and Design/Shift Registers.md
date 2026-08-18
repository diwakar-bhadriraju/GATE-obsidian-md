---
title: "Shift Registers in Digital Logic"
subject: "Digital Logic and Design"
topic: "Sequential Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/shift-registers-in-digital-logic/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Sequential Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/sequential-circuit
---


> [!abstract] Shift Registers in Digital Logic
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Sequential Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/shift-registers-in-digital-logic/)

---

# Shift Registers in Digital Logic

A shift register is a group of flip-flops connected in series to store and shift multiple bits of data either left or right with clock pulses.
- The registers which will shift the bits to the left are called “Shift left registers”.
- The registers which will shift the bits to the right are called “Shift right registers”.
## Serial-In Serial-Out Shift Register (SISO)
A Serial-In Serial-Out (SISO) shift register accepts data one bit at a time through a single input line and outputs data serially, using a series of flip-flops all triggered by the same clock. The main use of a SISO is to act as a delay element.
- Data enters and leaves one bit at a time in a serial sequence.
- Typically made of multiple D flip-flops connected in series and synchronised by a common clock.
![Serial-In Serial-Out Shift Register (SISO)](assets/FlipFlop-ba8656d251.png)
Serial-In Serial-Out Shift Register (SISO)
## Serial-In Parallel-Out Shift Register (SIPO)
A Serial-In Parallel-Out (SIPO) shift register accepts data serially through a single input line and produces all bits simultaneously as a parallel output, using multiple synchronized flip-flops. The main use of the SIPO register is to convert serial data into parallel data.
- Data is input one bit at a time and outputs all stored bits in parallel.
- Consists of connected D flip-flops with a common clock and a clear (CLR) signal to reset all flip-flops.
![Serial-In Parallel-Out shift Register (SIPO)](assets/FlipFlop1-14ffb359b3.png)
Serial-In Parallel-Out shift Register (SIPO)
## Parallel-In Serial-Out Shift Register (PISO)
A Parallel-In Serial-Out (PISO) shift register accepts parallel data simultaneously into each flip-flop and shifts it out serially through a single output line using synchronized flip-flops and multiplexers. It is used to convert parallel data to serial data.
- Data is loaded in parallel and then shifted out one bit at a time serially.
- Consists of D flip-flops with inputs controlled by multiplexers selecting between parallel data and previous flip-flop output, all clocked together.
![Parallel-In Serial-Out Shift Register (PISO)](assets/FIL-b1cb13f49c.jpg)
Parallel-In Serial-Out Shift Register (PISO)
## Parallel-In Parallel-Out Shift Register (PIPO)
A Parallel-In Parallel-Out (PIPO) shift register accepts and outputs data simultaneously across all flip-flops without any serial shifting, using synchronized control signals. It is used as a temporary storage device and also acts as a delay element.
- Data is loaded and retrieved in parallel from each flip-flop at the same time.
- Includes D flip-flops with no interconnections, controlled by common clock and clear (CLR) signals.
![Parallel-In Parallel-Out Shift Register (PIPO)](assets/FlipFlop2-0f42a8be97.png)
Parallel-In Parallel-Out Shift Register (PIPO)
## Bidirectional Shift Register
A Bidirectional Shift Register can shift binary data either to the left or right, enabling multiplication or division by 2 based on the selected mode.
- Mode 1 (high) shifts data right (division by 2); Mode 0 (low) shifts data left (multiplication by 2).
- Composed of four D flip-flops with inputs at both ends and gates controlled by mode signal to enable directional shifting.
![Bidirectional Shift Register](assets/Fil-78aa6562f2.jpg)
Bidirectional Shift Register
## Universal Shift Register
A Universal Shift Register is an N-bit register that supports both left and right shifting as well as parallel loading, using N flip-flops and N multiplexers with shared select lines to control the data flow.
- It combines the features of bidirectional and unidirectional shift registers, enabling versatile data manipulation (shift left, shift right, parallel load, and hold).
- Each flip-flop is connected to a multiplexer, and all multiplexers are controlled by common select lines to determine the register's operation mode.
![Universal Shift Register](assets/USR12-1e35d94d19.png)
Universal Shift Register
## Shift Register Counter
Shift Register Counters are the shift registers in which the outputs are connected back to the inputs in order to produce particular sequences. There are basically two types:
- Ring Counter
- Johnson Counter
### Ring Counter
A ring counter is basically a shift register counter in which the output of the first flip-flop is connected to the next flip-flop and so on and the output of the last flip-flop is again fed back to the input of the first flip-flop. The data pattern within the shift register will circulate as long as clock pulses are applied.
![Ring Counter Truth Table](assets/RingTT-copy-5c495b5a4b.jpg)
Ring Counter Truth Table
The circuit consists of four D flip-flops which are connected. The data pattern will repeat after every four clock pulses as shown in the truth table. A Ring counter is generally used because it is self-decoding.
![Ring Counter](assets/FlipFlop3-bef3b7ffb0.png)
Ring Counter
### Johnson Counter
A Johnson counter is basically a shift register counter in which the output of the first flip flop is connected to the next flip flop and so on and the inverted output of the last flip flop is again fed back to the input of the first flip flop. They are also known as twisted ring counters.
![Johnson Counter Truth Table](assets/JohnsonTT-copy-9406568a94.jpg)
Johnson Counter Truth Table
An n-stage Johnson counter yields a count sequence of 2n different states, thus also known as a mod-2n counter. The circuit consists of four D flip-flops which are connected, the data pattern will repeat every eight clock pulses. It only needs n number of flip-flops to generate a sequence of 2n states.
![Johnson Counter](assets/FlipFlop4-0f454cf120.png)
Johnson Counter
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/shift-registers-in-digital-logic/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Sequential Circuit

> [!note] Related notes
>
> - [[Amortized analysis for increment in counter]]
> - [[Asynchronous Sequential Circuits]]
> - [[Counters]]
> - [[D Flipflop]]
> - [[Design 101 sequence detector]]
> - [[Design counter for given sequence]]
> - [[Flip-flop types and their Conversion]]
> - [[Introduction of Sequential Circuits]]
> - [[Master Slave JK Flip Flop]]
> - [[n-bit Johnson Counter]]
