---
title: "Classical mechanics, part 3"
date: 2011-08-19 21:00:00Z
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


We saw before that Newton's 2nd law can be written in a more general form as

$$ \frac{d}{dt} \frac{\partial L}{\partial v}(x, \dot{x}) = \frac{\partial L}{\partial x}(x, \dot{x}), $$

known as the Euler-Lagrange equations. Hamilton discovered a principle that explains the origin of these equations. Consider some path of the system given by a curve $\gamma$, i.e.

$$ x(t) = \gamma(t) $$

$$ \dot{x}(t) = \frac{d}{dt}\gamma(t) $$

Then we may define a quantity associated with the path $\gamma$:

$$ S = \int L(\gamma, \dot{\gamma})dt $$

called the action. Hamilton discovered the following.


Theorem The path taken by a mechanical system is one which extremizes the action.


To prove this, suppose we perturb the path a small amount, while leaving the endpoints fixed, i.e. $\gamma \mapsto \gamma + \epsilon (\delta\gamma)$ with $\epsilon &gt; 0$ small and $\delta\gamma$ a path that is $0$ at its endpoints. Then

$$ L(\gamma + \epsilon\delta\gamma, \dot\gamma + \epsilon\delta\dot{\gamma}) = L(\gamma, \dot{\gamma}) + \epsilon \frac{\partial L}{\partial x}\delta\gamma + \epsilon \frac{\partial L}{\partial v} \delta\dot\gamma + o(\epsilon^2) $$

Thus

$$ S[\gamma + \epsilon\delta\gamma] = S[\gamma] + \epsilon \int \frac{\partial L}{\partial x} \delta \gamma dt + \epsilon \int \frac{\partial L}{\partial v} \delta \dot\gamma dt + o(\epsilon^2) $$

Integrating by parts, and using the fact that $\delta\gamma$ is $0$ on the endpoints, we have

$$ \int \frac{\partial L}{\partial v}\delta\dot\gamma dt = -\int \frac{d}{dt} \frac{\partial L}{\partial v} \delta\gamma dt $$


Combining the above, we have

$$ \frac{\delta S}{\delta \gamma}(\delta \gamma) = \int \left(\frac{\partial L}{\partial x} - \frac{d}{dt}\frac{\partial L}{\partial v} \right) \delta\gamma dt $$

Thus the variational derivative of $S$ is

$$ \frac{\delta S}{\delta \gamma} = \frac{\partial L}{\partial x} - \frac{d}{dt} \frac{\partial L}{\partial v} $$

So a path $\gamma$ is a critical point of $S$ (i.e. it extremizes $S$) if and only if the Euler-Lagrange equations are satisfied.
