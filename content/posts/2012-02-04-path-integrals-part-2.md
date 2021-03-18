---
title: "Path integrals, part 3"
date: 2012-02-04
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).




Consider the heat equation

$$ \frac{\partial \psi}{\partial t} = -\hat{H} \psi $$

We find similarly

$$ \langle x_N|U_t|x_0\rangle = \int \exp \sum_{j=0}^{N-1} ik_j(x_j - x_{j+1}) -\Delta t H(x_j, k_j) dx dk. $$


Now take $H(x,k) = k^2/2m + V(x)$ and complete the square:


$$ ik_j(x_j - x_{j+1}) - \Delta t k_j^2/2m - \Delta tV(x_j) + ik_{j+1}(x_{j+1} - x_{j+2}) - k_{j+1}^2/2m - V(x_{j+1}) $$


\\begin{align}
 ik_j a_j - \Delta t k_j^2/2m &= -(-2mi k_j a_j / \Delta t + k_j^2) \Delta t/2m \\\\\\
&= -(k_j^2 -2mi k_j a_j/\Delta t -m^2 a_j^2/(\Delta t)^2 + m^2 a_j^2/(\Delta t)^2) \Delta t/2m \\\\\\
&= -(k_j -mia_j/\Delta t)^2 \Delta t/2m -ma_j^2/2\Delta t
\\end{align}


Combining things together, we have that the heat kernel is given by

$$ \langle y|e^{-t \hat{H}}|x\rangle = \int e^{-S_{\textrm{euc}}} \mathcal{D}x $$


That is, Schwartz kernel of time evolution operator is given by the oscialltory Lorentzian signature path integral, whereas the heat kernel is given by the exponentially decaying path integral (better chance of being well-defined). Most importantly, the heat kernel contains most of the essential information about the spectrum of $\hat{H}$, which is really all we need in order to understand the dynamics.


See ABC of Instantons. (I never understood the title of Nekrasov's "ABCD of Instantons" until I found this classic).