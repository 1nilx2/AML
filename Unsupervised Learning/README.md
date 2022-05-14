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

Orthonormal Transformation means that new aixes will have unit vector length and uncorrelated with each other. 

<img src="https://latex.codecogs.com/svg.image?\mathbf{MM}^T=\mathbf{I}_P&space;">
<img src="https://latex.codecogs.com/svg.image?\mathbf{M}^{-1}=\mathbf{M}^T&space;">
<img src="https://latex.codecogs.com/svg.image?&space;\textrm{The&space;orthonormal&space;Transformation&space;of&space;}\mathbf{X}\textrm{&space;is&space;}\mathbf{XM}">
<img src="https://latex.codecogs.com/svg.image?\textrm{Unit&space;Vector:&space;}\left\|U\right\|=\sqrt{v_1^2&plus;v_2^2&plus;...&plus;v_n^2}=1"> 
<img src="https://latex.codecogs.com/svg.image?&space;\textrm{Orthogonal&space;Vectors:&space;}&space;\textbf{u}\cdot\textbf{v}=0">

<img src="https://latex.codecogs.com/svg.image?\textbf{EigenValue:&space;Sum&space;of&space;Squared&space;Loadings&space;=&space;}\left\|\boldsymbol{u}\right\|^2">


## Cluster Analysis

## Factor Analysis

