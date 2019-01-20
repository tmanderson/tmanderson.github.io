---
title: The Secret Tiling Problem
date: 2019-01-19 20:20:00 Z
categories:
- problem solving
tags:
- math
- problems
- problem solving
- documenting
---

This following problem was phrased to me as

> There is a 2^N by 2^N grid of tiles. Each tile is white on one side, and black on the other. The tiles are flipped randomly, so that some are flipped to white, and some are flipped to black.
> There are two people. Each one will be brought in to look at the tiles one by one.
> The first person will be brought in, and the weirdos running the experiment will pick one tile at random.
> Then, that first person will be allowed to flip one tile over.
> Then they will be dismissed.
> Then the second person will be brought in, and they will have to choose the tile that the weirdos picked.
> Before this happens, the two participants will have time to figure out how they're gonna choose the right tile.

## Defining the Problem

We define the grid $G$ in initial state $S_0 $ as
$$
G(n, S_0)=\{\{s_0,s_1,\dots,s_{2n} \}:s\in S_0\}
$$
Each of the $2^{4n}$ cells (or tiles), $s_n$ is assigned a value of either 0 (=black) or 1 (=white), defined with the given initial state $S_0$.

We will represent the _entire_ state of $G$ with a _binary representation_. For example, we can represent a 2x2 grid as
$$
G(1,\{0, 1, 1, 1\})=
\begin{bmatrix}
0 & 1 \\
1 & 1
\end{bmatrix}
= {0,1,1,1}=0111=7
$$
We define a transition $T$ on $G$ as
$$
T:[0,2^{4n}]\to[0,2^{2n}]
$$
Where $T$ can only modify the state of _one_ cell. So, $T$ must transition $G$ in any one of $2^{4n}$ initial states into a space containing the _cells_ of $G$.

The transition $T$ can only change the state _of a single cell_. For example, the following would be a _valid_ transition (for $G(1)=2\times2$ grid)
$$
\{1,1,1,1\}\Rightarrow\{0,1,1,1\} \hspace{1em} \color{green}\checkmark
$$
While the following is _not valid_
$$
\{1,1,1,1\}\Rightarrow\{0,0,1,1\} \hspace{1em} \color{red}\times
$$

| n    | Permutations of $S_0$  | Cells in $G(n)$   |
| ---- | ---------------------- | ----------------- |
| 1    | $2^{4(1)}=2^4=16$      | $2^{2(1)}=2^2=4$  |
| 2    | $2^{4(2)}=2^8=256$     | $2^{2(2)}=2^4=16$ |
| 3    | $2^{4(3)}=2^{12}=4096$ | $2^{2(3)}=2^6=64$ |

## The Problem

Is there any way to represent _one particular_ cell (the secret) within this grid with a single transition $T:S_0\to S_1$? 

Our solution must take $2^{4n}$ possible values (the possible initial states) and selectively convert them into one of $2^{2n}$ values (the index of the chosen tile). So, what we need to show is, given any possible initial state $S_0$, we can provide a valid transition $T$ to represent any cell within the grid.

With our initial state $S_0$ and the (secret) chosen cell $C$, we can respecify our transition signature
$$
T:
\underbrace{[0,2^{4n}]}_{S_0}
\to
\underbrace{[0,2^{2n}]}_\text{C}
$$

### Base Case $G(1, S_0)$

For the simplest non-trivial case, we consider the case where n = 1, C = 1. That is, a 2x2 grid with the **first cell** chosen as “the secret”.

All of the possible permutations for the initial state, $S_0$ of this grid are
$$
\begin{align}
\begin{bmatrix}
0 & 0 \\ 0 & 0
\end{bmatrix}
\begin{bmatrix}
0 & 0 \\ 0 & 1
\end{bmatrix}
\begin{bmatrix}
0 & 0 \\ 1 & 0
\end{bmatrix}
\begin{bmatrix}
0 & 0 \\ 1 & 1
\end{bmatrix}
&= 0,1,2,3
\\
\begin{bmatrix}
0 & 1 \\ 0 & 0
\end{bmatrix}
\begin{bmatrix}
0 & 1 \\ 0 & 1
\end{bmatrix}
\begin{bmatrix}
0 & 1 \\ 1 & 0
\end{bmatrix}
\begin{bmatrix}
0 & 1 \\ 1 & 1
\end{bmatrix}
&= 4,5,6,7
\\
\begin{bmatrix}
1 & 0 \\ 0 & 0
\end{bmatrix}
\begin{bmatrix}
1 & 0 \\ 0 & 1
\end{bmatrix}
\begin{bmatrix}
1 & 0 \\ 1 & 0
\end{bmatrix}
\begin{bmatrix}
1 & 0 \\ 1 & 1
\end{bmatrix}
&=8,9,10,11
\\
\begin{bmatrix}
1 & 1 \\ 0 & 0
\end{bmatrix}
\begin{bmatrix}
1 & 1 \\ 0 & 1
\end{bmatrix}
\begin{bmatrix}
1 & 1 \\ 1 & 0
\end{bmatrix}
\begin{bmatrix}
1 & 1 \\ 1 & 1
\end{bmatrix}
&=12,13,14,15
\end{align}
$$
And we will define our transition as
$$
T:[0,2^{4}]\to [0, 2^{2}]
$$

### Encoding $S_0$ (mod $2^{2n}$)

In order to meet the constraints of our transition, we need a way to restrict our output within the range of total cells ($2^{2n}$). We will do this by using the modulus of the total number of cells.

To do this, we encode all possible states in their binary representation, mod 4:

- 0, 4, 8, 12 = 0 (cell 1)
- 1, 5, 9, 13 = 1 (cell 2)
- 2, 6, 10, 14 = 2 (cell 3)
- 3, 7, 11, 15 = 3 (cell 4)

While this does account for our specified transition’s range $[0,2^2]$, we need to see if it is possible to create a transition for _any_ of these initial states, $S_0$.

The following table shows _all_ possible values of our transition for any given $S_0$ for our 2x2 grid

| $S_0$     | T($S_0$, C)   | mod 4      |
| --------- | ------------- | ---------- |
| {0,0,0,0} | 1, 2, 4, 8    | 1, 2, 0, 0 |
| {0,0,0,1} | 0, 3, 5, 9    | 0, 3, 1, 1 |
| {0,0,1,0} | 0, 3, 6, 10   | 0, 3, 2, 2 |
| {0,0,1,1} | 1, 2, 7, 11   | 1, 2, 3, 3 |
| {0,1,0,0} | 0, 5, 6, 12   | 0, 1, 2, 0 |
| {0,1,0,1} | 1, 4, 7, 13   | 1, 0, 3, 1 |
| {0,1,1,0} | 2, 4, 7, 14   | 2, 0, 3, 2 |
| {0,1,1,1} | 3, 5, 6, 15   | 3, 1, 2, 3 |
| {1,0,0,0} | 0, 1, 2, 4    | 0, 1, 2, 0 |
| {1,0,0,1} | 1, 8, 11, 13  | 1, 0, 3, 1 |
| {1,0,1,0} | 2, 8, 9, 14   | 2, 0, 1, 2 |
| {1,0,1,1} | 3, 9, 10, 15  | 3, 1, 2, 3 |
| {1,1,0,0} | 4, 8, 13, 14  | 0, 0, 1, 2 |
| {1,1,0,1} | 5, 9, 12, 15  | 1, 1, 0, 3 |
| {1,1,1,0} | 6, 10, 12, 15 | 2, 2, 0, 3 |
| {1,1,1,1} | 7, 11, 13, 14 | 3, 3, 1, 2 |

The table reveals to us that _it is not possible_ to represent a single chosen cell for any possible initial state. The second column shows that all values mod 10 (0-15) are not possible with a single valid transition (ie. Flipping a single tile). The same goes for the third column, mod 4 (0-3).

As we’re looking to encode _a single intelligible value_ from any given initial state, the previous example shows that we cannot represent all four grid cells for _any possible initial state_ $S_0 $. 

This shows that there is at least one grid that cannot encode its secret cell. $\square$