# AML
Advanced Machine Learning
Based on the slide from Prof.Gosh at UT Austin

## 2A apa regression

Function Approximation

### Parametric model
 - Set the sahpe and number of parameters(X)
 - determine weights
 - Generally can be said linear combination of basis functions
 - <img src="https://latex.codecogs.com/svg.image?f(x)=y(x,\mathbf{w})=\mathbf{w^T\Phi&space;(x)}" title="f(x)=y(x,\mathbf{w})=\mathbf{w^T\Phi (x)}" />

Assumptions
 - Expected value of T is linear in phi
 - All distributions around the expected values are assumed to be i.i.d zero mean Gaussian with constant variance

How can I verify the assumption
 - see the residuals  

What is the result of the assumption
- find the solution minimizing MSE on the training data yields the Maximum Likelihood Estimate(MLE) of the assumed generative model.

After fitting
 Interpretation of the partial derivative > exclude collinearity

### OLS
 - given the loss function of SSE, minimize it
 - In case of simple regression, closed form solution does exist
 - In case of non-linear, other methods such as MLP, gradient descent, and SGD

### Polynomial Curve Fitting
 - What matters is model complexity and the size of the data
 - Additional approaches using penalty term do exists. ex) Ridge, Lasso, ElasticNet
 - With higher order, the concern on over-fitting arises but this can be alleviated with more data

### Evaluate a Regression Model
- RMSE, R-squared, adj-R
- Matter of 'Bias-Variance Dilemma'
- Change model type > affects bias
- Change the amount of data > variance
- As the last choice, change the feature dimension/space.

## SGD-MLP

### Regression model

 - Linear VS Non-linear
 - almost linear: additive models, piecewise linear...
 - nonlinear
    - linear in fixed transform space (Plynomial, Fourier, Gabor)
    - general non-linear > feedforward neural networks(MLP)

#### how to learn weights?
 - linear
  > direct solution / one step using Newton's root finding / Iterative 
 - non-linear
  > cost function is not quadratic and, in general, non-convex
  > iterative updated is required!  



## 6-1

### Decision Trees (DT)

- Before conducting analysis, Let's see the pairwise scatter plot among the features

DT is a hierarchical classifier since it breaks down complex decision into series of simple decisions. 

Let's assume that we already know the shape of DT
How the split points are determined?

Error rate is not satisfactory. 
We adopt index which is able to measure the '(im)purity' 
 - ex) Gini, Entropy, Chi-squared
 - entropy: -Σp<sub>j</sub> log p<sub>j</sub>
 - gini: 1-Σ p<sub>j</sub><sup>2</sup>  
 
Get the tree grown. Is that all?
We have grown a large tree which is too specific. 
How to contorl the size
 - greedly selecting split is myopic, which does not allow the split at which classification error is not improved
 - Since we do not know the impact of the combination of splits, we need sometihng to deal with this. 
 - Grow and Prune, thus, has been suggested. 

DT Packagest
 - C4.5 used in ML using entropy criterion. Maximize information gain
 - CART in Scientific/Stats. Dafault is gini
 - CHAID in MKT/Stats. uses Chi-sq

Evaluation of DTs
 - (+) simple, intuitive, often fast, explainable
 - (+) feature selection (pruning process includes the penaly term similar with that of Lasso)
 - (+) can handle missing values. 

 - (-) often poorer performance 
 - (-) problem with complex decision boundaries (beyond just non-linear)
 - high variety (consider ensembles)


## 6-2
Classification Methods

1. Focus just on Class Boundaries
  - Decision trees
  - Support Vector Machines

2. Approximate Bayes Decision Rule (model the posterior)
  - Logistic Regression
  - Feedforward Neural Networks, including deep learning
    (In the case of universal and using as loss function MSE or cross-entropy)
  - K-Nearest-Neighbor
 
3. Approximate Bayes Decision Rule (model the likelihood)
  - LDA/QDA
  - Fisher's linear discriminant
  - Naive Bayes
  - Bayesian Belief Networks
 
 ### Revisit Bayesian Decision Rule

Given the X vector (dimension of D), 
Bayes dicidion rule choose the class such that the posteior probability is largest with the class. 
Posterior = (C<sub>i</sub>|**X**)  
          = (**X**,C<sub>i</sub>)/p(**X**)  
          = (**X**|C<sub>i</sub>)*p(C<sub>i</sub>)/p(**X**)

When it comes to comparing the higher probability of class member ship, p(**X**) doesn't need to be considered. 
Thus, the issue will be compressed into a joint probability

How to estimate the joint probabilities for each class?
there can be issue related to high dimensionality and interacting variables.
Refer to 1) Naive Bayes 2) DAG

### LDA (Linear Dscriminant Analysis)

by Bayes' theorem, 

 Pr(Y=k|X=x) = π<sub>k</sub>ƒ<sub>k</sub>(x) / Σ(l,K) π<sub>l</sub>ƒ<sub>l</sub>(x)
 
### Naive Bayes Approach

 - it assumes conditional independence: Given a class, attirubte of **X** is independent.
 - P(X|Y,Z) = P(X|Z)
 - P(**X**|C<sub>j</sub>) = P(x<sub>1</sub>|C<sub>j</sub>)*P(x<sub>2</sub>|C<sub>j</sub>)...P(x<sub>d</sub>|C<sub>j</sub>)
 - From multi-dimension to multiple **1-dimension**
