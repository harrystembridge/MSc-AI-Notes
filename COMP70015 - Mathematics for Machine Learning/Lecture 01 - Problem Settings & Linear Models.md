Interactive slides: https://math4ml.quail-lab.com/lectures/01/lecture_01#/L01_S01

![[ML Lecture 01 - Slides.pdf]]

![[ML Lecture 01 - Slides.pdf#page=1]]

![[ML Lecture 01 - Slides.pdf#page=2]]

![[ML Lecture 01 - Slides.pdf#page=3]]

![[ML Lecture 01 - Slides.pdf#page=4]]

![[ML Lecture 01 - Slides.pdf#page=5]]

![[ML Lecture 01 - Slides.pdf#page=6]]

![[ML Lecture 01 - Slides.pdf#page=7]]

![[ML Lecture 01 - Slides.pdf#page=8]]

![[ML Lecture 01 - Slides.pdf#page=9]]

![[ML Lecture 01 - Slides.pdf#page=10]]

![[ML Lecture 01 - Slides.pdf#page=11]]

![[ML Lecture 01 - Slides.pdf#page=12]]

![[ML Lecture 01 - Slides.pdf#page=13]]

![[ML Lecture 01 - Slides.pdf#page=14]]

![[ML Lecture 01 - Slides.pdf#page=15]]

![[ML Lecture 01 - Slides.pdf#page=16]]

![[ML Lecture 01 - Slides.pdf#page=17]]

![[ML Lecture 01 - Slides.pdf#page=18]]

![[ML Lecture 01 - Slides.pdf#page=19]]

![[ML Lecture 01 - Slides.pdf#page=20]]

![[ML Lecture 01 - Slides.pdf#page=21]]

![[ML Lecture 01 - Slides.pdf#page=22]]

![[ML Lecture 01 - Slides.pdf#page=23]]

![[ML Lecture 01 - Slides.pdf#page=24]]

![[ML Lecture 01 - Slides.pdf#page=25]]

* What happens if our vector is not full rank? Part is a linear combination of another, we are encoding redundant data.

![[ML Lecture 01 - Slides.pdf#page=26]]



![[ML Lecture 01 - Slides.pdf#page=27]]

![[ML Lecture 01 - Slides.pdf#page=28]]

![[ML Lecture 01 - Slides.pdf#page=29]]

![[ML Lecture 01 - Slides.pdf#page=30]]

![[ML Lecture 01 - Slides.pdf#page=31]]
* Here we can be more wrong, the further we are from the true speed limit... can be regression or classification.

![[ML Lecture 01 - Slides.pdf#page=32]]
* Don't necessarily have labels

![[ML Lecture 01 - Slides.pdf#page=33]]

![[ML Lecture 01 - Slides.pdf#page=34]]

![[ML Lecture 01 - Slides.pdf#page=35]]

![[ML Lecture 01 - Slides.pdf#page=36]]

![[ML Lecture 01 - Slides.pdf#page=37]]

![[ML Lecture 01 - Slides.pdf#page=38]]

![[ML Lecture 01 - Slides.pdf#page=39]]

![[ML Lecture 01 - Slides.pdf#page=40]]

![[ML Lecture 01 - Slides.pdf#page=41]]
* We either have a vector, matrix or tensor...
* What is the difference?
* Tensors have multiple dimensions and a single index per dimension


![[ML Lecture 01 - Slides.pdf#page=42]]
* This is called **Tensor Contraction** - we are contracting away a dimension.
* ***TYPO - $B_{k,o} ⇒ B_{k,u}$***


![[ML Lecture 01 - Slides.pdf#page=43]]

![[ML Lecture 01 - Slides.pdf#page=44]]

![[ML Lecture 01 - Slides.pdf#page=45]]
* This final condition, implies that T(0*v)=0*T(v)
* This means that everything must pass through the origin.

![[ML Lecture 01 - Slides.pdf#page=46]]

* We can get around this be normalising the data by subtracting the average:

![[ML Lecture 01 - Slides.pdf#page=47]]



![[ML Lecture 01 - Slides.pdf#page=48]]

* The second one of these is correct (you would lose points for writing the first 1)
* You can't multiply together the vectors in the first one.
* It doesn't type check.
* The output of the function in the second one is a scalar.

![[ML Lecture 01 - Slides.pdf#page=49]]

![[ML Lecture 01 - Slides.pdf#page=50]]

![[ML Lecture 01 - Slides.pdf#page=51]]

* This is our vector of predictions in a linear model.

![[ML Lecture 01 - Slides.pdf#page=52]]

![[ML Lecture 01 - Slides.pdf#page=53]]

![[ML Lecture 01 - Slides.pdf#page=54]]

![[ML Lecture 01 - Slides.pdf#page=55]]

* The p norm, when p = 1 calculates **the Manhattan distance**

![[ML Lecture 01 - Slides.pdf#page=56]]

![[ML Lecture 01 - Slides.pdf#page=57]]

* We can measure error using norms

![[ML Lecture 01 - Slides.pdf#page=58]]

![[ML Lecture 01 - Slides.pdf#page=59]]

* Choosing your norm, changes the answer you get for your parameters.
* We can reason about what p we choose in practice.
* What does this mean intuitively, do we favour being close to some or being less far away from others?

![[ML Lecture 01 - Slides.pdf#page=60]]

* Sub in $\hat{y} = \mathbf{X}\theta$

![[ML Lecture 01 - Slides.pdf#page=61]]

* $\text{argmin}$ returns the value of the argument which minimises the loss function, not the actual minimum value of the loss function.

![[ML Lecture 01 - Slides.pdf#page=62]]

![[ML Lecture 01 - Slides.pdf#page=63]]

![[ML Lecture 01 - Slides.pdf#page=64]]

![[ML Lecture 01 - Slides.pdf#page=65]]

![[ML Lecture 01 - Slides.pdf#page=66]]

* **SHOULD BE ABLE TO PROVE THIS:**
#examinable ![[ML Lecture 01 - Slides.pdf#page=67]]

![[ML Lecture 01 - Slides.pdf#page=67]]
* In exam? 

![[ML Lecture 01 - Slides.pdf#page=68]]

![[ML Lecture 01 - Slides.pdf#page=69]]

![[ML Lecture 01 - Slides.pdf#page=70]]