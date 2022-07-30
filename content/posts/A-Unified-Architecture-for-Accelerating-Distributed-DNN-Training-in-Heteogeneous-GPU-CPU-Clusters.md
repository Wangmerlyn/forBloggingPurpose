+++
title = "A Unified Architecture for Accelerating Distributed DNN Training in Heteogeneous GPU/CPU Clusters"
date = "2022-07-30T16:18:08+08:00"
author = "wang merlyn"
authorTwitter = "" #do not include @
cover = ""
tags = ["distributed learning", "AI-systems"]
keywords = ["", ""]
description = "OSDI'20"
showFullContent = false
readingTime = false
hideComments = false
math = true
+++
## Problems
- Sub-optimal inter-machine communication
- Sub-optimal intra-machine communication
- The CPU bottleneck
## Proposed Solutions

- An optimal inter-machine communication strategy that is generic and unfies all-reduce and PS
- Intra-machine optimization that accelerates communication inside GPU machines with diverse topology
- Summation Service that aggregates gradients oon CPUs and moves parameter updates to GPUs
# Design and Implementation
# Opportunity
Findings from ByteDance Clusters:

- Avg. CPU utilization: 20% ~ 35%
- 20% ~ 45% run non-dist jobs: Bandwidth unused

在异质的集群中存在空闲的CPU使用和带宽剩余，目标在于平衡空闲的资源
## Inter-machine Communication
PS只使用GPU到CPU间的网络，也就是说当CPU设备不够多的时候，GPU的带宽并不会被充分的使用（例如有2个CPU，3个GPU，那么相比CPU设备的带宽负载，GPU设备的带宽负载只有2/3）
all-reduce只使用GPU间的带宽，没有利用CPU带宽
现在问题在于，如果要结合PS和all-reduce方法，怎么平衡网络负载
### Best Partition Strategy
对于一个CPU机器，SS的负载决定了网络的交通情况，如果1个SS负责$x\%$的参数，那么每次训练的时候CPU机器都会向每个GPU发送$x\%M$的数据。
然而我们可以发现，每个GPU的工作交通是由SS和CS共同决定的，这里进行分类$SS_{CPU}$和$SS_{GPU}$。
在网络中，CS应该总共发送M的数据，当CS和位于同一台GPU上的SS进行通信的时候，是不会占用网络带宽的，这时候CS只使用$M-M_{SS_{GPU}}$的网络带宽
与此同时，1个GPU机器上的SS要求接受和发送来自其它(n-1)台机器的数据$(n-1)M_{SS_{GPU}}$，也就是说，一台GPU机器在给定带宽为$B$的时候，通信时间就是
$t_g=\frac{M+(n-2)M_{SS_{GPU}}}{B}$
相应的，当通信网络中有CPU存在的时候，每个CPU的通信时间就会变成
$t_c=\frac{M_{SS_{CPU}}}{B}$
由于模型通信总量限制
$M=kM_{SS_{CPU}}+nM_{SS_{GPU}}$
由于通信瓶颈，我们为了优化网络性能，目标就是在于优化函数$\min \max(t_c.t_g)$，进行规划之后可以解得
$t_{opt}=\frac{2n(n-1)M}{(n^2+kn-2k)B}$
## Intra-machine Communication
瓶颈发生在CPU和PCIe switch之间，现在问题的解决方法在于减少在这条连接上的通信负载，这其中会涉及到Ring All-Reduce通信原理和负载计算，建议参照[博客](https://freewsy.ml/posts/nccl-allreduce/)
### Solution: CPU-assisted Aggregation

1. 每个CPU管理的集群中进行reduce-scatter
1. 每个CPU集群下的GPU将各自持有的拥有全体整合数据的梯度片段通过总线进行复制给CPU
1. CPU之间进行相加整合

这样就可以让瓶颈链路上的数据传输总量降低为1次模型数据传输量

- CPU-assisted aggregation outperforms MPI/NCCL by 24% in theory
- **Principle**: avoid direct copy between GPUs under different PCIe switches
## CPU bottleneck
We need a module that can run on CPUs with high performance
通过观察可以发现，整个在CPU PS上进行的操作其实就是优化函数$W'=W-f(\nabla W)$，我们可以将整个过程分为两个部分

- 梯度相加（CPU friendly）
- 参数更新（heavy for CPU）

解决方法：让GPU负责参数更新






