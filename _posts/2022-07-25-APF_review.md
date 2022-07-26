---
layout: post
title: "POST TITLE"
date: YYYY-MM-DD hh:mm:ss -0000
categories: CATEGORY-1 CATEGORY-2
---


# "Communication-Efficient Federated Learning with Adaptive Parameter Freezing" review

## Back Ground

 There has been a great amount of communication cost in federated learning thus communication has become a bottleneck in Federated learning.

### Way to reduce the communication amount for distributed model training
* _quantizing_ the update into fewer bits
* _sparsify_ local updates


### The Challenges of boosting federal learning efficiency by skipping out of stablized parameters
* How to identify stabilized parameters effectively
* How to ensure that the model will converge to the optimal state


## The parameter changing feature
By assuming the global loss funcition of deep neural network is a  $\mu$ -strong convex function and the stochastic gradient of the loss funcition is bounded, the authors drew the conclusion that in the earlier stage of deep neural network training, the parameters $\omega$ approaches the optimal state $\omega^{\*}$ exponentially fast while in the later iterations, $\omega$ tend to oscillate around $\omega^*$.



## Identify stablized parameters
At first the authors proposed a indicator called _effective perbutation_ $$P_K^r=\frac{||\sum_{i=0}^{r} \mu_{k-i}||}{\sum_{i=0}^{r}||\mu_{k-i}||}$$ to describe the stableness of a certain parameter. Later the indicator was improved using exponential average $P_K=\frac{E_K}{E_K^{abs}}$ where $E_K = \alpha E_{K-1}+(1-\alpha)\Delta_K$, $E_{K}^{abs}=\alpha E_{K-1}+(1-\alpha)|\Delta_K|$ to avoid wasting storage for model snapshots and adjust the focus on recent model updates. If the effective perbutation hits below a threshold, the parameter is considered stable. The threshold can be adaptively changing.

## Adaptive parameter freezing
### Partial syncing
Freezing parameters locally on individual worker has been proven to be working poorly since works deal with non IDD data in a federated learning task, causing parameters to diverge after previous stablized parameters are out of sync.

### Permanent freezing
Permanent parameter freezing is gonna result in the loss of acurracy since parameters that are freezed when they are stable halfway in the training are still probably not optimal. 

### Parameter freezing principles
From the 2 observations above, the authors drew the following principles for adaptive parameter freezing.

1. Stablized parameters must be kept unchanged on each worker.
2. Temporary stableness must be handled.

### APF method
With the 2 principles above combined, the authors raised an "adaptive parameter freezing" mechanism. While keeping an eye on those stablized parameters, the freezing period should also be adaptively changing. After a parameter is recognized as stabilized, it should freezed for a specific amount of time that is controlled by a adaptive mechanism which is similar to TCP AIMD. By checking whether the parameter remains stable after unfreezing, the mechanism changes the freezing period adaptively. Taking efficiency into consideration, effective perbutation check is not necessary to be conducted once after each iteration, 

### Agressive APF
While dealing with over-parameterized models, certain parameters may not tend to converge due to their non-convex nature. Agressive APF works like APF but also randomly freeze parameters therefore filter out the training of less needed parameters.


