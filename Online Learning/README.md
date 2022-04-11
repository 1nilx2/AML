# Online Learning

## ETC (Explore then Commit)

 - In case where we have multiple solutions, How we can find the best solution?
 - based on the pre-determined knowledge on # of Samples and the Time Horizon


## UCB (Upper Confidence Bound)

### Comparison with other algorithms
 - ETC: sub-optimality gap Δ and number of sample n are known
 - ETC with Doubling Trick: Δ is known, arbitrary n
 - ε-Greedy: Samples for exploration are separated from exploitation
             Δ is known, n is arbitrary
 - Elimination: In each phase, # of samples per remaining arms is <ins>predetermined</ins>
                Δ unknown, n is fixed

#### All the algorithms above separate samples for exploration from exploitation

### UCB for smoothing regret graph (Compared to the doubling trick)
 - why is bad? 

### Key Difference
 - Number of samples for exploration for each arm is <ins>dynamic</ins>
 - No separation between exploration/exploitation
 - All samples contribute to imporve estimates

* Technical Challenge: Empirical estimates of arm score bases updon random number of sample, so usual __sub-Gaussian concentration__ do not hold.

### Model
Let {X<sub>i</sub>, i=1,2,...} sequence of iid 1-subGaussian RV, and τ as a RV

<img src="https://latex.codecogs.com/svg.image?P\Bigg(|\sum_{i=1}^\tau&space;X_i&space;|&space;>&space;\sqrt{2&space;\tau&space;(2log\tau&space;&plus;&space;log(1&space;\backslash&space;\delta)}\Bigg)&space;\leqq&space;\frac{\pi^2}{3}&space;\delta">


Compare to usual 1-subGaussian bound:

<img src="https://latex.codecogs.com/svg.image?P\bigg(&space;\frac{1}{n}&space;\sum_{i=1}^n&space;X_i&space;>&space;\sqrt{\frac{2n\log(1\backslash\delta)}{n}}\bigg)&space;\leqq&space;\delta">

### Principle of Optimism
 - Bet on the uncertainty <=> Empirical mean + Bonus (dependent upon uncertainty)

### UCB Case1. Unknown Δ, Known n

#### Setting: Unstructured Environment, K arms, reward: μ+1-subGaussian

<img src="https://latex.codecogs.com/svg.image?\inline&space;U_j(t-1,\delta)&space;=&space;\mu_j(t-1)&space;&plus;&space;\sqrt{\frac{2\ln(1&space;\backslash&space;\delta)}{T_j(t-1)}&space;}"> 

<img src="https://latex.codecogs.com/svg.image?\inline&space;\large&space;\bigg(&space;\mathit{where,}&space;\;\;&space;\hat{\mu}_j(t-1)&space;=&space;\frac{1}{T_j(t-1)}&space;\sum_{s=1}^{t-1}&space;X_s&space;X_{\left\{&space;A_s=j&space;\right\}}&space;\bigg)&space;">

<img src="https://latex.codecogs.com/svg.image?Also,\;&space;U_j(t-1,\delta)&space;=&space;\infty,&space;\;\;&space;if&space;\;\;&space;T_j(t-1)=0">

This forces the player to play each arm at least once initially. 

#### UCB algorithm:
 <img src="https://latex.codecogs.com/svg.image?\mbox{at&space;each&space;time&space;t:&space;}&space;A_t=\arg&space;\max_{1\leqq&space;j&space;\leqq&space;k}&space;U_j(\mbox{t-1},\delta)">

#### Intuition
* consider the best arm (arm 1 with the highest true mean)
