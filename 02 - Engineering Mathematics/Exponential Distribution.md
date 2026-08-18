---
title: "Exponential Distribution"
subject: "Engineering Mathematics"
topic: "Probability"
source: "https://www.geeksforgeeks.org/engineering-mathematics/probability-distributions-exponential-distribution/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Probability"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/probability
---


> [!abstract] Exponential Distribution
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Probability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/probability-distributions-exponential-distribution/)

---

# Exponential Distribution

The Exponential Distribution is one of the most commonly used probability distributions in statistics and data science. It is widely used to model the time or space between events in a Poisson process. In simple terms, it describes how long you have to wait before something happens, like a bus arriving or a customer calling a help center.
For example, if buses arrive at a bus stop every 15 minutes on average, the time you wait for the next bus can be modelled using an exponential distribution.
### Probability Density Function (PDF)
The probability density function of the exponential distribution is:
>
$$
f(x; \lambda) = \lambda e^{-\lambda x}, \quad x \geq 0
$$
Where:
-
$$
\lambda
$$
   > 0 is the rate parameter (how often events occur)
- x is the time or distance until the next event
### Cumulative Distribution Function (CDF)
The cumulative distribution function gives the probability that the event occurs within time :
>
$$
F(x; \lambda) = 1 - e^{-\lambda x}, \quad x \geq 0
$$
### Mean and Variance
- **Mean (Expected Value)**:
$$
E[X] = \frac{1}{\lambda}
$$
- **Variance**:
$$
\text{Var}(X) = \frac{1}{\lambda^2}
$$
### Memory-less Property
The exponential distribution is memory-less, which means:
>
$$
P(X > s + t \mid X > s) = P(X > t)
$$
This property tells us that the probability of waiting longer does not depend on how long you've already waited. This is unique to the exponential distribution.
## **Example**
> Suppose calls come into a customer support center at an average rate of 2 per minute. What is the probability that you wait more than 30 seconds for the next call?
**Solution**:
1. **Understand the Rate (λ):** Since 2 calls come in per minute, that means the average rate is: λ=2 calls per minute
2. **Convert Time:** Find the probability of waiting more than 30 seconds. But since the rate is in minutes, convert 30 seconds to minutes: 30 seconds=0.5 minutes
3. **Use the Exponential Distribution formula:**
$$
P(X > 0.5) = e^{-\lambda x} = e^{-2 \cdot 0.5} = e^{-1} \approx 0.3679
$$
So, there is about a 36.79% chance that the next call comes after 30 seconds.
## Example in Python
Before its implementation we should have some basic knowledge about [numpy](https://www.geeksforgeeks.org/numpy/python-numpy/), [matplotlib](https://www.geeksforgeeks.org/python/python-introduction-matplotlib/) and [seaborn](https://www.geeksforgeeks.org/python/introduction-to-seaborn-python/).
````python3
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
# Set the rate parameter lambda
lam = 1.5
# Generate exponential data
data = np.random.exponential(1/lam, 1000)
# Plot the KDE and histogram
sns.histplot(data, kde=True, stat="density")
plt.title("Exponential Distribution (lambda=1.5)")
plt.xlabel("Time")
plt.ylabel("Density")
plt.show()
````
**Output:**
![download](assets/download-dfd412854e.png)
Exponential Distribution
> **Note**: The exponential distribution is closely related to the [Poisson distribution](https://www.geeksforgeeks.org/maths/poisson-distribution/). If events occur following a Poisson process with rate , then the time between events is exponentially distributed with parameter .
## Real-World Applications
1. **Call Centers**: Time between incoming calls
2. **Bank Queues**: Time between customer arrivals
3. **Web Servers**: Time between requests
4. **Manufacturing**: Time until a machine part fails
5. **Transport**: Time between buses or trains
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/probability-distributions-exponential-distribution/)

## GATE CS

- Subject: Engineering Mathematics
- Topic: Probability

> [!note] Related notes
>
> - [[Bayes’s Formula for Conditional Probability]]
> - [[Binomial Distribution]]
> - [[Conditional Probability]]
> - [[Covariance and Correlation]]
> - [[Introduction to Probability]]
> - [[Law of Total Probability]]
> - [[Mean]]
> - [[Normal Distribution]]
> - [[Poisson Distribution]]
> - [[Probability Distribution]]
