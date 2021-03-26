+++
title = "Virasoro algebra from the free boson"
date = 2014-12-11
draft = false
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Usual physics derivations of the Virasoro algebra from the free boson in two dimensions usually use some sort of regularization procedure to compute the central charge. Following these notes I'd like to give a purely algebraic calculation of the central charge.



Let $A = \mathbf C[x_1, x_2, \dots]$ be the polynomial algebra in countably many generators. For an integer $k &gt; 0$, define a $k$-linear operator $a_k$ on $A$ by

$$ a_k = \frac{\partial}{\partial x_k}, \ k &gt; 0 $$

Similarly, for $k &lt; 0$ we define $a_k$ by multiplication:

$$ a_{-k} = k x_k, k &gt; 0 $$

For $k = 0$, we define $a_0$ to be multiplication by some fixed complex number (which by abuse of notation we also denote by $a_0$).


Lemma. We have the commutation relation $[a_m, a_n] = m \delta_{m+n}$ as linear operators on $A$.


For any monomial in the $a_k$, we define normal ordering $::$ to be the monomial obtained by reordering the terms so that the indices are increasing. (Mathematical interpretation: it is a section of the quotient map from the tensor algebra in the $a_k$ to the symmetric algebra, defined by lexicographic order.) For example,

$$ :a_j a_k:\ = \left\\{
\\begin{array}{rr}
a_j a_k, & j \leq k \\\\
a_k a_j, & j > k
\\end{array} \right. $$


Next we formally define a set of operators $L_k$ by

$$ L_k = \frac{1}{2}\sum_j :a_j a_{k-j}: $$


Proposition. The $L_k$ are well-defined as linear operators on $A$.


Proof. For sufficiently large $|j|$, at least one of $j$ or $k-j$ is positive, and hence $:a_j a_{k-j}:$ contains a differentiation (on the right). Since any element $f \in A$ is annihilated by all but finitely many of the differentiation operators $\partial_j$, the formal expression $L_k f$ contains only finitely many non-zero terms, and hence is well-defined.


Lemma. As operators on $A$, we have $[a_k, L_n] = k a_{k+n}$.


Theorem. As operators on $A$, we have

$$ [L_m, L_n] = (m-n) L_{m+n} + \frac{1}{12} (m^3-m) \delta_{m+n} $$


Proof. Fix $m,n$. For the sake of simplicity we will assume $m \neq n$ and $mn \neq 0$. (The other special cases can be treated by similar arguments.) By the same argument as the proof of the preceding proposition, for any fixed element $f \in A$ there exists some $N \gg 0$ such that

$$ [L_m, L_n]f = [L_m^N, L_n] f $$

where $L_m^N$ is the truncated operator

$$ L_m^N = \frac{1}{2}\sum_{|j| &lt; N} :a_j a_{m-j}: $$

Let us compute (noting that since $m \neq 0$, $:a_j a_{m-j}: = a_j a_{m-j}$)

\\begin{align}
  [L_m^N, L_n] &= \frac{1}{2} \sum_{|j| &lt; N} [a_j a_{m-j}, L_n] \\\\\\
  &= \frac{1}{2} \sum_{|j| &lt; N} (m-j) a_j a_{m+n-j} + \frac{1}{2} \sum_{|j| &lt; N}j a_{n+j} a_{m-j}
\\end{align}

Denote the two sums above by $S_1$ and $S_2$. It is clear that these should be related to the operator $L_{m+n}$, but to see the exact relation we will have to normal order the terms. Let's start with $S_1$. Note that $a_j a_{m+n-j}$ is already normal ordered, unless $j &gt; m+n-j$. Hence

\\begin{align}
  S_1 &= \frac{1}{2} \sum_{|j| &lt; N} (m-j) :a_j a_{m+n-j}: +  \frac{1}{2} \sum_{m+n\lt2j\lt2N} (m-j) [a_j, a_{m+n-j}] \\\\\\
&= \frac{1}{2} \sum_{|j| &lt; N} (m-j) :a_j a_{m+n-j}: +  \frac{\delta_{m+n}}{2} \sum_{m+n\lt2j\lt2N} j(m-j) \\\\\\
&= \frac{1}{2} \sum_{|j| &lt; N} (m-j) :a_j a_{m+n-j}: +  \frac{\delta_{m+n}}{2} \sum_{0\lt j\lt N} j(m-j)
\\end{align}


Similarly, we normal order the terms in $S_2$:

\\begin{align}
  S_2 &= \frac{1}{2} \sum_{|j| &lt; N}j :a_{n+j} a_{m-j}: -\frac{1}{2} \sum_{m-n\lt2j\lt2N}j [a_{m-j}, a_{n+j}] \\\\\\
&= \frac{1}{2} \sum_{|j| &lt; N}j :a_{n+j} a_{m-j}: -\frac{\delta_{m+n}}{2} \sum_{m\lt j\lt N}j (m-j) \\\\\\
&= \frac{1}{2} \sum_{|j| &lt; N}j :a_{n+j} a_{m-j}: -\frac{\delta_{m+n}}{2} \sum_{m\lt j\lt N}j (m-j) \\\\\\
&= \frac{1}{2} \sum_{|j| &lt; N}j :a_{n+j} a_{m-j}: -\frac{\delta_{m+n}}{2} \sum_{m\lt j\lt N}j (m-j)
\\end{align}


Hence we have

$$ S_1 + S_2 = \frac{1}{2} \sum_{|j| &lt; N} (m-j) :a_j a_{m+n-j}: +  \frac{1}{2} \sum_{|j| &lt; N}j :a_{n+j} a_{m-j}: + \frac{\delta_{m+n}}{2} \sum_{0\lt j\leq m} j(m-j)  $$

Now that everything is normal ordered, we can take the limit $N \to \infty$ without fear. After a simple cancellation, and explicitly summing the last term using well-known formulas for sums of powers of integers, we obtain:

$$ [L_m, L_n] = (m-n) L_{m+n} + \frac{1}{12} (m^3-m) \delta_{m+n} $$

For the usual conventions of the Virasoro algebra, this shows that this representation corresponds to central charge $c=1$.


Remark. If we tried to take the limit $N \to \infty$ in each of the terms $S_1, S_2$ separately, before taking their sum, we would obtain a formal infinite constant $\sum_{j} j(m-j)$. In any physics textbook, the author will simply zeta-regularize this sum to obtain a fininte result. However, the above calculation shows that this is not necessary. By taking care that each term in the expression $S_1+S_2$ was normal-ordered, before taking the limit, we obtain only finite constants with no need to regularize. Zeta regularization certainly has its uses (for example in rigorous definitions of functional determinants), but as the above calculation shows, it can also be an unnecessary crutch that obscures the underlying mathematical phenomena.


Remark. There is an analogous calculation which shows that one obtains a Virasoro representation from affine Lie algebras. Physically, this corresponds to the WZW model. Roughly, the generators of the affine Lie algebra behave as an infinite set of harmonic oscillators, similar to the Heisenberg algebra above. Sometime in the future I may write a sequel to this post giving the details of this calculation.
