---
title: "Propositions Laws and Algebra"
subject: "Discrete Mathematics"
topic: "Propositional and First-Order Logic"
source: "https://www.geeksforgeeks.org/engineering-mathematics/mathematical-logic-introduction-propositional-logic-set-2/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Discrete Mathematics/Propositional and First-Order Logic"
tags:
  - gate/cs
  - subject/discrete-mathematics
  - topic/propositional-and-first-order-logic
---


> [!abstract] Propositions Laws and Algebra
> 
> **Subject:** `Discrete Mathematics` &nbsp;|&nbsp; **Topic:** `Propositional and First-Order Logic`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematical-logic-introduction-propositional-logic-set-2/)

---

# Propositions Laws and Algebra

Propositions, Laws, and Algebra is a branch of propositional logic that deals with logical statements, logical operations, and algebraic laws used to simplify and analyze logical expressions. It forms the basis of logical reasoning and is widely used in mathematics and computer science.
## **Laws of Algebra of Propositions**
Below are the laws of Algebra of Propositions:
### **Idempotent Law**
> - p ∨ p ≅ p
> - p ∧ p ≅ p
>
> The truth table of the [conjunction](https://www.geeksforgeeks.org/engineering-mathematics/proposition-logic/) and disjunction of a proposition with itself will equal the proposition.
### **Associative Law**
> - (p ∨ q) ∨ r ≅ p ∨ (q ∨ r)
> - (p ∧ q) ∧ r ≅ p ∧ (q ∧ r)
>
> Associative Law states that propositions also follow associativity and can be written as mentioned above.
### **Distributive Law**
> - p ∨ (q ∧  r) ≅ (p ∨ q) ∧ (p ∨ r)
> - p ∧ (q ∨  r) ≅ (p ∧ q) ∨ (p ∧ r)
>
> Distributive Law states that propositions also follow the distribution and can be written as mentioned above.
### **Commutative Law**
> - p ∨ q ≅ q ∨ p
> - p ∧ q ≅ q ∧ p
>
> It states that propositions follow commutative property i.e if a=b then b=a
### **Identity Law**
> - p ∨ T ≅ T
> - p ∨ F ≅ p
> - p ∧ T ≅ p
> - p ∧ F ≅ F
>
> where T is a Tautology, F is a Contradiction and p is a proposition.
### **De Morgan's Law**
In [propositional logic](https://www.geeksforgeeks.org/engineering-mathematics/proposition-logic/) and boolean algebra, De Morgan's laws are a pair of transformation rules that are both valid [**rules of inference**](https://www.geeksforgeeks.org/engineering-mathematics/rules-of-inference/). They are named after Augustus De Morgan, a 19th-century British mathematician. The rules allow the expression of conjunctions and disjunctions purely in terms of each other via negation. In formal language, the rules are written as:
> -
$$
\neg (p\wedge q) \equiv \neg p \vee \neg q
$$
> -
$$
\neg (p\vee q) \equiv \neg p \wedge \neg q
$$
### **Involution Law**
> - ~~p ≅ p
### **Complement Law**
> - p ∨ ~p ≅ T
> - p ∧ ~p ≅ F
> - ~T ≅ F
> - ~F ≅ T
>
> where T is a Tautology, F is a Contradiction and p is a proposition.
## **Special Conditional Statements**
As we know that we can form new propositions using existing propositions and logical connectives. New conditional statements can be formed starting with a conditional statement 
$$
p\rightarrow q
$$
. In particular, there are three related conditional statements that occur so often that they have special names.
- **Implication :** 
$$
p\rightarrow q
$$
- **Converse :** The converse of the proposition 
$$
p\rightarrow q
$$
  is 
$$
q\rightarrow p
$$
- **Contrapositive :** The contrapositive of the proposition 
$$
p\rightarrow q
$$
  is 
$$
\neg q\rightarrow \neg p
$$
- **Inverse :** The inverse of the proposition 
$$
p\rightarrow q
$$
  is 
$$
\neg p\rightarrow \neg q
$$
**Note :** It is interesting to note that the truth value of the conditional statement 
$$
p\rightarrow q
$$
is the same as it's contrapositive, and the truth value of the Converse of 
$$
p\rightarrow q
$$
is the same as the truth value of its Inverse. When two compound propositions always have the same truth value, they are said to be equivalent. Therefore,
-
$$
p\rightarrow q \equiv \neg q\rightarrow \neg p
$$
-
$$
q\rightarrow p \equiv \neg p\rightarrow \neg q
$$
**Example :** Let p represent “Today is Friday” and q represent “It is raining today”.
> - **Implication (p → q):** If today is Friday, then it is raining.
> - **Converse (q → p):** If it is raining, then today is Friday.
> - **Contrapositive (~q → ~p):** If it is not raining, then today is not Friday.
> - **Inverse (~p → ~q):** If today is not Friday, then it is not raining.
## **Implicit Use of Biconditionals**
In natural language, biconditional statements are not always written explicitly using “if and only if”. They are often expressed using “if, then” or “only if” statements where the converse is implied but not directly stated.
> **For example**, the statement “If you complete your homework, then you can go out and play” may also imply “You can go out and play only if you complete your homework.” Thus, such statements can sometimes represent a biconditional relationship.
## **Precedence Order of Logical Connectives**
Logical connectives are used to construct compound propoitions by joining existing propositions. Although parenthesis can be used to specify the order in which the logical operators in the compound proposition need to be applied, there exists a precedence order in Logical Operators. The precedence Order is-
>
$$
\begin{array}{ |c|c| }    \hline    Operator & Precedence \\    \hline     \neg & 1 \\    \hline        \wedge & 2 \\    \vee & 3 \\    \hline    \rightarrow & 4 \\    \leftrightarrow & 5 \\    \hline\end{array}
$$
Here, higher the number lower the precedence. 
## **Translating English Sentences**
In propositional logic, English sentences can be translated into logical expressions using propositional variables and logical connectives. This helps in analyzing statements and representing them in a precise mathematical form.
**Example:** “You can access the Internet from campus only if you are a computer science major or you are not a freshman.”
Let:
- p = “You can access the Internet from campus”
- q = “You are a computer science major”
- r = “You are a freshman”
Using logical connectives, the logical expression for the given statement is:
>
$$
p\rightarrow (q\vee \neg r)
$$
**Some Examples are**
### 1. Implication
If today is Friday, then it is raining.
- **Converse:** If it is raining, then today is Friday.
- **Contrapositive:** If it is not raining, then today is not Friday.
- **Inverse:** If today is not Friday, then it is not raining.
### 2. Translate English Sentence
"You can access the Internet from campus only if you are a computer science major or you are not a freshman."
- Logical Expression: 𝑝 - > (𝑞 ∨ ¬ 𝑟 )
- Where:
  - **p** = "You can access the Internet from campus."
  - **q** = "You are a computer science major."
  - **r** = "You are a freshman."
## **GATE CS Corner Questions**
Practicing the following questions will help you test your knowledge. All questions have been asked in GATE in previous years or in GATE Mock Tests. It is highly recommended that you practice them.
- [GATE CS 2009, Question 24](https://www.geeksforgeeks.org/questions/the-binary-operation-is-defined-as-follows-pqpqttttftftffft/)
- [GATE CS 2014 Set-1, Question 63](https://www.geeksforgeeks.org/questions/which-one-of-the-following-propositional-logic-formulas-is/)
- [GATE CS 2006, Question 28](https://www.geeksforgeeks.org/questions/a-logical-binary-relation-is-defined-as-follows/)
- [GATE CS 2002, Question 8](https://www.geeksforgeeks.org/questions/if-x-then-y-unless-z-is-represented-by/)
- [GATE CS 2000, Question 30](https://www.geeksforgeeks.org/questions/let-a-b-c-d-be-propositions-assume-that/)
- [GATE CS 2015 Set-1, Question 24](https://www.geeksforgeeks.org/questions/which-one-of-the-following-is-not-equivalent-to/)
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/mathematical-logic-introduction-propositional-logic-set-2/)

## GATE CS

- Subject: Discrete Mathematics
- Topic: Propositional and First-Order Logic

> [!note] Related notes
>
> - [[Consensus Theorem]]
> - [[Introduction to Propositional Logic]]
> - [[Predicates and Quantifiers Set 1]]
> - [[Predicates and Quantifiers Set 2]]
> - [[Propositional Equivalence]]
> - [[Rules of Inference]]
> - [[Some theorems on Nested Quantifiers]]
> - [[Binomial Coefficients]]
> - [[Cartesian Product of Two Sets]]
> - [[Classes of Functions]]
