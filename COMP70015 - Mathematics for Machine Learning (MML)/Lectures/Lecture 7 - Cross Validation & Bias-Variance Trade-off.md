![[MML - Lecture 7.pdf]]

![[MML - Lecture 7.pdf#page=2|MML - Lecture 7, page 2]]

![[MML - Lecture 7.pdf#page=3|MML - Lecture 7, page 3]]


![[MML - Lecture 7.pdf#page=4|MML - Lecture 7, page 4]]

![[MML - Lecture 7.pdf#page=5|MML - Lecture 7, page 5]]

- Choosing your hyper parameters is learning...

![[MML - Lecture 7.pdf#page=7|MML - Lecture 7, page 7]]

![[MML - Lecture 7.pdf#page=8|MML - Lecture 7, page 8]]

![[MML - Lecture 7.pdf#page=9|MML - Lecture 7, page 9]]

- For all J in 1 to d, I want that the risk estimate holds for all of them, the risk estimate should come in less than $\epsilon$ with probability 1 - $\delta$

![[MML - Lecture 7.pdf#page=10|MML - Lecture 7, page 10]]

![[MML - Lecture 7.pdf#page=11|MML - Lecture 7, page 11]]

- We want that our error is less than 10%...
- We want to make sure we aren't overstating our confidence, so we give an upper bound.

![[MML - Lecture 7.pdf#page=12|MML - Lecture 7, page 12]]

![[MML - Lecture 7.pdf#page=13|MML - Lecture 7, page 13]]

![[MML - Lecture 7.pdf#page=14|MML - Lecture 7, page 14]]

- Using training set to estimate our error.
- For linear regression this isn't appropriate, because the term is unbounded anywhere you have an unbounded real number. So here we don't have an upper bound for linear regression.

![[MML - Lecture 7.pdf#page=15|MML - Lecture 7, page 15]]

- As we increase the number of datasets we are comparing, the number of test data points explodes. Often the number of test points required is larger than the entire dataset for the guarantees for a large number of datasets.


![[MML - Lecture 7.pdf#page=16|MML - Lecture 7, page 16]]

- We can't use the test data for us to tune our hyperparameters as it will hurt generalisation - it's cheating/overfitting.

![[MML - Lecture 7.pdf#page=17|MML - Lecture 7, page 17]]

- We introduce a validation set for determining our hyper-parameters.
- We get weak-law of large numbers guarantee

- Now we are splitting our data 3 ways - what if we don't have a lot of data.

![[MML - Lecture 7.pdf#page=19|MML - Lecture 7, page 19]]

![[MML - Lecture 7.pdf#page=20|MML - Lecture 7, page 20]]

- We take an average of all of our validation samples for our hyperparameters.

![[MML - Lecture 7.pdf#page=21|MML - Lecture 7, page 21]]

- But does this give us a picture of the true risk of our models?


![[MML - Lecture 7.pdf#page=22|MML - Lecture 7, page 22]]


![[MML - Lecture 7.pdf#page=24|MML - Lecture 7, page 24]]

![[MML - Lecture 7.pdf#page=25|MML - Lecture 7, page 25]]

![[MML - Lecture 7.pdf#page=26|MML - Lecture 7, page 26]]

![[MML - Lecture 7.pdf#page=27|MML - Lecture 7, page 27]]

![[MML - Lecture 7.pdf#page=28|MML - Lecture 7, page 28]]

![[MML - Lecture 7.pdf#page=29|MML - Lecture 7, page 29]]
![[MML - Lecture 7.pdf#page=30|MML - Lecture 7, page 30]]

![[MML - Lecture 7.pdf#page=31|MML - Lecture 7, page 31]]

![[MML - Lecture 7.pdf#page=32|MML - Lecture 7, page 32]]

![[MML - Lecture 7.pdf#page=33|MML - Lecture 7, page 33]]
$E[\hat{S}] = 0$ so this middle element cancels.


![[MML - Lecture 7.pdf#page=34|MML - Lecture 7, page 34]]

![[MML - Lecture 7.pdf#page=35|MML - Lecture 7, page 35]]

![[MML - Lecture 7.pdf#page=36|MML - Lecture 7, page 36]]

![[MML - Lecture 7.pdf#page=37|MML - Lecture 7, page 37]]

![[MML - Lecture 7.pdf#page=38|MML - Lecture 7, page 38]]

![[MML - Lecture 7.pdf#page=39|MML - Lecture 7, page 39]]

![[MML - Lecture 7.pdf#page=40|MML - Lecture 7, page 40]]

![[MML - Lecture 7.pdf#page=41|MML - Lecture 7, page 41]]

- ^ The expected prediction of our function...

![[MML - Lecture 7.pdf#page=42|MML - Lecture 7, page 42]]

![[MML - Lecture 7.pdf#page=43|MML - Lecture 7, page 43]]

![[MML - Lecture 7.pdf#page=44|MML - Lecture 7, page 44]]

![[MML - Lecture 7.pdf#page=45|MML - Lecture 7, page 45]]

![[MML - Lecture 7.pdf#page=46|MML - Lecture 7, page 46]]

![[MML - Lecture 7.pdf#page=47|MML - Lecture 7, page 47]]

![[MML - Lecture 7.pdf#page=48|MML - Lecture 7, page 48]]

![[MML - Lecture 7.pdf#page=49|MML - Lecture 7, page 49]]

![[MML - Lecture 7.pdf#page=50|MML - Lecture 7, page 50]]

![[MML - Lecture 7.pdf#page=51|MML - Lecture 7, page 51]]

![[MML - Lecture 7.pdf#page=52|MML - Lecture 7, page 52]]

![[MML - Lecture 7.pdf#page=53|MML - Lecture 7, page 53]]

![[MML - Lecture 7.pdf#page=54|MML - Lecture 7, page 54]]


![[MML - Lecture 7.pdf#page=55|MML - Lecture 7, page 55]]


![[MML - Lecture 7.pdf#page=56|MML - Lecture 7, page 56]]

![[MML - Lecture 7.pdf#page=57|MML - Lecture 7, page 57]]

![[MML - Lecture 7.pdf#page=58|MML - Lecture 7, page 58]]

![[MML - Lecture 7.pdf#page=59|MML - Lecture 7, page 59]]


![[MML - Lecture 7.pdf#page=60|MML - Lecture 7, page 60]]

![[MML - Lecture 7.pdf#page=61|MML - Lecture 7, page 61]]

![[Scan from 2026-10-27 10_33_56 AM.pdf]]

$E[\hat{\sigma}^2] - \sigma^2$

$\hat{\sigma}^2 = \frac{1}{k} \sum{(x_i-\hat{x})^2}$
$=\frac{1}{k}(\sum{x_i^2}-2k\hat{x}^2+k\hat{x}^2)$
$=\frac{1}{k}(\sum{x_i^2}-k\hat{x}^2)$

$E[\hat{\sigma}^2] = E[\frac{1}{k}(\sum{x_i^2}-k\hat{x}^2)]$
$=\frac{1}{k}(kE[X_i^2]-E[k\hat{x}^2])$
$=E[x^2]-E[\hat{x}^2]$

$=Var(X) + E[x]^2 - E[\hat{x}^2]$
$=\sigma^2 + \mu^2 - E[\hat{x}^2]$
$=\sigma^2 + \mu^2 - (Var(\hat{x}) + E[\hat{x}]^2)$

- We can drop the i's because of the iid assumption...


![[Scan from 2026-10-27 10_47_22 AM.pdf]]
![[Scan from 2026-10-27 10_49_13 AM.pdf]]