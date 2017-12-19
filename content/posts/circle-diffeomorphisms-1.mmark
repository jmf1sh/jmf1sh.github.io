---
title: "Circle diffeomorphisms"
date: 2012-07-13
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


This is the first of a series of posts based on these lecture notes on KAM theory. For now I just want to outline section 2, which is a toy model of KAM thoery.


Circle Diffeomorphisms


We consider a map \(\phi: \mathbb{R} \to \mathbb{R}\) defined by

\[ \phi(x) = x + \rho + \eta(x) \]

where \(\rho\) is its rotation number and \(\eta(x)\) is "small".


Define \(S_\sigma\) to be the strip \(\{ |\mathrm{Im} z|&lt;\sigma\} \subset \mathbb{C}\) and let \(B_\sigma\) be the space of holomorphic functions bounded on \(S_\sigma\) with sup norm \(\|\cdot\|_\sigma\).


Goal: Show that if \(\|\eta\|_\sigma\) is sufficiently small, then there exists some diffeomorphism \(H(x)\) such that

\[ H^{-1} \circ \phi \circ H (x) = x + \rho \]

i.e. that \(\phi\) is conjugate to a pure rotation.



Linearization


The idea is that if \(\eta\) is small, then \(H\) should be close to the identity, so we suppose that

\[ H(x) = x + h(x) \]

where \(h(x)\) is small. Plugging this into the equation above and discarding higher order terms yields

\[ h(x+\rho) - h(x) = \eta(x) \]

Since \(\eta\) is periodic, we Fourier transform both sides to obtain an explicit formula for the Fourier coefficients of \(h(x)\). We have to show several things:


1. The Fourier series defining \(h(x)\) converges in some appropriate sense.


2. The function \(H(x) = x + h(x)\) is a diffeomorphism.


3. The composition \(\tilde{\phi} = H^{-1} \circ \phi \circ H\) is closer to a pure rotation than \(\phi\), in the sense that

\[ \tilde{\phi}(x) = x + \rho + \tilde{\eta}(x) \]

where \(\|\tilde{\eta}\| \ll \|\eta\|\).



Newton's Method

Carrying out the analysis, one finds that for appropriate epsilons and deltas, if \(\eta \in B_\sigma\) then \(H \in B_{\sigma - \delta}\) and that \(\|\tilde{\eta}\|_{\sigma-\delta} \leq C \|\eta\|_\sigma^2\). By carefully choosing the deltas, we can iterate this procedure (composing the \(H\)'s) to obtain a well-defined limit \(H_\infty \in B_{\sigma/2}\) such that

\[ H_\infty^{-1} \circ \phi \circ H_\infty (x) = x + \rho, \]

as desired.


So in fact the idea of the proof is extremely simple, and all of the hard work is in proving some estimates.