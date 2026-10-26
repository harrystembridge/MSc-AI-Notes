![[MML - Lecture 6.pdf]]

![[MML - Lecture 6.pdf#page=3|MML - Lecture 6, page 3]]

- We can fit all of the arbitrarily complex functions to be infinitely powerful... so how do we choose which of these functions we want to use?

![[MML - Lecture 6.pdf#page=4|MML - Lecture 6, page 4]]

![[MML - Lecture 6.pdf#page=5|MML - Lecture 6, page 5]]

## Universal Function Approximation
- Sum of sigmoids can fit to anything.

![[MML - Lecture 6.pdf#page=6|MML - Lecture 6, page 6]]

![[MML - Lecture 6.pdf#page=7|MML - Lecture 6, page 7]]

![[MML - Lecture 6.pdf#page=8|MML - Lecture 6, page 8]]

![[MML - Lecture 6.pdf#page=9|MML - Lecture 6, page 9]]

![[MML - Lecture 6.pdf#page=10|MML - Lecture 6, page 10]]

- Linear models without basis expansion violates property 2! so it not a universal function approximator.

- If everything is a function universal approximator? Which one do we pick and why do we need to pick.

- Well like with everything, there is no such thing as free lunch, there is always tradeoffs!

![[MML - Lecture 6.pdf#page=11|MML - Lecture 6, page 11]]

![[MML - Lecture 6.pdf#page=12|MML - Lecture 6, page 12]]

![[MML - Lecture 6.pdf#page=13|MML - Lecture 6, page 13]]

![[MML - Lecture 6.pdf#page=14|MML - Lecture 6, page 14]]

![[MML - Lecture 6.pdf#page=15|MML - Lecture 6, page 15]]

![[MML - Lecture 6.pdf#page=16|MML - Lecture 6, page 16]]


![[MML - Lecture 6.pdf#page=17|MML - Lecture 6, page 17]]

![[MML - Lecture 6.pdf#page=18|MML - Lecture 6, page 18]]

![[MML - Lecture 6.pdf#page=19|MML - Lecture 6, page 19]]

![[MML - Lecture 6.pdf#page=20|MML - Lecture 6, page 20]]
![[MML - Lecture 6.pdf#page=21|MML - Lecture 6, page 21]]

![[MML - Lecture 6.pdf#page=22|MML - Lecture 6, page 22]]

![[MML - Lecture 6.pdf#page=23|MML - Lecture 6, page 23]]

![[MML - Lecture 6.pdf#page=24|MML - Lecture 6, page 24]]

- In general in ML, we don't know the form of randomness we are observing

![[MML - Lecture 6.pdf#page=25|MML - Lecture 6, page 25]]

- We want to be careful about the idea of something being random. 
- The outcome of sampling is random.
-  We want to know that some kind of approximation of our risk is a sensible thing to do.

![[MML - Lecture 6.pdf#page=26|MML - Lecture 6, page 26]]

![[MML - Lecture 6.pdf#page=27|MML - Lecture 6, page 27]]

![[MML - Lecture 6.pdf#page=28|MML - Lecture 6, page 28]]

![[MML - Lecture 6.pdf#page=29|MML - Lecture 6, page 29]]

- But what does it mean to converge in probability?

![[MML - Lecture 6.pdf#page=30|MML - Lecture 6, page 30]]

![[MML - Lecture 6.pdf#page=31|MML - Lecture 6, page 31]]

![[MML - Lecture 6.pdf#page=32|MML - Lecture 6, page 32]]

![[MML - Lecture 6.pdf#page=33|MML - Lecture 6, page 33]]

iid - independent and identically distributed

![[MML - Lecture 6.pdf#page=34|MML - Lecture 6, page 34]]

![[MML - Lecture 6.pdf#page=35|MML - Lecture 6, page 35]]

![[MML - Lecture 6.pdf#page=36|MML - Lecture 6, page 36]]

![[MML - Lecture 6.pdf#page=37|MML - Lecture 6, page 37]]

![[MML - Lecture 6.pdf#page=38|MML - Lecture 6, page 38]]

![[MML - Lecture 6.pdf#page=40|MML - Lecture 6, page 40]]

![[MML - Lecture 6.pdf#page=41|MML - Lecture 6, page 41]]

![[MML - Lecture 6.pdf#page=42|MML - Lecture 6, page 42]]

![[MML - Lecture 6.pdf#page=43|MML - Lecture 6, page 43]]

![[MML - Lecture 6.pdf#page=44|MML - Lecture 6, page 44]]

![[MML - Lecture 6.pdf#page=45|MML - Lecture 6, page 45]]


### Markov's Inequality vs Chebyshev's inequality

**Chebyshev's inequality** is closely related to Markov's inequality. It bounds the probability of observing a value far from the mean in terms of the variance, which is itself an expectation. Specifically, the probability that a random variable lies more than a distance $k$ from its mean is at most its variance divided by $k^2$:

$$  
P\big(|X - \mu| \geq k\big) \leq \frac{\sigma^2}{k^2}, \qquad k > 0  
$$

![[MML - Lecture 6.pdf#page=46|MML - Lecture 6, page 46]]

![[MML - Lecture 6.pdf#page=47|MML - Lecture 6, page 47]]

![[MML - Lecture 6.pdf#page=48|MML - Lecture 6, page 48]]

![[MML - Lecture 6.pdf#page=49|MML - Lecture 6, page 49]]

![[MML - Lecture 6.pdf#page=50|MML - Lecture 6, page 50]]

![[MML - Lecture 6.pdf#page=51|MML - Lecture 6, page 51]]

![[MML - Lecture 6.pdf#page=52|MML - Lecture 6, page 52]]

![[MML - Lecture 6.pdf#page=53|MML - Lecture 6, page 53]]

![[MML - Lecture 6.pdf#page=54|MML - Lecture 6, page 54]]

![[MML - Lecture 6.pdf#page=55|MML - Lecture 6, page 55]]

![[MML - Lecture 6.pdf#page=56|MML - Lecture 6, page 56]]

![[MML - Lecture 6.pdf#page=57|MML - Lecture 6, page 57]]

- How long should our trial be? How big should K be?
![[MML - Lecture 6.pdf#page=58|MML - Lecture 6, page 58]]

![[MML - Lecture 6.pdf#page=59|MML - Lecture 6, page 59]]

![[MML - Lecture 6.pdf#page=60|MML - Lecture 6, page 60]]

- We get the error and our confidence of the statements we are about to make. We are probably approximately correct...

- So then this tells us which model we pick:

$\hat{R}(f^\theta) < \hat{R}(g^\omega)$ but we can't say for sure which is better, we can just say which one is approximately probably better.

![[MML - Lecture 6.pdf#page=61|MML - Lecture 6, page 61]]

How big should k be?

![[MML - Lecture 6.pdf#page=62|MML - Lecture 6, page 62]]

![[MML - Lecture 6.pdf#page=63|MML - Lecture 6, page 63]]

![[MML - Lecture 6.pdf#page=64|MML - Lecture 6, page 64]]

![[MML - Lecture 6.pdf#page=65|MML - Lecture 6, page 65]]

![[MML - Lecture 6.pdf#page=66|MML - Lecture 6, page 66]]

![[MML - Lecture 6.pdf#page=67|MML - Lecture 6, page 67]]

![[MML - Lecture 6.pdf#page=68|MML - Lecture 6, page 68]]


![[MML - Lecture 6.pdf#page=69|MML - Lecture 6, page 69]]
