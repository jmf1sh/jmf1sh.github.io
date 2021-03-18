---
title: "Classical partition function"
date: 2015-08-18
draft: false
---

This post has been migrated from my old blog, the [math-physics learning seminar](https://mathphysseminar.blogspot.com/).


Let $(M, \omega)$ be a symplectic manifold of dimension $2n$, and let $H: M \to \mathbf{R}$ be a classical Hamiltonian. The symplectic form $\omega$ allows us to define a measure on $M$, given by integration against the top form $\omega^n / n!$. We will denote this measure by $d\mu$.


We imagine that $(M, \omega, H)$ represents some classical mechanical system. We suppose that the dynamics of this dynamical system are very complicated, e.g. some system of $10^{23}$ particles. The system is so complicated that not only can we not solve the equations of motion exactly, and even if we could, their solutions might be so complicated that we can't expect to learn very much from them.


So instead, we ask statistical questions. Imagine that we cannot measure the state of the system exactly (e.g. particles in a box), so we try to guess a probability distribution $\rho(x,p,t)$ on $M$ indicating that at time $t$ the system has probability $\rho(x,p,t) d\mu$ of being in the state $(x,p)$. Obviously, $\rho$ should satisfy the constraint $\int_M \rho d\mu = 1$.


How does $\rho$ evolve in time? We know that the system obeys Hamilton's equations,

$$ (\dot x, \dot p) = X_H = (\partial H / \partial p, -\partial H / \partial x) $$

 in local Darboux coordinates. Therefore, a particle located at $(x,p)$ in phase space at time $t$ will be located at $(x,p)+X_H dt$ in phase space at time $t+dt$. Therefore, the probability that a particle is at point $(x,p)$ at time $t+dt$, should be equal to the probability that the particle is at point $(x,p)-X_H dt$ at time $t$. Therefore, we have

$$ \frac{\partial \rho}{\partial t} = \frac{\partial H}{\partial x} \frac{\partial \rho}{\partial p} - \frac{\partial H}{\partial p} \frac{\partial \rho}{\partial x} = \{H, \rho\} $$


Given a probability distribution $\rho$, the entropy is defined to be

$$ S[\rho] = -\int_M  \rho \log \rho d\mu. $$


(A version of) the second law of thermodynamics. For a given average energy $U$, the system assumes a distribution of maximal possible entropy at thermodynamic equilibrium.


The goal now, is to determine what distribution $\rho$ will maximize the entropy, subject to the constraints (for fixed $U$)

\\begin{align*} \int_M H \rho d\mu &= U \\\

\int_M \rho d\mu &= 1 \\end{align*}


Setting aside technical issues of convergence, etc., this variational problem is easily solved using the method of Lagrange multipliers. Introducing parameters $\lambda_1, \lambda_2$, we consider the modified functional

$$ S[\rho, \lambda_1, \lambda_2, U] = \int_M\left(-\rho \log \rho +\lambda_1\rho +\lambda_2(H\rho)\right)d\mu -\lambda_1-\lambda_2 U. $$


Note that $\partial S / \partial U = -\lambda_2$, and this is conventionally identified with (minus) the inverse temperature.


Taking the variation with respect to $\rho$, we find

$$ 0= \frac{\delta S}{\delta \rho} = -\log \rho-1+\lambda_1+H\lambda_2$$

Therefore, $rho$ is proportional to $e^{-\beta H}$ where we have set $\beta=-\lambda_2$. Define the partition function $Z$ to be

$$ Z = \int_M e^{-\beta H} d\mu. $$

We therefore have proved (formally and heuristically only!):


Theorem. The probability distribution $\rho$ assumed by the system at thermodynamic equilibrium is given by

$$  \rho = \frac{e^{-\beta H}}{Z} $$

where $\beta &gt; 0$ is a real parameter, called the inverse temperature.


Corollary. At thermodynamic equilibrium, the average energy is given by

$$ U = -\frac{\partial \log Z}{\partial \beta} , $$

and the entropy is given by

$$ S = \beta U + \log Z.$$



