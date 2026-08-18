---
title: "Difference between Unipolar, Polar and Bipolar Line Coding Schemes"
subject: "Computer Networks"
topic: "Network Fundamental and Physical Layer"
source: "https://www.geeksforgeeks.org/digital-logic/difference-between-unipolar-polar-and-bipolar-line-coding-schemes/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Network Fundamental and Physical Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/network-fundamental-and-physical-layer
---


> [!abstract] Difference between Unipolar, Polar and Bipolar Line Coding Schemes
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Network Fundamental and Physical Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/difference-between-unipolar-polar-and-bipolar-line-coding-schemes/)

---

# Difference between Unipolar, Polar and Bipolar Line Coding Schemes

Data as well as signals that represents data can either be digital or analog. Line coding is the process of converting digital data to digital signals. By this technique we converts a sequence of bits to a digital signal. At the sender side digital data are encoded into a digital signal and at the receiver side the digital data are recreated by decoding the digital signal. 
We can roughly divide line coding schemes into five categories:
1. Unipolar (eg. NRZ scheme).
2. Polar (eg. NRZ-L, NRZ-I, RZ, and Biphase - Manchester and differential Manchester).
3. Bipolar (eg. AMI and Pseudoternary).
4. Multilevel
5. Multitransition
But, before learning difference between first three schemes we should first know the **characteristic** of these line coding techniques:
- There should be **self-synchronizing** i.e., both receiver and sender clock should be synchronized.
- There should have some error-detecting capability.
- There should be immunity to noise and interference.
- There should be less complexity.
- There should be no low-frequency component (**DC-component**) as long distance transfer is not feasible for low frequency component signal.
- There should be less base line wandering.
**Unipolar scheme -** In this scheme, all the signal levels are either above or below the axis.
- **Non return to zero (NRZ) -** It is unipolar line coding scheme in which positive voltage defines bit 1 and the zero voltage defines bit 0. Signal does not return to zero at the middle of the bit thus it is called NRZ.
          For example: Data =10110. ![](assets/Difference_Line_Coding_Schemes_1-459fc6fa79.jpg) But this scheme uses more power as compared to polar scheme to send one bit per unit line resistance. Moreover for continuous set of zeros or ones there will be self-synchronization and base line wandering problem.
**Polar schemes -** In polar schemes, the voltages are on the both sides of the axis.
- **NRZ-L and NRZ-I -** These are somewhat similar to unipolar NRZ scheme but here we use two levels of amplitude (voltages). For **NRZ-L(NRZ-Level)**, the level of the voltage determines the value of the bit, typically binary 1 maps to logic-level high, and binary 0 maps to logic-level low, and for **NRZ-I(NRZ-Invert)**, two-level signal has a transition at a boundary if the next bit that we are going to transmit is a logical 1, and does not have a transition if the next bit that we are going to transmit is a logical 0. **Note -** For NRZ-I we are assuming in the example that previous signal before starting of data set "01001110" was positive. Therefore, there is no transition at the beginning and first bit "0" in current data set "01001110" is starting from +V. Example: Data = 01001110.
![](assets/Difference_Line_Coding_Schemes_2-51758d1a04.jpg)
Comparison between NRZ-L and NRZ-I: Baseline wandering is a problem for both of them, but for NRZ-L it is twice as bad as compared to NRZ-I. This is because of transition at the boundary for NRZ-I (if the next bit that we are going to transmit is a logical 1). Similarly self-synchronization problem is similar in both for long sequence of 0's, but for long sequence of 1's it is more severe in NRZ-L.
- **Return to zero (RZ) -** One solution to NRZ problem is the RZ scheme, which uses three values positive,negative,and zero. In this scheme signal goes to 0 in the middle of each bit. **Note -** The logic we are using here to represent data is that for bit 1 half of the signal is represented by +V and half by zero voltage and for bit 0 half of the signal is represented by -V and half by zero voltage. Example: Data = 01001.
![](assets/Difference_Line_Coding_Schemes_3-7b6cd19219.jpg) Main disadvantage of RZ encoding is that it requires greater bandwidth. Another problem is the complexity as it uses three levels of voltage. As a result of all these deficiencies, this scheme is not used today. Instead, it has been replaced by the better-performing Manchester and differential Manchester schemes.
- **Biphase (Manchester and Differential Manchester ) -** Manchester encoding is somewhat combination of the RZ (transition at the middle of the bit) and NRZ-L schemes. The duration of the bit is divided into two halves. The voltage remains at one level during the first half and moves to the other level in the second half. The transition at the middle of the bit provides synchronization. Differential Manchester is somewhat combination of the RZ and NRZ-I schemes. There is always a transition at the middle of the bit but the bit values are determined at the beginning of the bit. If the next bit is 0, there is a transition, if the next bit is 1, there is no transition.
- **Note -** **1.** The logic we are using here to represent data using Manchester is that for bit 1 there is transition form -V to +V volts in the middle of the bit and for bit 0 there is transition from +V to -V volts in the middle of the bit. **2.** For differential Manchester we are assuming in the example that previous signal before starting of data set "010011" was positive. Therefore there is transition at the beginning and first bit "0" in current data set "010011" is starting from -V. Example: Data = 010011.
![](assets/Difference_Line_Coding_Schemes_4-289cc1beb1.jpg) The Manchester scheme overcomes several problems associated with NRZ-L, and differential Manchester overcomes several problems associated with NRZ-I as there is no baseline wandering and no DC component because each bit has a positive and negative voltage contribution. Only limitation is that the minimum bandwidth of Manchester and differential Manchester is twice that of NRZ.
**Bipolar schemes -** In this scheme there are three voltage levels positive, negative, and zero. The voltage level for one data element is at zero, while the voltage level for the other element alternates between positive and negative.
- **Alternate Mark Inversion (AMI) -** A neutral zero voltage represents binary 0. Binary 1's are represented by alternating positive and negative voltages.
- **Pseudoternary -** Bit 1 is encoded as a zero voltage and the bit 0 is encoded as alternating positive and negative voltages i.e., opposite of AMI scheme. Example: Data = 010010.
![](assets/Difference_Line_Coding_Schemes_5-1-d25462f6c0.jpg)The bipolar scheme is an alternative to NRZ. This scheme has the same signal rate as NRZ, but there is no DC component as one bit is represented by voltage zero and other alternates every time.
### **Advantages and disadvantages of Unipolar Line Coding Scheme:**
**Advantages:**
- **Simple receiver circuit:** The receiver circuit for unipolar line coding is simple, as it only needs to detect the presence or absence of a voltage.
- **Low DC component:** The unipolar line coding scheme has a low DC component, which is desirable for some communication systems.
- **Low cost:** Unipolar line coding scheme uses only a single voltage level, so it is easy to implement and requires fewer components, making it a cost-effective solution.
**Disadvantages:**
- **Poor noise immunity:** The unipolar line coding scheme has poor noise immunity and is susceptible to errors, as it does not have a differential signal.
- **Limited dynamic range:** The unipolar line coding scheme has a limited dynamic range, as it only uses positive voltage levels.
### Advantages and disadvantages of Polar Line Coding Scheme:
**Advantages:**
- **High noise immunity:** The polar line coding scheme has a high noise immunity, as it uses a differential signal.
- **Error resistance:** The polar line coding scheme is less susceptible to errors, as it uses a differential signal.
**Disadvantages:**
- **Complex receiver circuit:** The receiver circuit for polar line coding is complex, as it needs to detect the positive and negative voltage levels.
- **Limited data rate:** The polar line coding scheme has a limited data rate, as it requires a larger number of bits to represent the same information as the unipolar or bipolar line coding schemes.
**Advantages and disadvantages of Bipolar Line Coding Scheme:**
**Advantages:**
- **High data rate:** The bipolar line coding scheme has a high data rate, as it uses positive and negative voltage levels to represent the digital signal.
- **Differential signal**: The bipolar line coding scheme uses a differential signal, which improves noise immunity and error resistance.
**Disadvantages:**
- **Complex receiver circuit:** The receiver circuit for bipolar line coding is complex, as it needs to detect the positive and negative voltage levels.
- **Limited dynamic range:** The bipolar line coding scheme has a limited dynamic range, as it uses positive and negative voltage levels to represent the digital signal.
**Reference -** [Data Communications and Networking](https://www.geeksforgeeks.org/computer-networks/data-communication-definition-components-types-channels/) By Behrouz A.Forouzan (Book)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/digital-logic/difference-between-unipolar-polar-and-bipolar-line-coding-schemes/)

## GATE CS

- Subject: Computer Networks
- Topic: Network Fundamental and Physical Layer

> [!note] Related notes
>
> - [[Basics of Computer Networking]]
> - [[Difference between Broadband and]]
> - [[Layers of OSI Model]]
> - [[Let’s experiment with Networking]]
> - [[Network goals]]
> - [[Network Topologies]]
> - [[Redundant link problems]]
> - [[TCP IP Model]]
> - [[Transmission Modes in Computer Networks]]
> - [[Types of area networks – LAN, MAN and WAN]]
