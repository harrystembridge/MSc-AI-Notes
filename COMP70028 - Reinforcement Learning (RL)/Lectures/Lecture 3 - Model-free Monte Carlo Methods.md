![[RL - Lecture 3.pdf]]

## Introduction

![[RL - Lecture 3.pdf#page=3|RL - Lecture 3, page 3]]

![[RL - Lecture 3.pdf#page=5|RL - Lecture 3, page 5]]

![[RL - Lecture 3.pdf#page=6|RL - Lecture 3, page 6]]

![[RL - Lecture 3.pdf#page=9|RL - Lecture 3, page 9]]

>[!CARD] Monte Carlo Methods
>Methods that learn value functions and policies from sample episodes of experience, without requiring a model of the environment.

![[RL - Lecture 3.pdf#page=10|RL - Lecture 3, page 10]]

![[RL - Lecture 3.pdf#page=11|RL - Lecture 3, page 11]]

## Monte Carlo Policy Evaluation

![[RL - Lecture 3.pdf#page=12|RL - Lecture 3, page 12]]


![[RL - Lecture 3.pdf#page=13|RL - Lecture 3, page 13]]

![[RL - Lecture 3.pdf#page=14|RL - Lecture 3, page 14]]

![[RL - Lecture 3.pdf#page=15|RL - Lecture 3, page 15]]

![[RL - Lecture 3.pdf#page=16|RL - Lecture 3, page 16]]

* After 1 episode:
![[RL - Lecture 3.pdf#page=18|RL - Lecture 3, page 18]]


- Second iteration:
![[RL - Lecture 3.pdf#page=20|RL - Lecture 3, page 20]]

![[RL - Lecture 3.pdf#page=21|RL - Lecture 3, page 21]]


![[RL - Lecture 3.pdf#page=23|RL - Lecture 3, page 23]]

Answer: D - doesn't require a model

![[RL - Lecture 3.pdf#page=24|RL - Lecture 3, page 24]]

Answer: B - we need all the returns

## Monte Carlo Control
## On-policy
![[RL - Lecture 3.pdf#page=26|RL - Lecture 3, page 26]]

![[RL - Lecture 3.pdf#page=29|RL - Lecture 3, page 29]]

* One bad thing about Monte Carlo is we need episodes to end. If they run on for infinite time, we have a problem.

![[RL - Lecture 3.pdf#page=30|RL - Lecture 3, page 30]]

- Answer C: we cannot do policy improvement without knowing the transition probabilities.

![[RL - Lecture 3.pdf#page=31|RL - Lecture 3, page 31]]

- We need to sample all of the actions!
- THE EXPLORATION PROBLEM
![[RL - Lecture 3.pdf#page=32|RL - Lecture 3, page 32]]

![[RL - Lecture 3.pdf#page=33|RL - Lecture 3, page 33]]

- To converge means when the policy stops changing and values stop changing within a small delta.

![[RL - Lecture 3.pdf#page=36|RL - Lecture 3, page 36]]

> [!CARD] How can we avoid the unlikely assumption of exploring starts?
> The only general way to ensure all actions are selected infinitely often is for the agent to continue to select them.
> Two approaches to ensuring this:
> - On-policy methods
> - Off-policy methods



> [!CARD] On-policy Methods
> - Evaluate and improve the policy that is used to make decisions 
> - The policy being learned is the same as the policy being followed Must use stochastic policies to maintain exploration.
> Requires stochastic policies


> [!CARD] Off-policy Methods
> - Learn about one policy while following a different policy
> - Target policy: what we want to learn about 
> - Behavior policy: what we use to generate experience
> Requires stochastic policies


![[RL - Lecture 3.pdf#page=39|RL - Lecture 3, page 39]]
* Here we add an exploratory bonus... We want to reward exploration.
* A high $\epsilon$ encourages exploration of new paths.


![[RL - Lecture 3.pdf#page=40|RL - Lecture 3, page 40]]

* Answer is A!!! Because even the optimal option gets this bonus!!!


![[RL - Lecture 3.pdf#page=45|RL - Lecture 3, page 45]]

![[RL - Lecture 3.pdf#page=46|RL - Lecture 3, page 46]]
- We are going from deterministic policies, we are now learning stochastic policies.


![[RL - Lecture 3.pdf#page=48|RL - Lecture 3, page 48]]
- Only 1 action is greedy, so this evaluates to zero, so this is the max of Q (simplifies)

![[RL - Lecture 3.pdf#page=49|RL - Lecture 3, page 49]]
- We know that max is greater than or equal to a weighted average.
- It can be any weights as long as the weights sum to 1.
- 

![[RL - Lecture 3.pdf#page=50|RL - Lecture 3, page 50]]


![[RL - Lecture 3.pdf#page=53|RL - Lecture 3, page 53]]

- Remember if we can show that the policy improvement condition is true then we can use the policy improvement theorem to show that one policy is better than another.

![[RL - Lecture 3.pdf#page=54|RL - Lecture 3, page 54]]

Answer D!

### Off-policy
![[RL - Lecture 3.pdf#page=56|RL - Lecture 3, page 56]]

![[RL - Lecture 3.pdf#page=57|RL - Lecture 3, page 57]]

![[RL - Lecture 3.pdf#page=59|RL - Lecture 3, page 59]]

- We need the assumption of coverage for this to work:
	- If the $\pi$ is saying we want to go left, but our behaviour policy never goes left, then something isn't right.

![[RL - Lecture 3.pdf#page=60|RL - Lecture 3, page 60]]

Answer C

> [!CARD] The coverage assumption π(a|s) > 0 ⇒ b(a|s) > 0 means
> The behavior policy must try every action the target policy might take

![[RL - Lecture 3.pdf#page=61|RL - Lecture 3, page 61]]

![[RL - Lecture 3.pdf#page=62|RL - Lecture 3, page 62]]

> [!CARD] Importance Sampling
>  Weighting our episodes by how likely each episode would be under $\pi$ vs $b$

- If $\pi$ wants to do it and $b$ doesn't want to do it then the number will be smaller and vice versa.


![[RL - Lecture 3.pdf#page=66|RL - Lecture 3, page 66]]

- How do we treat visiting the same state on multiple trajectories?
- 2 options:
	- We can either do **ordinary importance sampling**.
	- Or, **weighted importance** sampling.


> [!CARD] Ordinary Importance Sampling
> **Bias:** Unbiased, since $\mathbb{E}[\rho_{t:T-1} G_t] = v_\pi(s)$.
> **Variance:** Unbounded (potentially infinite), because the ratios $\rho_{t:T-1}$ can be arbitrarily large.

> [!CARD] Weighted Importance Sampling
> **Bias:** Biased, but the bias converges to zero asymptotically as the number of samples grows.
> **Variance:** Much lower, and bounded, since each weight is normalised by the sum of the ratios, so any single return's weight is at most 1.



![[RL - Lecture 3.pdf#page=69|RL - Lecture 3, page 69]]

![[RL - Lecture 3.pdf#page=71|RL - Lecture 3, page 71]]

![[RL - Lecture 3.pdf#page=72|RL - Lecture 3, page 72]]

- Why is this? 
	- Because we are drawing from the behaviour policy.

- If we were using weighted sampling instead, we have much smoother learning! This comes from using ordinary importance sampling.

> [!CARD] What's the main reason weighted importance sampling is preferred over ordinary importance sampling?
> It has much lower variance

- Having an unbiased algorithm is kind of useless if it can never converge.

![[RL - Lecture 3.pdf#page=73|RL - Lecture 3, page 73]]

Answer C

![[RL - Lecture 3.pdf#page=74|RL - Lecture 3, page 74]]

![[RL - Lecture 3.pdf#page=74|RL - Lecture 3, page 74]]

![[RL - Lecture 3.pdf#page=75|RL - Lecture 3, page 75]]

- Just a rolling average used here for implementing our algorithm.
![[RL - Lecture 3.pdf#page=76|RL - Lecture 3, page 76]]

![[RL - Lecture 3.pdf#page=80|RL - Lecture 3, page 80]]

![[RL - Lecture 3.pdf#page=82|RL - Lecture 3, page 82]]

- b can be any soft policy, can keep on changing and can come from anywhere.

- Iterate backwards through that episode, update the weights.
- Choose the argmax of this Q that we're learning from b.

![[RL - Lecture 3.pdf#page=84|RL - Lecture 3, page 84]]


> [!CARD] What are the two main limitations of Monte Carlo methods?
> 1. Episode-based learning
> 2. High variance
>

> [!CARD] Why is episode-based learning a limitation of Monte Carlo methods?
> - Only works for episodic tasks
> - Must wait for episode completion to update
> - No online learning during episodes
> - Can be slow if episodes are long
>

> [!CARD] Why do Monte Carlo methods only work for episodic tasks?
> Value updates use the full return $G_t$, which is only known once the episode terminates.
>

> [!CARD] Why can't Monte Carlo methods learn online during an episode?
> They must wait for the episode to finish to compute the return, so no updates happen mid-episode.
>

> [!CARD] Why is high variance a limitation of Monte Carlo methods?
> - Sample returns can vary greatly
> - Especially problematic in off-policy methods
> - May need many episodes for good estimates
> - Importance sampling can make variance worse
>

> [!CARD] Why are sample returns high variance in Monte Carlo methods?
> The return $G_t$ sums many random rewards over a whole episode, so randomness in actions and transitions accumulates.
>

> [!CARD] Why does importance sampling make the variance of Monte Carlo methods worse?
> The ratios $\rho_{t:T-1} = \prod_k \frac{\pi(A_k|S_k)}{b(A_k|S_k)}$ can become very large, which amplifies the variance of the weighted returns.



![[RL - Lecture 3.pdf#page=85|RL - Lecture 3, page 85]]

![[RL - Lecture 3.pdf#page=86|RL - Lecture 3, page 86]]

Answer: C 

![[RL - Lecture 3.pdf#page=87|RL - Lecture 3, page 87]]

Answer: E

![[RL - Lecture 3.pdf#page=88|RL - Lecture 3, page 88]]

![[RL - Lecture 3.pdf#page=89|RL - Lecture 3, page 89]]

![[RL - Lecture 3.pdf#page=90|RL - Lecture 3, page 90]]
