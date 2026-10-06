---
flashcards:
  q-cmuy: { nid: 1791216040142, hash: mw2s8zvq, sync: c9bm3iag }
  q-7u4h: { nid: 1791216040155, hash: xepenrhe, sync: csiungcf }
  q-aq6v: { nid: 1791216040173, hash: zksqc4j4, sync: zskw8x2s }
  q-e5hh: { nid: 1791216040199, hash: jjpw9c7w, sync: kb5m6p6y }
  q-kdx5: { nid: 1791218987477, hash: 5zf7vmmi, sync: xhscvx2h }
---

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
> * $P(s′|s, a)$: Transition probabilities - how actions change states 
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
^q-e5hh

* Stock market is non-markovian as we do not see all the factors that impact the stock market prices
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=21|Reinforcement Learning - Lecture 1 pt2, page 21]]


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

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=29|Reinforcement Learning - Lecture 1 pt2, page 29]]
* Only immediate rewards matter


## Value Functions
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=32|Reinforcement Learning - Lecture 1 pt2, page 32]]

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

**Backup diagram:**
![[Reinforcement Learning - Lecture 1 pt2.pdf#page=43|Reinforcement Learning - Lecture 1 pt2, page 43]]

![[Reinforcement Learning - Lecture 1 pt2.pdf#page=44|Reinforcement Learning - Lecture 1 pt2, page 44]]

Answer C: The Bellman equation expresses the relationship between current and future values

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
