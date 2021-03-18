---
title: "Gaussian integrals and Wick's theorem"
date: 2012-03-03 15:00:00Z
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


We saw in the last update that the generating function $Z[J]$ can be expressed as

$$ Z[J] = e^{\frac{1}{2} J \cdot A^{-1} J} $$

(at least as long as we've normalize things so that $Z[0] = 1$. Now the wonderful thing is that this is something we can compute explicitly:

$$ Z[J] = \sum_{n = 0}^{\infty} \frac{(\frac{1}{2} A^{-1}_{ij} J^i J^j)^n}{n!}

= \sum_{n=0}^\infty \frac{(A^{-1}_{ij} J^i J^j)^n}{2^n n!} $$


For example, in the one-dimensional case (taking $A = 1$) we get

$$ Z[J] = \sum_{n=0}^\infty \frac{J^{2n}}{2^n n!} $$

On the other hand, by the definition of the generating function we have

$$ Z[J] = \sum_{n=0}^\infty \frac{\langle x^n \rangle}{n!} J^n $$

Comparing coefficients, we find

$$ \frac{\langle x^{2n} \rangle}{(2n)!} = \frac{1}{2^n n!} $$

so that

$$ \langle x^{2n} \rangle = \frac{(2n)!}{2^n n!}. $$

Let's give a combinatorial description. Given $2n$ objects, in how many ways can we divide them into pairs? If we care about the order in which we pick the pairs, then we have

$$ {2n \choose 2}{2n - 2 \choose 2} \cdots {2n-(2n-2) \choose 2} = \frac{(2n)!}{2^n} $$

Of course, there are $n!$ ways of ordering the $n$ pairs, so after dividing by this (to account for the overcounting) we get exactly the expression for $\langle x^{2n} \rangle$. This is the first case of Wick's theorem.


Now consider the general multidimensional case. Given $I = (i_1, \cdots, i_{2n})$, we define a contraction to be

$$ \langle x^{j_1} x^{k_1} \rangle \cdots \langle x^{j_n} x^{k_n} \rangle $$

where $j_1, k_1, \cdots, j_n, k_n$ is a choice of parition of $I$ into pairs.


Theorem (Wick's theorem, Isserlis' theorem) The expectation value

$$ \langle x^{i_1} \cdots x^{i_{2n}} \rangle $$

is the sum over all full contractions. There are $(2n)!/ 2^n n!$ terms in the sum.


Proof This follows from our formula for the power series of the generating function. The reason is that the coefficient of  $J^I$ in $(\frac{1}{2} A^{-1}_{ij} J^i J^k)^n$ is exactly given by summing products of $A^{-1}_{ij}$ over partitions of $I$ into pairs, and the $n!$ in the denominator takes care of the overcounting.


Next up: perturbation theory and Feynman diagrams.