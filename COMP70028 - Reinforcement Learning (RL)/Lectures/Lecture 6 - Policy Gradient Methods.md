![[RL - Lecture 6.pdf]]

![[RL - Lecture 6.pdf#page=2|RL - Lecture 6, page 2]]

![[RL - Lecture 6.pdf#page=3|RL - Lecture 6, page 3]]

![[RL - Lecture 6.pdf#page=4|RL - Lecture 6, page 4]]

# Introduction
![[RL - Lecture 6.pdf#page=5|RL - Lecture 6, page 5]]

![[RL - Lecture 6.pdf#page=7|RL - Lecture 6, page 7]]

# Policy Parameterisation
![[RL - Lecture 6.pdf#page=10|RL - Lecture 6, page 10]]

![[RL - Lecture 6.pdf#page=12|RL - Lecture 6, page 12]]

- Higher preferences incur higher probability
- Preferences can now be negative
- Softmax ensures the probabilities sum to 1

![[RL - Lecture 6.pdf#page=13|RL - Lecture 6, page 13]]

![[RL - Lecture 6.pdf#page=14|RL - Lecture 6, page 14]]

- parameterise with a gaussian instead
- Trying to parameterise the mean of the distribution and the standard deviation to derive the Gaussian.

![[RL - Lecture 6.pdf#page=16|RL - Lecture 6, page 16]]

- Very common for parameterising continuous control problems.

![[RL - Lecture 6.pdf#page=19|RL - Lecture 6, page 19]]

- How do we optimise these? i.e. compute the gradient.
- Optimise over the value functio
- Using gradient descent

# Policy Gradient Theorem

derivation #not-examinable 


![[RL - Lecture 6.pdf#page=20|RL - Lecture 6, page 20]]

![[RL - Lecture 6.pdf#page=28|RL - Lecture 6, page 28]]

![[RL - Lecture 6.pdf#page=33|RL - Lecture 6, page 33]]

#examinable
![[RL - Lecture 6.pdf#page=35|RL - Lecture 6, page 35]]

- One form of the policy-gradient theorem
- For any differentiable policy, the policy gradient is defined as how to make an action more likely given how good an action is and how often we visit the state.

![[RL - Lecture 6.pdf#page=40|RL - Lecture 6, page 40]]

- In practice... If Q is high, we'll do more of A
- If Q is low, it was bad, do less of A, make A less likely...

![[RL - Lecture 6.pdf#page=41|RL - Lecture 6, page 41]]

- Answer D, B is also correct in theory

- Understand the Policy-Gradient Theorem!
# REINFORCE
![[RL - Lecture 6.pdf#page=43|RL - Lecture 6, page 43]]


![[RL - Lecture 6.pdf#page=46|RL - Lecture 6, page 46]]

![[RL - Lecture 6.pdf#page=48|RL - Lecture 6, page 48]]

> [!CARD] What is the main advantage of policy gradient methods over value-based methods like Q-learning?
> Policy gradient methods can learn stochastic policies and handle continuous action spaces naturally

> [!CARD] In the REINFORCE algorithm, why do we multiply the gradient by the return $G_t$?
> To weight updates by how good the trajectory was, implementing the policy gradient theorem.

> [!CARD] How does subtracting a baseline b(s) from returns in REINFORCE affect the gradient estimate?
> It reduces variance without introducing bias (if b(s) doesn’t depend on actions)




![[RL - Lecture 6.pdf#page=50|RL - Lecture 6, page 50]]

- Monte Carlo, continued environments, rollout until terminal state
- Unbiased estimate but we can have high variance
- We need to complete episodes to compute returns.

- No value functions needed!

![[RL - Lecture 6.pdf#page=51|RL - Lecture 6, page 51]]
- initial policy 25% in each direction

![[RL - Lecture 6.pdf#page=52|RL - Lecture 6, page 52]]

![[RL - Lecture 6.pdf#page=53|RL - Lecture 6, page 53]]

![[RL - Lecture 6.pdf#page=54|RL - Lecture 6, page 54]]

- never learnt a value function

![[RL - Lecture 6.pdf#page=55|RL - Lecture 6, page 55]]

- Answer E (both B and D)
	- Multiplies some score by the log of policy.

![[RL - Lecture 6.pdf#page=56|RL - Lecture 6, page 56]]

![[RL - Lecture 6.pdf#page=58|RL - Lecture 6, page 58]]

- Probability distribution sums to one
- We settle the variance of the Q function

![[RL - Lecture 6.pdf#page=60|RL - Lecture 6, page 60]]

![[RL - Lecture 6.pdf#page=61|RL - Lecture 6, page 61]]

- Over time we get saved by the value function, reducing the size of the gradient

![[RL - Lecture 6.pdf#page=62|RL - Lecture 6, page 62]]
- Answer C - lower variance, same expected gradient

# Actor-Critic Methods
![[RL - Lecture 6.pdf#page=64|RL - Lecture 6, page 64]]

![[RL - Lecture 6.pdf#page=66|RL - Lecture 6, page 66]]

![[RL - Lecture 6.pdf#page=68|RL - Lecture 6, page 68]]
- How good something was, if it was good, do more of that...

![[RL - Lecture 6.pdf#page=69|RL - Lecture 6, page 69]]

![[RL - Lecture 6.pdf#page=70|RL - Lecture 6, page 70]]

![[RL - Lecture 6.pdf#page=71|RL - Lecture 6, page 71]]

![[RL - Lecture 6.pdf#page=72|RL - Lecture 6, page 72]]

![[RL - Lecture 6.pdf#page=73|RL - Lecture 6, page 73]]

![[RL - Lecture 6.pdf#page=74|RL - Lecture 6, page 74]]

![[RL - Lecture 6.pdf#page=75|RL - Lecture 6, page 75]]

![[RL - Lecture 6.pdf#page=76|RL - Lecture 6, page 76]]

- Answer E - Monte Carlo returns vs bootstraps

![[RL - Lecture 6.pdf#page=77|RL - Lecture 6, page 77]]

- Answer A - lower variance

![[RL - Lecture 6.pdf#page=78|RL - Lecture 6, page 78]]

- We just need to estimate if we should be doing more of A or less...
- It's just some scoring system for how good A is...

# Deep Reinforcement Learning - Policy-based Methods
#not-examinable 
![[RL - Lecture 6.pdf#page=80|RL - Lecture 6, page 80]]


![[RL - Lecture 6.pdf#page=83|RL - Lecture 6, page 83]]


![[RL - Lecture 6.pdf#page=86|RL - Lecture 6, page 86]]

![[RL - Lecture 6.pdf#page=88|RL - Lecture 6, page 88]]

![[RL - Lecture 6.pdf#page=93|RL - Lecture 6, page 93]]

![[RL - Lecture 6.pdf#page=94|RL - Lecture 6, page 94]]

![[RL - Lecture 6.pdf#page=95|RL - Lecture 6, page 95]]

![[RL - Lecture 6.pdf#page=98|RL - Lecture 6, page 98]]

![[RL - Lecture 6.pdf#page=99|RL - Lecture 6, page 99]]

![[RL - Lecture 6.pdf#page=100|RL - Lecture 6, page 100]]

