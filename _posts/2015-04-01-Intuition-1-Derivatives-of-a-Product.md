---
title: 'Honing Intuition #1'
date: 2015-04-01 06:48:00 Z
categories:
- intuition
layout: post
---

### Derivatives of a Product

Factoring and adding zero in various ways in order to reveal new relationships within equations
is often a frustrating procedure, and rightfully so – how does adding "nothing" make any intuitive
sense whatsoever. More often than not, it makes proving something exceptionally convenient – since
all the proof cares about is proving something mathematically, but no necessarily intuitively.

Intuitive ideas often run the risk of ruining the abstract nature of mathematics, which can also
hamper the potential applications of whatever abstract concept we have in question. However, I think
that with enough thought (and considerably less rigor than that involved in a proof) any abstract
idea can be intuited in an abstract way.

When going through the proof for "Derivatives of a Product" ("Essential Calculus with Applications", Silverman) 
there was a very unintuitive curious step where my first thought was

> where did that come from?!?

The technique used was "adding zero", which is still something that takes me a while to recognize and almost
never think to apply. In this proof however, a few terms appeared out of thin air (but in reality, "thin air"
is all we added) and it was those very terms that were essential to the proof. In my opinion, these steps
are what make a "good proof" no different than the solution to a "good sudoku puzzle", though I digress.

Though most times you come across the "product rule" and you're either greeted with the proof, or nothing but
a few steps that are to be (easily) memorized and applied blinded. So, in an attempt to bring some "abstract
intuition" to myself I grazed a while over the 6-line proof and thought a bit.

The proof in question is:

$$
\begin{aligned}
F^\prime(x)
&= \lim_{x \to 0}
\frac{F(x + \Delta x) - F(x)}{\Delta x} = \lim_{x \to 0}
\frac{f(x + \Delta x)g(x + \Delta x) - f(x)g(x)}{\Delta x}
\\
&= \frac{f(x + \Delta x)g(x + \Delta x) - f(x)g(x + \Delta x) + f(x)g(x + \Delta x) - g(x)f(x)}{\Delta x}
\\
&= \lim_{x \to 0}
\frac{f(x + \Delta x) - f(x)}{\Delta x}
\lim_{x \to 0} g(x + \Delta x) +
\lim_{x \to 0} f(x)
\lim_{x \to 0} \frac{g(x + \Delta x) - g(x)}{\Delta x}
\end{aligned}
$$

The rest was handled by previously stated theorems. However, it was the middle equation above
where the intuition just dropped off for me. After looking at the equation for some time, I 
came to start thinking about "compensating" for changes in one function, but having to "account"
for both before I was done.

So, I decided to have two constants:

$$k = g(x + \Delta x) \hspace{1.5em} l = f(x)$$

then, these values can replace their respective counterparts in the middle equation, allowing
us to easily solve for the limit for both $f$ and $g$. So, we can solve for $f(x)$ as follows:

$$
\begin{aligned}
F^\prime(x) &= \lim_{x \to 0} \frac{f(x + \Delta x)k - f(x)k}{\Delta x} \\\
            &= k \lim_{x \to 0} \frac{f(x + \Delta x) - f(x)}{\Delta x}
\end{aligned}
$$

Now, at this point we have **solved** for $f^\prime(x)$, which leads us to the whole "compensation"
bit I stated earlier. We have already "accounted" for the limit of $f(x)$, and now all we need to
do is account for $g(x)$, hence why we need only make the constant for $g$ the value we assigned
to $l$.

$$
\begin{aligned}
F^\prime(x) &= \lim_{x \to 0} \frac{g(x + \Delta x)l - g(x)l}{\Delta x} \\\
            &= l \lim_{x \to 0} \frac{g(x + \Delta x) - g(x)}{\Delta x}
\end{aligned}
$$

While this has no concrete or real-world meaning, it allowed to see some "abstract" balancing between
the values of $f$ and $g$ as we were finding the derivative through a limit. You can see that we have
to account for the change in each value individually, and whichever one comes first is then "resolved"
when evaluating the second.

There's definitely more than few vague thoughts in here, and I hope to hone some of my definitions,
but I think there is merit in focusing on the "abstract intuition" of proofs like this.
