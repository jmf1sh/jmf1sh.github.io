---
title: "Euler beta function and Dirichlet distribution"
date: 2018-07-10
draft: false
---

Let's remind ourselves how about the Euler beta function, defined as

\\[ B(x,y) = \int_0^1 t^{x-1} (1-t)^{y-1} dt. \\]

First, we will express \\(B(x,y)\\) in terms of the more familiar Gamma function,
defined as

\\[ \Gamma(x) = \int_0^\infty t^{x-1} e^{-t} dt. \\]

First, we have

\\[ \Gamma(x) \Gamma(y) = \int_0^\infty \int_0^\infty s^{x-1} t^{y-1} e^{-s-t} ds dt \\]

Now, suppose we have a multinomial distribution over \\(k\\) classes with probabilites \\(p_1, \ldots, p_k\\). In for \\(n\\) trials, the probability of observing \\(k_i\\) instances of class \\(i\\) is given by

\\[ P(n_1, \ldots, n_k) = {n \choose n_1, \ldots, n_k} \prod_i p_i^{n_i} \\]

Suppose that initially the probabilities \\(p_i\\) are unknown, and we wish to infer them from
a given observation of \\(n\\) trials. Using a conjugate prior, we can take the unknown probabilites
to follow the Dirichlet distribution

\\[ P(p_1, \ldots, p_k) = C_\alpha \prod_i p_i^{\alpha_i-1} \\]

(where the normalization constant \\(C_\alpha\\) can be computed explicitly in terms of the
generalized beta function, or equivalently in terms of the Gamma function).
Using Bayes' theorem we have

\\[
\\begin{aligned}
P(\alpha | n_1, \ldots, n_k) &= C P(n_1, \ldots, n_k | \alpha) P(\alpha) \cr
&= C' \prod_i p_i^{n_i+\alpha_i-1}
\\end{aligned}
\\]

This gives a new Dirichlet distribution with \\(\alpha_i\\) replaced by \\(\alpha_i+n_i\\).
Taking expectation values of the posterior we have

\\[E[p_i] = \frac{n_i+\alpha_i}{n+\sum_i \alpha_i}\\].

Taking the Jeffreys prior \\(\alpha_i = 1/2\\), we have finally

\\[E[p_i] = \frac{n_i+1/2}{n+n/2}\\].

Note that this assigns a non-zero value to \\(p_i\\) even in the case that \\(n_i = 0\\)!

For comparison, consider taking instead the estimate from maximum likelihood. We have

\\[ \log L(p, n) = C + \sum_i n_i \log p_i. \\]

Maximizing subject to the constraints \\(\sum_i p_i = 1\\), we have

\\[ n_i / p_i = \lambda \\]

for some Lagrange multiplier \\(\lambda\\), for all \\(i\\). Hence we obtain

\\[ p_i = n_i / n \\]

and note that in this case, we assign zero probability to any class which is not observed.
So we see that the expected distribution derived though Bayesian inference is more
conservative than maximum likelihood, in the sense that zero probabilities are assigned
only in the limit of infinitely many trials.