---
flashcards:
  q-uzs2: { nid: 1792408126545, hash: 3uku9kkw, sync: w53sc3cr }
  q-dz5e: { nid: 1792408126597, hash: ttbkijds, sync: zzmbiyrg }
  q-2why: { nid: 1792408126648, hash: ydjdm8nm, sync: i4vxwmzz }
  q-bmzb: { nid: 1792408126701, hash: hrtghhdc, sync: cpc9ee65 }
  q-xb5x: { nid: 1792408126750, hash: jmj5i5kx, sync: qqz4nnrn }
  q-dbkg: { nid: 1792408126792, hash: s4g2sj2n, sync: 5f7qqcn8 }
  q-7qjt: { nid: 1792408126853, hash: xpy3mvmz, sync: 38abi8yk }
  q-8ukv: { nid: 1792408127121, hash: xvf4cjq5, sync: bauv8zrf }
  q-a4m3: { nid: 1792408127275, hash: hfrssmsm, sync: 7nvbv982 }
  q-mhht: { nid: 1792408127315, hash: 5rf2kmvy, sync: v2mxwckg }
---

![[ML - Lecture 3.pdf]]


## Decision Trees
![[ML - Lecture 3.pdf#page=8|ML - Lecture 3, page 8]]

* What we have is an extremely fast function to evaluate our values. Just compare which value is larger and split the space.
* Regardless of the dimensionality of the feature space we can very quickly evaluate the function.

![[ML - Lecture 3.pdf#page=9|ML - Lecture 3, page 9]]

- Beyond a certain depth we may begin overfitting features.
- How do we get around this?
	- We can limit the depth of a tree.
	- Or we can limit the number of data points each leaf node has.
	- How else can we simplify or regularise the model?

![[ML - Lecture 3.pdf#page=10|ML - Lecture 3, page 10]]

We can PRUNE the tree.
![[ML - Lecture 3.pdf#page=11|ML - Lecture 3, page 11]]

![[ML - Lecture 3.pdf#page=12|ML - Lecture 3, page 12]]

> [!CARD] What makes decision trees useful?
> - Greedy training is fast. 
> - Prediction follows a short path of tests. 
> - Tests can use different feature types, such as colour, size or shape. 
^q-uzs2


> [!CARD] How we control complexity in a decision tree?
> - Choose depth
> - Minimum leaf size
> - Pruning using validation data. 
> - Compare held-out performance with the training error.
^q-dz5e

## Bagging and Random Forests
![[ML - Lecture 3.pdf#page=13|ML - Lecture 3, page 13]]

![[ML - Lecture 3.pdf#page=14|ML - Lecture 3, page 14]]



![[ML - Lecture 3.pdf#page=15|ML - Lecture 3, page 15]]

> [!CARD] Bias-variance tradeoff
> The higher the flexibility/variance of the model, the lower the bias.
> The higher the bias of the model, the lower the flexibility of the model.
^q-2why

- Bias: can your model represent the underlying function?
- Variance: will your learned solution depend on the particular training set? (e.g. influence of noise)

When we regularise, we reduce the variance of the model and increase the bias.

The more aggressive the regularisation the higher the bias of the model and the lower the variance.

![[ML - Lecture 3.pdf#page=16|ML - Lecture 3, page 16]]


![[ML - Lecture 3.pdf#page=17|ML - Lecture 3, page 17]]

* N.B. Bias-variance tradeoff math not examinable

![[ML - Lecture 3.pdf#page=18|ML - Lecture 3, page 18]]

![[ML - Lecture 3.pdf#page=19|ML - Lecture 3, page 19]]

![[ML - Lecture 3.pdf#page=20|ML - Lecture 3, page 20]]
- We hope that the errors for each of the models is uncorrelated.
- aka - ensemble learning
- We can do average of results or voting.

![[ML - Lecture 3.pdf#page=21|ML - Lecture 3, page 21]]

![[ML - Lecture 3.pdf#page=22|ML - Lecture 3, page 22]]

- We can use an ensemble to minimise the variance.
- But what about bias?

- We assume that the errors are uncorrelated.
- This means that the bias remains unaffected...
	- But is this a fair assumption to make in the real world?


## Bagging, Bootstrapping
![[ML - Lecture 3.pdf#page=23|ML - Lecture 3, page 23]]

> [!CARD] Bagging
> Sampling a subset of rows with repetition.
^q-bmzb

![[ML - Lecture 3.pdf#page=24|ML - Lecture 3, page 24]]

> [!CARD] Bias
^q-xb5x


> [!CARD] Variance
^q-dbkg


![[ML - Lecture 3.pdf#page=25|ML - Lecture 3, page 25]]


 
![[ML - Lecture 3.pdf#page=26|ML - Lecture 3, page 26]]

![[ML - Lecture 3.pdf#page=27|ML - Lecture 3, page 27]]

![[ML - Lecture 3.pdf#page=28|ML - Lecture 3, page 28]]

- Random forest, is a combination of decision trees, to improve the generalisation of the model.
![[ML - Lecture 3.pdf#page=29|ML - Lecture 3, page 29]]

> [!CARD] Limits and benefits of greedy feature selection.
> - Extremely flexible classifiers (power of composition) 
> - Low-cost (simple comparisons, no kernel evaluations) 
> - But: learned greedily An alternative: use a vast feature space through a kernel. 
> - Later splits do not jointly retune the earlier tests.
> 
^q-7qjt
## Kernels and SVMs
![[ML - Lecture 3.pdf#page=30|ML - Lecture 3, page 30]]

![[ML - Lecture 3.pdf#page=31|ML - Lecture 3, page 31]]

![[ML - Lecture 3.pdf#page=32|ML - Lecture 3, page 32]]
- $\alpha$ is being optimised in the training here for SVMs.
- 


![[ML - Lecture 3.pdf#page=33|ML - Lecture 3, page 33]]

![[ML - Lecture 3.pdf#page=34|ML - Lecture 3, page 34]]
![[ML - Lecture 3.pdf#page=35|ML - Lecture 3, page 35]]

![[ML - Lecture 3.pdf#page=36|ML - Lecture 3, page 36]]
![[ML - Lecture 3.pdf#page=37|ML - Lecture 3, page 37]]

> [!CARD] Trees and forests 
> Select paths of tests from many possible combinations. 
> Choose splits greedily, without jointly retuning earlier tests. 
^q-8ukv

> [!CARD] Fixed-kernel methods 
> Use implicit features through kernel evaluations. 
> Fit classifier coefficients while the chosen feature map stays fixed. 
^q-a4m3

> [!CARD] Neural networks 
> Optimise intermediate features and the final predictor together, using the final prediction loss.
^q-mhht

## Neural Networks
![[ML - Lecture 3.pdf#page=38|ML - Lecture 3, page 38]]

![[ML - Lecture 3.pdf#page=39|ML - Lecture 3, page 39]]

![[ML - Lecture 3.pdf#page=40|ML - Lecture 3, page 40]]

![[ML - Lecture 3.pdf#page=41|ML - Lecture 3, page 41]]

![[ML - Lecture 3.pdf#page=42|ML - Lecture 3, page 42]]

![[ML - Lecture 3.pdf#page=44|ML - Lecture 3, page 44]]

![[ML - Lecture 3.pdf#page=45|ML - Lecture 3, page 45]]

![[ML - Lecture 3.pdf#page=46|ML - Lecture 3, page 46]]

Exclusive OR function XOR cannot be solved using a linear function...
- How to solve this?

![[ML - Lecture 3.pdf#page=47|ML - Lecture 3, page 47]]

- We have a composition of functions, the input is transformed by 2 functions then combined.


- This is done with linear decision boundaries

![[ML - Lecture 3.pdf#page=48|ML - Lecture 3, page 48]]

- This is calculated by inspection
- But we can estimate the weights of the model by optimisation.

![[ML - Lecture 3.pdf#page=49|ML - Lecture 3, page 49]]

![[ML - Lecture 3.pdf#page=50|ML - Lecture 3, page 50]]

#IMPORTANT
![[ML - Lecture 3.pdf#page=51|ML - Lecture 3, page 51]]

![[ML - Lecture 3.pdf#page=52|ML - Lecture 3, page 52]]

We can't use a step perceptron as it is not differentiable.


![[ML - Lecture 3.pdf#page=53|ML - Lecture 3, page 53]]

> [!CARD] Why do we use non-linear activation functions in neural networks?
> Without non-linear activations, stacking layers would just collapse into a single linear transformation, so the network could only learn linear decision boundaries. Non-linearities let it model complex, non-linear functions.

![[ML - Lecture 3.pdf#page=54|ML - Lecture 3, page 54]]

![[ML - Lecture 3.pdf#page=55|ML - Lecture 3, page 55]]

![[ML - Lecture 3.pdf#page=56|ML - Lecture 3, page 56]]

* The boundaries look a lot like in the XOR case...

![[ML - Lecture 3.pdf#page=57|ML - Lecture 3, page 57]]


> [!CARD] Affine Transformation
> Affine means a linear transformation plus a bias/translation term (e.g., y = Wx + b), so it's linear in the weights but doesn't have to pass through the origin.


![[ML - Lecture 3.pdf#page=58|ML - Lecture 3, page 58]]

## Expressiveness and Representations
![[ML - Lecture 3.pdf#page=59|ML - Lecture 3, page 59]]

When we optimise in neural networks, there is no one unique optimal solution.

![[ML - Lecture 3.pdf#page=60|ML - Lecture 3, page 60]]

- You can take any function and approximate it using neural networks.

![[ML - Lecture 3.pdf#page=61|ML - Lecture 3, page 61]]

Assuming you use enough elements in your hidden layer, we can prove that you can approximate any function using a neural network with a single layer.

But how can we improve generalisation... we can use multiple hidden layers in the neural network.

![[ML - Lecture 3.pdf#page=62|ML - Lecture 3, page 62]]

![[ML - Lecture 3.pdf#page=63|ML - Lecture 3, page 63]]

![[ML - Lecture 3.pdf#page=64|ML - Lecture 3, page 64]]

![[ML - Lecture 3.pdf#page=65|ML - Lecture 3, page 65]]

![[ML - Lecture 3.pdf#page=66|ML - Lecture 3, page 66]]


- Probability distribution needs to sum to 1
- This triangular plane on the far right, this plane represents this, all the points must lie somewhere on this plane

![[ML - Lecture 3.pdf#page=67|ML - Lecture 3, page 67]]
![[ML - Lecture 3.pdf#page=68|ML - Lecture 3, page 68]]

- In real life we have much deeper neural network and much higher dimension feature space.