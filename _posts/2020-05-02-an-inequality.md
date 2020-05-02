---
title: An Inequality (from Twitter)
date: 2020-05-02 14:20:00 Z
categories:
- problem solving
tags:
- math
- problems
- problem solving
- documenting
- inequality
---

$k,n \in \bold{N}^*$ \hspace{1.5em} $n > k > 0$ \hspace{1.5em} $x \ge y > 0$
\\

$$
\frac{y^kx^{n-k}}{(x+y)^n}\le\frac{(n-1)^{n-1}}{n^n}
$$

The smattering of variables makes appeals to the inductionist (particularly that $n$, $n-1$ business) view, but being a aesthetic reductionist, I've gotta make this problem easier on the eyes:

$$
\begin{enumerate}
	\item $y^kx^{n-k}\le \frac{(x+y)^n(n-1)^{n-1}}{n^n}$
	\item $n^n(y^kx^{n-k})\le(x+y)^n(n-1)^{n-1}$
	\item $\text{and since }n^n > (n-1)^{n-1}$ for all $n > 0$
	\item $\text{letting us focus on } (y^kx^{n-k})<(x+y)^n$
	\item $x^k(y^kx^{n-k}) < (x+y)^nx^k)$
	\item $y^kx^n < x^k(x+y)^n$
	\item $x^n < \frac{x^k(x+y)^n}{y^k}$
	\item $\frac{x^n}{(x+y)^n} < \frac{x^k}{y^k}$
	\item $\frac{x}{x+y} < \frac{x^{k/n}}{y^{k/n}}$
\end{enumerate}
$$

Now, we evaluate our relational cases for the two unbounded (positive) variables $x,y$:
\\

$$
\begin{tabular}{| l  c  c |}
Case & LHS & RHS \\
$y = x$ & $\frac{x}{2x} = \frac{1}{2}$ & $\frac{x^{k/n}}{y^{k/n}} = 1$ \\
$y < x$ & $\frac{x}{x+y} < 1$ & $\frac{x^{k/n}}{y^{k/n}} > 1$ \\
$y > x$ & $\frac{x}{x+y} < \frac{1}{2}$ & $\frac{x^{k/n}}{y^{k/n}} < 1$
\end{tabular}
$$

The last row has overlap, but one look at the LHS of the inequality, and we see that as $y$ gets larger, the inequality $\frac{x}{x+y}<\frac{x^{k/n}}{y^{k/n}}$ holds in the limit $y\to\infty$

