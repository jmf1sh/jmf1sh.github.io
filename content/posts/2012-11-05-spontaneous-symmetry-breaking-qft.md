---
title: "Spontaneous symmetry breaking in QFT"
date: 2012-11-05
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


In this post I want to try to understand symmetry breaking and the origin of the moduli space of vacua. Most of this can be found in the lectures by Witten in vol. 2 of Quantum Fields and Strings.



Non-Example: Quantum Mechanics

The main point of confusion for me is that my quantum intuition comes from ordinary quantum mechanics. However, this turns out to be incredibly misleading because for most reasonable quantum mechanical systems, spontaneous symmetry breaking cannot occur. In fact, we'll see that even in field theory, the question of whether spontaneous symmetry breaking can occur is intimately related to the geometry of spacetime. Since quantum mechanics is QFT in $0+1$ dimensions (i.e., the spatial part of spacetime is just a point), spontaneous symmetry breaking is forbidden.


Consider a particle in one spatial dimension, with Hamiltonian

$$ H = -\frac{\hbar^2}{2} + (a^2-x^2)^2. $$

The classical ground states are given by the stationary solutions $x(t) = \pm a$. Hence we might expect that the quantum Hamiltonian has a degenerate ground state, i.e. the eigenspace of the lowest eigenvalue has dimension greater than one. However, this is not the case!


Sketch of proof: Define a function $E(\phi)$ on the unit sphere in $L^2(\mathbb{R})$. If $\phi$ is a global minimum, then it necessarily satisfies $H\psi = E_0 \phi$ where $E_0$ is the lowest eigenvalue of $H$. On the other hand, $E(\phi) = E(|\phi|)$ so $|\phi|$ is also a global minimum, hence satisfies $H|\phi| = E_0|\phi|$. This equation is elliptic, so by elliptic regularity $|\phi|$ must be at least $C^1$, and hence $\phi(x)$ has constant phase, so we might as well take $\phi(x)$ to be real and positive. Any other ground state $\psi$ would have these properties, and hence $(\phi,\psi) \neq 0$. Hence the eigenspace is 1-dimensional and the ground state is not degenerate.


Now by the Stone-von Neumann theorem, there is a unique irreducible representation of the canonical commutation relations on a separable Hilbert space, and by the argument above there is a unique (up to scale) vector $|\Omega\rangle$ which is the ground state of the Hamiltonian, called the vacuum vector. So for QM, we find a unique representation on $\mathcal{H}$ together with a unique vacuum vector $|\Omega\rangle \in \mathcal{H}$. The point I want to stress here is that the Poisson algebra of observables together with the Hamiltonian determine the data $\mathcal{H}, |\Omega\rangle)$ in an essentially unique way, so there is no ambiguity in quantization and no further choices need to be made.



QFT in Finite Volume


Now we'll argue that a similar symmetry breaking phenomenon should be expected whenever the spatial part of spacetime has finite volume. We'll have to use formal path integral arguments, so of course this won't be totally rigorous. Suppose we have two representations $\mathcal{H}_\pm$ with vacua $|\Omega\rangle_\pm$. Then we consider the direct sum $\mathcal{H} = \mathcal{H}_+ \oplus \mathcal{H}_-$. Then by construction, we should have

$$ (\Omega_+, e^{-tH} \Omega_-) = 0 $$

since $|\Omega\rangle_\pm$ are orthogonal eigenstates of $H$. On the other hand, we can compute this inner product using the Feynman-Kac formula. The semi-classical approximation to the path integral yields

$$ (\Omega_+, e^{-tH} \Omega_-) = C \exp\left(- \frac{S(t) V}{\hbar} \right) $$

Where $S(t)$ is the classical least action and $V$ is the volume of space. If $V &lt; \infty$, the right hand side is non-zero, contradicting our assumptions! Hence the vacuum is non-degenerate. So we find that QFT with finite spatial volume is much like QM, at least as far as symmetry breaking is concerned.


Note that this argument is essentially just a formal manipulation of the path integral, so you should expect a result of this form independent of the particular regularization scheme used to define the path integral.


QFT in Infinite Volume

Now we consider the case $V = \infty$, i.e. a non-compact space. Then the preceding argument fails spectacularly, as does the Stone-von Neumann theorem. So there is no guarantee of a unique irreducible representation of the algebra, and no guarantee of a unique vacuum vector.

So we see that the situation is significantly more complicated. We can expect a moduli space $\mathcal{M}$ of vacua of the theory, and the low energy effective theory is described by a $\sigma$-model with target $\mathcal{M}$. I'll try to discuss this in more detail in follow-up posts.
