---

title: "Introduction to Gaussian integrals"
date: 2012-03-03 09:00:00Z
draft: false
---

This post has been migrated from my old blog, the
[math-physics learning seminar](https://mathphysseminar.blogspot.com/).

As a warm-up for more serious stuff, I'd like to discuss Gaussian integrals
over $\mathbb{R}^d$. Gaussian integrals are the main tool for perturbative
quantum field theory, and I find that understanding Gaussian integrals in
finite dimensions is an immense aid to understanding how perturbative QFT
works. So let's get started.


The Basics
----------------------------------------------------------------------------

Let $A$ be some $d \times d$ symmetric positive definite matrix. We are
interested in the integral

$$ \int_{-\infty}^\infty \exp(-\frac{x \cdot Ax}{2}) dx. $$

Out of laziness, I will suppress the limits of integration and just write this as

$$ \int e^{-S(x)} dx. $$

where $S(x) = x \cdot Ax / 2$. Now for a function $f(x)$, we define the
expectation value $\langle f(x) \rangle$ to be

$$ \langle f(x) \rangle_0 = \int f(x) e^{-S(x)} dx $$

Occasionally, we might care about the normalized expectation value

$$ langle f(x) \rangle = \frac{\langle f(x) \rangle_0}{\langle 1 \rangle_0} = \frac{1}{\langle 1 \rangle_0} \int f(x) e^{-S(x)} dx. $$

We mostly care about asymptotics, so we will typically think of a function
$f(x)$ as being a polynomial (or Taylor series). So what we're really
interested in is

$$ \langle x^I \rangle = c\int x^I e^{-S(x)} dx, $$

where $I$ is a multi-index.


The Partition Function
----------------------------------------------------------------------------

Let us define $Z[J]$ by

$$ Z[J] = \int e^{-S(x) + J \cdot x} dx. $$


Now the great thing is that

$$ \langle x^I \rangle = \left. \frac{d^I}{dJ^I} \right|_{J = 0} Z[J], $$

so that once we know $Z[J]$, we can calculate anything. So let's try to compute
it. We have

$$
\\begin{align}
(Ax - J) \cdot A^{-1} (Ax - J) &= (Ax - J) \cdot (x - A^{-1} J) \\\\\\
&= x \cdot Ax - x \cdot J - J \cdot x + J \cdot A^{-1} J \\\\\\
&= x \cdot Ax - 2 x \cdot J + J \cdot A^{-1} J.
\\end{align}
$$
So we see that

$$ -\frac{1}{2} x \cdot A x + J \cdot x = \frac{1}{2} J \cdot A^{-1} J -\frac{1}{2} (x-A^{-1}J) \cdot A(x - A^{-1} J). $$

So, after a change of variales $x \mapsto x - A^{-1} J$ we find

$$ Z[J] = e^{\frac{1}{2} J \cdot A^{-1} J} Z[0]. $$

Now the argument in the exponential is

$$ \frac{1}{2} A^{-1}_{ij} J^i J^j $$

So we find that

$$
\langle x^i x^j \rangle = \frac{d^2}{dx^i dx^j} Z[J]|\_{J=0} = A\_{ij}^{-1}
$$

Now we are ready to prove Wick's theorem and discuss Feynman diagrams, which
we'll do in the next post.
