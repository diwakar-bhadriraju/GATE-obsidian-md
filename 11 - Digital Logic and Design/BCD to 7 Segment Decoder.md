---
title: "BCD to 7 Segment Decoder"
subject: "Digital Logic and Design"
topic: "Combinational Circuit"
source: "https://www.geeksforgeeks.org/digital-logic/bcd-to-7-segment-decoder/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Digital Logic and Design/Combinational Circuit"
tags:
  - gate/cs
  - subject/digital-logic-and-design
  - topic/combinational-circuit
---


> [!abstract] BCD to 7 Segment Decoder
> 
> **Subject:** `Digital Logic and Design` &nbsp;|&nbsp; **Topic:** `Combinational Circuit`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/bcd-to-7-segment-decoder/)

---

# BCD to 7 Segment Decoder

Prerequisite -
[Number System and base conversions](https://www.geeksforgeeks.org/digital-logic/number-system-and-base-conversions/)
## **Binary Coded Decimal (BCD)**
[BCD](https://www.geeksforgeeks.org/dsa/bcd-or-binary-coded-decimal/) is the encoding scheme each of the decimal numbers(0-9) is represented by its equivalent binary pattern(which is generally of 4-bits).
## **Seven segment**
Seven Segment display is an electronic device which consists of seven Light Emitting Diodes (LEDs) arranged in a some definite pattern (common cathode or common anode type), which is used to display Hexadecimal numerals(in this case decimal numbers, as input is BCD i.e., 0-9). Two types of seven segment LED display:
1. **Common Cathode Type:** In this type of display all cathodes of the seven LEDs are connected together to the ground or -Vcc(hence, common cathode) and LED displays digits when some 'HIGH' signal is supplied to the individual anodes.
2. **Common Anode Type:** In this type of display all the anodes of the seven LEDs are connected to battery or +Vcc and [LED](https://www.geeksforgeeks.org/digital-logic/types-and-applications-of-led/) displays digits when some 'LOW' signal is supplied to the individual cathodes.
But, seven segment display does not work by directly supplying voltage to different segments of LEDs. First, our decimal number is changed to its BCD equivalent signal then BCD to seven segment decoder converts that signals to the form which is fed to seven segment display. This BCD to seven segment decoder has four input lines (A, B, C and D) and 7 output lines (a, b, c, d, e, f and g), this output is given to seven segment LED display which displays the decimal number depending upon inputs.
![](assets/bcd-0cfe00dd6d.png)
### **Truth Table**
For common cathode type BCD to seven segment decoder:
![](assets/1221-7cb1b7fe91.png)
**Note -**
- For Common Anode type seven segment LED display, we only have to interchange all '0s' and '1s' in the output side i.e., (for a, b, c, d, e, f, and g replace all '1' by '0' and vice versa) and solve using K-map.
- Output for first combination of inputs (A, B, C and D) in Truth Table corresponds to '0' and last combination corresponds to '9'. Similarly rest corresponds from 2 to 8 from top to bottom.
- BCD numbers only range from 0 to 9,thus rest inputs from 10-F are invalid inputs.
**Example -**
![](assets/bcd-1-2cf185dcef.png)
**Explanation -**
For combination where all the inputs (A, B, C and D) are zero (see Truth Table), our output lines are a = 1, b = 1, c = 1, d = 1, e = 1, f = 1 and g = 0. So 7 segment display shows 'zero' as output. Similarly, for combination where one of the input is one (D = 1) and rest are zero, our output lines are a = 0, b = 1, c = 1, d = 0, e = 0, f = 0 and g = 0. So only LEDs 'b' and 'c' (see diagram above) will glow and 7 segment display shows 'one' as output.
**K-Maps:**
#for a:
![a](assets/bcd-a-b47313d7e6.png)
#for b:
![b](assets/bcd-b-bdc35f5d79.png)
#for c:
![c](assets/bcd-c-643ad7d408.png)
#for d:
![d](assets/bcd-d-bed34cf9d5.png)
#for e:
![e](assets/bcd-e-f9e5cd87b5.png)
#for f:
![f](assets/bcd-f-5be06069d8.png)
#for g:
![g](assets/bcd-g-a7abda97d8.png)
## Applications
- **Computerized Clocks:** BCD to 7-fragment decoders are utilized in advanced tickers to show time in hours, minutes, and seconds by changing over the paired time information into decipherable digits.
- **Counters and Clocks:** In counters and clocks, these decoders drive the 7-portion presentations to show the count value or passed time, making them fundamental in different counting and timing gadgets.
- **Adding machines:** Fundamental mini-computers use BCD to 7-section decoders to change over-paired coded decimal results from the number cruncher's processor into mathematical digits on the showcase.
- **Computerized Meters:** They are utilized in computerized voltmeters, ammeters, and recurrence meters to show estimation readings in a mathematical configuration, further developing lucidity.
## Advantages
- **Diminished Part Count:** Limits the quantity of parts expected to control a 7-portion show.
- Further developed Dependability: Gives a strong and solid change from BCD to show portions.
- **Simplicity of Mix:** Smoothes out the method involved with incorporating mathematical presentations into advanced frameworks.
## Disadvantages
- **Cost for Straightforward Applications:** Utilizing a dedicated decoder IC may be more costly than less complex answers for essential necessities.
- **Speed Limits:** Execution is limited by the decoder's handling speed, which is inadmissible for fast applications.
- **Size Imperatives:** The actual size of the decoder IC may not fit in minimized plans.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/bcd-to-7-segment-decoder/)

## GATE CS

- Subject: Digital Logic and Design
- Topic: Combinational Circuit

> [!note] Related notes
>
> - [[BCD Adder]]
> - [[Binary Decoder]]
> - [[Carry Look-Ahead Adder]]
> - [[Combinational circuits using Decoder]]
> - [[De-MUX]]
> - [[Encoder]]
> - [[Encoders and Decoders]]
> - [[Full Adder]]
> - [[Full Subtractor]]
> - [[Grey Code]]
