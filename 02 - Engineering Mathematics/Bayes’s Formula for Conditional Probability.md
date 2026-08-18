---
title: "Bayes' Theorem"
subject: "Engineering Mathematics"
topic: "Probability"
source: "https://www.geeksforgeeks.org/maths/bayes-theorem/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Probability"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/probability
---


> [!abstract] Bayes' Theorem
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Probability`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/maths/bayes-theorem/)

---

# Bayes' Theorem

Bayes' Theorem is a mathematical formula used to determine the conditional probability of an event based on prior knowledge and new evidence.
It adjusts probabilities when new information comes in and helps make better decisions in uncertain situations.
> **Bayes' Theorem helps us update probabilities based on prior knowledge and new evidence. In this case, knowing that the pet is quiet (new information), we can use Bayes' Theorem to calculate the updated probability of the pet being a cat or a dog, based on how likely each animal is to be quiet.**
## **Bayes Theorem and Conditional Probability**
Bayes' theorem (also known as the Bayes Rule or Bayes Law) is used to determine the conditional probability of event A when event B has already occurred.
The general statement of Bayes’ theorem is “The [conditional probability](https://www.geeksforgeeks.org/maths/conditional-probability/) of an event A, given the occurrence of another event B, is equal to the product of the probability of B, given A, and the probability of A divided by the probability of event B.**”** i.e.
> **For example,** if we want to find the probability that a white marble drawn at random came from the first bag, given that a white marble has already been drawn, and there are three bags each containing some white and black marbles, then we can use Bayes’ Theorem.
## **Bayes Theorem Formula**
For any two events A and B, Bayes's formula for the Bayes theorem is given by:
![p_a_b_](assets/p_a_b_-a4a3ba9328.webp)
Formula for the Bayes theorem
Where,
- **P(A)** and **P(B)** are the probabilities of events A and B; also, P(B) is never equal to zero.
- **P(A|B)** is the probability of event A when event B happens,
- **P(B|A)** is the probability of event B when A happens.
## **Bayes Theorem Statement**
**Bayes' Theorem for n sets of events is defined as,**
Let E1, E2,…, En be a set of events associated with the sample space S, in which all the events E1, E2,…, En have a non-zero probability of occurrence. All the events E1, E2,…, E form a partition of S. Let A be an event in space S for which we have to find the probability, then according to Bayes theorem,
>
$$
P(E_i \mid A) = \frac{P(E_i) \cdot P(A \mid E_i)}{\sum_{k=1}^{n} P(E_k) \cdot P(A \mid E_k)}
$$
>
> **for k = 1, 2, 3, …., n**
## **Bayes Theorem Derivation**
The proof of Bayes' Theorem is given as, according to the conditional probability formula,
$$
P(E_i \mid A) = \frac{P(E_i \cap A)}{P(A)}
$$
**.....(i)**
Then, by using the multiplication rule of probability, we get
$$
P(E_i \cap A) = P(E_i) \cdot P(A \mid E_i)
$$
**......(ii)**
Now, by the total probability theorem,
$$
P(A) = \sum_{k=1}^{n} P(E_k) \cdot P(A \mid E_k)
$$
**.....(iii)**
Substituting the value of P(Ei∩A) and P(A) from eq (ii) and eq(iii) in eq(i) we get,
>
$$
P(E_i \mid A) = \frac{P(E_i) \cdot P(A \mid E_i)}{\sum_{k=1}^{n} P(E_k) \cdot P(A \mid E_k)}
$$
Bayes’ theorem is also known as the formula for the probability of “causes”. As we know, the Ei‘s are a partition of the sample space S, and at any given time, only one of the events Ei occurs. Thus, we conclude that the Bayes theorem formula gives the probability of a particular Ei, given that event A has occurred.
## Terms Related to Bayes' Theorem
After learning about Bayes theorem in detail, let us understand some important terms related to the concepts we covered in the formula and derivation.
**Hypotheses**
- [Hypotheses](https://www.geeksforgeeks.org/maths/hypothesis/) refer to possible events or outcomes in the sample space; they are denoted as E1, E2, …, En.
- Each hypothesis represents a distinct scenario that could explain an observed event.
**Priori Probability**
- [Priori Probability](https://www.geeksforgeeks.org/maths/prior-probability/) P(Ei) is the initial probability of an event occurring before any new data is taken into account.
- It reflects existing knowledge or assumptions about the event.
- **Example:** The probability of a person having a disease before taking a test.
**Posterior Probability**
- [Posterior probability](https://www.geeksforgeeks.org/maths/posterior-probability/) (P(Ei∣A) is the updated probability of an event after considering new information.
- It is derived using the Bayes Theorem.
- **Example:** The probability of having a disease given a positive test result.
**Conditional Probability**
- The probability of an event A based on the occurrence of another event B is termed [conditional Probability](https://www.geeksforgeeks.org/maths/conditional-probability/).
- It is denoted as **P(A|B)** and represents the probability of A when event B has already happened.
**Joint Probability**
- When the probability of two or more events occurring together and at the same time is measured, it is marked as [Joint Probability](https://www.geeksforgeeks.org/engineering-mathematics/joint-probability-concept-formula-and-examples/).
- For two events A and B, it is denoted by joint probability is denoted as P(A∩B).
**Random Variables**
- Real-valued variables whose possible values are determined by random experiments are called [random variables](https://www.geeksforgeeks.org/engineering-mathematics/random-variable/).
- The probability of finding such variables is the experimental probability.
## Bayes Theorem Applications
Bayesian inference is very important and has found application in various activities, including medicine, science, philosophy, engineering, sports, law, etc., and Bayesian inference is directly derived from Bayes theorem.
**Some of the Key Applications are:**
- **AI & Machine Learning** → Used in [Naïve Bayes classifiers](https://www.geeksforgeeks.org/machine-learning/naive-bayes-classifiers/) to predict outcomes.
- **Medical Testing** → Finding the real probability of having a disease after a positive test.
- **Spam Filters** → Checking if an email is spam based on keywords.
- **Weather Prediction** → Updating the chance of rain based on new data.
## **Theorem of Total Probability**
Let E1, E2,…., En be mutually exclusive and exhaustive events of a sample space S, and let E be any event that occurs with some Ei​. Then, prove that :
> P(E) = n∑i=1P(E/Ei) . P(Ei)
**Proof:**
> Let S be the sample space.
> Since the events E1, E2,…,En​ are mutually exclusive and exhaustive, we have:
>
> S = E1 ∪ E2 ∪ E3  ∪ . . . ∪ En and Ei ∩ Ej = ∅ for i ≠ j.
> Now, consider the event E: E = E ∩ S 
> Substituting S with the union of Ei's:
> ⇒ E = E ∩ (E1 ∪ E2 ∪ E3 ∪ . . . ∪ En)
> Using distributive law:
> ⇒ E = (E ∩ E1) ∪ (E ∩ E2) ∪ . . . ∪ (E ∩ En)
> Since the events Ei​ are mutually exclusive, the intersections E∩Ei are also mutually exclusive.Therefore:
>
> P(E) = P{(E ∩ E1) ∪ (E ∩ E2)∪ . . . ∪(E ∩ En)}
> ⇒ P(E) = P(E ∩ E1) + P(E ∩ E2) + . . . + P(E ∩ En)
> {Therefore, (E ∩ E1), (E ∩ E2), . . . ,(E ∩ En)} are pairwise disjoint}
>
> ⇒ P(E) = P(E/E1) . P(E1) + P(E/E2) . P(E2) + . . . + P(E/En) . P(En)  [by [multiplication theorem](https://www.geeksforgeeks.org/maths/multiplication-theorem/)]
> ⇒ P(E) = n∑i=1P(E/Ei) . P(Ei)
**➢Practice:**[Solved Examples](https://www.geeksforgeeks.org/maths/bayes-theorem-practice-questions/)
### **Also Check**
> **Bayes Theorem for Programmers-**
>
> - [Bayes Theorem in Artificial Intelligence](https://www.geeksforgeeks.org/artificial-intelligence/bayes-theorem-in-artificial-intelligence/)
> - [Bayes Theorem in Machine Learning](https://www.geeksforgeeks.org/data-science/bayes-theorem-in-machine-learning/)
> - [Bayes’ Theorem in Data Mining](https://www.geeksforgeeks.org/data-analysis/bayes-theorem-in-data-mining/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/maths/bayes-theorem/)

## GATE CS

- Subject: Engineering Mathematics
- Topic: Probability

> [!note] Related notes
>
> - [[Binomial Distribution]]
> - [[Conditional Probability]]
> - [[Covariance and Correlation]]
> - [[Exponential Distribution]]
> - [[Introduction to Probability]]
> - [[Law of Total Probability]]
> - [[Mean]]
> - [[Normal Distribution]]
> - [[Poisson Distribution]]
> - [[Probability Distribution]]
