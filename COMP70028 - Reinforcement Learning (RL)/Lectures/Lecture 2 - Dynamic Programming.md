![[RL - Lecture 2.pdf]]

Reminder: A policy is a mapping of states to actions

## Introduction
![[RL - Lecture 2.pdf#page=5|RL - Lecture 2, page 5]]

Reminder: The Bellman equation tells us the value of being in a state s, given a policy $\pi$

![[RL - Lecture 2.pdf#page=6|RL - Lecture 2, page 6]]

> [!CARD] Dynamic programming
> A method for solving complex problems by breaking them into simpler subproblems, solving each subproblem once, and storing the results.

## Policy Evaluation
![[RL - Lecture 2.pdf#page=8|RL - Lecture 2, page 8]]


![[RL - Lecture 2.pdf#page=9|RL - Lecture 2, page 9]]

We can solve this directly but is not necessarily scalable as the state space grows.

![[RL - Lecture 2.pdf#page=10|RL - Lecture 2, page 10]]

We stop when the difference between the value between the two states is below some value $\theta$.


![[RL - Lecture 2.pdf#page=11|RL - Lecture 2, page 11]]

The in-place updates tend to move a bit faster.

![[RL - Lecture 2.pdf#page=12|RL - Lecture 2, page 12]]

![[RL - Lecture 2.pdf#page=13|RL - Lecture 2, page 13]]

* As we are always going right, there is no value here, we never hit a state which can give us a reward or penalise us.

![[RL - Lecture 2.pdf#page=14|RL - Lecture 2, page 14]]

Answer is (C)

![[RL - Lecture 2.pdf#page=15|RL - Lecture 2, page 15]]

* Answer D


![[RL - Lecture 2.pdf#page=16|RL - Lecture 2, page 16]]

* Answer A - it represents our current best estimate for the value of the next state.

## Policy Improvement
![[RL - Lecture 2.pdf#page=19|RL - Lecture 2, page 19]]

* Q tells us how valuable it is to be in a given state and take a particular action
* V tells us the value of a given state regardless of the action taken

### Policy Improvement Theorem
![[RL - Lecture 2.pdf#page=20|RL - Lecture 2, page 20]]

* If for one step I do something different to what $\pi$ would have done, action $\pi'$ and then I go back to following $\pi$.
* **If this then gives us a better value than the value for just following $\pi$ then we can say that $\pi'$ is a better policy!**
* If acting differently for just 1 step is better, than we can say the other policy is better.
* Proving that:
![[Pasted image 20261012163737.png]]
* Leads to:
![[Pasted image 20261012163751.png]]

![[RL - Lecture 2.pdf#page=31|RL - Lecture 2, page 31]]

* Just showing the policy improvement theorem works.

***Derivation unexaminable but the concept is...***

![[RL - Lecture 2.pdf#page=32|RL - Lecture 2, page 32]]
* But really need to understand this slide ^


![[RL - Lecture 2.pdf#page=33|RL - Lecture 2, page 33]]

* Answer E - we can apply the same logic at each future state, we can continue to unroll

## Policy Iteration
![[RL - Lecture 2.pdf#page=36|RL - Lecture 2, page 36]]

### Conditions for iteration to find the optimal policy
![[RL - Lecture 2.pdf#page=37|RL - Lecture 2, page 37]]


* Monotonic improvement, the policy improves each time

![[RL - Lecture 2.pdf#page=38|RL - Lecture 2, page 38]]

* Answer B is correct.

## Value Iteration
![[RL - Lecture 2.pdf#page=41|RL - Lecture 2, page 41]]

![[RL - Lecture 2.pdf#page=42|RL - Lecture 2, page 42]]

![[RL - Lecture 2.pdf#page=43|RL - Lecture 2, page 43]]

* Does the one step evaluation and the argmax in one go.

![[RL - Lecture 2.pdf#page=44|RL - Lecture 2, page 44]]

- Value iteration continues until the maximum change in value across all states falls below the threshold $\theta$
> [!CARD] What are the steps of the value iteration algorithm?
> - Initialise $V_0(s) = 0$ for all $s$
> - For $k = 0, 1, 2, \ldots$ update for all $s$: $V_{k+1}(s) = \max_a \sum_{s',r} P(s',r|s,a)[r + \gamma V_k(s')]$
> - Stop when $\max_s |V_{k+1}(s) - V_k(s)| < \theta$
> - Extract the policy: $\pi^*(s) = \arg\max_a \sum_{s',r} P(s',r|s,a)[r + \gamma V^*(s')]$

> [!CARD] What is the key difference between the value iteration update and the policy evaluation update?
> - Value iteration uses a $\max$ over actions
> - Policy evaluation uses a sum over actions weighted by the policy $\pi(a|s)$




![[RL - Lecture 2.pdf#page=46|RL - Lecture 2, page 46]]

![[RL - Lecture 2.pdf#page=47|RL - Lecture 2, page 47]]
* No longer -1 as we choose the best action at each step.


![[RL - Lecture 2.pdf#page=48|RL - Lecture 2, page 48]]

![[RL - Lecture 2.pdf#page=49|RL - Lecture 2, page 49]]

* Answer C - we implement both evaluation and improvement simultaneously.


> [!CARD] What is policy iteration?
> - Alternates policy evaluation and policy improvement
> - Evaluation: compute $V^{\pi_k}$ using iterative evaluation until it converges
> - Improvement: set $\pi_{k+1}(s) = \arg\max_a Q_{\pi_k}(s,a)$
> - Stop when $\pi_{k+1} = \pi_k$ (the policy is stable)

> [!CARD] Why does policy iteration find the optimal policy?
> - Monotonic improvement: $V^{\pi_{k+1}}(s) \geq V^{\pi_k}(s)$ for all $s$
> - Finite convergence: there are only $|\mathcal{A}|^{|\mathcal{S}|}$ possible policies and each improvement is strict until optimality
> - So it reaches $\pi^*$ in finite time

> [!CARD] What is the inefficiency in policy iteration?
> - Each evaluation step runs to full convergence, which can take 100+ iterations
> - The policy is thrown away straight after the improvement step
> - Early iterations already give the general shape of the values, so perfect accuracy isn't needed

> [!CARD] What is value iteration?
> - Does one step of policy evaluation followed by greedy improvement, merged into a single update
> - $V_{k+1}(s) = \max_a \sum_{s',r} P(s',r|s,a)[r + \gamma V_k(s')]$ for all $s$
> - It is the policy evaluation update with the sum over $\pi(a|s)$ replaced by a $\max$ over actions

> [!CARD] What is the spectrum between policy iteration and value iteration?
> - Policy iteration: complete evaluation + improvement
> - Truncated policy iteration: partial evaluation + improvement
> - Value iteration: one-step evaluation + improvement

> [!CARD] How does value iteration differ from policy iteration?
> - Policy iteration fully evaluates each policy before improving it
> - Value iteration does only one evaluation step before improving
> - Each value iteration sweep is cheaper, but it needs more sweeps overall
> - Both need full knowledge of the MDP




## Generalised Policy Iteration (GPI)
![[RL - Lecture 2.pdf#page=52|RL - Lecture 2, page 52]]


![[RL - Lecture 2.pdf#page=53|RL - Lecture 2, page 53]]

![[RL - Lecture 2.pdf#page=54|RL - Lecture 2, page 54]]

![[RL - Lecture 2.pdf#page=55|RL - Lecture 2, page 55]]
![[RL - Lecture 2.pdf#page=56|RL - Lecture 2, page 56]]
![[RL - Lecture 2.pdf#page=57|RL - Lecture 2, page 57]]

![[RL - Lecture 2.pdf#page=58|RL - Lecture 2, page 58]]

* Answer C


![[RL - Lecture 2.pdf#page=60|RL - Lecture 2, page 60]]

![[RL - Lecture 2.pdf#page=61|RL - Lecture 2, page 61]]

![[RL - Lecture 2.pdf#page=62|RL - Lecture 2, page 62]]
