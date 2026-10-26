---
flashcards:
  q-fepr: { nid: 1793032847287, hash: qjcxcurx, sync: uzfjdcwj }
  q-yv36: { nid: 1793032847445, hash: kss2ysfu, sync: iryqktst }
---

![[RL - Lecture 4.pdf]]

![[RL - Lecture 4.pdf#page=2|RL - Lecture 4, page 2]]

![[RL - Lecture 4.pdf#page=3|RL - Lecture 4, page 3]]

# Introduction
![[RL - Lecture 4.pdf#page=5|RL - Lecture 4, page 5]]

![[RL - Lecture 4.pdf#page=6|RL - Lecture 4, page 6]]

- Problem with Monte Carlo is we need episodes to end, and we are not really learning anything as the game progresses.
![[RL - Lecture 4.pdf#page=7|RL - Lecture 4, page 7]]

![[RL - Lecture 4.pdf#page=9|RL - Lecture 4, page 9]]

> [!CARD] Definition (Temporal Difference (TD) Learning) 
> A class of model-free methods that learn value functions by bootstrapping from current estimates, updating based on the difference between successive predictions.
^q-fepr

- Basically just bootstrapping

## TD(0) for Policy Evaluation

![[RL - Lecture 4.pdf#page=13|RL - Lecture 4, page 13]]
$\alpha$ is our step size/learning rate

![[RL - Lecture 4.pdf#page=14|RL - Lecture 4, page 14]]

- initialise to some arbitrary value, normally zero.

- Differences vs Monte Carlo, we are updating the value function as we are interacting, even before the episode ends.

![[RL - Lecture 4.pdf#page=15|RL - Lecture 4, page 15]]
![[RL - Lecture 4.pdf#page=16|RL - Lecture 4, page 16]]

- This is all happening step by step, the value of the second square is zero...

![[RL - Lecture 4.pdf#page=17|RL - Lecture 4, page 17]]

- Agent does the final step, gets the reward multiplied by the step value...

![[RL - Lecture 4.pdf#page=18|RL - Lecture 4, page 18]]

![[RL - Lecture 4.pdf#page=19|RL - Lecture 4, page 19]]

- Another episode

![[RL - Lecture 4.pdf#page=21|RL - Lecture 4, page 21]]

![[RL - Lecture 4.pdf#page=22|RL - Lecture 4, page 22]]

#IMPORTANT ![[RL - Lecture 4.pdf#page=23|RL - Lecture 4, page 23]]


| Property | Dynamic Programming | Monte Carlo | Temporal Difference |
|---|---|---|---|
| Target | Expected value: $\mathbb{E}[R_{t+1} + \gamma V(S_{t+1})]$ | $G_t$ | $R_{t+1} + \gamma V(S_{t+1})$ |
| Bootstraps | Yes | No | Yes |
| Samples | No | Yes | Yes |
| Model required | Yes | No | No |
| Online learning | Yes | No | Yes |
| Episode completion | Not needed | Required | Not needed |

![[RL - Lecture 4.pdf#page=24|RL - Lecture 4, page 24]]

![[RL - Lecture 4.pdf#page=25|RL - Lecture 4, page 25]]

Answer: C

![[RL - Lecture 4.pdf#page=26|RL - Lecture 4, page 26]]

Answer: D

![[RL - Lecture 4.pdf#page=27|RL - Lecture 4, page 27]]

Answer: A

- Why does Monte Carlo have zero bias but high variance?
	- It averages over the true returns which can vary massively.

## From Prediction to Control
![[RL - Lecture 4.pdf#page=29|RL - Lecture 4, page 29]]

![[RL - Lecture 4.pdf#page=30|RL - Lecture 4, page 30]]

![[RL - Lecture 4.pdf#page=32|RL - Lecture 4, page 32]]

- Exploration vs exploitation tradeoff...

## SARSA: On-Policy TD Control
![[RL - Lecture 4.pdf#page=34|RL - Lecture 4, page 34]]

![[RL - Lecture 4.pdf#page=35|RL - Lecture 4, page 35]]

![[RL - Lecture 4.pdf#page=36|RL - Lecture 4, page 36]]
- We are doing evaluation and improvement...


> [!CARD] $\epsilon$-Greedy Policy
> Choosing randomly between your actions with some probability but with a boost for the action that you believe to be best.
^q-yv36

![[RL - Lecture 4.pdf#page=38|RL - Lecture 4, page 38]]

- Termination is not guaranteed...

![[RL - Lecture 4.pdf#page=39|RL - Lecture 4, page 39]]
Answer: D

## Q-Learning Off-Policy TD Control
![[RL - Lecture 4.pdf#page=44|RL - Lecture 4, page 44]]
- Exploration-Exploitation Dilemma: We want to learn the optimal policy but we also want to explore!

![[RL - Lecture 4.pdf#page=46|RL - Lecture 4, page 46]]

![[RL - Lecture 4.pdf#page=47|RL - Lecture 4, page 47]]

![[RL - Lecture 4.pdf#page=50|RL - Lecture 4, page 50]]

SARSA vs Q-learning:
> [!CARD] **SARSA (on-policy)**
$$Q(S_t, A_t) \leftarrow Q(S_t, A_t) + \alpha\left[R_{t+1} + \gamma\, Q(S_{t+1}, A_{t+1}) - Q(S_t, A_t)\right]$$
*"What would happen if I follow my current policy?"*

> [!CARD] **Q-learning (off-policy)**
$$Q(S_t, A_t) \leftarrow Q(S_t, A_t) + \alpha\left[R_{t+1} + \gamma \max_{a} Q(S_{t+1}, a) - Q(S_t, A_t)\right]$$
*"What would happen if I acted optimally from now on?"*

![[RL - Lecture 4.pdf#page=51|RL - Lecture 4, page 51]]

![[RL - Lecture 4.pdf#page=52|RL - Lecture 4, page 52]]

![[RL - Lecture 4.pdf#page=53|RL - Lecture 4, page 53]]

![[RL - Lecture 4.pdf#page=54|RL - Lecture 4, page 54]]

- SARSA learns path A:
	- The distinction is this $\epsilon = 0.1$ 
	- SARSA is learning a safe path...
	- 10% chance you take a random action
	- SARSA is understanding this, it understands the randomness and the risk of going off the cliff and mitigates it by taking a further route.
![[RL - Lecture 4.pdf#page=55|RL - Lecture 4, page 55]]

- Q-learning takes path C:
	- This is because the policy is always acting optimally.
	- It learns the riskier path.

![[RL - Lecture 4.pdf#page=56|RL - Lecture 4, page 56]]

As we learn, this is what the reward functions look like.

![[RL - Lecture 4.pdf#page=57|RL - Lecture 4, page 57]]

- Path C - as $\epsilon$ decays, the chance of us falling off the cliff is very rare as there is less randomness so it eventually converges to G

- Assumptions of convergence here...

## Expected SARSA

- Middle ground between Q-Learning and SARSA

![[RL - Lecture 4.pdf#page=59|RL - Lecture 4, page 59]]

![[RL - Lecture 4.pdf#page=63|RL - Lecture 4, page 63]]

- Can be used on-policy or off-policy.
![[RL - Lecture 4.pdf#page=64|RL - Lecture 4, page 64]]

- Downside of Q-learning vs SARSA:
	- SARSA considers epsilon, which Q-learning doesn't

![[RL - Lecture 4.pdf#page=65|RL - Lecture 4, page 65]]

- Answer: C
- It averages over next actions.

## Double Learning
![[RL - Lecture 4.pdf#page=70|RL - Lecture 4, page 70]]

![[RL - Lecture 4.pdf#page=72|RL - Lecture 4, page 72]]

