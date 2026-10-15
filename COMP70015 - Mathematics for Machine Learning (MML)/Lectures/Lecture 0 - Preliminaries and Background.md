---
flashcards:
  q-dbap: { hash: kk5dpa4b }
  q-cieb: { hash: kk5dpa4b }
  q-in8b: { hash: kk5dpa4b }
  q-q7xw: { nid: 1791466717622, hash: ge82ex87, sync: mizfv4tr }
  q-thrf: { nid: 1791467463240, hash: h7g2v59z, sync: xgjrmeqg }
  q-sfmk: { nid: 1791467463255, hash: nmp4efwq, sync: mewjqxfc }
  q-8gzi: { nid: 1791467926715, hash: 2fnv7ai4, sync: 6yx5tzkb }
  q-ed6t: { nid: 1791467926737, hash: 8sfsbz5a, sync: wusf496x }
  q-6bk4: { nid: 1791467926756, hash: gxeq27qp, sync: jzvj5gj3 }
  q-ixry: { nid: 1791467926781, hash: afgk9hme, sync: kqp2prmr }
  q-9efk: { nid: 1791467926806, hash: 3pd8riiu, sync: rw9anhcw }
  q-gm5t: { nid: 1791467926831, hash: e6wad5y5, sync: a6tvvwpg }
  q-ahy7: { nid: 1791467926857, hash: 3apxdszz, sync: 6kd83w66 }
  q-cpb6: { nid: 1791467926881, hash: sc96v2sj, sync: w28u9957 }
  q-zx2s: { nid: 1791467926908, hash: 8f6v9zhz, sync: 4hk657fe }
  q-pziq: { nid: 1791467926933, hash: z7ag8yp3, sync: ek6jr93x }
  q-8yh7: { nid: 1791467926958, hash: ucyvrwyv, sync: dswyb9zt }
  q-8sxx: { nid: 1791467926984, hash: sbkkxhcz, sync: hs6egrd9 }
  q-asri: { nid: 1791467927009, hash: 6ftjjqmm, sync: 3qjktwjr }
  q-v392: { nid: 1791467927034, hash: pnhu6mnk, sync: 3x4dvwq9 }
  q-an2g: { nid: 1791467927058, hash: gehvvmuq, sync: gq4qq9g9 }
  q-diyg: { nid: 1791467927084, hash: 6jj79ver, sync: uphbw43v }
  q-a68q: { nid: 1791467927109, hash: yemiu8bu, sync: rhbak3gh }
  q-bj8q: { nid: 1791467927134, hash: uisretrh, sync: 6e7cxc3y }
  q-jc4x: { nid: 1791467927159, hash: s7e8e28q, sync: sfzynbqr }
  q-5nba: { nid: 1791467927184, hash: bknpn42b, sync: 8tbxf9em }
  q-5aht: { nid: 1791467927208, hash: anjkphz4, sync: 3d6bzyyj }
  q-rf8y: { nid: 1791467927235, hash: zcvuzyqd, sync: x8d38esk }
---

![[Mathematics for ML - Lecture 00.pdf]]

![[Mathematics for ML - Lecture 00.pdf#page=1]]

![[Mathematics for ML - Lecture 00.pdf#page=2]]

![[Mathematics for ML - Lecture 00.pdf#page=3]]

![[Mathematics for ML - Lecture 00.pdf#page=4]]
## Linear Algebra
### Matrices
A matrix has dimensions $n \times m$ where $n$ is the number of rows and $m$ is the number of columns.

> [!CARD] What is the shape of an $n \times m$ matrix? I.e. how many rows and columns has it got?
> This matrix has n rows and m columns:
> $\boldsymbol{X} = \begin{bmatrix} \boldsymbol{X}_{1,1} & \boldsymbol{X}_{1,2} & \cdots & \boldsymbol{X}_{1,m} \\ \boldsymbol{X}_{2,1} & \boldsymbol{X}_{2,2} & \cdots & \boldsymbol{X}_{2,m} \\ \vdots & \vdots & \ddots & \vdots \\ \boldsymbol{X}_{n,1} & \boldsymbol{X}_{n,2} & \cdots & \boldsymbol{X}_{n,m} \end{bmatrix}$
^q-q7xw
* Every entry of a vector is a scalar.
* To multiply two matrices together, the columns of the left hand term must equal the rows of the right hand term.

> [!CARD] What conditions do we need to multiply 2 matrices together?
> We need that the number of columns of the left hand term must equal the rows of the right hand term: i.e. if we want to perform $\mathbf{A \times B}$ we need $\boldsymbol{A} \in \mathbb{R}^{n \times m}$ and $\boldsymbol{B} \in \mathbb{R}^{m \times k}$. 
^q-thrf
* The result of multiplying A and B is a matrix C with elements: ![[Pasted image 20261008144724.png|282]]

> [!CARD] What is the result of $\mathbf{A \times B}$? And what dimensions does it have? Given $\boldsymbol{A} \in \mathbb{R}^{n \times m}$ and $\boldsymbol{B} \in \mathbb{R}^{m \times k}$ 
> $\boldsymbol{C}_{i,j} = \sum_{k=1}^{m} \boldsymbol{A}_{i,k} \boldsymbol{B}_{k,j}$
> With dimensions $\mathbf{C} \in \mathbb{R}^{n\times k}$
> 
^q-sfmk

### Notation

> [!CARD] What is the transpose of $\boldsymbol{v}$, written $\boldsymbol{v}^\top$?
> The transpose of $\boldsymbol{v}$.
>
^q-8gzi

> [!CARD] What is the inner (scalar) product $\boldsymbol{u}^\top \boldsymbol{v}$?
> The scalar product of $\boldsymbol{u}$ and $\boldsymbol{v}$.
>
^q-ed6t

> [!CARD] What is the outer product $\boldsymbol{u}\boldsymbol{v}^\top$, and what shape is it?
> An $n \times n$ matrix.
>
^q-6bk4

> [!CARD] What is the elementwise product $\boldsymbol{u} \odot \boldsymbol{v}$?
> $[\boldsymbol{u}_1\boldsymbol{v}_1, \dots, \boldsymbol{u}_n\boldsymbol{v}_n]$
>
^q-ixry

> [!CARD] What does $\dim(\boldsymbol{v})$ mean?
> The dimensionality of $\boldsymbol{v}$, namely $n$.
>
^q-9efk

> [!CARD] What is $\operatorname{diag}(\boldsymbol{v})$?
> The diagonal $n \times n$ matrix made from the vector $\boldsymbol{v}$.
>
^q-gm5t

> [!CARD] What does $\mathbf{1}$ or $\mathbf{1}_n$ denote?
> A vector of ones of length $n$.
>
^q-ahy7

> [!CARD] What does $\mathbf{0}$ or $\mathbf{0}_n$ denote?
> A vector of zeros of length $n$.
>
^q-cpb6

> [!CARD] What is the Euclidean ($\ell_2$) norm $\|\boldsymbol{v}\|$ or $\|\boldsymbol{v}\|_2$?
> $\sqrt{\sum_{i=1}^{n} \boldsymbol{v}_i^2}$
>
^q-zx2s

> [!CARD] What is the $\ell_1$ norm $\|\boldsymbol{v}\|_1$?
> $\sum_{i=1}^{n} |\boldsymbol{v}_i|$
>
^q-pziq

> [!CARD] What is the $i$th basis vector $\boldsymbol{e}_i$?
> A vector with 1 in dimension $i$ and 0 elsewhere.
>
^q-8yh7

> [!CARD] What does $\boldsymbol{X}_{:,j}$ denote?
> The $j$th column of the matrix $\boldsymbol{X}$.
>
^q-8sxx

> [!CARD] What does $\boldsymbol{X}_{i,:}$ denote?
> The $i$th row of the matrix $\boldsymbol{X}$, treated as a column vector.
>
^q-asri

> [!CARD] What does $\boldsymbol{X}_{ij}$ denote?
> The element in row $i$, column $j$ of $\boldsymbol{X}$.
>
^q-v392

> [!CARD] What is the transpose $\boldsymbol{X}^\top$ of a matrix?
> The matrix with rows and columns swapped.
>
^q-an2g

> [!CARD] What is $\operatorname{diag}(\boldsymbol{S})$ for a square matrix $\boldsymbol{S}$?
> The diagonal vector extracted from $\boldsymbol{S}$.
>
^q-diyg

> [!CARD] What is $\mathbf{I}$ or $\mathbf{I}_n$?
> The identity matrix of size $n \times n$.
>
^q-a68q

> [!CARD] What is the elementwise product $\boldsymbol{X} \odot \boldsymbol{Y}$?
> The elementwise product of $\boldsymbol{X}$ and $\boldsymbol{Y}$.
>
^q-bj8q

> [!CARD] What is the Kronecker product $\boldsymbol{X} \otimes \boldsymbol{Z}$?
> The Kronecker product of $\boldsymbol{X}$ and $\boldsymbol{Z}$.
>
^q-jc4x

> [!CARD] When is $\boldsymbol{S} \succ 0$ true?
> If and only if $\boldsymbol{S}$ is a positive definite matrix.
>
^q-5nba

> [!CARD] What is $\operatorname{tr}(\boldsymbol{S})$?
> The trace of the square matrix $\boldsymbol{S}$.
>
^q-5aht

> [!CARD] What do $\det(\boldsymbol{S})$ and $|\boldsymbol{S}|$ denote?
> The determinant of the square matrix $\boldsymbol{S}$.
>
^q-rf8y

![[Mathematics for ML - Lecture 00.pdf#page=5]]

## Calculus
### Multivariate Calculus

* We care about the derivatives of functions with vector arguments.
* We define the gradient of a function to be the collection of all its partial derivatives into a single **row** vector:
$$\boldsymbol{g} = \nabla f = \frac{\partial f}{\partial \boldsymbol{x}} = \left[\frac{df}{d\boldsymbol{x}_0}, \frac{df}{d\boldsymbol{x}_1}, \dots, \frac{df}{d\boldsymbol{x}_n}\right]$$
* Note that g is a function mapping vectors to vectors - aka a vector field.
* The derivative of an arbitrary vector field is a matrix we call the Jacobian:
$$\nabla f = \begin{bmatrix} \frac{\partial f_1}{\partial x_1} & \frac{\partial f_1}{\partial x_2} & \cdots & \frac{\partial f_1}{\partial x_n} \\ \frac{\partial f_2}{\partial x_1} & \frac{\partial f_2}{\partial x_2} & \cdots & \frac{\partial f_2}{\partial x_n} \\ \vdots & \vdots & \ddots & \vdots \\ \frac{\partial f_m}{\partial x_1} & \frac{\partial f_m}{\partial x_2} & \cdots & \frac{\partial f_m}{\partial x_n} \end{bmatrix} = \begin{bmatrix} \frac{\partial f_1}{\partial \boldsymbol{x}} \\ \frac{\partial f_2}{\partial \boldsymbol{x}} \\ \vdots \\ \frac{\partial f_m}{\partial \boldsymbol{x}} \end{bmatrix}$$
* How do we compute the Jacobian for a particular function?

![[Mathematics for ML - Lecture 00.pdf#page=6]]
## Probability & Statistics


![[Mathematics for ML - Lecture 00.pdf#page=7]]

![[Mathematics for ML - Lecture 00.pdf#page=8]]

> [!CARD] What are the 3 axioms of probability?
> 1. **Non-negativity**: $P(A) \geq 0$ for all events $A$
> 2. **Normalization**: $P(\Omega) = 1$
> 3. **Additivity**: if $A \cap B = \emptyset$, then $P(A \cup B) = P(A) + P(B)$

> [!CARD] How can we show the independence of events?
> $P(A\cup B) = P(A)\times P(B)$

> [!CARD] How to calculate the cumulative probability of a continuous random variable being between two values i.e. $P(a \leq X \leq b)$
> $P(a \leq X \leq b) = \int_a^b f(x)\,dx$
> where $f(x)$ is the probability density function (pdf) of $X$.

>[!CARD] How to calculate the variance of a continuous random variable?
>$V[X] = E[X^2] - E[X]^2$
>where $E[X] = \int_a^b xf(x)\,dx$




