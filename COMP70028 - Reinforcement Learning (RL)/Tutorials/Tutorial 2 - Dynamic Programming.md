![[RL - Tutorial 2.pdf]]

## 1 Policy Evaluation
### 1.1 Hand Calculation of Policy Evaluation
![[Scan from 2026-10-16 04_48_57 PM.pdf]]

![[Scan from 2026-10-16 04_56_04 PM.pdf]]

## 2 Policy Iteration
### Hand Calculation of Policy Iteration
![[Scan from 2026-10-16 05_27_43 PM.pdf]]The greedy policy picks, in each state, the action with the highest Q-value:

$$\pi_1(s) = \arg\max_a Q^{\pi_0}(s,a)$$

Just compare across each row of the Q table.

**State s₁:** compare Q(s₁, a₁) = 10 and Q(s₁, a₂) = 7.5. Since 10 > 7.5, π₁(s₁) = a₁.

**State s₂:** compare Q(s₂, a₁) = 10 and Q(s₂, a₂) = 5. Since 10 > 5, π₁(s₂) = a₁.

## Result

$$\pi_1(s_1) = a_1, \quad \pi_1(s_2) = a_1$$

|State|π₀|π₁|Changed?|
|---|---|---|---|
|s₁|a₁|a₁|No|
|s₂|a₂|a₁|Yes|

**Interpretation:** in s₂, π₀ was taking a₂, which mostly keeps you in s₂ (worth 5). Switching to a₁ sends you straight to s₁, which is the more valuable state (worth 10), and also earns a reward of 1 instead of the 0 or −2 that a₂ gives. So the improvement is intuitive.

Because the policy changed, policy iteration hasn't converged yet. The next step is to evaluate π₁ (solve for V^π₁), then repeat the improvement step. The algorithm stops once the greedy policy comes out the same as the one you just evaluated.

(b)

$$V^{\pi_1}(s) = \sum_{s',r} p(s',r|s,\pi_1(s))\left[r + \gamma V^{\pi_1}(s')\right]$$

## Step 1: Write the equations

**s₁, taking a₁:** outcomes (s₁, r = 4) with probability 0.6 and (s₂, r = 1) with probability 0.4.

$$V^{\pi_1}(s_1) = 0.6(4 + 0.9V^{\pi_1}(s_1)) + 0.4(1 + 0.9V^{\pi_1}(s_2))$$

**s₂, taking a₁:** outcome (s₁, r = 1) with probability 1.0.

$$V^{\pi_1}(s_2) = 1.0(1 + 0.9V^{\pi_1}(s_1))$$

## Step 2: Expand

Writing V₁ and V₂ for short:

$$V_1 = 2.8 + 0.54V_1 + 0.36V_2$$

$$V_2 = 1 + 0.9V_1$$

## Step 3: Solve

The second equation already gives V₂ in terms of V₁, so substitute it into the first:

$$V_1 = 2.8 + 0.54V_1 + 0.36(1 + 0.9V_1) = 3.16 + 0.864V_1$$

$$0.136V_1 = 3.16 \quad \Rightarrow \quad V_1 = \frac{395}{17} \approx 23.24$$

Then back-substitute:

$$V_2 = 1 + 0.9 \times 23.24 \approx 21.91$$

## Result

|State|V^π₀|V^π₁|
|---|---|---|
|s₁|10|23.24|
|s₂|5|21.91|

**Checks:**

- Plugging back in: 2.8 + 0.54(23.24) + 0.36(21.91) ≈ 23.24 ✓
- The policy improvement theorem guarantees V^π₁ ≥ V^π₀ in every state, and both values went up ✓

The big jump in s₁ makes sense too: under π₀, whenever you drifted to s₂ you tended to get stuck there earning little, whereas under π₁ you bounce straight back to s₁.

(c)
Comparing state by state:

**s₁:**

$$V^{\pi_1}(s_1) = \frac{395}{17} \approx 23.24 \quad > \quad V^{\pi_0}(s_1) = 10$$

Improvement of about 13.24 ✓

**s₂:**

$$V^{\pi_1}(s_2) = \frac{745}{34} \approx 21.91 \quad > \quad V^{\pi_0}(s_2) = 5$$

Improvement of about 16.91 ✓

|State|V^π₀|V^π₁|Difference|
|---|---|---|---|
|s₁|10|23.24|+13.24|
|s₂|5|21.91|+16.91|

So V^π₁(s) > V^π₀(s) in both states, strictly. This is consistent with the policy improvement theorem, which guarantees V^π₁ ≥ V^π₀ everywhere when π₁ is greedy with respect to Q^π₀.

Interestingly, s₁ also improved even though the action taken there didn't change. That's because s₁'s value depends on what happens after you land in s₂, and π₁ now behaves much better in s₂. Improvements in one state propagate to every state that can reach it.

(d)
## Step 1: Discounted next-state values

Using V^π₁(s₁) = 395/17 ≈ 23.235 and V^π₁(s₂) = 745/34 ≈ 21.912:

- 0.9 × V^π₁(s₁) ≈ 20.912
- 0.9 × V^π₁(s₂) ≈ 19.721

(Keeping three decimals here matters, because one of the comparisons below is fairly close.)

## Step 2: Compute Q^π₁

**Q(s₁, a₁):** (s₁, r = 4) with probability 0.6, (s₂, r = 1) with probability 0.4

$$Q^{\pi_1}(s_1,a_1) = 0.6(4 + 20.912) + 0.4(1 + 19.721) = 14.947 + 8.288 = 23.235$$

**Q(s₁, a₂):** (s₂, r = 3) with probability 1.0

$$Q^{\pi_1}(s_1,a_2) = 1.0(3 + 19.721) = 22.721$$

**Q(s₂, a₁):** (s₁, r = 1) with probability 1.0

$$Q^{\pi_1}(s_2,a_1) = 1.0(1 + 20.912) = 21.912$$

**Q(s₂, a₂):** (s₁, r = −2) with probability 0.2, (s₂, r = 0) with probability 0.8

$$Q^{\pi_1}(s_2,a_2) = 0.2(-2 + 20.912) + 0.8(0 + 19.721) = 3.782 + 15.777 = 19.559$$

||a₁|a₂|
|---|---|---|
|s₁|**23.24**|22.72|
|s₂|**21.91**|19.56|

**Sanity check:** π₁ takes a₁ in both states, and Q(s₁, a₁) = V^π₁(s₁) and Q(s₂, a₁) = V^π₁(s₂) ✓

## Step 3: Greedy policy π₂

- **s₁:** 23.24 > 22.72, so π₂(s₁) = a₁
- **s₂:** 21.91 > 19.56, so π₂(s₂) = a₁

$$\pi_2(s_1) = a_1, \quad \pi_2(s_2) = a_1$$

## Conclusion

**π₂ = π₁, so policy iteration has converged.**

When the greedy policy doesn't change, every state satisfies

$$V^{\pi_1}(s) = \max_a Q^{\pi_1}(s,a)$$

which is exactly the Bellman optimality equation. Its solution is unique, so π₁ must be optimal. In a finite MDP, policy iteration is guaranteed to reach this point in a finite number of steps, since there are only finitely many deterministic policies and each iteration strictly improves until it stops.

One thing worth noticing: the margin in s₁ is only about 0.51 (23.24 vs 22.72). a₂ gives a higher immediate reward (3 vs an expected 2.8), but it always sends you to s₂, which is the less valuable state. a₁ wins because it keeps you in s₁ 60% of the time.

## Solutions
![[tutorial_2_solutions.pdf]]