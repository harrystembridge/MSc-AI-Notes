- Write a paper that challenges the claim that Kryptonite-n is a dataset that cannot be solved with current ML methods.

Structure
1. Abstract
2. Introduction
3. Methodology
4. Experimental Design
5. Experimental Results
6. Discussion

Need code to reproduce experiments, set seeds...

Produce: 
- Jupyter Notebook to reproduce all the graphs in the latex document
- Latex document converted to PDF

Issues:
- The model is massively overfitting on the training set
- Doesn't generalise well
- Us implementing LoRA acts as a form of regularisation of the model


Delegation:
- Sean - explaining LoRA
- Fehed - Foundation model argument
- Jacob - More data argument
- Harry - Universal function approximation argument


# MML Meeting

## Agenda

1. Rearrange the latex doc, impose some structure
2. Discuss LoRA
3. Bring up point about being able to use our own models…
4. What code are we going to write?
5. Create Juptyer notebook for figures

## Next steps
1. Formalise what we have in LaTeX
2. Build the models and run the tests (in jupyter)
	1. LoRA/finetuning - Fehed and Sean
	2. MLP - Harry and Jacob

## Universal Approximation Theorem (UAT)
- Links back to lecture 6 content!
- State the universal approximation theorem.
- No free lunch theorem
- Universality is not a guarantee of generalisation 
- We can always pick a high-degree polynomial to fit our training data. But picking something that will generalise is no guarantee.
- The paper itself actually proves the fitting ability of the model with 1.000 for high-degree polynomials:
![[Pasted image 20261105120513.png]]
- Fundamental misunderstanding of UAT
- UAT (Weierstrass, Cybenko, Stone–Weierstrass) bounds only the approximation error. Figure 1's train accuracy shows that part working.
- The failure is in generalisation, which the lecture separates from approximation and links to inductive bias and No Free Lunch.
	- How this fits with Bias-Variance tradeoff, as we increase the flexibility of the model we greatly reduce the bias but massively increase the variance.
	- This is what causes the issues 
	- The wrong inductive bias...
- So we have low bias, but massive variance and no regularisation to help this which is hurting generalisation.
- If an MLP performs well on the test set, we have shown that we can indeed approximate the data with a function by determining which features are important to prevent overfitting.

- References:
	- Cybenko, G. (1989). Approximation by superpositions of a sigmoidal function. Mathematics of control, signals and systems, 2(4):303–314. 
	- De Branges, L. (1959). The stone-weierstrass theorem. Proceedings of the American Mathematical Society, 10(5):822–824.
	- Hornik, Stinchcombe & White (1989)
	- Wolpert & Macready (1997)

**Worth adding**

- **The Stone–Weierstrass conditions:** polynomials of degree at most 10 aren't closed under multiplication, so they're not an algebra, and the theorem never promised degree 10 would be enough. Compactness is also doubtful for raw inputs on ℝⁿ.
- **The paper cites Hornik but never trains a neural network,** which your MLP result fills in.
- **Hoeffding:** the polynomial models are significantly above chance, and the paper's "degree adds at most 3.1pp" is within noise.
- **When you "state the UAT":** use Cybenko for neural networks and Weierstrass / Stone–Weierstrass for polynomials. The paper's claim is about the polynomial version, but it cites the neural-network one.

**References**

- Put each reference on its own line; Cybenko and De Branges are currently run together.
- Add **Hornik, Stinchcombe & White (1989)**, which is in your lecture bibliography.
- If you state No Free Lunch formally, add **Wolpert & Macready (1997)**, _"No free lunch theorems for optimization"_.
- You could also cite your Lecture 6 notes for the UAT framing.


My thoughts - we use models and their performance to each mathematically and empirically refute the claims.


TODO:
> [!TODO]
> - [x] Add the original graph showing the test and training performance to the jupyter notebook and add the figure to the latex document
> - [x] Add Introduction
> - [x] Add Abstract
> - [x] Add MLP results
> - [x] Write discussion
> - [x] Tidy up mathematical outline of the UAT
> - [x] Raise an MR for my jupyter changes
> - [ ] Update figure
> - [ ] Finish discussion
> - [ ] Fix graphs
> - [ ] Talk about how we beat the accuracy threshold... How did we decide on this model, what did we do. Justify tradeoff between bias and variance and flexibility.
> 	- [ ] Here is the preprocessing we did
> 	- [ ] Here is the model design
> - [ ] Zip label files: four .npy files zipped together
> - [x] Add figure for MLP












