+++
title = "Classical mechanics, part 4"
date = 2011-08-23
draft = false
categories = ["physics"]
tags = ["classical-mechanics"]
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/). The original post can be found [here](https://mathphysseminar.blogspot.com/2011/08/classical-mechanics-4-hamiltons.html).


Recall from last time that a classical mechanical system consists of a manifold \\(M\\) (the configuration space) and a function \\(L\\) on the tangent bundle \\(TM\\). The equations of motion for a path \\(x(t)\\) in \\(M\\) are the 2nd order Euler-Lagrange equations:

\\[ \frac{d}{dt}\left( \frac{\partial L}{\partial v}(x, \dot{x}) \right) = \frac{\partial L}{\partial x}(x, \dot{x}) \\]


Hamilton discovered a way of recasting these equations as a first order system for a path in a related manifold, the cotangent bundle \\(T^\ast M\\). The benefits are twofold: in addition to reducing the equations to a first order system (at the cost of introducing new variables), it turns out that this framework makes it much easier to find conserved quantities and prove theorems about mechanical systems. So let's see what he did.


Theorem Under mild assumptions on \\(L\\), there is a function \\(H\\) on \\(T^\ast M\\) constructed canonically out of \\(L\\) such that solutions of the Euler-Lagrange equations are in 1-1 correspondence with solutions \\(q(t), p(t)\\) on \\(T^\ast M\\) of Hamilton's equations

\\[ \dot{q} = \frac{\partial H}{\partial p}(q, p) \\]

\\[ \dot{p} = -\frac{\partial H}{\partial q}(q,p) \\]

Furthermore, if the original Lagrangian function \\(L\\) is not explicitly time-dependent, then the function \\(H\\) is constant for any solution of the equations of motion.


To start with, introduce coordinates \\(x, v\\) on \\(TM\\) as before. We will define new coordinates \\(q,p\\) as follows:

\\[ q(x,v) = x \\]

\\[ p(x,v) = \frac{\partial L}{\partial x}(x,v) \\]

Our assumption on \\(L\\) will be the following: the above formulas can be inverted to obtain \\(x\\) and \\(v\\) as functions of \\(q\\) and \\(p\\). It is easily seen from the definition of \\(p\\) that under a coordinate transformation (of \\(x\\)), it behaves as a 1-form, so the coordinates \\(q\\) and \\(p\\) can be interpreted as local coordinates on the cotangent bundle \\(T^\ast M\\). We construct the Hamiltonian as

\\[ H(q,p) = p\cdot v(q,p) - L(x(q,p), v(q,p)) \\]

(this is the Legendre transform--more later). Of course, the above formula is not well-defined if we cannot solve for \\(x\\) and \\(v\\) in terms of \\(p\\) and \\(q\\)--hence the assumption. Now we check:

\\[ \frac{\partial H}{\partial p} = v + p \frac{\partial v}{\partial p} - \frac{\partial L}{\partial x} \frac{\partial x}{\partial p} -\frac{\partial L}{\partial v}\frac{\partial v}{\partial p} = v + p\frac{\partial v}{\partial p} - p\frac{\partial v}{\partial p} = v\\]

Since \\(\dot{x} = v\\), this is the first of Hamilton's equations.


For the second, we perform a similar computation:

\\[ \frac{\partial H}{\partial q} = -\frac{\partial L}{\partial x} \frac{\partial x}{\partial q} - \frac{\partial L}{\partial v} \frac{\partial v}{\partial q} = -\frac{\partial L}{\partial x} \\]

But the Euler-Lagrange equations say that

\\[ \dot{p} = \frac{d}{dt}\frac{\partial L}{\partial v} = \frac{\partial L}{\partial x} = -\frac{\partial H}{\partial x}, \\]

so we've obtained the second of Hamilton's equations.


For the last part, suppose that the Lagrangian does not depend explicitly on time, i.e.

\\[ \frac{\partial L}{\partial t} = 0. \\]

Then we compute:

\\[ \frac{d}{dt}H = \frac{\partial H}{\partial q}\dot{q} + \frac{\partial H}{\partial p}\dot{p} = \frac{\partial H}{\partial q} \frac{\partial H}{\partial p} - \frac{\partial H}{\partial p} \frac{\partial H}{\partial q} = 0. \\]

Hence \\(H\\) is automatically conserved. For this reason, \\(H\\) is often called the energy of the system.


Later, we will see that conserved quantities correspond to symmetries, and conservation of energy is a statement about the symmetry corresponding to time translation.
