---
title: "Random Variable"
subject: "Engineering Mathematics"
topic: "Probability"
source: "https://www.geeksforgeeks.org/random-variable/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Probability"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/probability
---


> [!abstract] Random Variable
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Probability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/random-variable/)

---

# Random Variable

A random variable is a key concept in statistics that connects theoretical probability with real-world data. It is a function that assigns a real number to each outcome in the sample space of a random experiment.
> **For example:** When you roll a die, the outcome is one of the six faces. A random variable can assign a number (like 1 to 6) to each of these outcomes, allowing us to analyze the results using statistical methods.
![random_variable](assets/random_variable-7754e9b21e.webp)
There are two possible outcomes, modeled as random variables
We define a random variable as a function that maps from the sample space of an experiment to the real numbers. Mathematically, a Random Variable is expressed as,
> **X: S →R**
**Where:**
- **X** is aRandom Variable (It is usually denoted using a capital letter)
- **S** is Sample Space
- **R** is a Set of Real Numbers
Random variables are generally represented by capital letters like X and Y.
### **Random Variable Examples**
**Example 1:** If two unbiased coins are tossed, then find the random variable associated with that event.
**Solution:**
> Suppose Two (unbiased) coins are tossed
> X = number of heads. [X is a random variable or function]
>
> Here, the sample space S = {HH, HT, TH, TT}
Suppose a random variable X takes m different values, X = {x1, x2, x3,..., xm}, with corresponding probabilities **P(X = x**i**) = p**i,** where 1 ≤ i ≤ m.
The probabilities must satisfy the following conditions :
- 0 ≤ pi ≤ 1; where 1 ≤ i ≤ m
- p1 + p2 + p3 + ....... + pm = 1 or we can say 0 ≤ pi ≤ 1 and ∑pi = 1
**Example 2:** Suppose a die is thrown (X = outcome of the dice) and the sample space S = {1, 2, 3, 4, 5, 6}.
**Solution:**
> The output of the function will be:
>
> - P(X = 1) = 1/6
> - P(X = 2) = 1/6
> - P(X = 3) = 1/6
> - P(X = 4) = 1/6
> - P(X = 5) = 1/6
> - P(X = 6) = 1/6
>
> This also satisfies the condition ∑6i=1 P(X = i) = 1, since:
> P(X = 1) + P(X = 1) + P(X = 2) + P(X = 3) + P(X = 4) + P(X = 5) + P(X = 6) = 6 × 1/6 = 1
## Variate
A variate is a general term often used interchangeably with a random variable, particularly in contexts where the random variable is not yet fully specified by a particular probabilistic experiment.
- It is an abstract concept that represents a real-valued outcome of a random process, but is not necessarily tied to a specific probability distribution.
- It has the same properties as a random variable, such as a defined range of possible values.
- The range of values that a random variable X can take is denoted as Rx ( range of X ).
- Individual values within this range are called quantiles.
- The probability of the random variable X taking a specific value x is written as P(X = x).
## Types of Random Variables
Random variables are of two types, that are as follows:
![Types-of-random_variable](assets/Types-of-random_variable-f0c74394f9.webp)
Types Of Random Variable
## **Discrete Random Variable**
A Discrete Random Variable takes on a finite or countably infinite number of values. The probability function associated with a discrete random variable is called as Probability Mass Function.
### PMF(Probability Mass Function)
If X is a discrete random variable and the PMF of X is P(xi), then
- 0 ≤ pi ≤ 1
- ∑p(xi) = 1, where the sum is taken over all possible values of x
### **Discrete Random Variables Example**
**Example:** Let S = {0, 1, 2}
| xi | 0 | 1 | 2 |
| --- | --- | --- | --- |
| Pi(X = xi) | P1 | 0.3 | 0.5 |
**Find the value of P (X = 0)**
**Solution:**
> We know that the sum of all probabilities is equal to 1. And P (X = 0) be P1
> P1 + 0.3 + 0.5 = 1
> P1 = 0.2
>
> Then, P (X = 0) is 0.2
## **Continuous Random Variable**
A Continuous Random Variable takes on an infinite number of values. The probability function associated with it is said to be [PDF (Probability Density Function)](https://www.geeksforgeeks.org/engineering-mathematics/probability-density-function/).
### **PDF** (Probability Density Function)
If X is a continuous random variable. P (x < X < x + dx) = f(x)dx then,
- 0 ≤ f(x) ≤ 1; for all x
- ∫ f(x) dx = 1 over all values of x
Then P (X) is said to be a PDF of the distribution.
**Example:**  Find the value of P (1 < X < 2) f(x) = kx3; 0 ≤ x ≤ 3 = 0. Otherwise, f(x) is a density function.
**Solution:**
> If a function f is said to be a density function, then the sum of all probabilities is equal to 1.
>
> Since it is a continuous random variable Integral value is 1 overall sample space s.
>
> ∫ f(x) dx = 1
> ∫ kx3 dx = 1
> K[x4]/4 = 1
>
> Given interval, 0 ≤ x ≤ 3 = 0
>
> K[34 – 04]/4 = 1
> K(81/4) = 1
> K = 4/81
>
> Thus,
>
> P (1 < X < 2) = k × [X4]/4
> P = 4/81 × [16-1]/4
> P = 15/81
## Random Variable Formulas
There are two main random variable formulas,
### 1. Mean of a Random Variable
For any random variable X where P is its respective probability, we define its mean as,
> Mean(μ) = ∑ X.P
**Where,**
- X is the random variable that consists of all possible values.
- P is the probability of the respective variables
### 2. Variance of a Random Variable
The variance of a random variable tells us how the random variable is spread about the mean value of the random variable. The variance of the Random Variable is calculated using the formula,
> Var(x) = σ2 = E(X2) - {E(X)}2
**Where,**
- E(X2) = ∑X2P
- E(X) = ∑XP
## Random Variable Functions
For any random variable X if it assume the values x1, x2,...xn where the probability corresponding to each random variable is P(x1), P(x2),...P(xn), then the expected value of the variable is,
Expectation of X, E(x) = ∑ x.P(x)
Now, for any new random variable Y in which the random variable X is its input, i.e., Y = f(X), then the cumulative distribution function of Y is,
> Fy(Y) = P(g(X) ≤ y)
## Probability Distribution and Random Variable
For a random variable, its probability distribution is calculated using three methods,
- Theoretical listing of outcomes and probabilities of the outcomes.
- Experimental listing of outcomes followed by their observed relative frequencies.
- Subjective listing of outcomes followed by their subjective probabilities.
The probability of a random variable X that takes values x is defined using a probability function of X that is denoted by f (x) = f (X = x).
## Random Variables in Computer Science
Random variables are important in computer science for dealing with uncertainty and chance.
- They are used to study the average behavior of algorithms that use random steps, such as QuickSort.
- In machine learning, they help describe input data, predictions, and errors.
- Simulations use them to model events like customer arrivals or data flow in a network.
- In cybersecurity, random variables help create strong, unpredictable keys.
- They are also useful in checking how well data structures like hash tables perform.
- In networking, they help predict delays and traffic.
- Even in games and animation, random variables create random actions and natural-looking effects.
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/random-variables-practice-problems/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/random-variable/)

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
> - [[Law of Total Probability]]
> - [[Mean]]
> - [[Normal Distribution]]
> - [[Poisson Distribution]]
