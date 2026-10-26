![[RL - Tutorial 3.pdf]]
## Understanding Monte Carlo Methods
### 1.1 MC vs DP: Conceptual Understanding
a) DP requires knowledge of transition probabilities while MC does not. Apples to DP but not MC.
> [!CARD] What is a transition probability in reinforcement learning?
> The probability of moving to next state s' given that the agent takes action $a$ in state $s: p(s' | s, a) = Pr(S_{t+1} = s' | S_t = s, A_t = a)$. For each $(s, a)$, the probabilities over all $s'$ sum to 1. DP needs the full MDP model including transition probabilities.  MC learns from sample episodes without needing this information.


b) ~~Both can only be applied to episodic tasks.~~ Wrong: only MC methods requite episodic tasks to terminate so returns can be computing. DP can work with continuing tasks.
> [!CARD] What is an episodic task in reinforcement learning?
> A task that splits into finite, independent episodes, each running from a start state to a terminal state, after which the environment resets. The return is a finite sum, so discounting is optional. Monte Carlo methods need episodic tasks because they average complete returns, which are only known once an episode ends. DP can work using continuing tasks.

c) ~~MC uses bootstrapping while DP does not.~~ Wrong: only DP uses bootstrapping i.e. updating values based on the estimates of other states. MC waits for actual returns.
> [!CARD] What is bootstrapping in RL, and how do DP and Monte Carlo differ on it?
> Updating a value estimate using other current value estimates instead of only actual observed returns. DP bootstraps: $V(s)$ is updated using the estimate $V(s')$, and it needs a model. Monte Carlo does not bootstrap: V(s) is updated toward the full observed return $G_t$, so it needs no model but must wait until the episode ends.

d) MC learns directly from experience without a model while DP does not. DP requires a model to learn from trajectories.
> [!CARD] How do MC and DP differ in their need for a model?
> MC learns directly from sampled experience (episodes) without needing a model. DP requires a model of the environment (the transition probabilities and rewards) to compute its updates.


e) both will converge to the optimal policy under appropriate conditions...
What conditions?
- DP will converge with sufficient iterations.
- MC will converge with sufficient episodes and appropriate exploration.

### 1.2 Computing Returns
a) ![[Pasted image 20261024105046.png]]
![[Pasted image 20261024105053.png]]

> [!CARD] What is $G_t$ in reinforcement learning?
> The return: the total discounted reward collected from time t onward. $G_t = R_{t+1} + γR_{t+2} + γ²R_{t+3} + … + γ^{T−t−1}R_T$, which satisfies the recursion $G_t = R_{t+1} + γG_{t+1}$. In MC methods, $V(s_t)$ is updated toward the sampled $G_t$.


## Monte Carlo Policy Evaluation
### 2.1 First-visit vs Every-visit MC
![[Scan from 2026-10-24 02_02_14 PM.pdf]]

> [!CARD] What is the difference between first-visit and every-visit Monte Carlo?
> They differ in how they handle a state visited more than once in an episode. First-visit MC averages only the return following the first visit to s in each episode. Every-visit MC averages the returns following every visit to s. Both converge to v_π(s). First-visit is unbiased, while every-visit is biased but consistent.


![[tutorial_3_solutions.pdf]]
