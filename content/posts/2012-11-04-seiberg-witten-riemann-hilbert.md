+++
title = "Seiberg-Witten theory and the Riemann-Hilbert problem"
date = 2012-11-04
draft = false
tags = [
    "qft"
]
categories = [
    "physics"
]
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


 References:

    Introduction to Seiberg-Witten theory and its stringy origin
    Seiberg-Witten and follow-up

The Classical Moduli Space of Vacua

For definiteness, we'll consider just the case of $SU(2)$ considered by Seiberg and Witten. There is a scalar Higgs field $\phi$. The classical vacua of the theory are given by the absolute minima of the potential energy, which in this case is proportional to

$$ \mathrm{Tr}[\phi, \phi^\dagger]^2 $$

Hence at the minimum, $[\phi,\phi^\dagger]=0$ and $\phi$ is diagonalizable. Hence the classical moduli space of vacua $\mathcal{M}\_{cl}$ is just $\mathbb{C}$, with complex coodinate $a$, corresponding to the Higgs field

$$ \phi = \left( \\begin{array}{rr}a & 0 \\ 0 & -a\\end{array} \right) $$

Actually, due to gauge invariance, it is better to introduce another copy of the complex plane $\mathcal{B}$ with local coordinate $u = \frac{1}{2} Tr \phi^2 = a^2$. Then we can think of $\mathcal{M}\_{cl}$ as a branched cover of $\mathcal{B}$, with $a$ a (local) choice of square root of $u$.


The goal is to understand the low energy effective theory. We introduce a cutoff $\Lambda$ to define the quantum theory, and integrate out all degrees of freedom except for the low momentum modes of $\phi$ (in particular, we integrate out the gauge field d.o.f.). The result is a $\sigma$-model with target $\mathcal{M}\_{cl}$. The kinetic term of the $\sigma$-model is governed by the metric on $\mathcal{M}\_{cl}$, hence the low energy effective action determines a metric on $\mathcal{M}\_{cl}$.


We'll see that 1-loop calculations introduce monodromy, so that in the quantum theory, "functions" on $\mathcal{M}\_{cl}$ are actually sections of non-trivial bundles over $\mathcal{M}\_{cl}$, and furthermore that the metric receives corrections from instantons (or BPS states). So what we really would like to understand/construct is the quantum moduli space of vacua $\mathcal{M}$, which will be some non-trivial modification of $\mathcal{M}\_{cl}$. The key to the Seiberg-Witten solution is that susy allows us to reduce the problem to finding a specified set of holomorphic functions (in the $u$ coordinate$ satsfying certain monodromies, and that once we know the monodromies the solution is given to us by the Riemann-Hilbert correspondence.


The Riemann-Hilbert Correspondence

Let $X$ be $\mathbb{P}^1$ with punctures at the points $z_1, \ldots, z_n$. Let $U$ be the universal cover of $X$ and let $G$ be the fundamental group of $X$ (pick some basepoint away from the punctures). A set of monodromy matrices is exactly what is needed to specify a representation $V$ of $G$. Since $U / G = X$, we can form the associated bundle $E = U \times_G V$ over $X$. The (trivial) $G$-connection on $U \to X$ induces a flat connection $\nabla$ on $E$. This gives a map from representations of $G$ to flat connections on $X$.


Conversely, given a flat connection on $X$, the monodromy about the punctures determines a representation of $G$. Hence monodromy is a map from flat connections on $X$ to representations of $G$. The Riemann-Hilbert correspondence is that these two maps are bijections, modulo the natural notions of equivalence (conjugacy and gauge transformations).


Gross Overview of the Seiberg-Witten Approach

We are now ready to sketch the "big picture" idea of Seiberg and Witten, which applies not only to their $N=2, d=4$ example but also to certain other compactifications of the $N=1, d=6$ theory (in particular, the one considered by Gaiotto-Moore-Neitzke).


As discussed above, the theory will have a classical moduli space of vacua $\mathcal{M}$, which turns out to be a complex manifold (or variety, and possibly with singularities). We'll let $u$ be an abstract local complex coordinate on $\mathcal{M}$. Supersymmetry then tells us that the main quantities we are interested in (to compute the low energy effective action) are holomorphic in $u$ (away from the singularities/punctures of $\mathcal{M}$!). The general outline is as follows:


    Identify functions $f_i(u)$ which by susy are holomorphic in $u$.
    Compute the 1-loop corrections to $f_i(u)$.
    Compute monodromies of the corrected $f_i(u)$.
    Find the desired $f_i(u)$ by solving the Riemann-Hilbert problem for these monodromies.

Now, to be more clear, it is a consequence of susy that the renormalized quantities $f_i(u)$ are given schematically by

$$ f_{i, \mathrm{ren}}(u) = f_{i, \mathrm{cl}}(u) + f_{i,1}(\frac{u}{\Lambda}) + \sum_{k=0}^\infty c_{i,k} \left(\frac{\Lambda}{u} \right)^k $$


Here, $f_{i,\mathrm{cl}}(u)$ is the classical function, $f_{i,1}(u)$ is the one-loop correction, and the terms in the series are corrections coming from instantions (BPS states). Non-renormalization theorems due to susy guarantee that there are no higher loop corrections. One expects the instanton series to converge, and hence the monodromy is completely determined by the one-loop calculation. This is the key: by Riemann-Hilbert, the monodromy determines the $f_i(u)$ uniquely--solving the Riemann-Hilbert problem is equivalent to computing the infinitely-many instantion corrections!


Now in general, solving the Riemann-Hilbert problem is difficult, so this reduction is of a theoretical but not necessarily practical nature. The second main idea of Seiberg and Witten is that we can solve this Riemann-Hilbert problem explicitly by introducing a family of curves $\{C_u\}_{u\in\mathcal{B}}$, called Seiberg-Witten curves (or spectral curves).



Electric-Magnetic Duality


An absolutely key requirement of the Seiberg-Witten construction is electric-magnetic duality. Maxwell's equations in vacuum are

$$ dF = 0, \ \ \ d\ast F = 0. $$

Here $F$ is a 2-form, and $\ast F$ is its Hodge dual, a $(d-2)$-form in $d$-dimensions. The first equation implies that $F = dA$ for some 1-form $A$, and we normally think of the second equation as the Euler-Lagrange equations for the action written in terms of $A$. However, we could equally well take the starting point to be the second equation, taking $\ast F = dB$, and take the first equation to be the Euler-Lagrange equations for $B$. The problem with either of these approaches is that they allow particles of either electric or magnetic charge, but not both.


To put electric and magnetic charge on equal footing, we introduce fields $F$ and $F_D$ (a 2-form and a (d-2)-form$. Then the Lagrangian is (up to factors that I'm too lazy to care about)

$$ \mathcal{L} = \mathrm{Tr} F \wedge F_D $$

However, to recover Maxwell's equations, we need to impose $\ast F_D = F$ as a constraint. So to get the right equations of motion, introduce an auxiliary field $\lambda$ (a Lagrange multiplier), and modify the Lagrangian:

$$ \mathcal{L} = \mathrm{Tr} F \wedge F_D + \lambda(F - \ast F_D) $$

Variation with respect to $(F, F_D, \lambda)$ will reproduce Maxwell's equations exactly, but in this form the EM duality is manifest. Since EM duality exchanges electric and magnetic charges, we should consider how to modify the Lagrangian to couple the field to EM sources. Let $J_e, J_m$ be the electric and magnetic currents, respectively. Up to conventions, Maxwell's equations read

$$ dF = J_m, \ \ \ d F_D = J_e. $$

Then we take the Lagrangian to be

$$ \mathcal{L} = \mathrm{Tr} F \wedge F_D + \lambda(F - \ast F_D) + F \wedge J_e + J_m \wedge F_D $$

to reproduce the right equations of motion.


In this form, we can consider particles with electric or magnetic charge (or both--dyons). If our gauge group has rank $r$, then the lattice of electric charges is $\mathbb{Z}^r$, while the lattice of magnetic charges is $(\mathbb{Z}^\ast)^r$. Hence the lattice of electromagnetic charges is

$$ \Gamma = \mathbb{Z}^r \oplus (\mathbb{Z}^\ast)^r $$

which comes with a natural symplectic pairing

$$\langle \cdot, \cdot \rangle: \Gamma \otimes \Gamma \to \mathbb{Z}.$$


(You might ask why we take the natural sympletic pairing as opposed to the natrual symmetric pairing. This is because there is actually a larger $SL(2,\mathbb{Z})$ symmetry of the theory which preserves the symplectic pairing but not the symmetric pairing.)


Now there is an obvious source of symplectic lattices. Simply let $C$ be a genus $r$ compact Riemann surface. Then $\Gamma = H_1(C, \mathbb{Z})$ is a symplectic lattice of rank $2r$, where the symplectic pairing is now given by the intersection pairing. In fact, we can say more--if we take $a$- and $b$-cycles as generators, these form a Darboux (symplectic) basis of $\Gamma$.


Back to the gauge theory problem. Recall that the 1-loop calculation and consideration of BPS states leads to a set of monodromy data on $\mathcal{B}$. Suppose now that we could find a complex surface $C \to \mathcal{B}$ whose fibers $C_u$ are (possibly singular) genus $r$ curves, and such that the monodromies of $\Gamma_u := H_1(C_u, \mathbb{Z})$ agree with the given monodromies. Then we can solve the Riemann-Hilbert problem by doing geometry on this family, i.e. by finding holomorphic sections of certain associated bundles.


The SU(2) Seiberg-Witten Solution

We will now specialize to the case considered in the original paper of Seiberg and Witten. I will only construct the family--the details of the solution will follow in a subsequent post.


In this case, the group has rank $r=1$, so we should be looking for a family of elliptic curves. In this case, the solution is almost obvious, given what I've said above. Seiberg and Witten argue that the moduli space $\mathcal{B}$ must be $\mathbb{C} \setminus \{\Lambda^2, -\Lambda^2\}$. The punctures at $\pm \Lambda^2$ come from BPS states whose mass goes to zero at those values of $u$. So the monodromy consists of three matrices, $M_\infty, M_\pm$, the monodromies computed around $\infty$ and $\pm \Lambda^2$. These generate a certain modular subgroup $G$ of $SL(2, \mathbb{Z})$, allowing us to realize $\mathcal{B}$ as the modular curve $H / G$ (where $H$ is the upper half-plane). Now, the space of elliptic curves is just $H / SL(2, \mathbb{Z})$. So given any $u \in \mathbb{B}$, we pick a lift $\tilde{u}$ in $H$ and let $C_u$ be the corresponding elliptic curve. This is exactly the family needed to solve the Riemann-Hilbert problem!


Next time: details of this construction, including exact formulas, and some words about instanton counting.
