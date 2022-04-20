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


