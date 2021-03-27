---
title: "The basic idea of the quantum BV complex"
date: 2014-05-14
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/). This post was originally written by Dylan Butson.

Let \\(M\\) be an oriented \\(n\\)-dimensional manifold and \\(\mathfrak{X}^\bullet(M):=\Gamma(M,\wedge^{-\bullet} TM)\\), so that \\(\mathfrak{X}^\bullet(M)\\) is concentrated in non-positive degree. Let \\(\mu\in \Omega^n(M)\\) a volume form on \\(M\\). Then interior product with \\(\mu\\) gives an isomorphism \\(\vee\mu: \mathfrak{X}^k(M)\xrightarrow{\cong}\Omega^{n-k}(M)\\). From this, we induce a degree 1 differential \\(\Delta_\mu\\) on \\(\mathfrak{X}^\bullet(M)\\) from the de Rham differential \\(d\\) on \\(\Omega^\bullet(M)\\), defined by \\(\Delta_\mu= (\vee\mu)^{-1}\circ d\circ\vee\mu\\), making \\(\mathfrak{X}^\bullet(M)\\) into a cochain complex isomorphic to \\(\Omega^\bullet(M)[k]\\); in particular \\(H^k(\mathfrak{X})=H^{n+k}(\Omega)\\).

If \\(M\\) is compact and connected, then \\(H^0(\mathfrak{X})=H^n(\Omega)\\) is one dimensional, and upon fixing a basis to identify \\(H^0(\mathfrak{X})\xrightarrow{\cong}\mathbb{R}\\), the quotient map gives a map \\(\pi:C^\infty(M)\to \mathbb{R}\\). We have the following:

Proposition Let \\(1\in C^\infty(M)\\) be the constant function taking the value \\(1\\). Then \\([1]\in H^0(\mathfrak{X})\\) is nontrivial and after choosing it as a basis the resulting map \\(\pi:C^\infty(M)\to \mathbb{R}\\) is given by \\[ f\mapsto\frac{ \int_M f\mu}{\int_M \mu}\\] Proof Let \\(f\in C^\infty(M)\\) and suppose \\(f=\Delta_\mu(X)\\) for \\(X\in\mathfrak{X}^1(M)\\). Then \\[f\mu = f\vee \mu = \Delta_\mu(X)\vee\mu= d(X\vee \mu)\\] so that \\(f\mu\\) is exact and by Stokes' theorem integrates to \\(0\\) on \\(M\\). Thus all \\(f\in \text{Im } \Delta_\mu\\) integrate to zero against \\(\mu\\) on \\(M\\), so that the above map indeed descends to the quotient.

The above arguement also implies that were \\(1\in\text{Im }\Delta_\mu\\) then \\(\mu\\) would integrate to zero, contradicting that \\(\mu\\) is a volume form, so that \\([1]\in H^0(\mathfrak{X})\\) is indeed nontrivial. The map is thus well-defined, linear, and has the appropriate action on a basis so that it is correct as claimed. \\(\square\\)

This recovers the standard definition of the expectation of an observable in the path integral picture of quantum field theory. The upshot is that having formulated the integration homologically, we can hope to extend this homological definition of expectation to situations where the integral itself is not well defined.

Consider the case \\(M=V\\) a vector space, which in particular described the situation in coordinates on \\(M\\). We are interested in measures of the form \\(\mu=e^{-S/\hbar}\mu_0\\) where \\(\mu_0\\) is the Lesbesgue measure on \\(V\\), given by \\(\mu_0=dx^1\wedge ...\wedge dx^n\\). Let \\(X\in \mathfrak{X}^k(M)\\), we have:

\\[ \\begin{aligned} d(X\vee \mu) & = d(e^{-S/\hbar}(X\vee\mu_0)) \cr
&= de^{-S/\hbar}\wedge (X\vee \mu_0)+e^{-S/\hbar}d(X\vee \mu_0)\cr
&= -\frac{1}{\hbar}e^{-S/\hbar} dS\wedge (X\vee \mu_0) + e^{-S/\hbar} (\Delta_{\mu_0}X)\vee \mu_0 \cr
&= -\frac{1}{\hbar}e^{-S/\hbar} (dS\vee X)\vee \mu_0 + (\Delta_{\mu_0}X)\vee \mu\cr
&= \left(-\frac{1}{\hbar}dS\vee X + \Delta_{\mu_0}X \right)\vee \mu
\\end{aligned} \\]

so that \\[\Delta_\mu=\Delta_{\mu_0}-\frac{1}{\hbar}\iota_{dS}\\] Further, we can explicitly compute \\(\Delta_{\mu_0}\\): for \\(X\in\mathfrak{X}^k(M)\\) we have that \\(X=\sum_I X^I \partial_I\\), where the sum is over increasing \\(k\\)-tuples \\(I\subset\{1,...,n\}\\). We have

\\[ \\begin{aligned}
d(X\vee \mu_0) & = d\left( \sum_I X^I \partial_I\vee(dx^1\wedge ...\wedge dx^n)\right)\cr
& = d\left( \sum_I X^I (-1)^?dx^1\wedge ...\wedge \hat{dx^I} \wedge ...\wedge dx^n \right)\cr
& = \sum_I \sum_{i\in I} \partial_{x^i} X^I (-1)^?dx^i\wedge dx^1\wedge ...\wedge \hat{ dx^I}\wedge ...\wedge dx^n\cr
& = \left( \sum_i \partial_{x^i} (dx^i\vee X) \right) \vee \mu
\\end{aligned} \\]

so that \\[\Delta_{\mu_0} = \sum_i \partial_{x^i} \iota_{dx^i}\\] To be slightly more careful about the formal variable \\(\hbar\\) and allow the \\(\hbar\to 0\\) limit to be more clear, we refine our complex to be:
\\[ \mathfrak{X}^\bullet(M)[[\hbar]] \quad\quad\text{equipped with}\quad\quad \hbar \Delta_\mu= \hbar\Delta_{\mu_0} -\iota_{dS}\\]
Next, we restrict consideration only to polynomial observables (functions), and vector fields with polynomial coefficients, denoting the resulting complex \\(\text{PV}^\bullet\\). One can check that \\(H^0(\text{PV})\\) is still one dimensional, so that the above proposition holds and we maintain the integral intepretation of this cohomology.

Now, we can identify \\(\text{PV}^\bullet[[\hbar]]\\) with the graded-commutative graded algebra \\(\mathbb{K}[[x^1,...,x^n,\xi_1,...,\xi_n,\hbar]]\\) where \\(x^1,...,x^n,\hbar\\) are in degree 0 and \\(\xi_1,...,\xi_n\\) are in degree -1 as follows: \\[ x^i \mapsto x^i \quad\quad \partial_i\mapsto \xi_i\quad\quad \partial_i\wedge\partial_j\mapsto \xi_i\xi_j \quad\quad \hbar\mapsto \hbar\\] Under this identification, the map \\(\iota_{dx^i}:PV^k(M)\to \text{PV}^{k-1}(M)\\) is identified with \\(\partial_{\xi_i}\\). Now, we require our action function \\(S:M\to \mathbb{R}\\) also be polynomial, and further, that \\[S(x)=\frac{1}{2}\sum_{i,j} a_{ij}x^ix^j- b(x)\\] for \\(a_{ij}\\) symmetric and non-degenerate and for \\(b\in I^3\\) where \\(I=(x^1,...,x^n)\subset \mathbb{K}[[x^1,...,x^n]]\\), that is, \\(b(x)\\) a polynomial with no terms of degree less than 3. This implies that

\\[ \\begin{aligned}
\hbar\Delta_\mu & = \hbar\Delta_{\mu_0} -\iota_{dS} \cr
& = \hbar \sum_i \partial_{x^i} \iota_{dx^i} - \sum_i (\partial_{x^i}S) \iota_{dx^i} \cr
& = \hbar \sum_i \partial_{x^i} \iota_{dx^i} + \sum_i (\partial_{x^i}b) \iota_{dx^i} - \sum_{i,j}a_{ij}x^i\iota_{dx^j}
\\end{aligned} \\]

and under our identification this becomes \\[\hbar\Delta_\mu = \hbar \sum_i \partial_{x^i}\partial_{\xi_i} + \sum_i (\partial_{x^i}b)\partial_{\xi_i} - \sum_{i,j}a_{ij}x^i\partial_{\xi_j}\\] The computation of the degree 0 cohomology of a given polynomial \\(f\in\mathbb{K}[[x_1,...,x_n]]\\) under this differential is taken up in Gwilliam, Johnson-Freyd where it is shown the answer is precisely the Feynman diagram expansion for the expectation of \\(f\\) which we expect.
