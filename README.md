# AML
Advanced Machine Learning

Bayesian Decision Rule

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
 - P(**X**|C<sub>j</sub>) = P(x<sub>1</sub>|C<sub>j</sub>)*P(x<sub>2</sub>|C<sub>j</sub>)*...*P(x<sub>d</sub>|C<sub>j</sub>)
