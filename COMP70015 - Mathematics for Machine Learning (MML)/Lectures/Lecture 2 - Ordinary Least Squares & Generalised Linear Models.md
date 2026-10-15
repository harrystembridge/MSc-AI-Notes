![[Lecture 02 - Maths for Machine Learning.pdf]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=7|Lecture 02 - Maths for Machine Learning, page 7]]
![[Lecture 02 - Maths for Machine Learning.pdf#page=8|Lecture 02 - Maths for Machine Learning, page 8]]
![[Lecture 02 - Maths for Machine Learning.pdf#page=9|Lecture 02 - Maths for Machine Learning, page 9]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=10|Lecture 02 - Maths for Machine Learning, page 10]]

* Numerator layout for derivatives:
![[Lecture 02 - Maths for Machine Learning.pdf#page=11|Lecture 02 - Maths for Machine Learning, page 11]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=12|Lecture 02 - Maths for Machine Learning, page 12]]

Prove that: $\nabla_\theta \mathbf{c}^T\theta = \mathbf{c}^T$   

![[Lecture 02 - Maths for Machine Learning.pdf#page=13|Lecture 02 - Maths for Machine Learning, page 13]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=14|Lecture 02 - Maths for Machine Learning, page 14]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=15|Lecture 02 - Maths for Machine Learning, page 15]]

Domain and codomain: R^n -> R 

![[Lecture 02 - Maths for Machine Learning.pdf#page=16|Lecture 02 - Maths for Machine Learning, page 16]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=17|Lecture 02 - Maths for Machine Learning, page 17]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=18|Lecture 02 - Maths for Machine Learning, page 18]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=19|Lecture 02 - Maths for Machine Learning, page 19]]

Here $\theta$ Is the OLS - the ordinary least squares estimator.

![[Lecture 02 - Maths for Machine Learning.pdf#page=20|Lecture 02 - Maths for Machine Learning, page 20]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=21|Lecture 02 - Maths for Machine Learning, page 21]]


![[Lecture 02 - Maths for Machine Learning.pdf#page=24|Lecture 02 - Maths for Machine Learning, page 24]]

OLS needs our terms to be linear.

Adding + b violates linearity.

![[Lecture 02 - Maths for Machine Learning.pdf#page=25|Lecture 02 - Maths for Machine Learning, page 25]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=26|Lecture 02 - Maths for Machine Learning, page 26]]

Here we can create a linear transformation but through an extended basis.

We **expand our basis**?

See proof below we have a linear transformation:

![[Lecture 02 - Maths for Machine Learning.pdf#page=27|Lecture 02 - Maths for Machine Learning, page 27]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=28|Lecture 02 - Maths for Machine Learning, page 28]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=29|Lecture 02 - Maths for Machine Learning, page 29]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=30|Lecture 02 - Maths for Machine Learning, page 30]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=31|Lecture 02 - Maths for Machine Learning, page 31]]

* We create a plane of arbitrary direction, it must just intercept zero, this is to ensure that we still have a linear transformation but it just happens in extended space.

![[Lecture 02 - Maths for Machine Learning.pdf#page=33|Lecture 02 - Maths for Machine Learning, page 33]]

We can extend this to further dimensions:

![[Lecture 02 - Maths for Machine Learning.pdf#page=33|Lecture 02 - Maths for Machine Learning, page 33]]

$\phi_k$ is the contribution of the basis expansion.

![[Lecture 02 - Maths for Machine Learning.pdf#page=34|Lecture 02 - Maths for Machine Learning, page 34]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=35|Lecture 02 - Maths for Machine Learning, page 35]]


![[Lecture 02 - Maths for Machine Learning.pdf#page=36|Lecture 02 - Maths for Machine Learning, page 36]]

The error reduces monotonically. It is infinitely powerful.

## Regularisation
![[Lecture 02 - Maths for Machine Learning.pdf#page=37|Lecture 02 - Maths for Machine Learning, page 37]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=38|Lecture 02 - Maths for Machine Learning, page 38]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=39|Lecture 02 - Maths for Machine Learning, page 39]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=40|Lecture 02 - Maths for Machine Learning, page 40]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=41|Lecture 02 - Maths for Machine Learning, page 41]]

* Linear regression not suitable here, we shouldn't have negative values in the model

**Steps:**
1. Expand loss
2. Differentiate
3. Set = zero and solve

Let's use poisson distribution instead.

![[Lecture 02 - Maths for Machine Learning.pdf#page=42|Lecture 02 - Maths for Machine Learning, page 42]]
![[Lecture 02 - Maths for Machine Learning.pdf#page=43|Lecture 02 - Maths for Machine Learning, page 43]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=44|Lecture 02 - Maths for Machine Learning, page 44]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=45|Lecture 02 - Maths for Machine Learning, page 45]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=46|Lecture 02 - Maths for Machine Learning, page 46]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=47|Lecture 02 - Maths for Machine Learning, page 47]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=48|Lecture 02 - Maths for Machine Learning, page 48]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=49|Lecture 02 - Maths for Machine Learning, page 49]]

Differentiating:

![[Lecture 02 - Maths for Machine Learning.pdf#page=50|Lecture 02 - Maths for Machine Learning, page 50]]

Applying non-linearity to a vector just means applying the operator to each element in the vector.

* The algorithm fails here! We can't find a solution, cannot be solved as we can't take log of zero. Can't isolate $X\theta$

![[Lecture 02 - Maths for Machine Learning.pdf#page=51|Lecture 02 - Maths for Machine Learning, page 51]]


![[Lecture 02 - Maths for Machine Learning.pdf#page=52|Lecture 02 - Maths for Machine Learning, page 52]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=53|Lecture 02 - Maths for Machine Learning, page 53]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=54|Lecture 02 - Maths for Machine Learning, page 54]]


![[Lecture 02 - Maths for Machine Learning.pdf#page=55|Lecture 02 - Maths for Machine Learning, page 55]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=56|Lecture 02 - Maths for Machine Learning, page 56]]

![[Lecture 02 - Maths for Machine Learning.pdf#page=57|Lecture 02 - Maths for Machine Learning, page 57]]

> [!CARD] Limits of basis expansion.
> ...

## Practice Exam Question

![[Lecture 02 - Maths for Machine Learning.pdf#page=58|Lecture 02 - Maths for Machine Learning, page 58]]

![[Pasted image 20261008102342.png]]

a) Answer to a is in the practice questions.
b) 
![[Scan from 2026-10-08 10_39_45 AM.pdf]]

c) 