---
flashcards:
  q-6844: { nid: 1792066025230, hash: 5wzubuax, sync: 7ina2trp }
  q-ycum: { nid: 1792066025264, hash: fxcfu8ee, sync: hbm3j7ig }
  q-ig4r: { nid: 1792066025288, hash: twd43ir5, sync: u8sx2wtb }
---

![[MML - Lecture 3.pdf]]

* The identity matrix, is 1s along the diagonal and 0s everywhere else

> [!CARD] Identity Matrix
> $$
^q-6844
I = \begin{pmatrix}
1 & 0 & \cdots & 0 \\
0 & 1 & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & 1
\end{pmatrix} $$
> For a 3×3 case specifically:
> 
> $$
I_3 = \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix} $$

* When we multiply something by the identity matrix, it just gives itself i.e. $\mathbf{X} \times \mathbf{I} = \mathbf{X}$ 

![[MML - Lecture 3.pdf#page=2|MML - Lecture 3, page 2]]

![[MML - Lecture 3.pdf#page=3|MML - Lecture 3, page 3]]

![[MML - Lecture 3.pdf#page=4|MML - Lecture 3, page 4]]

![[MML - Lecture 3.pdf#page=5|MML - Lecture 3, page 5]]

![[MML - Lecture 3.pdf#page=6|MML - Lecture 3, page 6]]


> [!CARD] What is $\lambda \times \mathbf{I_3}$?
> $$
^q-ycum
\lambda \times I_3 = \begin{pmatrix}
\lambda & 0 & 0 \\
0 & \lambda & 0 \\
0 & 0 & \lambda
\end{pmatrix} $$

![[MML - Lecture 3.pdf#page=7|MML - Lecture 3, page 7]]


![[MML - Lecture 3.pdf#page=8|MML - Lecture 3, page 8]]

![[MML - Lecture 3.pdf#page=9|MML - Lecture 3, page 9]]

![[MML - Lecture 3.pdf#page=10|MML - Lecture 3, page 10]]

![[MML - Lecture 3.pdf#page=11|MML - Lecture 3, page 11]]

> [!CARD] What is the ith canonical basis vector e?
> $$
^q-ig4r
e_i = \begin{pmatrix} 0 \\ \vdots \\ 0 \\ 1 \\ 0 \\ \vdots \\ 0 \end{pmatrix} \leftarrow i\text{-th position} $$
> We can use this to isolate terms in a vector and we can of course transpose it.

* The sum of the matrices is element wise.
* The outer product of 2 vectors is a matrix.
![[MML - Lecture 3.pdf#page=12|MML - Lecture 3, page 12]]

> [!CARD] The Squared 2-norm (squared Euclidean norm) of a vector
> The squared 2-norm (squared Euclidean norm) of a vector $x \in \mathbb{R}^n$ is:
> 
>$$
\|x\|_2^2 = \sum_{i=1}^n x_i^2 = x^\top x $$
> 
> A few useful facts:
>
>- It's the sum of squares of the components — always non-negative, zero only when $x = 0$.
>- It equals the dot product of $x$ with itself: $\|x\|_2^2 = x \cdot x = x^\top x$.
>- Unlike $\|x\|_2$ itself, the squared norm has no square root, which makes it smooth (differentiable everywhere) and easy to differentiate:
>
>$$
\nabla_x \left( \|x\|_2^2 \right) = 2x $$
>
>This is why it shows up constantly in optimization and ML (e.g. least squares, ridge regression, gradient descent) — it avoids the non-smoothness of $\sqrt{\cdot}$ at $x=0$ while still penalizing large deviations.

* When you perform the inner product of two vectors you get a scalar: 
![[MML - Lecture 3.pdf#page=13|MML - Lecture 3, page 13]]

> [!CARD] The outer product of 2 vectors
> For $u \in \mathbb{R}^m$ and $v \in \mathbb{R}^n$, the outer product is: 
> $$ u v^\top = \begin{pmatrix} u_1 \\ u_2 \\ \vdots \\ u_m \end{pmatrix}
\begin{pmatrix} v_1 & v_2 & \cdots & v_n \end{pmatrix} = \begin{pmatrix}
u_1 v_1 & u_1 v_2 & \cdots & u_1 v_n \\
u_2 v_1 & u_2 v_2 & \cdots & u_2 v_n \\
\vdots & \vdots & \ddots & \vdots \\
u_m v_1 & u_m v_2 & \cdots & u_m v_n
\end{pmatrix} $$
>
> **Dimensions:**
>
> $$
\underbrace{u}_{m \times 1} \; \underbrace{v^\top}_{1 \times n} = \underbrace{uv^\top}_{m \times n} $$
> 
> So $u$ is $m \times 1$, $v^\top$ is $1 \times n$, and the result $uv^\top$ is an $m \times n$ matrix — contrast with the inner (dot) product $u^\top v$, which requires $m = n$ and produces a scalar ($1\times1$).

> [!CARD] The Kronecker Delta
> The Kronecker delta is defined as:
> 
> $$
\delta_{ij} = \begin{cases} 1 & \text{if } i = j \\ 0 & \text{if } i \neq j \end{cases} $$
> It's essentially an indicator for index equality, and it's exactly the entries of the identity matrix:
>
>$$
I_{ij} = \delta_{ij} $$
Useful property — it acts as a "selector" under summation:
> $$
\sum_j \delta_{ij} \, x_j = x_i $$
> It isolates terms in a summations.
> Let $x = (5, 7, 2)$, so $x_1=5,\ x_2=7,\ x_3=2$. Fix $i=2$:
> $$ \sum_{j=1}^{3} \delta_{2j}\, x_j = \delta_{21}x_1 + \delta_{22}x_2 + \delta_{23}x_3 = 0\cdot 5 + 1\cdot 7 + 0\cdot 2 = 7 $$
> All terms vanish except the one where $j=i=2$, so the sum just "picks out" $x_2$ — confirming $\sum_j \delta_{ij}x_j = x_i$.
> 

> [!CARD] The $diag$ function.
> $$
\operatorname{diag}(2, 5, 3) =
\begin{pmatrix}
2 & 0 & 0 \\
0 & 5 & 0 \\
0 & 0 & 3
\end{pmatrix}$$
> 
> $(\operatorname{diag}(x))_{ij} = x_i\,\delta_{ij}$ — puts vector entries on the diagonal, zero elsewhere.

> [!CARD] The Hadamard Product
> $$
\begin{pmatrix} 2 \\ 3 \\ 4 \end{pmatrix} \odot \begin{pmatrix} 5 \\ 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 10 \\ 3 \\ 8 \end{pmatrix}$$
$(u \odot v)_i = u_i v_i$ — elementwise multiplication, same-shape in, same-shape out.
> $$
u \odot v = \operatorname{diag}(u)\, v$$
> 
> Check: $\operatorname{diag}(u)v$ has $i$-th entry $\sum_j \operatorname{diag}(u)_{ij} v_j = u_i v_i$, matching $(u\odot v)_i$.


![[MML - Lecture 3.pdf#page=14|MML - Lecture 3, page 14]]

![[MML - Lecture 3.pdf#page=15|MML - Lecture 3, page 15]]

![[MML - Lecture 3.pdf#page=16|MML - Lecture 3, page 16]]

> [!CARD] The Jacobian
> For $f:\mathbb{R}^n \to \mathbb{R}^m$, the Jacobian is:
> $$
J = \begin{pmatrix}
\dfrac{\partial f_1}{\partial x_1} & \cdots & \dfrac{\partial f_1}{\partial x_n} \\
\vdots & \ddots & \vdots \\
\dfrac{\partial f_m}{\partial x_1} & \cdots & \dfrac{\partial f_m}{\partial x_n}
\end{pmatrix}, \quad J_{ij} = \frac{\partial f_i}{\partial x_j} $$
$m \times n$ matrix of all first-order partial derivatives.


![[MML - Lecture 3.pdf#page=17|MML - Lecture 3, page 17]]

![[MML - Lecture 3.pdf#page=18|MML - Lecture 3, page 18]]

* Limits of the linear model is often we want to predict something constrained, maybe just something positive or classificatoin.

## Logistic Regression

![[MML - Lecture 3.pdf#page=19|MML - Lecture 3, page 19]]

![[MML - Lecture 3.pdf#page=20|MML - Lecture 3, page 20]]


Where S is the predicted probabilities and y is the actual label 1 or 0

![[MML - Lecture 3.pdf#page=21|MML - Lecture 3, page 21]]

![[MML - Lecture 3.pdf#page=22|MML - Lecture 3, page 22]]
* Kronecker delta in play here


![[MML - Lecture 3.pdf#page=23|MML - Lecture 3, page 23]]

![[MML - Lecture 3.pdf#page=24|MML - Lecture 3, page 24]]

![[MML - Lecture 3.pdf#page=25|MML - Lecture 3, page 25]]

![[MML - Lecture 3.pdf#page=26|MML - Lecture 3, page 26]]

To differentiate, we break it out into an outer, middle and inner function and differentiate seperately and times together (chain rule)

![[MML - Lecture 3.pdf#page=27|MML - Lecture 3, page 27]]

![[MML - Lecture 3.pdf#page=28|MML - Lecture 3, page 28]]

The Hessian tells us about the curvature of a function.

![[MML - Lecture 3.pdf#page=29|MML - Lecture 3, page 29]]

Final graph represents our Hessian, the derivative of the derivative tells us about the curvature of the function.

![[MML - Lecture 3.pdf#page=30|MML - Lecture 3, page 30]]

![[MML - Lecture 3.pdf#page=31|MML - Lecture 3, page 31]]

> [!CARD] Epoch 
> The number of iterations it takes for you to see your entire data set at least once.

* Full gradient decent means each iteration sees all of the data.


![[MML - Lecture 3.pdf#page=32|MML - Lecture 3, page 32]]

![[MML - Lecture 3.pdf#page=33|MML - Lecture 3, page 33]]

![[MML - Lecture 3.pdf#page=34|MML - Lecture 3, page 34]]

* If the learning rate is too high, we end up over shooting!
* The Jacobian tells us what direction to move in.
* What does the Hessian show us?

* If we have a low learning rate and a small number of steps - we won't get very far down the gradient...
![[MML - Lecture 3.pdf#page=35|MML - Lecture 3, page 35]]

![[MML - Lecture 3.pdf#page=36|MML - Lecture 3, page 36]]

Computational complexity of OLS vs Gradient descent?

![[MML - Lecture 3.pdf#page=38|MML - Lecture 3, page 38]]

![[MML - Lecture 3.pdf#page=39|MML - Lecture 3, page 39]]

The computational complexity is $nml$ or $n^2m$

![[MML - Lecture 3.pdf#page=40|MML - Lecture 3, page 40]]

And the complexity of inverting a matrix is $n^3$

![[MML - Lecture 3.pdf#page=41|MML - Lecture 3, page 41]]

![[MML - Lecture 3.pdf#page=42|MML - Lecture 3, page 42]]

![[MML - Lecture 3.pdf#page=43|MML - Lecture 3, page 43]]

Whether n or m is bigger depends on the number of features or the number of data points.

$n$ is the number of data points
$m$ is the number of features.

Written as is we would always pick OLS, but we can manipulate our gradient descent term to be something much more efficient.

![[MML - Lecture 3.pdf#page=44|MML - Lecture 3, page 44]]

* By factoring out $X^T$ we reduce the complexity by a factor of N.

![[MML - Lecture 3.pdf#page=45|MML - Lecture 3, page 45]]

* We only need compute it once.
* So GD is only of complexity mn K many times:
![[MML - Lecture 3.pdf#page=46|MML - Lecture 3, page 46]]

- So now we need to make a decision on which is best given this information GD or OLS? Depends on how many k steps we think it will take for our model to converge.

![[MML - Lecture 3.pdf#page=48|MML - Lecture 3, page 48]]

* We generally do batch/stochastic gradient decent.


![[MML - Lecture 3.pdf#page=49|MML - Lecture 3, page 49]]

 ![[MML - Lecture 3.pdf#page=50|MML - Lecture 3, page 50]]
![[MML - Lecture 3.pdf#page=51|MML - Lecture 3, page 51]]

* We should adjust our learning rate as we get closer to the minimum, THIS IS WHAT THE HESSIAN IS FOR?

The Jacobian tells us the direction we should move in and the Hessian should tell us how quickly we should go there - I think

Newton's method tends to be computationally prohibitive.

Our objective is empirical risk minimisation i.e. minimising the loss function.