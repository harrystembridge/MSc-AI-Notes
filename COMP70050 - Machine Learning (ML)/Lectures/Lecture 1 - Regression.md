![[Machine Learning - Regression.pdf]]

![[Machine Learning - Regression.pdf#page=3|Machine Learning - Regression, page 3]]

* **Standard practices that should be applied to all features:**
![[Machine Learning - Regression.pdf#page=7|Machine Learning - Regression, page 7]]

* Standardise to zero mean and unit variance for comparable scale.
* Intercept is removed from the regularisation.

![[Machine Learning - Regression.pdf#page=8|Machine Learning - Regression, page 8]]

* Ensure to keep normalisation consistent across validation and test and training sets to prevent information leakage.

![[Machine Learning - Regression.pdf#page=9|Machine Learning - Regression, page 9]]

## Probabilistic Modeling
![[Machine Learning - Regression.pdf#page=10|Machine Learning - Regression, page 10]]

* Upper case is random value, lower case is observed values:
![[Machine Learning - Regression.pdf#page=11|Machine Learning - Regression, page 11]]

* We want to model the dependencies of multiple random variables.

![[Machine Learning - Regression.pdf#page=12|Machine Learning - Regression, page 12]]


![[Machine Learning - Regression.pdf#page=13|Machine Learning - Regression, page 13]]

![[Machine Learning - Regression.pdf#page=14|Machine Learning - Regression, page 14]]

![[Machine Learning - Regression.pdf#page=15|Machine Learning - Regression, page 15]]

![[Machine Learning - Regression.pdf#page=16|Machine Learning - Regression, page 16]]

* I want to assess the performance of a set of parameters. This set of parameters has a certain level of fit when compared to the data.

![[Machine Learning - Regression.pdf#page=17|Machine Learning - Regression, page 17]]

![[Machine Learning - Regression.pdf#page=18|Machine Learning - Regression, page 18]]

![[Machine Learning - Regression.pdf#page=19|Machine Learning - Regression, page 19]]

* We will assume that we have a covariance matrix of type c.

![[Machine Learning - Regression.pdf#page=20|Machine Learning - Regression, page 20]]

* This is reminder of things assumed from probability, assumed pre-req knowledge.

![[Machine Learning - Regression.pdf#page=21|Machine Learning - Regression, page 21]]

* A prior, about where our parameter's "should be".
* **The prior is that the model should be simple** - i.e. there should be a small L2 norm...
* We assume gaussian distribution of the error term/noise in the model:

![[Machine Learning - Regression.pdf#page=22|Machine Learning - Regression, page 22]]

![[Machine Learning - Regression.pdf#page=23|Machine Learning - Regression, page 23]]

* We want to minimise the negative log liklihood with respect to our parameters.
* **This is minimising an L2 norm**
* This assumes there is some kind of gaussian process going on with the underlying noise in the model.

![[Machine Learning - Regression.pdf#page=24|Machine Learning - Regression, page 24]]

![[Machine Learning - Regression.pdf#page=25|Machine Learning - Regression, page 25]]

* This prior means this regularisation is now aligned with the prior distribution of our parameters.
* *Does this link to how we determine the size of our regularisation parameter?*

![[Machine Learning - Regression.pdf#page=26|Machine Learning - Regression, page 26]]

* Here we are determining $\lambda$ by assuming that we understand the prior distribution of the data. 
![[Pasted image 20261007105427.png]]
* Where $\lambda$ is our regularisation parameter.
* If our noise (variance) increases, we should have a larger regularisation parameter $\lambda$.
* $\tau$ represents how complex the model should be... higher $\tau$ means that the model can be more complex, maybe we don't understand the underlying dynamics of the model.
* As $\tau$ increases $\lambda$, our regularisation parameter, should decrease (we want to allow complexity so reduce the scale of the punishment).

![[Machine Learning - Regression.pdf#page=27|Machine Learning - Regression, page 27]]

![[Machine Learning - Regression.pdf#page=28|Machine Learning - Regression, page 28]]

* **Parameter posterior is not examinable!**

