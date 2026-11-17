![[ML - Lecture 4.pdf]]

![[ML - Lecture 4.pdf#page=2|ML - Lecture 4, page 2]]

![[ML - Lecture 4.pdf#page=3|ML - Lecture 4, page 3]]

- We send gradients back through the network so we don't have to repeat computation.

## Optimisation
### Gradient Descent and SGD
![[ML - Lecture 4.pdf#page=4|ML - Lecture 4, page 4]]

![[ML - Lecture 4.pdf#page=5|ML - Lecture 4, page 5]]

![[ML - Lecture 4.pdf#page=6|ML - Lecture 4, page 6]]

![[ML - Lecture 4.pdf#page=7|ML - Lecture 4, page 7]]

![[ML - Lecture 4.pdf#page=8|ML - Lecture 4, page 8]]

- Learning rates make or break the training.
	- Too big and we diverge
	- Too small we train forever

- Decaying learning rates:
![[ML - Lecture 4.pdf#page=9|ML - Lecture 4, page 9]]

- We can start with relatively high learning rates and decrease accordingly.
- The optimisation of NN is harder than other ML techniques.

### Momentum and Adam
![[ML - Lecture 4.pdf#page=10|ML - Lecture 4, page 10]]



![[ML - Lecture 4.pdf#page=11|ML - Lecture 4, page 11]]

![[ML - Lecture 4.pdf#page=12|ML - Lecture 4, page 12]]

![[ML - Lecture 4.pdf#page=13|ML - Lecture 4, page 13]]

![[ML - Lecture 4.pdf#page=14|ML - Lecture 4, page 14]]

- For very small changes in B, we have very big changes in our loss.

![[ML - Lecture 4.pdf#page=15|ML - Lecture 4, page 15]]

- Function similar to quadratic in the cross section

$L(a,b) = (y-abx)^2 = (1-ab)^2$
$1 - 2ab + a^2 b^2$


![[ML - Lecture 4.pdf#page=16|ML - Lecture 4, page 16]]

- When we have a very highly curved function we need to make sure we have a low learning rate or we converge...


![[ML - Lecture 4.pdf#page=17|ML - Lecture 4, page 17]]

- If our learning rate here is too high here, we will quickly diverged.
- This is because the gradient is very steep.
- We can adjust the learning rate to change with the gradient of the function.

![[ML - Lecture 4.pdf#page=18|ML - Lecture 4, page 18]]

![[ML - Lecture 4.pdf#page=19|ML - Lecture 4, page 19]]

- You can start in very similar places with GD but end up at different minima of the function
	- We can get stuck in local minima
	- And it can be very tricky to correctly set the learning rate for highly curved functions.

![[ML - Lecture 4.pdf#page=20|ML - Lecture 4, page 20]]

- We have a lot of points that do not converge. How do we solve this in GD?

SGD - Stochastic Gradient Descent
![[ML - Lecture 4.pdf#page=21|ML - Lecture 4, page 21]]

> [!CARD] How does momentum differ from (S)GD in the parameter update?
> SGD updates directly with the gradient: $\theta_{t+1} = \theta_t - \eta_t g_t$. Momentum updates with an exponential moving average of past gradients: $m_t = \beta m_{t-1} + (1-\beta) g_t$, then $\theta_{t+1} = \theta_t - \eta_t m_t$. Across a valley, successive gradients point in opposite directions and cancel in $m_t$. Along it they agree and add up.

$$
% (S)GD
\boldsymbol{\theta}_{t+1} = \boldsymbol{\theta}_t - \eta_t \mathbf{g}_t
\\
% Momentum
\mathbf{m}_t = \beta \mathbf{m}_{t-1} + (1-\beta)\mathbf{g}_t
\boldsymbol{\theta}_{t+1} = \boldsymbol{\theta}_t - \eta_t \mathbf{m}_t$$

Momentum: $\beta = 0$ we go back to gradient descent

![[ML - Lecture 4.pdf#page=22|ML - Lecture 4, page 22]]

![[ML - Lecture 4.pdf#page=23|ML - Lecture 4, page 23]]

- Momentum can overshoot and bypass the local minimum as it has the memory of the direction of travel. 
	- We can also bypass the global minimum but we will return.

![[ML - Lecture 4.pdf#page=24|ML - Lecture 4, page 24]]
- RMSProp keeps an average of the gradient squared.

![[ML - Lecture 4.pdf#page=22|ML - Lecture 4, page 22]]

- Adam takes the best of both worlds and normalises the gradient using both techniques.
- We combine the estimate of momentum, taking the gradient valued across every axis and the current gradient value.

![[ML - Lecture 4.pdf#page=26|ML - Lecture 4, page 26]]

![[ML - Lecture 4.pdf#page=27|ML - Lecture 4, page 27]]

![[ML - Lecture 4.pdf#page=28|ML - Lecture 4, page 28]]

![[ML - Lecture 4.pdf#page=29|ML - Lecture 4, page 29]]

- Adam: adaptive moment estimation.

### Depth Issues
![[ML - Lecture 4.pdf#page=30|ML - Lecture 4, page 30]]
- Vanishing or exploding gradients problems

![[ML - Lecture 4.pdf#page=31|ML - Lecture 4, page 31]]

![[ML - Lecture 4.pdf#page=32|ML - Lecture 4, page 32]]

![[ML - Lecture 4.pdf#page=33|ML - Lecture 4, page 33]]
- The behaviour of the derivative of the sigmoidal is challenging.


![[ML - Lecture 4.pdf#page=34|ML - Lecture 4, page 34]]

![[ML - Lecture 4.pdf#page=35|ML - Lecture 4, page 35]]

- Better behaved ReLU functions

![[ML - Lecture 4.pdf#page=36|ML - Lecture 4, page 36]]

![[ML - Lecture 4.pdf#page=37|ML - Lecture 4, page 37]]

![[ML - Lecture 4.pdf#page=38|ML - Lecture 4, page 38]]

- If I have an input to a combination of layers, I can output the transformation of the input and the input itself. 
- This is known as a skipped signal.

![[ML - Lecture 4.pdf#page=39|ML - Lecture 4, page 39]]

- Allows us to skip layers that are defective or are doing something wrong.

![[ML - Lecture 4.pdf#page=40|ML - Lecture 4, page 40]]

- Skip connections can have the effect of convexifying the loss function.

![[ML - Lecture 4.pdf#page=41|ML - Lecture 4, page 41]]

![[ML - Lecture 4.pdf#page=42|ML - Lecture 4, page 42]]

### Scale Issues
![[ML - Lecture 4.pdf#page=43|ML - Lecture 4, page 43]]

![[ML - Lecture 4.pdf#page=44|ML - Lecture 4, page 44]]

![[ML - Lecture 4.pdf#page=45|ML - Lecture 4, page 45]]
![[ML - Lecture 4.pdf#page=46|ML - Lecture 4, page 46]]

- Best practice with normalisation:
![[ML - Lecture 4.pdf#page=47|ML - Lecture 4, page 47]]

- Should we normalise across batches - batchnorm
- Should we normalise across current activation vector - layernorm

![[ML - Lecture 4.pdf#page=48|ML - Lecture 4, page 48]]

![[ML - Lecture 4.pdf#page=49|ML - Lecture 4, page 49]]

![[ML - Lecture 4.pdf#page=50|ML - Lecture 4, page 50]]

- In layer normalisation, we go sample by sample...

![[ML - Lecture 4.pdf#page=51|ML - Lecture 4, page 51]]

- Neural Networks can very quickly overfit - big parameter budget.


## Generalisation
### Dropout

![[ML - Lecture 4.pdf#page=52|ML - Lecture 4, page 52]]

![[ML - Lecture 4.pdf#page=53|ML - Lecture 4, page 53]]

- The **weight decay rate** is set instead of lamda, similiar to lambda,
- Just ensure that the weights don't get too big.
- Just another regulariser.

![[ML - Lecture 4.pdf#page=54|ML - Lecture 4, page 54]]

- Similar to random forest and pruning?

![[ML - Lecture 4.pdf#page=55|ML - Lecture 4, page 55]]

Bernoulli(p) - for each of the activations, what is the probability that one stays alive. To what extent do we decimate our network.

How does dropout compare to L2 regularisation?
![[ML - Lecture 4.pdf#page=56|ML - Lecture 4, page 56]]


### Data Augmentation
![[ML - Lecture 4.pdf#page=57|ML - Lecture 4, page 57]]
![[ML - Lecture 4.pdf#page=58|ML - Lecture 4, page 58]]


![[ML - Lecture 4.pdf#page=60|ML - Lecture 4, page 60]]

### Early Stopping
![[ML - Lecture 4.pdf#page=61|ML - Lecture 4, page 61]]

![[ML - Lecture 4.pdf#page=62|ML - Lecture 4, page 62]]

- Take the solution that gives the best performance on the validation set.


![[ML - Lecture 4.pdf#page=63|ML - Lecture 4, page 63]]

- Choosing hyper-parameters based on cross-validation...

## Convolutional Networks
![[RL - Lecture 4B.pdf]]

![[RL - Lecture 4B.pdf#page=2|RL - Lecture 4B, page 2]]

- Denoise images 

![[RL - Lecture 4B.pdf#page=3|RL - Lecture 4B, page 3]]

![[RL - Lecture 4B.pdf#page=4|RL - Lecture 4B, page 4]]

- end up with a much smoother surface

![[RL - Lecture 4B.pdf#page=5|RL - Lecture 4B, page 5]]

- box filter just takes the average of neighbouring pixels.

![[RL - Lecture 4B.pdf#page=6|RL - Lecture 4B, page 6]]

![[RL - Lecture 4B.pdf#page=7|RL - Lecture 4B, page 7]]

![[RL - Lecture 4B.pdf#page=8|RL - Lecture 4B, page 8]]

![[RL - Lecture 4B.pdf#page=9|RL - Lecture 4B, page 9]]

- Different kernels are needed to detect different properties within an image.
- These Kernels are not constructed manually, they are shaped by back-propagation from the loss function.


![[RL - Lecture 4B.pdf#page=10|RL - Lecture 4B, page 10]]

![[RL - Lecture 4B.pdf#page=11|RL - Lecture 4B, page 11]]
![[RL - Lecture 4B.pdf#page=12|RL - Lecture 4B, page 12]]

![[RL - Lecture 4B.pdf#page=13|RL - Lecture 4B, page 13]]

![[RL - Lecture 4B.pdf#page=14|RL - Lecture 4B, page 14]]

- We set most weights to be zero by design.
- Reuse the same weights at every location.
- This reduces D.O.F. for the model, most elements in the matrix are zero so can improve the efficiency of implementation.
- Convolution involves pooling the input signal and applying some filter

![[RL - Lecture 4B.pdf#page=15|RL - Lecture 4B, page 15]]

![[RL - Lecture 4B.pdf#page=16|RL - Lecture 4B, page 16]]

![[RL - Lecture 4B.pdf#page=17|RL - Lecture 4B, page 17]]

![[RL - Lecture 4B.pdf#page=18|RL - Lecture 4B, page 18]]

![[RL - Lecture 4B.pdf#page=19|RL - Lecture 4B, page 19]]

![[RL - Lecture 4B.pdf#page=20|RL - Lecture 4B, page 20]]

![[RL - Lecture 4B.pdf#page=21|RL - Lecture 4B, page 21]]

- here we are downsizing by 2/stride of 2

![[RL - Lecture 4B.pdf#page=22|RL - Lecture 4B, page 22]]

- Give us the benefit of robustness against noise in our signals.

![[RL - Lecture 4B.pdf#page=23|RL - Lecture 4B, page 23]]

- How information propogates from the input signal through the network.

![[RL - Lecture 4B.pdf#page=24|RL - Lecture 4B, page 24]]

![[RL - Lecture 4B.pdf#page=25|RL - Lecture 4B, page 25]]

- We have a fully connected layer which gives us our categorical response.
- In the convolutional layers, each sample identifies signals and passes them through to the output layer...

## Vision Tasks
![[RL - Lecture 4B.pdf#page=26|RL - Lecture 4B, page 26]]

![[RL - Lecture 4B.pdf#page=27|RL - Lecture 4B, page 27]]

![[RL - Lecture 4B.pdf#page=28|RL - Lecture 4B, page 28]]

![[RL - Lecture 4B.pdf#page=29|RL - Lecture 4B, page 29]]

![[RL - Lecture 4B.pdf#page=30|RL - Lecture 4B, page 30]]

![[RL - Lecture 4B.pdf#page=31|RL - Lecture 4B, page 31]]

![[RL - Lecture 4B.pdf#page=32|RL - Lecture 4B, page 32]]

![[RL - Lecture 4B.pdf#page=33|RL - Lecture 4B, page 33]]

![[RL - Lecture 4B.pdf#page=34|RL - Lecture 4B, page 34]]


![[RL - Lecture 4B.pdf#page=35|RL - Lecture 4B, page 35]]

![[RL - Lecture 4B.pdf#page=36|RL - Lecture 4B, page 36]]

![[RL - Lecture 4B.pdf#page=37|RL - Lecture 4B, page 37]]

![[RL - Lecture 4B.pdf#page=38|RL - Lecture 4B, page 38]]

![[RL - Lecture 4B.pdf#page=39|RL - Lecture 4B, page 39]]

![[RL - Lecture 4B.pdf#page=40|RL - Lecture 4B, page 40]]


![[RL - Lecture 4B.pdf#page=41|RL - Lecture 4B, page 41]]

![[RL - Lecture 4B.pdf#page=42|RL - Lecture 4B, page 42]]

![[RL - Lecture 4B.pdf#page=43|RL - Lecture 4B, page 43]]

![[RL - Lecture 4B.pdf#page=44|RL - Lecture 4B, page 44]]

![[RL - Lecture 4B.pdf#page=45|RL - Lecture 4B, page 45]]

![[RL - Lecture 4B.pdf#page=46|RL - Lecture 4B, page 46]]

![[RL - Lecture 4B.pdf#page=47|RL - Lecture 4B, page 47]]

![[RL - Lecture 4B.pdf#page=48|RL - Lecture 4B, page 48]]

![[RL - Lecture 4B.pdf#page=49|RL - Lecture 4B, page 49]]

![[RL - Lecture 4B.pdf#page=50|RL - Lecture 4B, page 50]]

![[RL - Lecture 4B.pdf#page=51|RL - Lecture 4B, page 51]]

![[RL - Lecture 4B.pdf#page=52|RL - Lecture 4B, page 52]]

![[RL - Lecture 4B.pdf#page=53|RL - Lecture 4B, page 53]]

![[RL - Lecture 4B.pdf#page=54|RL - Lecture 4B, page 54]]

![[RL - Lecture 4B.pdf#page=55|RL - Lecture 4B, page 55]]

![[RL - Lecture 4B.pdf#page=56|RL - Lecture 4B, page 56]]

![[RL - Lecture 4B.pdf#page=57|RL - Lecture 4B, page 57]]

## Transfer Learning
![[RL - Lecture 4B.pdf#page=58|RL - Lecture 4B, page 58]]


## Exercises
$X ⇒ Z ⇒ h$
![[Scan from 2026-10-29 01_30_47 PM.pdf]]