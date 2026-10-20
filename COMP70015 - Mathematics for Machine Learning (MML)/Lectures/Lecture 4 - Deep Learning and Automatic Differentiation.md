![[MML - Lecture 4.pdf]]
* Gradient decent, we think about our parameters as a ball rolling down the hill.
![[MML - Lecture 4.pdf#page=2|MML - Lecture 4, page 2]]

![[MML - Lecture 4.pdf#page=3|MML - Lecture 4, page 3]]

![[MML - Lecture 4.pdf#page=4|MML - Lecture 4, page 4]]


![[MML - Lecture 4.pdf#page=5|MML - Lecture 4, page 5]]

![[MML - Lecture 4.pdf#page=6|MML - Lecture 4, page 6]]

![[MML - Lecture 4.pdf#page=7|MML - Lecture 4, page 7]]

![[MML - Lecture 4.pdf#page=8|MML - Lecture 4, page 8]]
![[Pasted image 20261016145128.png]]

![[MML - Lecture 4.pdf#page=9|MML - Lecture 4, page 9]]


![[MML - Lecture 4.pdf#page=10|MML - Lecture 4, page 10]]


![[MML - Lecture 4.pdf#page=11|MML - Lecture 4, page 11]]

![[MML - Lecture 4.pdf#page=12|MML - Lecture 4, page 12]]

![[MML - Lecture 4.pdf#page=13|MML - Lecture 4, page 13]]

![[MML - Lecture 4.pdf#page=14|MML - Lecture 4, page 14]]
* Technically, logistic regression is a neural network... just with no hidden layers.

![[MML - Lecture 4.pdf#page=15|MML - Lecture 4, page 15]]

> [!CARD] A Hidden Neuron
> A neuron whose value we do not observe, because we never see it.

$z=h(\mathbf{W}^{(1)}\mathbf{x})$
$\hat{y} = g^{-1}(\mathbf{W}^{(2)}\mathbf{z})$
$z\in \mathbb{R}^k$


* All we are doing when we add hidden nodes, is I'm adding columns to the weight matrix. 
* This is what we call the width of a layer.

![[MML - Lecture 4.pdf#page=16|MML - Lecture 4, page 16]]

* As well as width, we can also add depth...
* Depth, is the number of layers.
* Zero layer regression is logistic regression.
* We can make it arbitrarily deep.
![[MML - Lecture 4.pdf#page=18|MML - Lecture 4, page 18]]

* Why is it called an activation function?
	- Historical where function was 0 or 1...


![[MML - Lecture 4.pdf#page=19|MML - Lecture 4, page 19]]

* As we increases the number of basis vectors, we get more flexibility
* This is **a learned basis expansion**
* ***I don't really understand this idea of a basis expansion...***
* I think it is just increasing the dimensionality increasing the complexity of the function we can predict.

*  As we increases the number of hidden neurons, we get a better and better fit.

* Generalised linear model:
![[Pasted image 20261016151820.png]]
vs
![[Pasted image 20261016152034.png]]

![[MML - Lecture 4.pdf#page=20|MML - Lecture 4, page 20]]
* The function with a learned bias, we we can more accurately fit the function we are predicting but with fewer hidden parameters.
* Should we introduce a bias? or should we not include a bias.
* LLMs DON'T include biases.

![[Pasted image 20261016152425.png]]

A CNN or convolutional neural network applies a FILTER.

* Learned bias vs inductive bias
	* inductive bias - we add a bias in function space
	* learned bias - 

- As I move in parameter space I also move in function space.

> [!CARD] Inductive Bias
> The actual representation of my parameters and the function class, brings my function space closer to the kinds of functions that I want to learn. We still go through the origin.
> ![[Pasted image 20261016153536.png]]
>


> [!CARD] Learned Bias
> The affine transformation that brings my planes off the origin.
> ![[Pasted image 20261016153513.png]]
> 


* If all of these functions are infinitely good function approximators, why should we pick one over the other?

![[MML - Lecture 4.pdf#page=21|MML - Lecture 4, page 21]]

![[MML - Lecture 4.pdf#page=22|MML - Lecture 4, page 22]]

![[MML - Lecture 4.pdf#page=23|MML - Lecture 4, page 23]]

This is our neural network.

If we differentiate for the gradient:

![[MML - Lecture 4.pdf#page=24|MML - Lecture 4, page 24]]

We don't want to compute this every time just to work out how to continue learning the function in gradient decent.

![[MML - Lecture 4.pdf#page=25|MML - Lecture 4, page 25]]

We do numerical differentiation instead.

![[MML - Lecture 4.pdf#page=26|MML - Lecture 4, page 26]]
But we really mean $L(\theta)$ as it's the loss function.


* Forward mode automatic differentiation.

![[MML - Lecture 4.pdf#page=27|MML - Lecture 4, page 27]]

![[MML - Lecture 4.pdf#page=28|MML - Lecture 4, page 28]]

![[MML - Lecture 4.pdf#page=29|MML - Lecture 4, page 29]]

![[MML - Lecture 4.pdf#page=30|MML - Lecture 4, page 30]]

![[MML - Lecture 4.pdf#page=31|MML - Lecture 4, page 31]]

![[MML - Lecture 4.pdf#page=32|MML - Lecture 4, page 32]]

![[MML - Lecture 4.pdf#page=33|MML - Lecture 4, page 33]]

![[MML - Lecture 4.pdf#page=34|MML - Lecture 4, page 34]]

![[MML - Lecture 4.pdf#page=35|MML - Lecture 4, page 35]]

![[MML - Lecture 4.pdf#page=36|MML - Lecture 4, page 36]]

![[MML - Lecture 4.pdf#page=37|MML - Lecture 4, page 37]]

![[MML - Lecture 4.pdf#page=38|MML - Lecture 4, page 38]]

![[MML - Lecture 4.pdf#page=39|MML - Lecture 4, page 39]]

![[MML - Lecture 4.pdf#page=40|MML - Lecture 4, page 40]]

If we have n columns and T rows...

![[MML - Lecture 4.pdf#page=41|MML - Lecture 4, page 41]]

![[MML - Lecture 4.pdf#page=42|MML - Lecture 4, page 42]]

![[MML - Lecture 4.pdf#page=43|MML - Lecture 4, page 43]]

![[MML - Lecture 4.pdf#page=44|MML - Lecture 4, page 44]]

![[MML - Lecture 4.pdf#page=45|MML - Lecture 4, page 45]]

![[MML - Lecture 4.pdf#page=45|MML - Lecture 4, page 45]]

![[MML - Lecture 4.pdf#page=46|MML - Lecture 4, page 46]]

![[MML - Lecture 4.pdf#page=47|MML - Lecture 4, page 47]]

![[MML - Lecture 4.pdf#page=48|MML - Lecture 4, page 48]]

![[MML - Lecture 4.pdf#page=49|MML - Lecture 4, page 49]]

![[MML - Lecture 4.pdf#page=50|MML - Lecture 4, page 50]]

![[MML - Lecture 4.pdf#page=51|MML - Lecture 4, page 51]]

![[MML - Lecture 4.pdf#page=52|MML - Lecture 4, page 52]]

For deep neural networks we should use reverse mode! But why?