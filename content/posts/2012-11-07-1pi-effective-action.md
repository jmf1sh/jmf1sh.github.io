+++
title = "The 1PI effective action"
date = 2012-11-07
draft = false
tags = [
    "qft"
]
categories = [
    "physics"
]
+++

This post has been migrated from my old blog, the
[math-physics learning seminar](https://mathphysseminar.blogspot.com/).

In this post I'd like to try to understand the 1PI effective action that is
often of interest. Suppose we have a QFT in some bosonic field \\(\phi(x)\\) taking
values in a vector space (this is important). Then its vev
\\(\phi_{cl}(x) := \langle \phi(x) \rangle\\) is just an ordinary (but possibly
distributional) field on spacetime. The question is, what is the field equation
satisfied by \\(\phi_{cl}\\)? I.e., if we average over quantum effects by replacing
all fields by their vevs, what is the action that governs this (now completely
classical) theory? The 1PI effective action answers exactly this question.

Consider the generating functional

\\[ Z[J] = \int e^{-S[\phi]+\langle \phi, J \rangle} \mathcal{D}\phi \\]

Then for a given source \\(J\\), define the \\(J\\)-vev of \\(\phi(x)\\) to be

\\[ \phi_J(x) = \frac{\partial \log Z[J]}{\partial J}. \\]

Now let's take \\(\Gamma\\) to be the Legendre transform of \\(\log Z\\) with respect
to \\(J\\):

\\[ \Gamma[\phi_J] = \langle J, \phi_J \rangle - \log Z[J] \\]

Then we compute:

\\[ \frac{\partial \Gamma}{\partial \phi_J} = J + \frac{\partial J}{\partial \phi_J} \phi_J -\frac{\partial \log Z[J]}{\partial J} \frac{\partial J}{\partial \phi_J} = J. \\]


Now consider the situation without a background source, i.e. \\(J = 0\\). Then
\\(\phi_0 = \phi_{cl}\\) and we find

\\[ \frac{\partial \Gamma}{\partial \phi_{cl}} = 0 \\]

Hence, \\(\phi_{cl}\\) satisfies the Euler-Lagrange equations associated to the
functional \\(\Gamma\\). Note that from the Legendre transform, \\(\Gamma\\) takes
quantum effects (i.e. Feynman diagrams with loops) into account, even though
the field and the equations are purely classical!

By studying these equations, we might find instanton solutions (or solitons in Lorentz signature).

Now for the name. Some combinatorics and algebra (which I will skip!) show that
\\(\Gamma[\phi_{cl}]\\) is itself a generating functional for certain correlation
functions, then 1PI correlation functions:

\\[ \frac{\partial^n \Gamma}{\partial \phi(x_1) \cdots \partial \phi(x_n)} = \langle \phi(x_1) \cdots \phi(x_n) \rangle_{1PI}. \\]

The 1PI subscript means that the RHS is computed in perturbation theory by
summing over only the connection 1PI (1 particle irreducible) Feynman diagrams.

Warning: As usual, there are regularization issues, both in the UV and IR. UV
divergences can be solved by a cutoff (if we only care about effective field
theory), but IR divergences are much more technical. For this reason (and
others), it is sometimes preferable to try to understand the low energy dynamics
by studying the Wilsonian effective action. As the Wilsonian effective action
does not take IR modes into account, it can avoid many of the difficulties of
the 1PI effective action.
