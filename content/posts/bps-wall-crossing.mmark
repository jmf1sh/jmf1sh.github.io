---
title: "BPS states and wall-crossing"
date: 2012-10-29
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


This is the first in what I hope will become a series of posts on BPS state counting and wall-crossing. I'm participating in gLab, and our most immediate goal is to understand the Kontsevich-Soibelman wall-crossing formula (KSWCF) in the context of quadratic differentials on a (punctured) Riemann surface, following the lectures of Kontsevich and Neitzke at IHES.


The purpose of these posts is to keep a written record of my attempts to understand the physics behind the WCF as well as the work of Gaiotto-Moore-Neitzke.


References:


    Witten's lectures on dynamics of QFT
    Gaiotto-Moore-Neitzke
    Kontsevich-Soibelman
    Seiberg and Witten
    Distler's blogpost, and
     This post on the n-Category cafe (note: Bridgeland's talk relates quadratic differentials to stability conditions).



Video Lectures:


    IHES Lectures by Neitzke and Kontsevich
    Lectures by Moore on the (2,0) d=6 superconformal theory
    PITP 2010 (Gaiotto, Moore, Witten, Seiberg, others!)
    Neitzke: What is a BPS state?
    Gauge fields and strings


Physics Setup:


Warning: I'm still trying to sort this all out, so a lot of this will be fuzzy and/or completely wrong. I will try to point out the points of confusion.


We will start with some kind of family of susy gauge theories (or rather, a single  "theory" with a family of vacua, depending on what asymptotic boundary conditions we specify in the path integral). We let \(\mathcal{B}\) be some kind of manifold (or variety, possibly with singularities?), and \(\{\mathcal{H}_u\}_{u \in \mathcal{B}}\) a family (bundle) of Hilbert spaces, depending on \(u \in \mathcal{B}\). Concretely, \(\mathcal{B}\) will parametrize the vacuum expectation values (VEVs) of the scalar fields of the theory. (Note, for non-scalar fields we can typically expect VEVs to vanish, for example by looking at the action of the Lorentz group.) Actually, to be more precise, \(\mathcal{B}\) parametrizes the Coulomb branch--where the VEVs break the gauge symmetry to a maximal torus (as opposed to the Higgs branch, where the VEVs just break the gauge group to a smaller subgroup).


The next ingredient is a lattice \(\Gamma\), the charge lattice, which is supposed to parametrize all possible electric and magnetic charges. Since electric and magnetic charges are dual, this lattice has a pairing \(\Gamma \otimes \Gamma \to \mathbb{Z}\) which is symplectic (or possibly just Poisson?). (Actually, maybe we should think of \(\Gamma\) as being a bundle of lattices over \(\mathcal{B}\), but this isn't completely clear to me.) The lattice gives a grading of \(\mathcal{H}\):

\[ \mathcal{H} = \bigoplus_{\gamma \in \Gamma} \mathcal{H}_\gamma \].


Now, the Hilbert spaces \(\mathcal{H}_u\) are supposed to carry representations of the \(\mathcal{N}=2\) susy algebra, with central charge \(Z\). On any state of charge \(\gamma\) above the point \(u \in \mathcal{B}\), the central charge \(Z\) acts as a scalar, which we denote by \(Z_\gamma(u)\). Manipulations with the susy algebra show the BPS bound \(M \geq |Z_\gamma(u)|\), where \(M\) is the mass of a state with charge \(\gamma\). A state is called BPS if it saturates this bound.


Finally, I'll end this post by attempting to define (or at least motivate) the walls of marginal stability. In all known examples, we have

\[ |Z_{\gamma_1 + \gamma_2}(u)|^2 = |Z_{\gamma_1}(u)|^2 + |Z_{\gamma_2}(u)|^2 +2 \mathrm{Re}(Z_{\gamma_1}(u) \bar{Z}_{\gamma_2}(u) ) \]

If the cross-term is negative, then it is possible to form stable bound states (since the mass of a BPS state of charge \(\gamma_1+\gamma_2\) is strictly less than the sum of the corresponding masses); and it is impossible to form stable bound states if the cross-term is positive. This (naive!) dichotomy tells us that there is something very special about the intermediate case. For a pair of charges \(\gamma_1, \gamma_2\) we define a wall in \(\mathcal{B}\) by

\[ W(\gamma_1, \gamma_2) = \{u \in \mathcal{B} \ | \ \mathrm{Re}(Z_{\gamma_1}(u)\bar{Z}_{\gamma_2}(u)) = 0 \} \]

and we define \(W \subset \mathcal{B}\) to be the union of all the walls.


The idea of wall-crossing is the following. We define some functions \(\Omega(\gamma; u)\) on \(\mathcal{B} \setminus W\) which are locally constant. These functions are supposed to count the number of BPS states of charge \(\gamma\) (where count really means take the trace of a particular operator over \(\mathcal{H}_{\gamma, \mathrm{BPS}}\)). The wall-crossing formula is an explicit formula that relates \(\Omega(\gamma; u_+)\) and \(\Omega(\gamma; u_-)\) for \(u_+, u_-\) on opposite sides of a wall in \(\mathcal{B}\). There are two applications of WCF:


1. We pick some particular \(u \in \mathcal{B}\) for which \(\Omega\) is particularly easy to calculate ("extreme stability"). Then by KSWCF we actually know how to compute \(\Omega\) on all of \(\mathcal{B} \setminus W\).


2. Gaiotto-Moore-Neitzke study a certain QFT whose low energy effective action is a sigma model with target space \(\mathcal{M}\), the moduli space of Higgs bundles over a Riemann surface. The invariants \(\Omega(\gamma; u)\) together with KSWCF allow them to compute the low energy effective action explicitly, giving an explicit construction of holomorphic Darboux coordinates on \(\mathcal{M}\). This is enough to recover the full hyperkahler metric on \(\mathcal{M}\), in local coordinates!



Tasklist (incomplete!):


    Define susy algebra, derive BPS bound
    Understand/construct the charge lattice and its pairing
    Sketch that 3d sigma model with \(\mathcal{N}=4\) has a hyperkahler target
    Sketch/understand why the low energy effective action has target Higgs
    Understand computation of effective action: Seiberg-Witten curves and all that
    Understand how KSWCF implies consistency of the Darboux coordinates

