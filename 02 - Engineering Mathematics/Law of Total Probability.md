---
title: "Law of Total Probability"
subject: "Engineering Mathematics"
topic: "Probability"
source: "https://www.geeksforgeeks.org/maths/mathematics-law-of-total-probability/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Probability"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/probability
---


> [!abstract] Law of Total Probability
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Probability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/mathematics-law-of-total-probability/)

---

# Law of Total Probability

The Law of Total Probability helps determine the probability of an event by considering all possible ways it can occur.
It states that if an event can occur through several [mutually exclusive](https://www.geeksforgeeks.org/maths/mutually-exclusive-events/) and [exhaustive events](https://www.geeksforgeeks.org/maths/exhaustive-events/), then its total probability is the sum of the probabilities of each possible way it can occur.
- It expresses the probability of an event in terms of conditional probabilities.
- It is applicable when the sample space is partitioned into mutually exclusive and exhaustive events.
![_law_of_total_probability](assets/_law_of_total_probability-f45f4eb23e.webp)
If A₁, A₂, A₃, ..., Aₙ form a partition of the sample space S, then for any event B,
>
$$
P(B) = \sum_{i=1}^{n} P(B \cap A_i)
$$
>
>
$$
= \sum_{i=1}^{n} P(B \mid A_i)\, P(A_i)
$$
The figure shows that the sample space is divided into [disjoint events](https://www.geeksforgeeks.org/engineering-mathematics/independency-of-disjoint-events/) A₁, A₂, and A₃. Event B overlaps with these partitions. Therefore, the probability of B is obtained by adding the probabilities of B occurring within each partition.
### Proof
> Since A₁, A₂, A₃, ... form a partition of the sample space S,
>
>
$$
S=\bigcup_{i} A_i
$$
>
> For any event B,
>
>
$$
B = B \cap S
$$
>
>
$$
B = B \cap \left(\bigcup_{i} A_i\right)
$$
>
>
$$
B = \bigcup_{i}(B \cap A_i)
$$
>
> by the distributive law.
>
> Since the sets (B ∩ Aᵢ) are disjoint (because the Aᵢ's are disjoint), by the addition [axiom of probability](https://www.geeksforgeeks.org/maths/axiomatic-approach-to-probability/),
>
>
$$
P(B)=P\!\left(\bigcup_{i}(B \cap A_i)\right)
$$
>
>
$$
P(B)=\sum_{i} P(B \cap A_i)
$$
>
> Using the definition of [conditional probability](https://www.geeksforgeeks.org/maths/conditional-probability/),
>
>
$$
P(B \cap A_i)=P(B \mid A_i)\,P(A_i)
$$
>
> Substituting,
>
>
$$
P(B)=\sum_{i} P(B \mid A_i)\,P(A_i)
$$
>
> **Hence proved.**
**Note:** The Law of Total Probability is used when the direct probability of an event is unknown, but the conditional probabilities under different mutually exclusive cases and the probabilities of those cases are known. It is also known as the Total Probability Theorem or the Law of Alternatives.
## Applications
### 1. Bayes' Theorem
The Law of Total Probability is used to calculate the denominator in [Bayes' Theorem](https://www.geeksforgeeks.org/maths/bayes-theorem/). It helps determine the probability of a cause after observing an event.
**Used in:**
- Spam email detection
- Text classification
- Sentiment analysis
### 2. Expectation-Maximization (EM) Algorithm
The EM algorithm is used to estimate hidden (latent) variables in probabilistic models. The Law of Total Probability helps compute the probability of observed data by considering all possible hidden variables.
**Used in:**
- Gaussian Mixture Models (GMMs)
- Data clustering
### 3. Hidden Markov Models (HMMs)
In HMMs, the actual states are hidden and only observations are visible. The Law of Total Probability is used to calculate the probability of an observed sequence by considering all possible hidden states.
**Used in:**
- Speech recognition
- Part-of-Speech (POS) tagging
- Gene prediction
### 4. Bayesian Networks and Marginalization
The Law of Total Probability is used to find the probability of an event by considering all possible values of unknown variables. This process is known as marginalization.
**Used in:**
- Medical diagnosis
- Sensor networks
- Decision-making systems
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/law-of-total-probability-practice-problems/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/mathematics-law-of-total-probability/)

## GATE CS

- Subject: Engineering Mathematics
- Topic: Probability

> [!note] Related notes
>
> - [[Bayes’s Formula for Conditional Probability]]
> - [[Binomial Distribution]]
> - [[Conditional Probability]]
> - [[Covariance and Correlation]]
> - [[Exponential Distribution]]
> - [[Introduction to Probability]]
> - [[Mean]]
> - [[Normal Distribution]]
> - [[Poisson Distribution]]
> - [[Probability Distribution]]
