---
title: "Introduction to Reinforcement Learning"
date: 2018-01-14
draft: false
---

I would like to record the basic formalism of reinforcement learning. Hopefully, this will lead to a post or series of posts giving a basic tensorflow implementation of a simple deep reinforcement learning model. But first, we have to know what problem we are trying to solve.

To begin, we have the following data (which are considered to be given as part of the problem):
* a set of states $$\mathcal{S}$$
* for each state $$s \in \mathcal{S}$$, a set $$\mathcal{A}_s$$ of actions
* for each state $$s$$, a mapping $$t_s: \mathcal{A}_s \to \mathcal{S}$$ evolving the system according to the chosen state
* for each state $$s$$, a reward function $$r_s: \mathcal{A}_s \to \mathbb{R}$$

In addition, we also introduce a parameter $$\gamma \in (0,1)$$ as a measure of ``impatience,'' with 0 representing infinite impatience and 1 representing infinite patience. The importance of $$\gamma$$ will become clearer below.

Now for a definition: a _policy_ $$\pi$$ is a choice, for each state $$s$$, of a probability distribution on the set of actions $$\mathcal{A}_s$$. Associated to the above data, we also have
* the set $$\mathcal{P}$$ of policies associated with the states and actions

Now, consider a sequnce of actions $$a_0, a_1, \ldots$$ starting from an initial state $$s_0$$ transforming the system in a sequence of states $$s_0, s_1, \ldots$$. Associated to this, we can define a total reward

$$ r_{\mathrm{total}} = r_0(s_0, a_0) + \gamma r(s_1, a_1) + \gamma^2 r(s_2, a_2) + \cdots$$

The weighting by $$\gamma$$ will turn out to be very important shortly. Now recall that a policy $$\pi$$ assigns a probability distribution to the viable actions, and therefore for a given policy $$\pi$$ we can consider the expected value of the above quantity. We define the $$Q$$-function to be

$$ Q(s, a) = \max_{\pi} \mathbb{E}_\pi[r_{\mathrm{total}}] $$

From the definition, we see that $$Q$$ measures the maximum possible expected reward starting from the initial state $$s$$ and action $$a$$. The importance of $$Q$$ is clear--if we know $$Q$$, then we can find the best sequence of actions greedily: at each state $$s$$, we simply choose an action $$a$$ that maximizes $$Q(s,a)$$.

Now comes the magic. From the definition of $$r_{\mathrm{total}}$$ above, we have

<p>
\begin{align*}
Q(s,a) &= \max_{\pi} \mathbb{E}_\pi[r(s,a) + \gamma r(s_1, a_1) + \cdots] \\
&= r(s,a) + \gamma \max_\pi \mathbb{E}_\pi[r(s_1, a_1) + \gamma r(s_2, a_2) + \cdots] \\
&= r(s,a) + \gamma \max_{a'} Q(t(a), a')
\end{align*}
</p>

This recursive relation is known as the _Bellman equation_. To understand how to solve this equation, let us introduce the space $$\mathcal{F}$$ as follows:

$$ \mathcal{F} = \{ (s,a) \ | \ s \in \mathcal{S}, a \in \mathcal{A}_s \} $$

Using the sup-norm, we obtain a Banach space of functions $$\mathcal{F} \to \mathbb{R}$$. Let $$B$$ be the (non-linear) operator on this space defined by

$$ B(q)(s,a) = r(s,a) + \gamma \max_{a'} q(t(s,a), a') $$

which is known as the _Bellman operator_. As stated above, the desired $$Q$$-function satisfies the fixed-point equation $$Q = B(Q)$$. Under reasonable assumptions, it is a straightforward exercise to verify that

$$\| B(q_1) - B(q_2) \| \leq \gamma \| q_1 - q_2 \| $$

making $$B$$ into a contraction on the space of functions $$\mathcal{F} \to \mathbb{R}$$, provided that $$\gamma \in (0,1)$$. Therefore, by the [Banach fixed-point theorem](https://en.wikipedia.org/wiki/Banach_fixed-point_theorem), the Bellman equation has a unique solution $$Q^\ast$$. Furthermore, this solution can be constructed as follows: we take an initial function $$Q_0$$, and take $$Q^\ast$$ to be the limit of the sequence defined by
$$ Q_{n+1} = B(Q_n). $$

Now, the basic ideas of deep reinforcement learning are the following
* use a neural network to provide a reasonable finite-dimensional approximation to the aforementioned Banach space
* using an approximate $$Q$$, generate new sequences of actions and add these to a running list of _experiences_
* periodically, take a random sample of past experiences and use these to update the $$Q$$ function via the Bellman equation

For more details, see [Human-level control through deep reinforcement learning](https://www.nature.com/articles/nature14236). I plan to follow up with more posts giving a basic implementation using [tensorflow](https://www.tensorflow.org/) and [OpenAI Gym](https://github.com/openai/gym).