![[ML - Lecture 6.pdf]]

# Introduction
## Supervised Learning so far: models, transfer

![[ML - Lecture 6.pdf#page=3|ML - Lecture 6, page 3]]

![[ML - Lecture 6.pdf#page=4|ML - Lecture 6, page 4]]

![[ML - Lecture 6.pdf#page=5|ML - Lecture 6, page 5]]

![[ML - Lecture 6.pdf#page=6|ML - Lecture 6, page 6]]

![[ML - Lecture 6.pdf#page=7|ML - Lecture 6, page 7]]

- Image vision transformer
![[ML - Lecture 6.pdf#page=8|ML - Lecture 6, page 8]]

- Additional token - the class token
- One token charged with predicting the class
- Transformers scale better than CNNs

![[ML - Lecture 6.pdf#page=9|ML - Lecture 6, page 9]]

- Small models plateau, transformers continue to see reductions in error with more compute, but there are diminishing returns.

![[ML - Lecture 6.pdf#page=10|ML - Lecture 6, page 10]]

![[ML - Lecture 6.pdf#page=11|ML - Lecture 6, page 11]]

![[ML - Lecture 6.pdf#page=12|ML - Lecture 6, page 12]]

![[ML - Lecture 6.pdf#page=13|ML - Lecture 6, page 13]]

## Self-supervision
![[ML - Lecture 6.pdf#page=14|ML - Lecture 6, page 14]]

![[ML - Lecture 6.pdf#page=15|ML - Lecture 6, page 15]]

#not-examinable
![[ML - Lecture 6.pdf#page=16|ML - Lecture 6, page 16]]

![[ML - Lecture 6.pdf#page=17|ML - Lecture 6, page 17]]

![[ML - Lecture 6.pdf#page=18|ML - Lecture 6, page 18]]

![[ML - Lecture 6.pdf#page=19|ML - Lecture 6, page 19]]



![[ML - Lecture 6.pdf#page=20|ML - Lecture 6, page 20]]

![[ML - Lecture 6.pdf#page=21|ML - Lecture 6, page 21]]

- Our transformations of each image should be close in spaces or at least closer than the transformations of another image.

![[ML - Lecture 6.pdf#page=22|ML - Lecture 6, page 22]]

![[ML - Lecture 6.pdf#page=23|ML - Lecture 6, page 23]]

![[ML - Lecture 6.pdf#page=24|ML - Lecture 6, page 24]]

![[ML - Lecture 6.pdf#page=25|ML - Lecture 6, page 25]]

## Language Models: predict, then sample

![[ML - Lecture 6.pdf#page=26|ML - Lecture 6, page 26]]

![[ML - Lecture 6.pdf#page=27|ML - Lecture 6, page 27]]

![[ML - Lecture 6.pdf#page=28|ML - Lecture 6, page 28]]

![[ML - Lecture 6.pdf#page=29|ML - Lecture 6, page 29]]

![[ML - Lecture 6.pdf#page=30|ML - Lecture 6, page 30]]

![[ML - Lecture 6.pdf#page=31|ML - Lecture 6, page 31]]

![[ML - Lecture 6.pdf#page=32|ML - Lecture 6, page 32]]


![[ML - Lecture 6.pdf#page=33|ML - Lecture 6, page 33]]

#examinable
# Learning the Structure of Data
## Generative Models and Hidden Factors
![[ML - Lecture 6.pdf#page=34|ML - Lecture 6, page 34]]

![[ML - Lecture 6.pdf#page=35|ML - Lecture 6, page 35]]

![[ML - Lecture 6.pdf#page=36|ML - Lecture 6, page 36]]

![[ML - Lecture 6.pdf#page=37|ML - Lecture 6, page 37]]

![[ML - Lecture 6.pdf#page=38|ML - Lecture 6, page 38]]

![[ML - Lecture 6.pdf#page=39|ML - Lecture 6, page 39]]

![[ML - Lecture 6.pdf#page=40|ML - Lecture 6, page 40]]

![[ML - Lecture 6.pdf#page=41|ML - Lecture 6, page 41]]

![[ML - Lecture 6.pdf#page=42|ML - Lecture 6, page 42]]

![[ML - Lecture 6.pdf#page=43|ML - Lecture 6, page 43]]
### K-Means
![[ML - Lecture 6.pdf#page=44|ML - Lecture 6, page 44]]

![[ML - Lecture 6.pdf#page=45|ML - Lecture 6, page 45]]

- Euclidian distance from my point and my cluster centre
- Take the average and assign the cluster again
- Repeat until we converge

![[ML - Lecture 6.pdf#page=46|ML - Lecture 6, page 46]]

![[ML - Lecture 6.pdf#page=47|ML - Lecture 6, page 47]]

![[ML - Lecture 6.pdf#page=48|ML - Lecture 6, page 48]]

### PCA
![[ML - Lecture 6.pdf#page=49|ML - Lecture 6, page 49]]

![[ML - Lecture 6.pdf#page=50|ML - Lecture 6, page 50]]

![[ML - Lecture 6.pdf#page=52|ML - Lecture 6, page 52]]

![[ML - Lecture 6.pdf#page=53|ML - Lecture 6, page 53]]

![[ML - Lecture 6.pdf#page=54|ML - Lecture 6, page 54]]

![[ML - Lecture 6.pdf#page=55|ML - Lecture 6, page 55]]

![[ML - Lecture 6.pdf#page=56|ML - Lecture 6, page 56]]

- Minimise the average error

![[ML - Lecture 6.pdf#page=57|ML - Lecture 6, page 57]]

We get a $D\times D$ matrix

![[ML - Lecture 6.pdf#page=58|ML - Lecture 6, page 58]]

![[ML - Lecture 6.pdf#page=59|ML - Lecture 6, page 59]]

![[ML - Lecture 6.pdf#page=60|ML - Lecture 6, page 60]]

![[ML - Lecture 6.pdf#page=61|ML - Lecture 6, page 61]]

![[ML - Lecture 6.pdf#page=62|ML - Lecture 6, page 62]]

![[ML - Lecture 6.pdf#page=63|ML - Lecture 6, page 63]]

![[ML - Lecture 6.pdf#page=64|ML - Lecture 6, page 64]]

### Autoencoders
![[ML - Lecture 6.pdf#page=66|ML - Lecture 6, page 66]]

![[ML - Lecture 6.pdf#page=67|ML - Lecture 6, page 67]]

- we are now looking at non-linear encoding and decoding. 
- Using a neural network.

![[ML - Lecture 6.pdf#page=68|ML - Lecture 6, page 68]]



![[ML - Lecture 6B.pdf]]

![[ML - Lecture 6B.pdf#page=2|ML - Lecture 6B, page 2]]

- k-means and PCA essentially linear functions, autoencoder is a general, non-linear function
- All minimise L2 norm

![[ML - Lecture 6B.pdf#page=3|ML - Lecture 6B, page 3]]

![[ML - Lecture 6B.pdf#page=4|ML - Lecture 6B, page 4]]

![[ML - Lecture 6B.pdf#page=5|ML - Lecture 6B, page 5]]

![[ML - Lecture 6B.pdf#page=6|ML - Lecture 6B, page 6]]

![[ML - Lecture 6B.pdf#page=7|ML - Lecture 6B, page 7]]


![[ML - Lecture 6B.pdf#page=8|ML - Lecture 6B, page 8]]

![[ML - Lecture 6B.pdf#page=9|ML - Lecture 6B, page 9]]
- Picking random codes from the autoencoder, we end up with a high proportion of invalid examples.
- This is not generative...

# Gaussian Mixtures
![[ML - Lecture 6B.pdf#page=10|ML - Lecture 6B, page 10]]

![[ML - Lecture 6B.pdf#page=11|ML - Lecture 6B, page 11]]

![[ML - Lecture 6B.pdf#page=12|ML - Lecture 6B, page 12]]

![[ML - Lecture 6B.pdf#page=13|ML - Lecture 6B, page 13]]

![[ML - Lecture 6B.pdf#page=14|ML - Lecture 6B, page 14]]

![[ML - Lecture 6B.pdf#page=15|ML - Lecture 6B, page 15]]

- Ancestral sampling
![[ML - Lecture 6B.pdf#page=16|ML - Lecture 6B, page 16]]

- Expectation Maximisation Algorithm

![[ML - Lecture 6B.pdf#page=17|ML - Lecture 6B, page 17]]

![[ML - Lecture 6B.pdf#page=18|ML - Lecture 6B, page 18]]

![[ML - Lecture 6B.pdf#page=19|ML - Lecture 6B, page 19]]
- Bayesian Updating


# Expectation Maximisation
![[ML - Lecture 6B.pdf#page=20|ML - Lecture 6B, page 20]]


![[ML - Lecture 6B.pdf#page=21|ML - Lecture 6B, page 21]]

![[ML - Lecture 6B.pdf#page=22|ML - Lecture 6B, page 22]]
- Use bayes' rule to update...

![[ML - Lecture 6B.pdf#page=23|ML - Lecture 6B, page 23]]

- Bayes' rule used to assign point n to cluster k

![[ML - Lecture 6B.pdf#page=24|ML - Lecture 6B, page 24]]

![[ML - Lecture 6B.pdf#page=25|ML - Lecture 6B, page 25]]

![[ML - Lecture 6B.pdf#page=26|ML - Lecture 6B, page 26]]

![[ML - Lecture 6B.pdf#page=27|ML - Lecture 6B, page 27]]

![[ML - Lecture 6B.pdf#page=28|ML - Lecture 6B, page 28]]

![[ML - Lecture 6B.pdf#page=29|ML - Lecture 6B, page 29]]

![[ML - Lecture 6B.pdf#page=30|ML - Lecture 6B, page 30]]

![[ML - Lecture 6B.pdf#page=28|ML - Lecture 6B, page 28]]

