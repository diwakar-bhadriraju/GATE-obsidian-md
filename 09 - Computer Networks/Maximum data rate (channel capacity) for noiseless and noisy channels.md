---
title: "Maximum Data Rate (channel capacity) for Noiseless and Noisy channels"
subject: "Computer Networks"
topic: "Data Link Layer"
source: "https://www.geeksforgeeks.org/computer-networks/maximum-data-rate-channel-capacity-for-noiseless-and-noisy-channels/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Computer Networks/Data Link Layer"
tags:
  - gate/cs
  - subject/computer-networks
  - topic/data-link-layer
---


> [!abstract] Maximum Data Rate (channel capacity) for Noiseless and Noisy channels
> 
> **Subject:** `Computer Networks` &nbsp;|&nbsp; **Topic:** `Data Link Layer`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/maximum-data-rate-channel-capacity-for-noiseless-and-noisy-channels/)

---

# Maximum Data Rate (channel capacity) for Noiseless and Noisy channels

As early as 1924, an AT&T engineer, Henry Nyquist, realized that even a perfect channel has a finite transmission capacity. He derived an equation expressing the maximum data rate for a finite-bandwidth noiseless channel. In 1948, Claude Shannon carried Nyquist's work further and extended to it the case of a channel subject to random(that is, thermodynamic) noise (Shannon, 1948). This paper is the most important paper in all of the information theory.
Data rate governs the speed of data transmission. A very important consideration in data communication is how fast we can send data, in bits per second, over a channel. Data rate depends upon 3 factors:
- The bandwidth available
- Number of levels in digital signal
- The quality of the channel – level of noise
Two theoretical formulas were developed to calculate the data rate: one by Nyquist for a noiseless channel, another by Shannon for a noisy channel.  
## **Noiseless Channel**
For a [noiseless channel](https://www.geeksforgeeks.org/computer-networks/noiseless-channel-protocol/), the Nyquist bit rate formula defines the theoretical maximum bit rate. Nyquist proved that if an arbitrary signal has been run through a low-pass filter of [bandwidth](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-bandwidth-definition-working-importance-uses/), the filtered signal can be completely reconstructed by making only 2\*Bandwidth (exact) samples per second. Sampling the line faster than 2\*Bandwidth times per second is pointless because the higher-frequency components that such sampling could recover have already been filtered out.
If the signal consists of L discrete levels, Nyquist's theorem states:
> BitRate = 2 \* Bandwidth \* log2(L) bits/sec
In the above equation, bandwidth is the bandwidth of the channel, L is the number of signal levels used to represent data, and [BitRate](https://www.geeksforgeeks.org/digital-logic/bit-rate/) is the bit rate in bits per second. Bandwidth is a fixed quantity, so it cannot be changed. Hence, the data rate is directly proportional to the number of signal levels. 
**Note:** Increasing the levels of a signal may reduce the reliability of the system. 
### **Example**
> **Input1:** Consider a noiseless channel with a bandwidth of 3000 Hz transmitting a signal with two signal levels. What can be the maximum bit rate? 
> **Output1 :** BitRate = 2 \* 3000 \* log2(2) = 6000bps 
>
> **Input2:** We need to send 265 kbps over a noiseless channel with a bandwidth of 20 kHz. How many signal levels do we need? 
> **Output2 :** 265000 = 2 \* 20000 \* log2(L) 
> log2(L) = 6.625 
> L = 26.625 = 98.7 levels
The amount of thermal noise present is measured by the ratio of the signal power to the noise power, called the [**SNR (Signal-to-Noise Ratio)**](https://www.geeksforgeeks.org/physics/signal-to-noise-ratio-formula/)**.**
### Advantages
1. Maximum [data transfer rate](https://www.geeksforgeeks.org/computer-science-fundamentals/what-is-data-transfer-rate/) is high
2. Error-free transmission
3. **Low latency:** Since there is no noise in the channel, the [transmission delay](https://www.geeksforgeeks.org/computer-networks/delays-in-computer-network/) is very low. This means that data can be transmitted quickly and in real-time.
4. **High signal quality:** A noiseless channel provides high signal quality, which means that the data is transmitted with high accuracy and without any distortion.
5. **Suitable for critical applications:** A noiseless channel is well-suited for applications that require high reliability and precision, such as in medical equipment, military communication, and aerospace systems.
6. **Easy to design and implement:** Since a noiseless channel is a theoretical concept, it is easy to design and simulate in a controlled environment. This allows researchers to study the theoretical limits of communication systems without having to worry about practical limitations.
7. **Useful for benchmarking:** A noiseless channel is a useful benchmark for evaluating the performance of communication systems. By comparing the performance of real-world systems to the theoretical limits of a noiseless channel, researchers can identify areas where improvements can be made.
### Disadvantages
1. Not realistic as most channels have some degree of noise
2. **Cost:** Implementing a noiseless channel requires expensive equipment and resources, making it impractical for many applications.
3. **Limited range:** A noiseless channel has a limited range, meaning that it cannot be used for long-distance communication.
4. **Vulnerability to interference:** Although a noiseless channel is free from external noise, it is still vulnerable to interference from other sources such as electromagnetic radiation, which can cause errors in transmission.
5. **Lack of error correction:** Since a noiseless channel is error-free, it does not provide any error correction mechanism. This means that any errors that do occur in transmission cannot be detected or corrected, making the communication less reliable.
6. **Incompatibility with existing systems:** Most existing communication systems are designed to operate in noisy channels. A noiseless channel may not be compatible with these systems, which would require significant changes to be made to the infrastructure.
## **Noisy Channel Shannon Capacity**
In reality, we cannot have a noiseless channel. Channel will always be [noisy](https://www.geeksforgeeks.org/computer-networks/noiseless-channel-protocol/). [Shannon capacity](https://www.geeksforgeeks.org/electronics-engineering/shannon-capacity/) is used, to determine the theoretical highest data rate for a noisy channel: 
> Capacity = bandwidth \* log2(1 + SNR) bits/sec
In the above equation, bandwidth is the bandwidth of the channel, SNR is the signal-to-noise ratio, and capacity is the capacity of the channel in bits per second.  Bandwidth is a fixed quantity, so it cannot be changed. Hence, the channel capacity is directly proportional to the power of the signal, as SNR = (Power of signal) / (power of noise). 
The signal-to-noise ratio (S/N) is usually expressed in decibels (dB) given by the formula: 
> 10 \* log10(S/N)
So for example a signal-to-noise ratio of 1000 is commonly expressed as: 
> 10 \* log10(1000) = 30 dB
This tells us the best capacities that real channels can have. For example, [ADSL (Asymmetric Digital Subscriber Line)](https://www.geeksforgeeks.org/computer-networks/introduction-to-asymmetric-digital-subscriber-line-adsl/), which provides Internet access over normal telephonic lines, uses a bandwidth of around 1 MHz. the SNR depends strongly on the distance of the home from the telephone exchange, and an SNR of around 40 dB for short lines of 1 to 2km is very good. with these characteristics, the channel can never transmit much more than 13Mbps, no matter how many or how few signals level are used and no matter how often or how infrequently samples are taken.
### **Examples**
> **Input1 :** A telephone line normally has a bandwidth of 3000 Hz (300 to 3300 Hz) assigned for data communication. The SNR is usually 3162. What will be the capacity for this channel? 
> **Output1 :** C = 3000 \* log2(1 + SNR) = 3000 \* 11.62 = 34860 bps 
>
> **Input2 :** The SNR is often given in decibels. Assume that SNR(dB) is 36 and the channel bandwidth is 2 MHz. Calculate the theoretical channel capacity. 
> **Output2 :** SNR(dB) = 10 \* log10(SNR) 
> SNR = 10(SNR(dB)/10) 
> SNR = 103.6 = 3981 
>
> Hence, C = 2 \* 106 \* log2(3982) = 24 MHz 
The maximum data rate, also known as the channel capacity, is the theoretical limit of the amount of information that can be transmitted over a communication channel. The maximum data rate for noiseless and noisy channels can be calculated using Shannon's theorem. 
### **Advantages**
1. More realistic as most channels have some degree of noise
2. Techniques like error correction can be used to improve transmission reliability
3. **Longer range**: Unlike a noiseless channel, a noisy channel can be used for long-distance communication as it can propagate signals over large distances.
4. **Greater flexibility**: A noisy channel can be used for a wide range of applications, from simple voice communication to high-speed data transfer.
5. **Lower cost:** Since most communication channels are noisy, using a noisy channel is generally more cost-effective than implementing a noiseless channel.
6. **Better security:** Noise in a channel can help to obscure the transmitted signal, making it more difficult for unauthorized users to intercept and decode the **signal.**
7. **Higher capacity**: A noisy channel can support higher data rates than a noiseless channel by using advanced modulation schemes and error correction techniques. This makes it possible to transmit more data over the same channel bandwidth.
8. **Adaptable:** Communication systems using a noisy channel can be designed to adapt to changing conditions, such as variations in signal strength or interference levels. This makes them more reliable and adaptable in dynamic environments.
### Disadvantages
1. Maximum data rate is lower than in noiseless channels
2. Higher probability of errors in transmission
3. In a noisy channel, the maximum data rate is lower than in a noiseless channel due to the presence of noise. The presence of noise limits the maximum amount of information that can be transmitted over the channel.
4. **Increased complexity:** In a noisy channel, additional techniques such as error correction and signal processing are required to ensure reliable transmission. This adds complexity to the system design and can increase the cost of implementation.
5. **Limited range:** The presence of noise in a channel can limit the range of the communication, particularly in wireless systems, where interference from other sources can also affect the quality of the signal.
6. **Interference:** Noise can come from many sources, including other electronic devices and environmental factors such as weather conditions, which can interfere with the transmission and degrade the quality of the signal.
7. **Degraded signal quality:** The presence of noise in a channel can cause distortion in the signal, resulting in a loss of signal quality and clarity. This can make it difficult to distinguish between different data values, leading to errors in transmission.
8. **Security issues:** The presence of noise can make it easier for unauthorized users to intercept and decode the signal, leading to potential security issues such as data theft or unauthorized access to sensitive information.
Advances in digital signal processing and error correction techniques have allowed for the development of more sophisticated modulation and encoding schemes that can increase the maximum data rate of noisy channels. However, these techniques can also increase the complexity and cost of the communication system.
Noiseless channels have a higher maximum data rate and provide error-free transmission. However, they are not realistic as most channels have some degree of noise. Noisy channels have a lower maximum data rate but are more realistic, and techniques like error correction can be used to improve transmission reliability. The choice of channel type depends on the specific needs of the communication system.
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/computer-networks/maximum-data-rate-channel-capacity-for-noiseless-and-noisy-channels/)

## GATE CS

- Subject: Computer Networks
- Topic: Data Link Layer

> [!note] Related notes
>
> - [[Aloha]]
> - [[Back-off Algorithm for CSMA CD]]
> - [[Bit Stuffing]]
> - [[Carrier sense multiple access]]
> - [[Collision Avoidance in wireless networks]]
> - [[Collision Detection in CSMA CD]]
> - [[Computer Networks Error Detection]]
> - [[Controlled Access Protocols]]
> - [[Difference between Byte stuffing and Bit stuffing]]
> - [[Efficiency of CSMA CD]]
