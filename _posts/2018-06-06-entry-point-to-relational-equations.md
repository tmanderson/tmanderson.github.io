---
title: Entry Point To Relational Equations
date: 2018-06-06 16:03:00 Z
categories:
- thoughts
layout: post
---

# Entry-Point to Relational Equations

I've been actively working with linear algebra for the past year or so, and this whole time I've always had this deep-seeded feeling that I was still missing some fundamental detail to help explain _why_ multiple equations sharing the same variables can reveal an interrelation between the equations involved.

Recently, while viewing a fantastic [Herbert Gross lecture](https://www.youtube.com/watch?v=MfN1lqArwAg) there was an interesting point made at ~28:14 revealing something I saw as a great entry point to that intuitive relational definition I was looking for.

So, I started with Mr. Gross' example – solving two of the simplest equations:
$$
\begin{array}
  bb_1=x+y \\
  x=b_1-y \\
  \\ \\ \\
  x=b_1-\frac{b_1-b_2}{2}
\end{array}
\hspace{1.5em}
\begin{array}
  xx-y=b_2 \\ \\
  x-b_2=y \\
  b_1-y-b_2=y \\
  b_1-b_2=2y \\
  \frac{b_1-b_2}{2}=y \\
\end{array}
$$
My first thought when seeing the values here was that *x* and *y* both have the appearance of a fractional value. So, quickly intuition (reactionary) seemed to suggest that "maybe these are averages, relative to dimension, represent the weight of each variable". So, in order to see if this was true in the next dimension, I tried three equations in three unknowns:
$$
\begin{array}
  bb_1=x+y+z \\
  x=b_1-y-z \\ \\ \\ \\ \\ \\\\\\\\\\\\
  x=b_1-\frac{b_1-b_2}{2}-\frac{b_1-b_3}{2} \\
  2x=\bcancel{2b_1}-\bcancel{b_1}-b_2-\bcancel{b_1}+b_3 \\
  2x=b_2+b_3 \\
  x = \frac{b_2+b_3}{2}
\end{array}
\hspace{1.5em}
\begin{array}
  bb_2=x-y+z \\ \\
  y=x+z-b_2 \\
  y=(b_1-y\bcancel{-z})+\bcancel{z}-b_2 \\
  y = b_1-y-b_2 \\
  2y = b_1-b_2 \\
  y =\frac{b_1-b_2}{2} \\ \\\\\\\\\\\\\\\\\\
\end{array}
\hspace{1.5em}
\begin{array}
  bb_3=x+y-z \\ \\ \\ \\ \\ \\ \\
  z=x+y-b_3 \\
  z=(b_1\bcancel{-y}-z)+\bcancel{y}-b_3 \\
  z=b_1-z-b_3 \\
  2z=b_1-b_3 \\
  z=\frac{b_1-b_3}{2}\\\\\\\\\\
\end{array}
$$
My intuition was, unsurprisingly, incorrect. However, what is revealed here was pretty striking to me, while I feel that many who are much more familiar with mathematics than myself may see this as something _given_ or just plain _obvious_, for me this was the "intuitional" foundation I'd been looking for.

Notice the values for each variable are indicative of equations in which the variable exhibits _new information_, which is to say _the sign_ in equation 2 and 3 for *y* and *z* are different than in the other equations in which they appear.

From here you can see that in the *y* and *z* terms, the $b_n$ values correlate to the equations in which the _sign_ (eg. -,+) was different. Then we see the *x*-term is simply _defined_ in terms of the equations with which *y* and *z* were presented with their extra information.

We see that *x* couldn't have been defined any other way. In all three equations it has the _exact same_ value and nothing else to tell us otherwise. While the two other variables were, in retrospect, the obvious values that would reveal to us the _interrelations_ between the equations originall presented.
