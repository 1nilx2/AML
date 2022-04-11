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
