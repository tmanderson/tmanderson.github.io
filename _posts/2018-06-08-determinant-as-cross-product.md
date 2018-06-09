---
title: Determinant As Cross Product
date: 2018-06-08 00:00:00 Z
---

If you're already familiar with determinants (and there's a whole lot of entry points to that one), or more specifically the computation of a determinant using [Laplacian Expansion](https://www.wikiwand.com/en/Laplace_expansion), there's a simple device to recall the cross-product operation (which is basically the same as representing the cross-product as the [_formal determinant_](https://www.wikiwand.com/en/Cross_product#/Matrix_notation)).

Given the following row vectors in $\mathbb{R}^3$
$$
\bold{v}_1=\begin{bmatrix}a & b & c\end{bmatrix} \hspace{1.5em} \bold{v}_2=\begin{bmatrix}d & e & f\end{bmatrix}
$$
Create a matrix whose rows are $v_1$ and $v_2$
$$
\bold{\text{M}}=\begin{bmatrix}\bold{v}_1 \\ \bold{v}_2\end{bmatrix} =\begin{bmatrix}a&b&c \\ d&e&f\end{bmatrix}
$$
and ignore each column, and compute the determinant for each sub-matrix[^1]
$$
\begin{bmatrix}\bcancel{a}&b&c \\ \bcancel{d}&e&f\end{bmatrix} \Rightarrow bf-ce \\
\begin{bmatrix}a&\bcancel{b}&c \\ d&\bcancel{e}&f\end{bmatrix} \Rightarrow -(af-cd)=cd-af\underline{\href{#note-on-the-sign-switch}{*}}  \\
\begin{bmatrix}a&b&\bcancel{c} \\ d&e&\bcancel{f}\end{bmatrix} \Rightarrow ae-bd \\
$$
Well, that's it. If we take each determinant and express the result as a new column vector
$$
\begin{bmatrix}bf-ce \\ cd-af \\ ae-bd \end{bmatrix}
$$
and there's our cross product of $\bold{v}_1$ and $\bold{v}_2$.

I prefer this, as it avoids any business about the non-generality of the cross-product (ie. it's only defined for $\mathbb{R}^3$) and enables the reinforcement of the far more general (and arguably useful) operation(s) of Laplacian Expansion. 

------

#### Note on the sign switch

If you're confused by the second term, recall that during the process of cofactor expansion (ie. Laplacian Expansion) you must alternate your signs for each cofactor
$$
\begin{bmatrix}
\bold{+} & \bold{-} & \bold{+} \\
\bold{-} & \bold{+} & \bold{-} \\
\bold{+} & \bold{-} & \bold{+} \\
\end{bmatrix}
$$
but in the cross-product's case, we just follow that of column 1 above, which would give us **+** for the first and last entry and **-** for the middle. Which all works out to the proper value.
