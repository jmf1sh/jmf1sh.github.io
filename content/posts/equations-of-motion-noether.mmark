---
title: "Equations of motion and Noether's theorem in the functional formalism"
date: 2012-11-29
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


First, let us recall the derivation of the equations of motion and Noether's theorem in classical field theory. We have some action functional \(S[\phi]\) defined by some local Lagrangian:

\[ S[\phi] = \int L(\phi, \partial \phi) dx. \]

The classical equations of motion are just the Euler-Lagrange equations

\[ \frac{\delta S}{\delta \phi(x)} = 0

 \iff \partial_\mu \left( \frac{\partial L}{\partial(\partial_\mu\phi)} \right)

= \frac{\partial L}{\partial \phi} \]


Now suppose that \(S\) is invariant under some transformation \(\phi(x) \mapsto \phi(x) + \epsilon(x) \eta(x)\), so that \(S[\phi] = S[\phi+\epsilon \eta]\). Here we treat \(\eta\) as a fixed function but \(\epsilon\) may be an arbitrary infinitesimal function. The Lagrangian is not necessarily invariant, but rather can transform with a total derivative:

\[ L(\phi+\epsilon \eta) = L(\phi)

+ \frac{\partial L}{\partial (\partial_\mu \phi)} \eta \partial_\mu \epsilon

+ \epsilon \partial_\mu f^\mu \]

For some unknown vector field \(f^\mu\) (which we could compute given any particular Lagrangian). So let's compute

\begin{align}\delta_\epsilon S &amp;= \int \delta_\epsilon L \\\

&amp;= \int \frac{\partial L}{\partial (\partial_\mu \phi)}

\eta \partial_\mu \epsilon + \epsilon \partial_\mu f^\mu \\\

&amp;= \int \partial_\mu \left(f^\mu - \frac{\partial L}{\partial (\partial_\mu \phi)} \eta \right) \epsilon

\end{align}

Let us define the Noether current \(J^\mu\) by

\[ J^\mu = \frac{\partial L}{\partial (\partial_\mu \phi)} \eta - f^\mu. \]

Then the previous computation showed that

\[ \frac{\delta S}{\delta \epsilon} = -\partial_\mu J^\mu. \]

If \(\phi\) is a solution to the Euler-Lagrange equations, then the variation \(dS\) vanishes, hence we obtain:


Theorem (Noether's theorem) The Noether current is divergence free, i.e.

\[ \partial_\mu J^\mu = 0.\]


Functional Version


First, we derive the functional analogue of the classical equations of motion. Consider an expectation value

\[ \langle \mathcal{O(\phi)} \rangle

= \int \mathcal{O}(\phi) e^{\frac{i}{\hbar} S} \mathcal{D}\phi \]

We'll assume that \(\phi\) takes values in a vector space (or bundle). Then we can perform a change of variables \(\psi = \phi + \epsilon\), and since \(\mathcal{D}\phi = \mathcal{D}\psi\) we find that

\[ \int \mathcal{O}(\phi+\epsilon) \exp\left(\frac{i}{\hbar} S[\phi] \right) \mathcal{D}\phi \]

is independent of \(\epsilon\). Expanding to first order in \(\epsilon\), we have

\[ 0 = \int \left(\frac{\delta\mathcal{O}}{\delta \phi}

 + \frac{i \mathcal{O}}{\hbar} \frac{\delta S}{\delta \phi} \right)

 \exp \left( \frac{i}{\hbar} S \right) \mathcal{D}\phi  \]

So we find the quantum analogue of the equations of motion:

\[ \left\langle \frac{\delta \mathcal{O}}{\delta \phi} \right\rangle

+ \frac{i}{\hbar} \left\langle \mathcal{O} \frac{\delta S}{\delta \phi} \right\rangle = 0\]


Next, we move on to the quantum version of Noether's theorem. Suppose there is a transformation \(Q\) of the fields leaving the action invariant. Assuming the path integral measure is invariant, we obtain

\[ \left\langle QF \right \rangle + \frac{i}{\hbar} \left\langle F QS \right\rangle = 0\]

To compare with the classical result, consider \(Q\) to be the (singular) operator

\[ Q = \frac{\delta}{\delta \epsilon(x)} \]

Then by the previous calculations,

\[ Q S = -\delta_\mu J^\mu, \]

so we obtain

\[ \left\langle \frac{\delta \mathcal{O}}{\delta \epsilon(x)} \right\rangle

= \frac{i}{\hbar} \left\langle \mathcal{O} \partial_\mu J^\mu \right\rangle.  \]

This is the Ward-Takahashi identity, the quantum analogue of Noether's theorem.
