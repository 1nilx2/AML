# AML
Advanced Machine Learning
Based on the slide from Prof.Gosh at UT Austin

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
 
Adopting Naive Bayes Approach

 - it assumes conditional independence: Given a class, attirubte of **X** is independent.
 - P(X|Y,Z) = P(X|Z)
 - P(**X**|C<sub>j</sub>) = P(x<sub>1</sub>|C<sub>j</sub>)*P(x<sub>2</sub>|C<sub>j</sub>)...P(x<sub>d</sub>|C<sub>j</sub>)
 - From multi-dimension to multiple **1-dimension**
