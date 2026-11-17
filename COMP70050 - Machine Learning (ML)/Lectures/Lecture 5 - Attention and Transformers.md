![[ML - Lecture 5.pdf]]
![[ML - Lecture 5.pdf#page=2|ML - Lecture 5, page 2]]

## Task and Context
### Task-specific processing
![[ML - Lecture 5.pdf#page=3|ML - Lecture 5, page 3]]
- limited number of inputs determining the weights to learn.
- Sparse network.


![[ML - Lecture 5.pdf#page=4|ML - Lecture 5, page 4]]

![[ML - Lecture 5.pdf#page=5|ML - Lecture 5, page 5]]

![[ML - Lecture 5.pdf#page=6|ML - Lecture 5, page 6]]


![[ML - Lecture 5.pdf#page=7|ML - Lecture 5, page 7]]

![[ML - Lecture 5.pdf#page=8|ML - Lecture 5, page 8]]

![[ML - Lecture 5.pdf#page=9|ML - Lecture 5, page 9]]

![[ML - Lecture 5.pdf#page=10|ML - Lecture 5, page 10]]

### Context-dependent Processing
![[ML - Lecture 5.pdf#page=12|ML - Lecture 5, page 12]]

![[ML - Lecture 5.pdf#page=13|ML - Lecture 5, page 13]]

![[ML - Lecture 5.pdf#page=14|ML - Lecture 5, page 14]]

- We can throw out signals which are not relevant to the classification and pick up the signals that are.

![[ML - Lecture 5.pdf#page=15|ML - Lecture 5, page 15]]

![[ML - Lecture 5.pdf#page=16|ML - Lecture 5, page 16]]

![[ML - Lecture 5.pdf#page=17|ML - Lecture 5, page 17]]

![[ML - Lecture 5.pdf#page=18|ML - Lecture 5, page 18]]

![[ML - Lecture 5.pdf#page=19|ML - Lecture 5, page 19]]

![[ML - Lecture 5.pdf#page=20|ML - Lecture 5, page 20]]

### Tokens and Applications
![[ML - Lecture 5.pdf#page=21|ML - Lecture 5, page 21]]

![[ML - Lecture 5.pdf#page=22|ML - Lecture 5, page 22]]

![[ML - Lecture 5.pdf#page=23|ML - Lecture 5, page 23]]

![[ML - Lecture 5.pdf#page=24|ML - Lecture 5, page 24]]

![[ML - Lecture 5.pdf#page=25|ML - Lecture 5, page 25]]

## Attention
### Weighted Sums
![[ML - Lecture 5.pdf#page=27|ML - Lecture 5, page 27]]

![[ML - Lecture 5.pdf#page=28|ML - Lecture 5, page 28]]

![[ML - Lecture 5.pdf#page=29|ML - Lecture 5, page 29]]

![[ML - Lecture 5.pdf#page=30|ML - Lecture 5, page 30]]

![[ML - Lecture 5.pdf#page=31|ML - Lecture 5, page 31]]

![[ML - Lecture 5.pdf#page=32|ML - Lecture 5, page 32]]

![[ML - Lecture 5.pdf#page=33|ML - Lecture 5, page 33]]
- we have been doing this already in kernel regression,
- For a given input X, we can compute the output of the regression 
- The nearby points contribute more to the prediction at the current location vs points further away.
- Softmax like unit

![[ML - Lecture 5.pdf#page=34|ML - Lecture 5, page 34]]

### Queries, Keys and Values
![[ML - Lecture 5.pdf#page=35|ML - Lecture 5, page 35]]


![[ML - Lecture 5.pdf#page=36|ML - Lecture 5, page 36]]

![[ML - Lecture 5.pdf#page=37|ML - Lecture 5, page 37]]

![[ML - Lecture 5.pdf#page=38|ML - Lecture 5, page 38]]

![[ML - Lecture 5.pdf#page=39|ML - Lecture 5, page 39]]

![[ML - Lecture 5.pdf#page=40|ML - Lecture 5, page 40]]

![[ML - Lecture 5.pdf#page=41|ML - Lecture 5, page 41]]

![[ML - Lecture 5.pdf#page=42|ML - Lecture 5, page 42]]
#examinable
Note: check lecture recordings for workings

![[ML - Lecture 5.pdf#page=43|ML - Lecture 5, page 43]]

![[ML - Lecture 5.pdf#page=44|ML - Lecture 5, page 44]]

![[ML - Lecture 5.pdf#page=45|ML - Lecture 5, page 45]]

![[ML - Lecture 5.pdf#page=46|ML - Lecture 5, page 46]]

![[ML - Lecture 5.pdf#page=47|ML - Lecture 5, page 47]]

![[ML - Lecture 5.pdf#page=48|ML - Lecture 5, page 48]]

![[ML - Lecture 5.pdf#page=49|ML - Lecture 5, page 49]]

![[ML - Lecture 5.pdf#page=50|ML - Lecture 5, page 50]]

![[ML - Lecture 5B.pdf]]


![[ML - Lecture 5B.pdf#page=2|ML - Lecture 5B, page 2]]

- We want the input to the self attention layer to be the same dimensionality as the output.

![[ML - Lecture 5B.pdf#page=3|ML - Lecture 5B, page 3]]
- Row by row, apply softmax unit

![[ML - Lecture 5B.pdf#page=4|ML - Lecture 5B, page 4]]

![[ML - Lecture 5B.pdf#page=5|ML - Lecture 5B, page 5]]

![[ML - Lecture 5B.pdf#page=6|ML - Lecture 5B, page 6]]

![[ML - Lecture 5B.pdf#page=7|ML - Lecture 5B, page 7]]

- Fully connected networks have fixed dimensionality.
- Convolutional networks have more flexible input dimensionality.

![[ML - Lecture 5B.pdf#page=8|ML - Lecture 5B, page 8]]

![[ML - Lecture 5B.pdf#page=9|ML - Lecture 5B, page 9]]

![[ML - Lecture 5B.pdf#page=10|ML - Lecture 5B, page 10]]

![[ML - Lecture 5B.pdf#page=11|ML - Lecture 5B, page 11]]

![[ML - Lecture 5B.pdf#page=12|ML - Lecture 5B, page 12]]

![[ML - Lecture 5B.pdf#page=13|ML - Lecture 5B, page 13]]

![[ML - Lecture 5B.pdf#page=14|ML - Lecture 5B, page 14]]


![[ML - Lecture 5B.pdf#page=15|ML - Lecture 5B, page 15]]

![[ML - Lecture 5B.pdf#page=16|ML - Lecture 5B, page 16]]

![[ML - Lecture 5B.pdf#page=17|ML - Lecture 5B, page 17]]

![[ML - Lecture 5B.pdf#page=18|ML - Lecture 5B, page 18]]

- The keys and the values are now provided by some external tokens.
- Token dimensionality no longer has to be the same.

![[ML - Lecture 5B.pdf#page=19|ML - Lecture 5B, page 19]]

![[ML - Lecture 5B.pdf#page=20|ML - Lecture 5B, page 20]]

![[ML - Lecture 5B.pdf#page=21|ML - Lecture 5B, page 21]]

![[ML - Lecture 5B.pdf#page=22|ML - Lecture 5B, page 22]]
![[ML - Lecture 5B.pdf#page=23|ML - Lecture 5B, page 23]]


![[ML - Lecture 5B.pdf#page=24|ML - Lecture 5B, page 24]]

![[ML - Lecture 5B.pdf#page=25|ML - Lecture 5B, page 25]]

![[ML - Lecture 5B.pdf#page=26|ML - Lecture 5B, page 26]]

![[ML - Lecture 5B.pdf#page=27|ML - Lecture 5B, page 27]]

- Multiple tokens, mixed amongst themselves.
- Each token carries the information it needs to provide a prediction for a task.

![[ML - Lecture 5B.pdf#page=28|ML - Lecture 5B, page 28]]

![[ML - Lecture 5B.pdf#page=29|ML - Lecture 5B, page 29]]

![[ML - Lecture 5B.pdf#page=30|ML - Lecture 5B, page 30]]

![[ML - Lecture 5B.pdf#page=31|ML - Lecture 5B, page 31]]

![[ML - Lecture 5B.pdf#page=32|ML - Lecture 5B, page 32]]

![[ML - Lecture 5B.pdf#page=33|ML - Lecture 5B, page 33]]

![[ML - Lecture 5B.pdf#page=34|ML - Lecture 5B, page 34]]

![[ML - Lecture 5B.pdf#page=35|ML - Lecture 5B, page 35]]
