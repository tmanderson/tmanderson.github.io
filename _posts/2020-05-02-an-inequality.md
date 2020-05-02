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

$k,n \in \textbf{N}^*$ \hspace{1.5em} $n > k > 0$ \hspace{1.5em} $x \ge y > 0$

$$
\frac{y^kx^{n-k}}{(x+y)^n}\le\frac{(n-1)^{n-1}}{n^n}
$$

The smattering of variables makes appeals to the inductionist (particularly that $n$, $n-1$ business) view, but being a aesthetic reductionist, I've gotta make this problem easier on the eyes:

<ol>
	<li>$y^kx^{n-k}\le \frac{(x+y)^n(n-1)^{n-1}}{n^n}</li>
	<li>$n^n(y^kx^{n-k})\le(x+y)^n(n-1)^{n-1}$</li>
	<li>$\text{and since }n^n > (n-1)^{n-1}$ for all $n > 0$</li>
	<li>$\text{letting us focus on } (y^kx^{n-k})<(x+y)^n$</li>
	<li>$x^k(y^kx^{n-k}) < (x+y)^nx^k)$</li>
	<li>$y^kx^n < x^k(x+y)^n$</li>
	<li>$x^n < \frac{x^k(x+y)^n}{y^k}$</li>
	<li>$\frac{x^n}{(x+y)^n} < \frac{x^k}{y^k}$</li>
	<li>$\frac{x}{x+y} < \frac{x^{k/n}}{y^{k/n}}$</li>
</ol>

Now, we evaluate our relational cases for the two unbounded (positive) variables $x,y$:

<table>
<thead>
	<th>Case</th>
	<th>LHS</th>
	<th>RHS</th>
</thead>
<tbody>
  <tr>
    <td>$y = x$</td>
    <td>$\frac{x}{2x} = \frac{1}{2}$</td>
    <td>$\frac{x^{k/n}}{y^{k/n}} = 1$</td>
  </tr>
  <tr>
    <td>$y < x$</td>
    <td>$\frac{x}{x+y} < 1$</td>
    <td>$\frac{x^{k/n}}{y^{k/n}} > 1$<td>
  </tr>
  <tr>
    <td>$y > x$</td>
    <td>$\frac{x}{x+y} < \frac{1}{2}$</td>
    <td>$\frac{x^{k/n}}{y^{k/n}} < 1$</td>
  </tr>
</tbody>
</table>
$$

The last row has overlap, but one look at the LHS of the inequality, and we see that as $y$ gets larger, the inequality $\frac{x}{x+y}<\frac{x^{k/n}}{y^{k/n}}$ holds in the limit $y\to\infty$

