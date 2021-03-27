+++
title = "Classical mechanics, part 2"
date = 2011-08-19T15:00:00Z
draft = false
categories = ["physics"]
tags = ["classical-mechanics"]
+++

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


After the previous post, we are now familiar with Newton's 2nd law

$$ \mathbf{F} = m\mathbf{a}, $$

which (suitably interpreted) holds for any system of \\(N\\) particles. However, this equation requires the use of cartesian coordinates, which for many systems may not be the most convenient choice. Suppose we have some other coordinates \\(q^i = q^i(x^j)\\). What is the correct analogue of Newton's 2nd law for the \\(q\\)-coordinates?


To make life easier, we will assume for now that the force \\(\mathbf{F}\\) is conservative; i.e.

$$ \mathbf{F} = -\nabla V(x) $$

for some potential function \\(V(x)\\). Under this assumption, Newton's 2nd law is

$$ m\mathbf{a} + \nabla V(x) = 0. $$

Let us define the function \\(T\\) by

$$ T(x,v) = \frac{1}{2}m |v|^2, $$

and define the function \\(L\\) as

$$ L(x,v) = T(x,v) - V(x). $$

Then we have immediately that Newton's 2nd law is equivalent to

$$ \frac{d}{dt}\frac{\partial L}{\partial v}(x, \dot{x}) - \frac{\partial L}{\partial x}(x,\dot{x})  = 0. $$

Why go through the trouble of introducing these auxiliary functions and rewriting Newton's 2nd law in this way? The answer lies in the following theorem.


Theorem For any choice of coordinates \\(y = y(x)\\), Newton's 2nd law is equivalent to the equations

$$ \frac{d}{dt}\frac{\partial \tilde{L}}{\partial w}(y, \dot{y}) - \frac{\partial \tilde{L}}{\partial y}(y,\dot{y})  = 0, $$

where \\(w = dY_x(v)\\) and \\(\tilde{L}(y,w) = L(x(y,w), v(y,w)\\). These equations are called the Euler-Lagrange equations.


The proof of this theorem is a straightforward calculation using the chain rule. Let \\(M\\) denote the manifold \\(\mathbb{R}^{3N}\\) (or some open subset thereof). The coordinate change \\(y = y(x) \\) can be thought of as a diffeomorphism \\(Y: M \to M\\) given by \\(x \mapsto y(x) \\). The differential \\( dY: TM \to TM\\) is also a diffeomorphism. In coordinates, we have

$$ y = y(x) $$

$$ w = dY_x(v)  = Jv $$

where \\(y,w\\) are coordinates on the target \\(TM\\).


Now we need to compute the derivatives of \\(\tilde{L}\\).


$$ \frac{\partial L}{\partial x} = \frac{\partial \tilde{L}}{\partial y}\frac{\partial y}{\partial x} + \frac{\partial \tilde{L}}{\partial w}\frac{\partial w}{\partial x} = \tilde{L}_y J + \tilde{L}_w H v $$

where \\(J\\) is the matrix of mixed partials and \\(H\\) is the Hessian matrix.


$$ \frac{\partial L}{\partial v} = \frac{\partial \tilde{L}}{\partial y} \frac{\partial y}{\partial v} + \frac{\partial \tilde{L}}{\partial w} \frac{\partial w}{\partial v} = \tilde{L}_w J $$


Then we have

$$ \frac{d}{dt}\left( \tilde{L}_w J \right) = \frac{d}{dt}\tilde{L}_w J + \tilde{L}_w H \dot{x}  $$

Subtracting \\(\frac{\partial L}{\partial x}\\) from this and using the calculation above, we obtain

$$ \left( \frac{d}{dt} \tilde{L}_w - \tilde{L}_y \right) J $$

and since \\(J\\) is invertible, this is \\(0\\) if and only if \\(\frac{d}{dt} \tilde{L}_w - \tilde{L}_y\\) is.

But this is exactly what we wanted to prove!
