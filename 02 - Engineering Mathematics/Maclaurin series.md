---
title: "Maclaurin series"
subject: "Engineering Mathematics"
topic: "Calculus"
source: "https://www.geeksforgeeks.org/engineering-mathematics/maclaurin-series/"
source_site: GeeksforGeeks
type: gate-cs-note
topics: "Engineering Mathematics/Calculus"
tags:
  - gate/cs
  - subject/engineering-mathematics
  - topic/calculus
---


> [!abstract] Maclaurin series
> 
> **Subject:** `Engineering Mathematics` &nbsp;|&nbsp; **Topic:** `Calculus`
> **Source:** [GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/maclaurin-series/)

---

# Maclaurin series

Prerequisite - [Taylor theorem and Taylor series](https://www.google.com/amp/s/www.geeksforgeeks.org/taylors-theorem-and-taylor-series/amp/)
We know that formula for expansion of Taylor series is written as:
$$
f(x)=f(a)+\sum_{n=1}^{\infty}\frac{f^n(a)}{n!}(x-a)^n
$$
Now if we put a=0 in this formula we will get the formula for expansion of Maclaurin series. T
hus Maclaurin series expansion can be given by the formula -
$$
f(x)=f(0)+\sum_{n=1}^{\infty}\frac{f^n(0)}{n!}(x)^n
$$
**Maclaurin series expansion of some elementary functions :**
1. **Exponential function :**
$$
f(x)=e^x
$$
   Differentiating n times,
$$
f^n(x)=e^x.
$$
   So we get
$$
f^n(0)=1
$$
   Thus
$$
e^x = 1+\frac{x}{1!}+ \frac{x^2}{2!}+ \frac{x^3}{3!}+....+ \frac{x^{n-1}}{(n-1)!}+\frac{x^n}{n!}
$$
2. **f(x) = cos x**
$$
\cosx= 1-\frac{x^2}{2!}+\frac{x^4}{4!}-\frac{x^6}{6!}+
$$
   .....
3. **f(x) = sin x**
$$
\sinx = x-\frac{x^3}{3!}+\frac{x^5}{5!}-\frac{x^7}{7!}+....
$$
4. **f(x) = (ax + b)^m**
$$
(ax+b)^m=b^m[1+m(a/b)\frac{x}{1!}+m(m-1)(a/b)^2\frac{x^2}{2!}+m(m-1)(m-2)(a/b)^3\frac{x^3}{3!}+.....
$$
5. **f(x) = ln(1+x)**
$$
\ln(1+x)=x-\frac{x^2}{2}+\frac{x^3}{3}-\frac{x^4}{4}+\frac{x^5}{5}+.....+(-1)^{n-1}\frac{x^n}{n}+.....
$$
6. **f(x) = ln(1-x)**
$$
\ln(1-x)=-(x+\frac{x^2}{2}+\frac{x^3}{3}+\frac{x^4}{4}+\frac{x^5}{5}+.....+\frac{x^n}{n}+....)
$$
**Example-1:**
Find the first seven terms of f(x) = ln(sec x).
**Explanation :**
$$
f(x) = ln(\secx)
$$
$$
f(0) = ln(\sec0)=0
$$
Differentiating w.r.t. x,
$$
f'(x)= (1/secx).\secx.\tanx = \tan x
$$
$$
f'(0)= \tan 0 = 0
$$
$$
f''(x)= \sec^2x\scriptstyle\implies f’’(0) = \sec^20=1
$$
$$
f'’'(x)= 2\secx.\secx.\tanx=2sec^2x.tanx\scriptstyle\implies f’’’(0) = 0
$$
$$
f''''(x)= 4\sec^2x.\tan^2x+2\sec^4x\scriptstyle\implies f’’’’(0) = 0+2 = 2
$$
$$
f'’’’'(x)= 8\sec^2x.\tan^3x+16\sec4x.\tanx\scriptstyle\implies f’’’’’(0) = 0
$$
$$
f'’’’'’(x)= 16\sec^2x.\tan^4x+88\sec4x.\tan^2x+16\sec^6x\scriptstyle\implies f’’’’’’(0) = 16
$$
Thus we get the Maclaurin series as -
$$
f(x) = f(0)+f'(0).x/1!+f''(0).x^2/2!+f'''(0).x^3/3!+.... \text{upto 7 terms}
$$
$$
f(x)=ln(\secx)=0+1.x^2/2!+0+2.x^4/4!+0+16x^6/6!+....
$$
$$
f(x)=\frac{x^2}{2}+\frac{x^4}{12}+\frac{x^6}{45}+....
$$
**Example-2:**
Evaluate Maclaurin series for tan x.
**Explanation :**
$$
f(x) = \tan x, f(0)=0
$$
$$
f'(x) = \sec^2x
\scriptstyle\implies f'(0)=1
$$
$$
f''(x) = 2\sec^x.\secx.\tanx=2\sec^2x.\tanx=2(\tanx+\tan^3x)
\scriptstyle\implies f''(0)=0
$$
$$
f'''(x) = 2+8\tan^2x+6\tan^4x
\scriptstyle\implies f'''(0)=2
$$
$$
f''''(x) = 16\tanx+40\tan^3x+24\tan^5x
\scriptstyle\implies f''''(0)=0
$$
$$
f'''''(x) = 16\sec^2x+120\tan^2x.sec^2x+120\tan^4x\sec^2x
\scriptstyle\implies f'''''(0)=16
$$
Thus we get Maclaurin series as -
$$
\tanx=x+\frac{1}{3}x^3+\frac{2}{15}x^5+.......
$$
---

## Source

[GeeksforGeeks](https://www.geeksforgeeks.org/engineering-mathematics/maclaurin-series/)

## GATE CS

- Subject: Engineering Mathematics
- Topic: Calculus

> [!note] Related notes
>
> - [[Absolute Minima and Maxima]]
> - [[Application of Derivative]]
> - [[Cauchy’s mean value theorem]]
> - [[Chain Rule Derivative]]
> - [[Continuity]]
> - [[Differentiability]]
> - [[Euler's Formula]]
> - [[Finding the Various nth term of any polynomial sequence]]
> - [[Indefinite Integrals]]
> - [[Indeterminate Forms]]
