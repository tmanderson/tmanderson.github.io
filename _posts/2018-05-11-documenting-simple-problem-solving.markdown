---
title: Documenting Simple Problem Solving
date: 2018-05-11 14:23:00 Z
categories:
- problem solving
tags:
- math
- problems
- problem solving
- documenting
---

### Question 1

The integers 1-17 can be resorted so any adjacent pair sums to a perfect square. What is the sum of the first and last number of this resorted sequence?

Questions:

1. What is the largest perfect square we can make out of any two of these integers? **25**. 
2. We need to find two numbers that can _only_ sum to _one_ of the perfect squares we can represent.

**16**, **17**

Answer: 16+17=33

### Question 2

$xy + 1$ is divisible by 24
is $x + y$ also divisible by 24?

Two properties come to mind:

1. The product of two odd numbers is always odd
2. The sum of two odd numbers always even

So, **we know** $x + y$ is divisible by 24 _sometimes_ but could it be _always_?

What are the multiples of 24?

> 24, 48, 72, 96, 120, 144, 168, 192, 216

1. Since $xy+1$ is divisible by 24, we look for any multiple $m-1$ with integer factors
2. $96-1=95$ looks good (95 is divisible by 5!)
3.  $216-1=215$ looks good, for the same reason
4. So, we've found two multiples and both are factors of $5$ with $19$ and $43$
5. Now we've found two sets sharing a common multiple ($5$), let's say then that $x=5$ and our variable ("changable" value) is $y$
6. We can check this with the given equations $\frac{xy+1}{24}\in\mathbb{I}$[^1] and note that $x=5$ and $y$ varies as we find larger and larger multiples of 24
7. Noticed that $19+5=24\times1$ and $43+5=24\times2$
8. So, if the _first_ multiple with $5$ was $y_1=24\times1-5=19$
9. and the _second_ multiple with $5$ was $y_2=24\times2-5=43$
10. it may be that $n$ is our key to finding _every_ $y_n$
11. If that's the case then $y_n=24\times n-5$
12. We checked the next few cases for $n=3$ and $n=4$ which checked out
13. So, by induction, we claim that $y_n=24n-5$ is true for any $n$.

$$
\begin{gathered}
5 \times 19 + 1 =& 96 &= 24 \times 4 \cr
5 \times 43 + 1 =& 216 &= 24 \times 9 \cr
5 \times 67 + 1 =& 336 &= 24 \times 14 \cr
\end{gathered}
$$

| $n$  | $y_n$   |
| ---- | ------- |
| 1    | 24-5=19 |
| 2    | 48-5=43 |
| 3    | 72-5=67 |
| 4    | 96-5=91 |

$$
y_n=24n-5 \\\
y_n = \frac{24 \times (4 + 5(n-1))}{5} - 1
$$

[^1]: $\in\mathbb{I}$ just means that the result of the left side of $\in$ is an integer value (non-rational and positive). Also stated "is in the group of integers" which is any integer.