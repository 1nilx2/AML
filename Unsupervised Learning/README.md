# Unsupervised Learning

## Big Data and Sufficient Statistics


## Principal Components Analysis

### Properties
 - Information 
 - Dimensionality Reduction
 - Uncorrelated
 - **Insight**

### PCA is just rotation of Vantage Point
Implementing PCA, we could find different coordinate system that allows us to see our data in different perspective. 
But, we need to make sure that all or as much geometry of original data will be preserved. 
What makes this possible is Orthonormal Transformation and Variance Maximization. 

**Standardize before PCA!

Orthonormal Transformation means that new aixes will have unit vector length and uncorrelated with each other. 
<img src="https://latex.codecogs.com/svg.image?&space;\textrm{The&space;orthonormal&space;Transformation&space;of&space;}\mathbf{X}\textrm{&space;is&space;}\mathbf{XM}">

<img src="https://latex.codecogs.com/svg.image?\textrm{Unit&space;Vector:&space;}\left\|U\right\|=\sqrt{v_1^2&plus;v_2^2&plus;...&plus;v_n^2}=1"> 

<img src="https://latex.codecogs.com/svg.image?&space;\textrm{Orthogonal&space;Vectors:&space;}&space;\textbf{u}\cdot\textbf{v}=0">


### Properties
<img src="https://latex.codecogs.com/svg.image?\mathbf{MM}^T=\mathbf{I}_P&space;">
<img src="https://latex.codecogs.com/svg.image?\mathbf{M}^{-1}=\mathbf{M}^T&space;">
<img src="https://latex.codecogs.com/svg.image?\textbf{EigenValue:&space;Sum&space;of&space;Squared&space;Loadings&space;=&space;}\left\|\boldsymbol{u}\right\|^2">


## Cluster Analysis(CA)
 Uncover structure in a dataset by aggregating similar observations into groups called clusters.
Cluster Analysis does not actually reduce the number of rows but does reduce **the number of entities to understand**
The two major problems of CA are to determine the number of cluster and to cluster membership

### Examples of application of CA
- Marketing: Market segmentation
- Politics: Analysis of voter blocs
- Psychology: Definition of personality types, mental diseases
- Biology Reconstructing the evolutionary 'tree of life'
- Linguistics: Reconstructing ancestral languages
- Anthropology: Mapping patterns of human migration and settlement
- Environment: Identifying weather patters and their propensity for air pollution

### Basic Stpes in CA
1) Select obersvations to be clustered
2) Define the variables to be used in clustering
3) Compute similarities (dissimilarities) among the observations
4) Create groups of similar observations
5) Validate the resulting clusters

### Quantifiable characteristics of clusters
1) Density: concentration of cases
2) Variance: dispersion from the center of a cluster
3) Dimension: size/radius of the cluster
4) Shape: typically ellipsoidal
5) Separation: degree to which clusters overlap/disconnected

### Similarities and Dissimilarities
 - Similarity matrix is also called proximity matrix and consists of n x n entities
 - Two concepts: Correlation and Distance

#### Correlation Coefficients
It uses same formula as the ordinary correlation coefficient, but the formula is applied to two observations
Thus, correlations as similarities have the difficulty that small variations in large numbers (such as salary)
may overwhelm proportionately much larger variations in small numbers (such as family size)

Possible remedy is to standardize variables but this suggestion is controversial because
it implies that all variables are equally important in assessing similarity 
& bias from selection of highly correlated variables as the basis for clustering. 

#### Distance Measures
<img src="https://latex.codecogs.com/svg.image?\textbf{1)&space;Euclidean&space;(L}^2&space;\textbf{&space;distance)&space;=&space;}\sqrt{\sum_{k=1}^{p}(x_{ik}-x_{jk})^2}&space;">

<img src="https://latex.codecogs.com/svg.image?\textbf{2)&space;Manhattan&space;(city-block&space;-&space;L}^1&space;\textbf{&space;distance)&space;=&space;}\sum_{k=1}^{p}|x_{ik}-x_{jk}|">

<img src="https://latex.codecogs.com/svg.image?\textbf{3)&space;Mahalanobis&space;distance}&space;=&space;\textbf{(X}_i-\textbf{X}_j\textbf{)'S}^{-1}\textbf{(X}_i-\textbf{X}_j\textbf{)}">

where x_ik




## Factor Analysis

