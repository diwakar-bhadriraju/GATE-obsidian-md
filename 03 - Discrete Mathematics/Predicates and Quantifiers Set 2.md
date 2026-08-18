---
title: "Predicates and Quantifiers Rules"
subject: "Discrete Mathematics"
topic: "Propositional and First-Order Logic"
source: "https://www.geeksforgeeks.org/engineering-mathematics/mathematical-logic-predicates-quantifiers-set-2/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Propositional and First-Order Logic"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/propositional-and-first-order-logic
---


> [!abstract] Predicates and Quantifiers Rules
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Propositional and First-Order Logic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematical-logic-predicates-quantifiers-set-2/)

---

# Predicates and Quantifiers Rules

Before diving into Predicates and Quantifiers Rules, you need to know about [predicates and quantifiers](https://www.geeksforgeeks.org/engineering-mathematics/mathematic-logic-predicates-quantifiers/) and [propositional logic](https://www.geeksforgeeks.org/engineering-mathematics/proposition-logic/) rules.
## **Logical Equivalences involving Quantifiers**
Two logical statements involving predicates and quantifiers are considered equivalent if and only if they have the same truth value, no matter which predicates are substituted into these statements, irrespective of the domain used for the variables in the propositions.
There are two very important equivalences involving quantifiers:
> 1. ∀x (P(x) ∧ Q(x)) ≡∀x P(x) ∧ ∀x Q(x)
> 2. ∃**x** (**P**(**x**) ∨ **Q**(**x**)) ≡ ∃**x P**(**x**) ∨ ∃**x Q**(**x**)
The question arises whether the equivalences would hold if the conjunction were replaced with disjunction in (1) and disjunction were replaced with the conjunction in (2).
The answer may seem like Yes, but on second thought, you would realize that the answer is No. To prove why they are not equivalent, we must understand what makes two statements equivalent, as explained in [Propositional Equivalences](https://www.geeksforgeeks.org/engineering-mathematics/mathematical-logic-propositional-equivalences/).
If after interchanging, they are equivalent, then,
> ∀x (P(x) ∨ Q(x)) ⇔ ∀x P(x) ∨ ∀x Q(x)
> and
> ∃x (P(x) ∧ Q(x)) ⇔ ∃x P(x) ∧ ∃x Q(x)
Both must be true.
Let us first check for ∀x (P(x) ∨ Q(x)) ⇔ ∀x P(x) ∨ ∀x Q(x). Is ∀x ((P(x) ∨ Q(x)) ⇒∀x P(x) ∨ ∀x Q(x) is true?
```
The answer is No.
```
**Proof:**
> - Suppose the hypothesis ∀x (P(x) ∨ Q(x)) is true.
> - This means there are certain x values for which P(x) is true and others where Q(x) is true.
> - It is also possible that for some x values, both P(x) and Q(x) are true.
> - But in any case, all x values must either satisfy P(x), Q(x), or both, since the hypothesis is true.
> - The conclusion (right-hand side) is true when the disjunction (P(x) ∨ Q(x)) is true.
From the reasoning above, we can see that P(x) is true for some values of x, and Q(x) is true for others. Thus, both "∀x P(x)" and "∀x Q(x)" are false, since neither of them is true for all values of x.
If P(x) and Q(x) are true for all x, then this equivalence would be true. However, in all other cases, it is false. Therefore,
> ∀x P(x) ∨ ∀x Q(x) ≡ F
According to our assumption, the hypothesis is true, but our conclusion turned out to be false. This cannot be true for a conditional; therefore, the conditional
> ∀x (P(x) ∨ Q(x)) ⇒ ∀x P(x) ∨ ∀x Q(x) is false.
Since one conditional is false, the complete biconditional is false.
Hence, ∀x(P(x) ∨ Q(x))
$$
\not\equiv
$$
 ∀xP(x) ∨ ∀xQ(x)
In a similar way, it can also be proved that
∃x(P(x) ∧ Q(x))
$$
\not\equiv
$$
 ∃xP(x) ∧ ∃xQ(x)
As an exercise, prove the above non-equivalence and also the equivalences involving quantifiers stated above. Remember to prove the bi-conditional and not just one conditional.
## **Negation of Quantifiers**
### Rules of Negations
When we negate statements with quantifiers, the type of quantifier is reversed. A negated universal quantifier turns into an existential quantifier, and a negated existential quantifier turns into a universal quantifier.
> ¬∀x P(x) ≡ ∃x ¬P(x)
- "It is not true that for all x, P(x) is true" is the same as "There exists an x such that P(x) is false."
Similarly:
> ¬∃x P(x) ≡∀x ¬P(x)
- "There does not exist an x such that P(x) is true" is the same as "For all x, P(x) is false."
### Example of Negating Universal Quantifier
Consider the statement : ∀x P(x) as
> "Every Computer Science Graduate has taken a course in Discrete Mathematics."
The above statement is a universal quantification. Here, P(x) is the statement "x has taken a course in Discrete Mathematics" and the domain of x is all Computer Science Graduates.
The negation of this statement is ¬∀x P(x) and can be expressed using an existential quantification as ∃x ¬P(x):
> "It is not the case that every computer science graduate has taken a course in Discrete Mathematics"
> or
> "There is a computer science graduate who has not taken a course in Discrete Mathematics".
## **Nested Quantifiers**
It is possible to use two quantifiers such that one quantifier is within the scope of the other one. In such cases the quantifiers are said to be nested. For example,
> ∀x ∃y (x + y = 0)
The above statement is interpreted as
> "For all x, there exists a y such that x + y = 0"
**Note:** The relative order in which the quantifiers are placed is important unless all the quantifiers are of the same kind, i.e., all are universal quantifiers or all are existential quantifiers.
### Also Check
> **GATE CS Corner Questions**
>
> Majority of the questions asked in GATE from Discrete Mathematics focus on Predicate Logic. Almost all of them involve quantifiers. Practicing the following questions will help you test your knowledge. All questions have been asked in GATE in previous years or in GATE Mock Tests.
>
> - [GATE CS 2012, Question 17](https://www.geeksforgeeks.org/questions/what-is-the-correct-translation-of-the-following-statement/)
> - [GATE CS 2013, Question 27](https://www.geeksforgeeks.org/questions/what-is-the-logical-translation-of-the-following-statement/)
> - [GATE CS 2013, Question 47](https://www.geeksforgeeks.org/questions/which-one-of-the-following-is-not-logically-equivalent/)
> - [GATE CS 2010, Question 30](https://www.geeksforgeeks.org/questions/suppose-the-predicate-fx-y-t-is-used-to/)
> - [GATE CS 2009, Question 26](https://www.geeksforgeeks.org/questions/which-of-the-above-two-are-equivalent/)
> - [GATE CS 2005, Question 36](https://www.geeksforgeeks.org/questions/let-px-and-qx-be-arbitrary-predicates-which-of/)
> - [GATE CS 2016 Set-2, Question 37](https://www.geeksforgeeks.org/questions/which-one-of-the-following-well-formed-formulae-in-predicate/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematical-logic-predicates-quantifiers-set-2/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Propositional and First-Order Logic

> [!note] Related notes
>
> - [[Consensus Theorem]]
> - [[Introduction to Propositional Logic]]
> - [[Predicates and Quantifiers Set 1]]
> - [[Proposition Laws and Algebra]]
> - [[Propositional Equivalence]]
> - [[Rules of Inference]]
> - [[Some theorems on Nested Quantifiers]]
> - [[Binomial Coefficients]]
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
