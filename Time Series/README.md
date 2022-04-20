# Time Series

## Model Building

### Model Building Desiderata
- Explanatory Power
- Parsimony: lack of it causes multicollinearty
- Valid: L, H, I, (N)

Tension between Explanatory Power and Parsimony > Balance is required. 
However, good balance does not ensure 'Validity of a model'


### Stepwise Regression
One of good ways balancing the exp power and parsimony is **Stepwise Regression**

#### Forward Stepwise
##### Procedure
Starts regression with one predictor > find the best feature in terms of R^2 / RMSE
(This process can be replaced with just looking at correlation as in simple linear regression the corr^2 is equivalent to R^2)

Goes to the regression with two predictors
Choose the predictor that adds the most R^2 (incremental)

##### Characteristics
 - It's greedy <=> Optimal Solution in Stepwise does not mean optimial solution when we explore whole possibilities (2^#features -1)
 - However, It's good enough
 - Forward Regression prefers **Parsimony** over the explanatory power. 
 - In general, we set the entry p-value criteria as 0.05


#### Backward Stepwise
##### Procedure
Starts with the model that contains all predictors
Kicks out the predictor which reduces the least amount of R^2 
<=> eliminate the least important variable in explaning the variability of the dependent.

##### Characteristics
 - Greedy, as forward does
 - Backward and Forward do not necessariliy result in same model. 
 - Backward prefers **Explanatory Power** over Parsimony

#### (Regular) Stepwise
It is a mixture of forward and backward

##### Procedure
Starts with single models and follows the flow of the Forward's 
However, if p-value of an existant predictor increase over a threshold, usually 0.10, due to the inclusion of new predictor, 
that predictor having low significance will be dropped. 


#### n/p ratio
n = the number of observation
p = the number of predictors 

Usually the ratio lower than 5 is considered bad, because it is likely to cause overfitting.
The ratio higher than 15 (or 10 sometimes) is considered good, meaning model has parsimony

##### Role of Stepwise
In this context, Stepwise Regression plays a role of balancing the explanatory power and parsimony. 
In more detail, by retaining the predictors having high significance only and by removing less siginificant features, 
Stepwise helps to maintain decent n/p ratio at the little cost of explanatory power. 
