---
flashcards:
  q-cmuy: { nid: 1791216040142, hash: mw2s8zvq, sync: j86m8j5h }
  q-7u4h: { nid: 1791216040155, hash: ymdjecyx, sync: pr7ugch6 }
  q-aq6v: { nid: 1791216040173, hash: zksqc4j4, sync: vr38vvvi }
  q-e5hh: { nid: 1791216040199, hash: jhfsaa98, sync: upf9uwnx }
  q-kdx5: { nid: 1791218987477, hash: 5zf7vmmi, sync: 8d4zm6zb }
  q-3bj5: { nid: 1794333506717, hash: rdhxywe9, sync: 8yiqrn24 }
  q-nk8f: { nid: 1794340756750, hash: pti3k475, sync: 4kfecmnb }
  q-68tb: { hash: 5q4vjudw }
  q-3g4i: { hash: rqia3z43 }
---
> [!TODO] TODO
> - [ ] Add formulas
>	- [ ] Add formula for bellman equation
>	- [ ] Add formula for V
>	- [ ] Add formula for Q etc.
>- [ ] Add defintions for Anki.
>- [ ] Run transcript through claude and check nothing else missed
>- [ ] Redo tutorials 1 and 2 with improved notes



![[Reinforcement Learning - Lecture 1.pdf]]

![[Reinforcement Learning - Lecture 1 pt2.pdf]]

## Formulas
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=6|Reinforcement Learning - Lecture 1 pt2, page 6]]

## How does RL fit with other types of ML
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=7|Reinforcement Learning - Lecture 1 pt2, page 7]]

## Challenges with RL
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=8|Reinforcement Learning - Lecture 1 pt2, page 8]]

> [!CARD] What are the challenges with RL?
> 1. Delayed consequences
> 2. Exploration vs exploitation
> 3. Credit assignment
> 4. Non-stationary
^q-cmuy

## Markov Decision Processes
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=10|Reinforcement Learning - Lecture 1 pt2, page 10]]

> [!CARD] Markov Decision Process (MDP)
> A model for sequential decision making when outcomes are uncertain.
> Formally defined by the tuple (S, A, P, R):
> 
> * $S$: Set of states - all possible situations 
> * $A$: Set of actions - all possible decisions 
> * $P(s′|s, a)$: Transition probabilities - how actions change states, the probability of reaching state $s'$ given you are in state $s$ applying action $a$
> * $R(s, a, s′)$: Reward function - immediate feedback for transitions
> 
> If you can specify the above, you can apply RL...
^q-7u4h

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=11|Reinforcement Learning - Lecture 1 pt2, page 11]]

> [!CARD] The RL Loop
> 
> 
^q-aq6v

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=12|Reinforcement Learning - Lecture 1 pt2, page 12]]

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=17|Reinforcement Learning - Lecture 1 pt2, page 17]]![[Reinforcement Learning - Lecture 1 pt2.pdf#page=18|Reinforcement Learning - Lecture 1 pt2, page 18]]
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=19|Reinforcement Learning - Lecture 1 pt2, page 19]]
* The probability of each outcome stays consistent throughout
* Stochastic - sometimes the agent gets stuck, it wants to move right but sometimes with some degree of probability we won't let it...

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=20|Reinforcement Learning - Lecture 1 pt2, page 20]]

> [!CARD] Markov Property
> The future is independent of the past given the present:
> $P(s_{t+1}|s_t, a_t, s_{t−1}, a_{t−1}, . . . , s_0, a_0) = P(s_{t+1}|s_t, a_t)$
> The current state contains all information needed to predict the future.
^q-e5hh

* Stock market is non-markovian as we do not see all the factors that impact the stock market prices
* State transition diagram
* State transition graph
* Transition graph
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=21|Reinforcement Learning - Lecture 1 pt2, page 21]]

> [!CARD] State Transition Diagram/Graph
> - Circles = states, 
> - Dots = actions (a1 or a2) the agent can choose 
> - Arrows out of a dot = possible next states, labelled with probability (p) and reward (r)
> - The p’s leaving each dot sum to 1
> - Square = terminal state (episode ends; no outgoing transitions)
^q-3bj5

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=22|Reinforcement Learning - Lecture 1 pt2, page 22]]

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=23|Reinforcement Learning - Lecture 1 pt2, page 23]]


## Policies and Returns
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=26|Reinforcement Learning - Lecture 1 pt2, page 26]]

> [!CARD] Policy
> A policy $\pi$ is a mapping from states to actions
> 
^q-kdx5


![[Reinforcement Learning - Lecture 1 pt2.pdf#page=27|Reinforcement Learning - Lecture 1 pt2, page 27]]

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=28|Reinforcement Learning - Lecture 1 pt2, page 28]]
* $\gamma = 0$ is shortsighted aka myopic (only immediate rewards matter)
* $\gamma = 0.9$ is balanced
* $\gamma = 1$ is far sighted - all rewards matter equally regardless of delay

> [!CARD] Discounted Return ($G_t$) 
> $$G_t = R_{t+1} + \gamma R_{t+2} + \gamma^2 R_{t+3} + \cdots = \sum_{k=0}^{\infty} \gamma^k R_{t+k+1}
> $$
> - $\gamma = 0$ is shortsighted aka myopic (only immediate rewards matter)
> - $\gamma = 0.9$ is balanced
> - $\gamma = 1$ is far sighted - all rewards matter equally regardless of delay
^q-nk8f



![[Reinforcement Learning - Lecture 1 pt2.pdf#page=29|Reinforcement Learning - Lecture 1 pt2, page 29]]
* Only immediate rewards matter


## Value Functions
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=32|Reinforcement Learning - Lecture 1 pt2, page 32]]

> [!CARD] State Value Function (V Function)
> The value of state S under policy $\pi$ is the expected return:
> $$
> V^\pi(s) = \mathbb{E}_\pi\left[G_t \mid S_t = s, \pi \right]$$
> Intuition: how good is it to be in state s?
^q-68tb


> [!CARD] Action Value Function (Q Function)
> The value of taking action a in the state s under policy $\pi$:
> $$Q^\pi(s,a) = \mathbb{E}_\pi\left[G_t \mid S_t = s, A_t = a, \pi \right]$$
> Intuition: how good is it to take action a in state s?
^q-3g4i


* We are not measuring a reward here, we are measuring the return

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=33|Reinforcement Learning - Lecture 1 pt2, page 33]]
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=34|Reinforcement Learning - Lecture 1 pt2, page 34]]
* The goal state is always terminal...
* Value functions tell us which states are good to be in.

## Bellman Equations
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=37|Reinforcement Learning - Lecture 1 pt2, page 37]]
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=42|Reinforcement Learning - Lecture 1 pt2, page 42]]
* We can determine the value of a state from the discounted value of the next state I end up in for a given policy. (RECURSIVE)
* Look at all potential outcomes that may happen for each and every action.
* Now we can bootstrap using this, we can determine things without running the agent for the full duration.

> [!CARD] Derivation of the Bellman Equation
> 
> $$
\begin{aligned}
V^\pi(s) &= \mathbb{E}[G_t \mid S_t = s, \pi] && \text{(expected return from state)} \\
&= \mathbb{E}[R_{t+1} + \gamma G_{t+1} \mid S_t = s, \pi] && \text{(break into immediate + future)} \\
&= \mathbb{E}\big[R_{t+1} + \gamma\, \mathbb{E}[G_{t+1} \mid S_{t+1}, \pi] \mid S_t = s, \pi\big] && \text{(linearity \& total expectation}^*\text{)} \\
&= \mathbb{E}[R_{t+1} + \gamma V^\pi(S_{t+1}) \mid S_t = s, \pi] && \text{(recursive value definition)} \\
&= \sum_{a} \pi(a \mid s) \sum_{s', r} P(s', r \mid s, a)\big[r + \gamma V^\pi(s')\big] && \text{(expand expectation)}
\end{aligned}
> $$

| Term              | Meaning                                                                                                                          |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| 𝑉𝜋(𝑠)          | **State-value function**: the expected total discounted return if you start in state 𝑠 and follow policy 𝜋 thereafter.         |
| 𝔼[ ⋅]            | **Expectation** over the randomness in the policy's action choices and the environment's transitions and rewards.                |
| 𝜋                | The **policy**, a rule for choosing actions. Conditioning on 𝜋 means actions are drawn from it.                                 |
| 𝜋(𝑎 ∣𝑠)        | Probability that the policy picks action 𝑎 in state 𝑠.                                                                         |
| 𝑆𝑡              | The state at time 𝑡.                                                                                                            |
| 𝑅𝑡+1            | The **immediate reward** received after acting at time 𝑡.                                                                       |
| 𝐺𝑡              | The **return**, the discounted sum of future rewards: 𝐺𝑡 =𝑅𝑡+1 +𝛾𝑅𝑡+2 +𝛾2𝑅𝑡+3 +…                                       |
| 𝐺𝑡+1            | The return from the next time step onward. Since 𝐺𝑡 =𝑅𝑡+1 +𝛾𝐺𝑡+1, this is the "future" part.                              |
| 𝛾 ∈[0,1]         | The **discount factor**. It weights future rewards less than immediate ones.                                                     |
| 𝑃(𝑠′,𝑟 ∣𝑠,𝑎) | The environment **dynamics**: the probability of moving to next state 𝑠′ and receiving reward 𝑟, given state 𝑠 and action 𝑎. |
| 𝑠′               | A possible next state.                                                                                                           |
| 𝑟                | A possible reward value.                                                                                                         |
| ∑𝑎               | Sum over all actions available in 𝑠, weighted by 𝜋(𝑎 ∣𝑠).                                                                    |
| ∑𝑠′,𝑟           | Sum over all next states and rewards, weighted by 𝑃(𝑠′,𝑟 ∣𝑠,𝑎).                                                             |
1. **Definition.** The value of a state is the expected return from it.
2. **Split the return.** Write 𝐺𝑡 =𝑅𝑡+1 +𝛾𝐺𝑡+1, which separates the immediate reward from everything after it.
3. **Inner expectation.** By linearity of expectation, 𝔼[𝑅𝑡+1 +𝛾𝐺𝑡+1] splits into two expectations. By the law of total expectation, 𝔼[𝐺𝑡+1] can be computed by first conditioning on 𝑆𝑡+1. This step relies on the **Markov property**: given 𝑆𝑡+1, the future doesn't depend on how you got there.
4. **Recognise 𝑉𝜋.** The inner term 𝔼[𝐺𝑡+1 ∣𝑆𝑡+1,𝜋] is exactly 𝑉𝜋(𝑆𝑡+1) by definition. This gives the recursive form.
5. **Expand the expectation.** Write the expectation explicitly. First average over actions with 𝜋(𝑎 ∣𝑠), then over outcomes with 𝑃(𝑠′,𝑟 ∣𝑠,𝑎). The result is the **Bellman expectation equation**.

**Backup diagram:**
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=43|Reinforcement Learning - Lecture 1 pt2, page 43]]

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=44|Reinforcement Learning - Lecture 1 pt2, page 44]]

Answer C: The Bellman equation expresses the relationship between current and future values.

NOTE **THE DERIVATION IS EXAMINABLE!!!** - add derivation to Anki

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=45|Reinforcement Learning - Lecture 1 pt2, page 45]]

## Optimal Policies
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=47|Reinforcement Learning - Lecture 1 pt2, page 47]]
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=48|Reinforcement Learning - Lecture 1 pt2, page 48]]

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=49|Reinforcement Learning - Lecture 1 pt2, page 49]]
* If the value in all states is better for one policy than another, then the policy is optimal.

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=49|Reinforcement Learning - Lecture 1 pt2, page 49]]![[Reinforcement Learning - Lecture 1 pt2.pdf#page=50|Reinforcement Learning - Lecture 1 pt2, page 50]]
* You can have multiple optimal policies
* All optimal policies can achieve the same values
* V (Value) function tells us the best state to be in
* Q function tells us the best action to take

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=52|Reinforcement Learning - Lecture 1 pt2, page 52]]

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=53|Reinforcement Learning - Lecture 1 pt2, page 53]]

* If we know Q*, we can use it act optimally, we can define a policy from it.
* We can choose the action that maximises Q for a given state.
* We can be greedy - we always choose the best values possible.

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=54|Reinforcement Learning - Lecture 1 pt2, page 54]]

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=55|Reinforcement Learning - Lecture 1 pt2, page 55]]


![[Reinforcement Learning - Lecture 1 pt2.pdf#page=56|Reinforcement Learning - Lecture 1 pt2, page 56]]

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=57|Reinforcement Learning - Lecture 1 pt2, page 57]]