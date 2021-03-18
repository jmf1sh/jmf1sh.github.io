---
title: "Path integrals, part 1"
date: 2012-01-16
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Consider the Hilbert space $\mathcal{H} = L^2(\mathbb{R})$ with Lebesgue measure and a Hamiltonian $H = T(k) + V(x)$ (a sum of kinetic and potential energy). Then the quantum hamiltonian $\hat{H}$ acts as

\\begin{align}

(\hat{H}\psi)(y) &= \frac{1}{2\pi} \int e^{ik(y-x)} T(k) \psi(x) dx dk + V(y)\psi(y) \\\

&= \frac{1}{2\pi}\int e^{ik(y-x)} H(k,x) \psi(x) dx dk \\\

\\end{align}


Now consider the Schrodinger equation

$$ \frac{\partial \psi}{\partial t} = i \hat{H} \psi. $$


We would like to obtain a formula for the solution operator $U_t = e^{-i \hat{H} t}$. Let us consider its Schwartz kernel $\langle{y}|U_t|{x}\rangle$. Let $N$ be a large integer so that $\Delta t = t/N$ is "small". Then we can write

$$ U_t = U_{\Delta t}^N, $$

Now consider a single term:

\\begin{align}

 \langle{y}|U_{\Delta t}|x\rangle &\simeq \langle{y}|1-i\Delta{t}\hat{H}|x\rangle \\\

&= \delta(y-x) -i \Delta t \langle x|\hat{H}|y\rangle \\\

&= \frac{1}{2\pi}\int e^{ik(y-x)}( 1 - i \Delta t H(k,x)) dk \\\

&\simeq \frac{1}{2\pi}\int e^{ik(y-x) - i \Delta t H(k,x)} dk\\\

\\end{align}

Now we have (taking $x_0 = x$ and $x_N = y$)

\\begin{align}

\langle y|U_t|x\rangle &= \int dx_1 \cdots dx_{N-1} \\\

& \ \times \langle x_N|U_{\Delta t}|x_{N-1}\rangle \cdots \langle x_1|U_{\Delta t}|x_0\rangle \\\


&= \frac{1}{(2\pi)^N} \int dx_1 \cdots dx_{N-1} dk_0 \cdots dk_{N-1} \\\

& \ \times \ e^{ik_N(x_N-x_{N-1}) - i \Delta t H(k_{N-1},x_{N-1})} \cdots

e^{-ik_N(x_1-x_0) - i \Delta t H(k_0,x_0)} \\\

&= \frac{1}{(2\pi)^N} \int dx_1 \cdots dx_{N-1} dk_0 \cdots dk_{N-1} \\\

& \ \times \ \exp \sum_{j=0}^{N-1} ik_j(x_{j+1} - x_j) - i \Delta t H(k_j,x_j)


\\end{align}

Note this kind of integral seems like it should have a natural interpretation in symplectic or contact geometry, since the expression $dxdk/(2\pi)^N$ is very nealy the Liouville measure. This is the most general form of the path integral.


Now assume that $H(k,x) = k^2/2m + V(x)$. Then the $k$-dependent terms have the form

$$ \int e^{ik(y-x) - i\Delta t k^2/2m}. $$

Complete the square

\\begin{align}

 ik(y-x) -i\Delta t k^2/2m &= -\frac{i \Delta t}{2m} (k^2 - \frac{2m}{\Delta t}k(y-x)) \\\

&= -\frac{i \Delta t}{2m} (k^2 - \frac{2m}{\Delta t}k(y-x) + \frac{m^2}{\Delta t^2}(y-x)^2 -\frac{m^2}{\Delta t^2}(y-x)^2) \\\

&= -\frac{i \Delta t}{2m}(k - \frac{m}{\Delta t}(y-x))^2 + \frac{i m}{2 \Delta t}(y-x)^2

\\end{align}

Now, using that

$$ \int e^{-ak^2} = \sqrt{\frac{\pi}{a}} $$

We have

$$ \int e^{-\frac{i \Delta t}{2m}(k-\frac{m}{\Delta t}(y-x))^2} = \sqrt{\frac{2\pi m}{i \Delta t}} $$

Putting it altogether, we get the more familiar version of the path integral,

\\begin{align} \langle y|U_t|x\rangle &\simeq C^N \int dx_1 \cdots dx_{N-1} \\\

& \ \times \ \exp i\sum_{j=0}^{N-1} \frac{m}{2\Delta t}(x_{j+1}-x_j)^2 - V(x_j) \Delta t

\\end{align}

where

$$ C = \frac{1}{2\pi} \sqrt{\frac{2 \pi m}{i \Delta t}} = \sqrt{\frac{m}{2\pi i \Delta t}} $$



