---
flashcards:
  q-6j5z: { nid: 1791202216307, hash: amv98w5v, sync: iutp5vvu }
---

**Office hours**: Room 450 HXLY - 5pm-6pm Mondays
![[Machine Learning - Lecture 1.pdf]]

## Self-supervision 
![[Machine Learning - Lecture 1.pdf#page=11|Machine Learning - Lecture 1, page 11]]

* Pre-training model with unlabelled data
* Never have explicit labels for the reference data but there is some supervision in the sense that information is either removed or hidden.


## Partial Supervision
![[Machine Learning - Lecture 1.pdf#page=12|Machine Learning - Lecture 1, page 12]]
* Weak labels
* E.g. the type of data big tech firms have, social media likes etc.

## Reinforcement Learning
![[Machine Learning - Lecture 1.pdf#page=13|Machine Learning - Lecture 1, page 13]]

* Rewards often come a very long time after decisions are made.

Focus on supervised problems and unsupervised problems

## Regression
![[Machine Learning - Lecture 1.pdf#page=23|Machine Learning - Lecture 1, page 23]]

* A set of points provided to us, for a new point, where should it's value be?
* Given x, what is a new points y, what are we predicting.
![[Machine Learning - Lecture 1.pdf#page=24|Machine Learning - Lecture 1, page 24]]
* Red represents the weight we give each prediction

### Kernel Regression
![[Machine Learning - Lecture 1.pdf#page=25|Machine Learning - Lecture 1, page 25]]
* h is the kernel weight, how quickly or slowly this kernel is decaying from xi ***(note for later: latex in obsidian?)***
![[Machine Learning - Lecture 1.pdf#page=26|Machine Learning - Lecture 1, page 26]]
* Our prediction at position x, is a weighted aggregation of all other kernels, weighted by $a_i$
* This is non-parametric regression, when we are asked to predict the value of y for our new value of x, we need to look at the full training set and compute an expression that aggregates all the data
* i, iterates through the points in the dataset
* j, iterates through the whole data set too, irrespective of i
$$a_i$$
![[Machine Learning - Lecture 1.pdf#page=27|Machine Learning - Lecture 1, page 27]]
* With kernel regression we must consider the entire training set with every new prediction
* Computation scales with training set size.
### Challenges of Non-Parametric Regression
![[Machine Learning - Lecture 1.pdf#page=28|Machine Learning - Lecture 1, page 28]]

* We need to load the entire training set in memory
* Complexity scales with the size of the training set
* The curse of dimensionality

> [!CARD] **Challenge of non-parametric regression (Kernel Regression)**
> Memory, Prediction, Locality
^q-6j5z

**Notation**: bold for vectors, normal for scalars, semi-colon separates function arguments

![[Machine Learning - Lecture 1.pdf#page=33|Machine Learning - Lecture 1, page 33]]

### Linear Regression
![[Machine Learning - Lecture 1.pdf#page=34|Machine Learning - Lecture 1, page 34]]
* Minimise distance between line and points in training set
* i.e. minimise the sum of the squared residuals
![[Pasted image 20261005120643.png|500]]****
* Find w that minimises RSS
* Minimisation problem
* Find a point where the gradient is zero
![[Machine Learning - Lecture 1.pdf#page=36|Machine Learning - Lecture 1, page 36]]

* At the minimum, the gradient is zero
![[Pasted image 20261005120918.png]]

### Differentiating through the residual
![[Machine Learning - Lecture 1.pdf#page=37|Machine Learning - Lecture 1, page 37]]
* Just calculating the derivative w.r.t $w_o$

> [!info] Won't ask this derivation in the exam, but will ask why we do this.

![[Machine Learning - Lecture 1.pdf#page=38|Machine Learning - Lecture 1, page 38]]

![[Machine Learning - Lecture 1.pdf#page=39|Machine Learning - Lecture 1, page 39]]
* Different rows in the matrix represent points in the training set
![[Pasted image 20261005121530.png]]
* This is the normal equation, this gives you the optimal value of $\hat{w}$

![[Machine Learning - Lecture 1.pdf#page=40|Machine Learning - Lecture 1, page 40]]
![[Machine Learning - Lecture 1.pdf#page=41|Machine Learning - Lecture 1, page 41]]
![[Machine Learning - Lecture 1.pdf#page=42|Machine Learning - Lecture 1, page 42]]
![[Machine Learning - Lecture 1.pdf#page=43|Machine Learning - Lecture 1, page 43]]
* This gives us our optimal parameter vector $\hat{w}$

![[Machine Learning - Lecture 1.pdf#page=44|Machine Learning - Lecture 1, page 44]]

* Think about the scalar x

![[Machine Learning - Lecture 1.pdf#page=46|Machine Learning - Lecture 1, page 46]]

* We can scale this for polynomials of degree q
![[Machine Learning - Lecture 1.pdf#page=47|Machine Learning - Lecture 1, page 47]]
![[Machine Learning - Lecture 1.pdf#page=48|Machine Learning - Lecture 1, page 48]]
* Now too many dimension to work with?
![[Machine Learning - Lecture 1.pdf#page=49|Machine Learning - Lecture 1, page 49]]

* If you can express a point as a linear combination of other points then it is technically possible that we can fit 100 points with <100 features.
* If the set of points is of lower cardinality than the number of dimensions then we can effectively fit points of higher dimensionality to a plane.
* How many rows/ranks of this matrix are linearly independent?
* Dimensionality reduction???

![[Machine Learning - Lecture 1.pdf#page=50|Machine Learning - Lecture 1, page 50]]

* What happens when we have more parameters than data points/observations?
* We could have zero RSS but doesn't mean we will do a good job of prediction new observations.
![[Machine Learning - Lecture 1.pdf#page=51|Machine Learning - Lecture 1, page 51]]
* High dimension does a bad job of approximating the actual underlying function
* Bottom right 2 diagrams show us reducing the dimensionality, less reduce the degrees of freedom and not allow $w_1$ to vary.
* Here we start pruning degrees of freedom but we don't know where to stop...

![[Machine Learning - Lecture 1.pdf#page=52|Machine Learning - Lecture 1, page 52]]

* All points along the blue line in the bottom graphs exhibit the same cost, we can compensate the cost by varying in $w_1$ and $w_2$.
* The more observations we have, the easier it is to localise the minimum.
* This is the opposite, we keep on adding data and continually doing a better job of fitting (reducing the cost in terms of RSS).
![[Machine Learning - Lecture 1.pdf#page=53|Machine Learning - Lecture 1, page 53]]
![[Machine Learning - Lecture 1.pdf#page=54|Machine Learning - Lecture 1, page 54]]
* We now have an additional objective, a new cost in the function in our optimisation problem that we need to respect.
* $\lambda$ is our regularisation parameter which penalises overfitting
* Ridge uses an absolute cost function, allows parameters to collapse to zero.
* What is the correct amount of regularisation to apply?
	* Larger $\lambda$ we penalise large coefficients more?

![[Machine Learning - Lecture 1.pdf#page=56|Machine Learning - Lecture 1, page 56]]
* The impact of the regularisation parameter is to allow the matrix to be invertible.
* Is X transpose X invertible? - condition, determinants non-zero and full rank matrix.
* KxK needs to have K to be invertible - not an invertible matrix in this case.
* Rank deficient matrix + full rank matrix gives invertible matrix. System is indeed invertible by adding lambda to it.
![[Machine Learning - Lecture 1.pdf#page=57|Machine Learning - Lecture 1, page 57]]
* Increasing the regularisation parameter from left to right.
* There is an objective of being close to the training point.
* It wants to keep the weight close to zero, it penalises large parameters.
* So how do we set the size of the regularisation parameter, how do we choose between being flexible and smooth or inflexible in space.
* As $\lambda$ goes to infinity, we fit the parameters to zero, we don't fit any data at all. This outweighs the objective function.

### Choosing the correct value of $\lambda$
![[Machine Learning - Lecture 1.pdf#page=58|Machine Learning - Lecture 1, page 58]]

![[Machine Learning - Lecture 1.pdf#page=59|Machine Learning - Lecture 1, page 59]]

* The noisier the data is/the smaller the data set is, the larger $\lambda$ should be... (sometimes)
* K-folds, i.e. k segmentations of the data set
* Don't use test set multiple times, only use once.
