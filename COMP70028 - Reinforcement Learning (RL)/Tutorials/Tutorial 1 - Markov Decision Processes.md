![[RL - Tutorial 1.pdf]]

## 1 Understanding MDPs
### 1.1 MDP Formulation
***(a)  State and Action Spaces: Define the state space S and action space A for this problem. Be explicit about what each represents.***

S is the set of states: the location of the robot on the 1D track  $S = \{1,2,3,4\}$ 
A is the set of actions: $A = \{LEFT, RIGHT, STAY\}$

***(b) Transition Function: Assume deterministic transitions (the robot always moves as in- tended). Define the transition function P (s′|s, a) and write it out explicitly for at least 3 state-action pairs. What happens at the boundaries?***

$P(s'|s,a)$

$P(0|1,LEFT) = 1$
$P(1|1,STAY) = 1$
$P(0|1,RIGHT) = 0$
$P(3|4,STAY) = 0$


***(c) Reward Function: Design a reward function R(s, a, s′) where: reaching the goal gives +10, each step costs −1, and staying in place when not at the goal costs −2. Write out R(s, a, s′) for at least 3 cases.***

$R(s,a,s')$

$R(1,RIGHT,2) = -1$

$R(1,STAY,1) = -2$

$R(3,RIGHT,4) = +10$

### 1.2 The Markov Property
***(a) Pong, where the state is a single frame of the screen.*** No, this does not satisfy the Markov property as knowing where the ball is now is not sufficient to tell us where the ball is going next. If we knew the direction of then we make it satisfy the property. The future is dependent on the past.
***(b) Pong, where the state is the last 4 frames of the screen stacked together.***  Yes, it does, as we can infer where the ball is going. The future is not dependent on the past.
***(c) A robot arm, where the state is its joint angles only.*** No as we don't know where the joint's are going. The future is dependent on the past.
***(d) A robot arm, where the state is its joint angles and joint velocities.*** Yes, as we know where the joints are going next. The future is not dependent on the past.
***(e) Texas Hold’em poker, where the state is your own two cards and the cards on the table.***  No, as we don't know what cards will be drawn next. The future is dependent on the previously drawn cards.
***(f) Chess, where the state is the position of the pieces on the board.*** Yes, the future is independent of what's happened in the past.

### 1.3 Computing Returns
(a) $\gamma = 0.9 \implies G_0 = 1 + 0.9 \times 2 + 0.9^2 \times 5 + 0.9^3 \times 0 = 6.85$
(b) $\gamma = 0.5 \implies G_0 = 3.25$
(c) with $\gamma = 0$ the agent only cares about the return now so $G_0 = 1$
(d) ultimately we care about finding our goal state sooner rather than later, we prefer rewards now over rewards tomorrow so we should discount rewards that come later.
(e) Will be the infinite sum of a geometric sequence:
$S = \sum_{n=0}^{\infty} a r^n = \frac{a}{1 - r} \quad \text{for } |r| < 1$

or for constant reward r:

$G_0 = \sum_{n=0}^{\infty} r \gamma^n = \frac{r}{1 - \gamma} \quad \text{for } |\gamma| < 1$

So $G_0 = \frac{1}{1-0.9}=10$

(f) if $\gamma = 1$ $G_0 \to \infty$ is infinitely large, this is not acceptable for continuing tasks as if we care about future rewards as much as current rewards, there is no incentive to reach the terminal state.

## 2 Bellman Equation Derivation
![[Scan from 2026-10-09 05_13_50 PM.pdf#page=1]]
![[Scan from 2026-10-09 05_13_50 PM.pdf#page=2]]

**(c) Explain in words what this equation means. Why is it recursive?**

~~The equation means that the expected payoff in the current state is equal to the sum of expected payoffs possible from the the current state and the sum of all the expected payoffs from all possible future states.~~ It's recursive because we need to compute the payoff of the final state and work backwards to the current state. ***Is this a good definition?*** - no this is completely wrong

The Bellman equation says the value of a state under policy π is the expected immediate reward plus the discounted value of the next state, averaged over the actions the policy might take and the transitions the environment might produce: $V^π(s) = Σ_a π(a|s) Σ_{s’,r} P(s’,r|s,a)[r + γV^π(s’)].$

The value V^π(s) of being in state s under policy π is found by summing over every action a, weighting each by the probability π(a|s) that the policy picks it, and then summing over every possible next state s’ and reward r, weighting each by its transition probability P(s’,r|s,a). Within each of those outcomes, you add the immediate reward r to the value V^π(s’) of the state you land in, shrunk by the discount factor γ (between 0 and 1) so that future returns count for less than immediate ones.

From claude ^ I can probably refine these.
## 3 Solving the Bellman Equation for a Fixed Policy
### Exact Policy Evaluation
(a) ***Compute the expected immediate reward rπ(s) = P a π(a|s) P s′ P (s′|s, a)R(s, a, s′) for each state, and the state transition matrix Pπ under π.***

The policy is deterministic! i.e. if we are in state $S_1$, then we always take action $a_1$ this means that:

$\pi(a_1|s_1)=1$ 
$\pi(a_2|s_2)=1$ 
$\pi(a_1|s_2)=0$ 
$\pi(a_2|s_1)=0$

If we are in state 2 we always employ action 2

~~So this means that $r_\pi(s_1) = 0.6 \times 4 + 0.4 \times 1 + 1.0 \times 3 = 5.8$~~ < incorrect - ignore action 2 in state 1, the policy is deterministic!

$r_\pi(s_1) = 0.6 \times 4 + 0.4 \times 1 = 2.8$ < correct answer 

And $r_\pi(s_2) = 1.0 \times 1 + 0.2 \times -2 + 0.8 \times 0 = 0.6$  < incorrect - ignore action 1 in state 2, the policy is deterministic!

$r_\pi(s_2) = 0.2 \times -2 + 0.8 \times 0 = -0.4$

State the transition matrix $P_\pi$ under $\pi$.

**Transition matrix, 1 per action?*

Here we don't need one per action as the policy is deterministic?

|       | $S_1$ | $S_2$ |
| ----- | ----- | ----- |
| $S_1$ | 0.6   | 0.4   |
| $S_2$ | 0.2   | 0.8   |

(b) Write down the Bellman equation for V π(s1) and V π(s2). This gives two linear equations in two unknowns; solve them exactly.

Reminder: ![[Pasted image 20261010150408.png|343]]
or, more usefully: ![[Pasted image 20261010161730.png|375]]

![[Scan from 2026-10-10 03_27_07 PM.pdf]]

This is incorrect, the numbers are wrong but correct jist, we can come back to this...

(c) 

**In matrix form the Bellman equations read:**

$V^\pi = r_\pi + \gamma P_\pi V^\pi$
So, $V^\pi = (I - \gamma P_\pi)^{-1} r_\pi$

$V^\pi = r_\pi + \gamma P_\pi V^\pi$ — start

$V^\pi - \gamma P_\pi V^\pi = r_\pi$ — move $V^\pi$ terms together

$(I - \gamma P_\pi) V^\pi = r_\pi$ — factor out $V^\pi$ (insert $I$)

$V^\pi = (I - \gamma P_\pi)^{-1} r_\pi$ — left-multiply by inverse

***Why does this become impractical for MDPs with many states?***

Inverting a matrix of dimensions $S \times S$ costs $O(S^3)$, which quickly becomes infeasible as the number of states grows. This motivates the iterative models...

(d) Q is the value of a given state for a given action.

![[Pasted image 20261013105128.png]]

![[Pasted image 20261013105526.png]]

(e)

![[Pasted image 20261013105540.png]]

## 4 Optimal Value Functions and Policies
### 4.1 From $Q^*$ to $V^*$ to $\pi^*$
![[Pasted image 20261013110507.png]]

### 4.2 Optimal Values and Reward Design
![[Pasted image 20261013111427.png]]

![[Pasted image 20261013111446.png]]
## Solutions
![[70028_1_model_answer.pdf]]