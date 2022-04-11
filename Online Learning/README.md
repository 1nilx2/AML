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

Then P(<img src="https://render.githubusercontent.com/render/math?math= P(|\sum_{i=1}^τX_i> |  )  ">)
