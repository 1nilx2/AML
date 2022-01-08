# AML
Advanced Machine Learning
Based on the slide from Prof.Gosh at UT Austin

# Project Link
https://medium.com/@eacabrera3/real-time-sign-language-detection-system-e3d6cf49121a

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

#### Gradient Descent 
  Continuous updated of weights (betas) following the curve of the cost function E(w)
  Learning Rate controls the speed of convergence
   - too small: slow convergence
   - too large: unstable/diverge
   * if convergence is required, consider adaptive learning rate

#### Stochastic Gradient Descent (SGD)
  On-line version: usually, converging to a point does not need to be ensured
  
  Why SGD?
   - Better for large data sets
   - Often faster than plain/batch gradient descent
   - **Less prone to local minima**, thus can be applied to complex loss function
   - Work well on streaming settings

### Multi-Layered Perceptrons (MLP)
  most popular before deep learning (or DNN, Deep Nueral Network). MLP conducts feedforward only while DNN can loop.

#### Learning via Error Backpropagation
  1. pass forward
  2. calculate error comparing with the desired output
  3. backward pass: compute gradients of weights w.r.t. loss and update all the weights.

#### Design Parameters
 1. '# of hidden units/nodes 
  - model complexity 
 2. '# of epochs/iterations: 
  - how long do you train
  - use a cross-validation to know when to stop
 3. Activation fuction
  - tranform the output from the previous layer 
  - usually add **non-linearity**
  - ReLU, Tanh, Sigmod, and so on.
 4. Learning rate
  - speed of training
  - one can consider varying approaches like Momentum.

## Convolutional Neural Networks
* referece: Introduction to CNN; Jianxin Wu; May 1, 2017

### Notation
  1. small bold: column vector
  2. capital: matrix
    ex) <img src="https://latex.codecogs.com/svg.image?X\in&space;\mathbb{R}^{H\times&space;W\times&space;D}" title="X\in \mathbb{R}^{H\times W\times D}" /> is a matrix with H rows, W columns, and D tensor(channel)
  3. Tensor: useful in many aspects such as expressing colors by different tensors.

### CNN in a nutshell

 1. The architecture
  - A CNN usually takes an order 3 tensor (H*W*3)
  - Input from an layers flows to the next layer which can be a convolution, pooling, normarization, fully connected, fully conncet, etc layer.
  - x1 > w1 > x2 > w2 >...> xl > wl > z
  - Usually xl is a C-dimensional vector whose i-th entry encodes the posterior probability of x1 comes from the i-th class. 
  - for this, (l-1)th layer used to adopt softmax transformation 
  - find the discrepancy between xl and target value t. If it's a simple loss function, it becomes a half of squared-error.
 
 2. Stochastic gradient descent(SGD)
  What can be the method for minizming loss. One of the potential winner is the SGD. Based on the idea that loss can be minimized when the gradient of the loss function is closed to zero and that batch gradient method has a difficulty in overcoming local-minima, SGD has been arised. the weight for j-th feature will be updated by <img src="https://latex.codecogs.com/svg.image?w^{i}=w^{i}-\eta&space;\frac{\partial&space;z}{\partial&space;w^{i}}&space;" title="w^{i}=w^{i}-\eta \frac{\partial z}{\partial w^{i}} " /> . Varying the way of optimizing the loss, spin-offs can be made such as Momentum, ADAM etc. 
  
 3. Using a sequence of the partial derivatives, we can do backward propagate the error with reasonable computation resources. This is called Error back propagation.
   
 




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
