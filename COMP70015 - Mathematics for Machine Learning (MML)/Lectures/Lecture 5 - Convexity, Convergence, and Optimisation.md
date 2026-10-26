---
flashcards:
  q-g76d: { nid: 1792517386818, hash: q27ifvp4, sync: s8ua7zmc }
  q-7y59: { nid: 1792517386856, hash: ge6qwbcn, sync: rarpbztj }
  q-shwr: { nid: 1792517386920, hash: ingg6rya, sync: km8vcfup }
  q-u5er: { nid: 1792517386987, hash: ss4g54p6, sync: 3hdjbnix }
  q-vutq: { nid: 1792517387041, hash: 9aui2ekk, sync: 448ecagg }
---

![[MML - Lecture 5.pdf]]

- When we do optimisation we hope to find a global minimum...

## When does gradient descent work?

![[MML - Lecture 5.pdf#page=2|MML - Lecture 5, page 2]]

![[MML - Lecture 5.pdf#page=3|MML - Lecture 5, page 3]]

![[MML - Lecture 5.pdf#page=4|MML - Lecture 5, page 4]]

![[MML - Lecture 5.pdf#page=5|MML - Lecture 5, page 5]]

> [!CARD] A progress bound in gradient descent.
> Every step in gradient descent is getting better. i.e. the loss is getting smaller.
^q-g76d

![[MML - Lecture 5.pdf#page=6|MML - Lecture 5, page 6]]

![[MML - Lecture 5.pdf#page=7|MML - Lecture 5, page 7]]
- We can't prove this because we don't know what $L(\theta)$ is...
- Doesn't matter what loss or model we use.

![[MML - Lecture 5.pdf#page=8|MML - Lecture 5, page 8]]

![[MML - Lecture 5.pdf#page=9|MML - Lecture 5, page 9]]


![[MML - Lecture 5.pdf#page=10|MML - Lecture 5, page 10]]

![[MML - Lecture 5.pdf#page=11|MML - Lecture 5, page 11]]

![[MML - Lecture 5.pdf#page=12|MML - Lecture 5, page 12]]

![[MML - Lecture 5.pdf#page=13|MML - Lecture 5, page 13]]

We approximate the function with the Taylor expansion.

> [!CARD] Assumptions required to prove that a step of gradient descent “improves” things, i.e. reduces the loss. $\mathcal{L}(\theta^{(t+1)}) \leq \mathcal{L}(\theta^{(t)}) - c, \qquad c \in \mathbb{R}_+$
> - Assumption 1: a twice-differentiable loss
> $$ 
> \mathcal{L}(\boldsymbol{w}) \approx \mathcal{L}(\boldsymbol{v})+ \underbrace{\nabla \mathcal{L}(\boldsymbol{v})(\boldsymbol{w}-\boldsymbol{v})}_{\text{first order: the gradient}}+ \underbrace{\frac{1}{2}(\boldsymbol{w}-\boldsymbol{v})^{\top} \boldsymbol{H}(\boldsymbol{v})(\boldsymbol{w}-\boldsymbol{v})}_{\text{second order: the Hessian } \boldsymbol{H}(\boldsymbol{v})}$$
> - Assumption 2: Lipschitz Smoothness 
>$$ \|\nabla \mathcal{L}(\boldsymbol{w}) - \nabla \mathcal{L}(\boldsymbol{v})\| \leq L \|\boldsymbol{w} - \boldsymbol{v}\|$$
>Lipschitz smoothness (L-smoothness) means the gradient of the loss can't change faster than a constant rate $L$, so the curvature is bounded and the function can never bend more sharply than a quadratic with curvature $L$. This is why a step size of $1/L$ guarantees gradient descent makes progress.
^q-7y59

![[MML - Lecture 5.pdf#page=14|MML - Lecture 5, page 14]]

> [!TODO] Learn this proof!


![[MML - Lecture 5.pdf#page=15|MML - Lecture 5, page 15]]


![[MML - Lecture 5.pdf#page=16|MML - Lecture 5, page 16]]

![[MML - Lecture 5.pdf#page=17|MML - Lecture 5, page 17]]

![[MML - Lecture 5.pdf#page=18|MML - Lecture 5, page 18]]

![[MML - Lecture 5.pdf#page=19|MML - Lecture 5, page 19]]

![[MML - Lecture 5.pdf#page=20|MML - Lecture 5, page 20]]

- When I make a step, I can't make things worse.

- What about the LOCAL MINIMA problem.

![[MML - Lecture 5.pdf#page=21|MML - Lecture 5, page 21]]
#IMPORTANT #examinable 

![[MML - Lecture 5.pdf#page=22|MML - Lecture 5, page 22]]

![[MML - Lecture 5.pdf#page=23|MML - Lecture 5, page 23]]

![[MML - Lecture 5.pdf#page=24|MML - Lecture 5, page 24]]

![[MML - Lecture 5.pdf#page=26|MML - Lecture 5, page 26]]

![[MML - Lecture 5.pdf#page=27|MML - Lecture 5, page 27]]

> [!CARD] Secant definition of convexity - for all x and y:
	> - We are smoothly trading off using t, the value of the function in output space:
	> - ![[Pasted image 20261020093650.png]]
	> - We can trade it off, inside the function in the input space:
	> - ![[Pasted image 20261020093718.png]]
	> - The Secant should always be above the function
^q-shwr

- Tangent definition of convexity:
	- The Tangent should always be below the function for convexity
- Hessian definition of convexity

![[MML - Lecture 5.pdf#page=28|MML - Lecture 5, page 28]]

![[MML - Lecture 5.pdf#page=29|MML - Lecture 5, page 29]]

![[MML - Lecture 5.pdf#page=30|MML - Lecture 5, page 30]]

![[MML - Lecture 5.pdf#page=31|MML - Lecture 5, page 31]]

![[MML - Lecture 5.pdf#page=32|MML - Lecture 5, page 32]]

- What does it mean to converge?
> [!CARD] Convergence definition
>a sequence x_1, x_2, ... is said to converge to a limit T if for any epsilon > 0 we have an integer K such that $\forall M > K, \; |x_M - T| < \epsilon$
^q-u5er

![[MML - Lecture 5.pdf#page=33|MML - Lecture 5, page 33]]

![[MML - Lecture 5.pdf#page=34|MML - Lecture 5, page 34]]

![[MML - Lecture 5.pdf#page=35|MML - Lecture 5, page 35]]

![[MML - Lecture 5.pdf#page=36|MML - Lecture 5, page 36]]

![[MML - Lecture 5.pdf#page=37|MML - Lecture 5, page 37]]

![[MML - Lecture 5.pdf#page=38|MML - Lecture 5, page 38]]


![[MML - Lecture 5.pdf#page=39|MML - Lecture 5, page 39]]

![[MML - Lecture 5.pdf#page=40|MML - Lecture 5, page 40]]

![[MML - Lecture 5.pdf#page=41|MML - Lecture 5, page 41]]

![[MML - Lecture 5.pdf#page=42|MML - Lecture 5, page 42]]

![[MML - Lecture 5.pdf#page=43|MML - Lecture 5, page 43]]

![[MML - Lecture 5.pdf#page=44|MML - Lecture 5, page 44]]

![[MML - Lecture 5.pdf#page=45|MML - Lecture 5, page 45]]

![[MML - Lecture 5.pdf#page=46|MML - Lecture 5, page 46]]

![[MML - Lecture 5.pdf#page=47|MML - Lecture 5, page 47]]

![[MML - Lecture 5.pdf#page=48|MML - Lecture 5, page 48]]

> [!CARD] Eigenvalues and eigenvectors
>for a square matrix $\boldsymbol{A} \in \mathbb{R}^{n \times n}$, a non-zero vector $\boldsymbol{v}$ is an eigenvector of $\boldsymbol{A}$ with corresponding eigenvalue $\lambda$ if $\boldsymbol{A}\boldsymbol{v} = \lambda \boldsymbol{v}$, i.e. $\boldsymbol{A}$ only scales $\boldsymbol{v}$ without changing its direction. The eigenvalues are the roots of the characteristic equation $\det(\boldsymbol{A} - \lambda \boldsymbol{I}) = 0$.
>
>**Intuition:** most vectors get rotated and stretched when you apply a matrix, but eigenvectors are the special directions that only get stretched or flipped, and the eigenvalue tells you by how much.
^q-vutq

![[MML - Lecture 5.pdf#page=49|MML - Lecture 5, page 49]]

- Linear transformations STRETCH the space...
- 3blue1brown video on eigenvalues and eigenvectors is useful.

![[MML - Lecture 5.pdf#page=50|MML - Lecture 5, page 50]]

![[MML - Lecture 5.pdf#page=51|MML - Lecture 5, page 51]]

![[MML - Lecture 5.pdf#page=52|MML - Lecture 5, page 52]]

![[MML - Lecture 5.pdf#page=53|MML - Lecture 5, page 53]]

![[MML - Lecture 5.pdf#page=54|MML - Lecture 5, page 54]]

![[MML - Lecture 5.pdf#page=55|MML - Lecture 5, page 55]]

- When you choose alpha (your learning rate) to be less than 2 over your max eigen val, you will always converge in linear regression...

![[MML - Lecture 5.pdf#page=56|MML - Lecture 5, page 56]]

![[MML - Lecture 5.pdf#page=57|MML - Lecture 5, page 57]]

- When does it converge
- What does it mean to converge
- When do we have a unique minimum

