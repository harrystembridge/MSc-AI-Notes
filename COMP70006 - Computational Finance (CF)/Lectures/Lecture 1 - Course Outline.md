![[Lecture 00 - Computational Finance.pdf]]

![[Lecture 00 - Computational Finance.pdf#page=12|Lecture 00 - Computational Finance, page 12]]
![[Lecture 00 - Computational Finance.pdf#page=13|Lecture 00 - Computational Finance, page 13]]

Let $X$ be the payoff. A fair coin gives $P(\text{no heads in two flips}) = \left(\tfrac12\right)^2 = \tfrac14$, so

$$P(\text{at least one head}) = 1 - \tfrac14 = \tfrac34.$$

Expected value:

$$E[X] = \tfrac34 \cdot £9 + \tfrac14 \cdot £0 = £6.75.$$

The proposition is worth **£6.75** in expectation, assuming a fair coin and a risk-neutral valuation.

Is this actually correct? no

Using the basic propositions as the pricing basis (no-arbitrage, not expected value):

**State prices**

- Proposition #1 (pay £1, get £3 on heads): $3q_H = 1 \Rightarrow q_H = \tfrac13$.
- Proposition #2 (pay £1, get £1 for sure): $q_H + q_T = 1 \Rightarrow q_T = \tfrac23$.

**Backward induction**

After the first flip, the node values (as on the slide) are:

- Head: both outcomes pay £9, so the node is worth £9.
- Tail: pays £9 on heads and £0 on tails, so the node is worth $9q_H = £3$.

At the root, a bet paying £9 on heads and £3 on tails splits as a sure £3 plus £6 on heads:

$$V = 3 + 6q_H = 3 + 6\cdot\tfrac13 = £5.$$

**Equivalent direct check**

The proposition pays £0 only on TT and £9 otherwise:

$$V = 9\left(1 - q_T^2\right) = 9\left(1-\tfrac49\right) = £5.$$

The new proposition is worth **£5**.