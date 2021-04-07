+++
title = "Classical mechanics, part 6"
date = 2011-09-01
draft = false
categories = ["physics"]
tags = ["classical-mechanics"]
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/). The original post can be found [here](https://mathphysseminar.blogspot.com/2011/09/classical-mechanics-6-poisson-brackets.html).


Last time we saw that a classical mechanical system which has a Lagrangian formulation can (under some mild assumptions) be repackaged as a symplectic manifold \\((M, \omega)\\) together with a smooth function \\(H\\) called the Hamiltonian. The equations of motion then become

\\[ \dot{x} = X_H \\]

where \\(X_H\\) is the Hamiltonian vector field associated with \\(H\\) (sometimes called the symplectic gradient of \\(H\\)). This identifies solutions to the equations of motion with certain curves in the manifold \\(M\\), which together form a 1-parameter group of diffeomorphisms (in fact, symplectomorphisms) of \\(M\\).


Today, I'd like to discuss a dual formulation. Instead of thinking of the equations of motion as describing evolution of the points of \\(M\\), we will instead think of the equations of motion as describing evolution of the functions on \\(M\\). We will see later that this is the classical analog of the Heisenberg picture in quantum mechanics.


Definition An observable on \\(M\\) is a smooth real-valued function on \\(M\\).


Suppose we have a classical mechanical system \\(M, \omega, H\\). By integrating the equations of motion, we obtain a 1-parameter family of symplectomorphisms \\(\phi_t\\). For any point \\(x \in M\\), the curve \\(x(t)\\) defined by

\\[ x(t) = \phi_t(x) \\]

solved Hamilton's equations.


Now suppose we have some observable \\(f\\). Its value along any solution to the equations of motion is

\\[ f(x(t) = f(\phi_t(x)) = f_t(x) \\]

where \\(f_t := f \circ \phi_t\\). So, if we only care about the values of observables along any solution to the equations of motion, the transformation

\\[ x \mapsto x(t) = \phi_t(x) \\]

\\[ f \mapsto f \\]

which is the Schrodinger picture, is indistinguishable from the transformation

\\[ x \mapsto x \\]

\\[ f \mapsto f_t = f \circ \phi_t \\]

which we will call the Heisenberg picture. What is the analog of Hamilton's equations for the Heisenberg picture? Let us compute:

\\[ \frac{d}{dt} f_t = \frac{d}{dt}f(\phi_t) = df \circ \frac{d}{dt}\phi_t \\]

Since \\(\phi_t\\) is generated by the vector field \\(X_H\\), we obtain

\\[ \frac{d}{dt} f_t = X_H(f) = df(X_H) = \omega^{-1}(dH, df) \\]

For two observables \\(f\\) and \\(g\\), let us define the Poisson bracket of \\(f\\) and \\(g\\) as

\\[ \\{f, g\\} := \omega^{-1}(df, dg). \\]

Then we have

\\[ \frac{d}{dt} f_t = \\{H, f_t \\} \\]

which is called the Heisenberg equation of motion.


Theorem The Poisson bracket \\(\{\cdot, \cdot\}\\) satisfies the following properties:

1. It is \\(\mathbb{R}\\)-linear and skew-symmetric.

2. It satisfies the Jacobi identity.

3. It satisfies the Leibniz rule \\(\\{fg,h\\} = f\\{g,h\\} + \\{f,h\\}g\\).


Proof Too lazy for now! But it's really easy.


Now let \\(\mathscr{A} = C^\infty(M, \mathbb{R})\\) be the commutative algebra of observables. This has an additional structure: the Poisson bracket \\(\\{,\\}\\), so we will call \\(\mathscr{A}\\) a Poisson algebra.


Now let us consider something completely crazy. Consider the following generalization of mechanical system.


Tentative Definition A mechanical system is an algebra \\(\mathscr{A}\\) together with a Poisson bracket \\(\\{\cdot, \cdot\\}\\) on \\(\mathscr{A}\\) and an element \\(H \in \mathscr{A}\\) called the Hamiltonian. The Heisenberg equations of motion are

\\[ \frac{d}{dt} f_t = \\{H, f_t\\} \\]

for any \\(f \in \mathscr{A}\\).


This definition is a little too vague at the moment, since without specifying a topology on \\(\mathscr{A}\\) we have no way of making sense of the Heisenberg equation. However, up to this caveat, this definition of mechanical system captures the essence of all of classical mechanics, classical field theory, quantum mechanics, and quantum field theory!