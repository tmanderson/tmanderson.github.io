---
title: References
date: 2018-05-15 18:35:00 Z
---

### Quaternions
Here's a [fantastic explanation](^1) of the complex _space_, which illustrates _why_ the complex values of a quaternion _appear_ to have no correlation to imaginary arithmetic (but, it in fact does and makes plenty of sense!):

$i,j,k$ are not imaginary numbers. Imaginary numbers arise only when you are talking about the complex plane $\mathbb{C}$, which has a very simple one to one mapping with the 2-D plane $\mathbb{R}^2$. Quaternions arise when you are talking about three dimensions, i.e. looking for solutions to $x2+1=0$ in 3-D.

If you want to get a physical picture, consider $i$ as rotating a vector or a line segment in 3-D by $90^\circ$ taking X-axis as the axis of rotation. Similarly, $j,k$ correspond to rotations about Y and Z axes respectively. This is similar to imaginary number $i$, which corresponds to a right angle rotation in the complex plane. Since in 3-D there are more than one independent axes of rotation possible, 3 to be precise, there are 3 quaternions.

Now, two $90^\circ$ rotations about X, Y or Z axis will take the vector $\mathbf{x}$ to its mirror image ($\mathbf{-x}$). So, $i^2=j^2=k^2=-1$.

A right angle rotation about X axis followed by an equal amount of rotation about Y corresponds to an overall effective rotation of $90^\circ$ about Z axis. So, $ij=k$. Similarly, you can physically verify the quaternion multiplication laws.

Do not try to think of their multiplication as arithmetic. They are compositions of rotation operations. If this looks too confusing, a little background in group theory will bring you enough mathematical maturity to be comfortable with these.

[^1]: https://math.stackexchange.com/q/296357
