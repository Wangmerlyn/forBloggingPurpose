+++
title = "MagX Review and Memo"
date = "2022-08-02T22:35:05+08:00"
author = "Wang Merlyn"
authorTwitter = "" #do not include @
cover = ""
tags = ["IoT", "Mobile Computing"]
keywords = ["", ""]
description = "The overall review of MagX: Wearable, Untethered Hands Tracking with Passive Magnets"
showFullContent = false
readingTime = false
hideComments = false
math = true
+++



# Related Work
## Hand Tracking Applications

### Hand Tracking App

Motion-based: IMUs

* pretraining
* error accumulation
* single point of instrumentation
* employs supervised learning

Vision-based: IR cameras/ laser

* fine-grained
* gesture model
* robust against positional drift
* privacy, power consumption, computation

RF-based: RF

* NLOS issues
* power requirements

Other

Microphone: SaveFace

* low-cost
* heavy training
* binary classification

Ultra Sound:

* finger movements


### Magnetic Tracking

Sensing Magnetic Induction

Sensing the current induced on a coil by a magnet

* high tracking accuracy
* long sensing range
* requires an energy-intensive magnetic field generator
* large induction coil

Tracking Electromagnetic Field

Each electromagnetic generates an oscillating magnetic field at specific frequencies.

This method is also using magnetometers

* richer channel info 
* requires wearing powered electromagnetics

Tracking Passive Magnet

LM-based method: array of magnetometers (16)

* no orientation
* machine-learning-based
* pre-defined pose


# Algorithm

## Tracking Algorithm
$\vec{B} = \frac{\mu_0}{4 \pi} \times ( \frac{3( \vec{m} \cdot \vec{r} )\vec{r}_{ij}}{|\vec{r}|^5} - \frac{\vec{m}}{|\vec{r}|^3})$

对于特定的偶极子就是求6个参数$x,y,z,m,\theta,\phi$
每个magnometer的观察量都可以被认为是背景磁场和所有无源磁体的线性组合

$\vec{B_i} = G + \sum_{j=1}^{M} \frac{\mu_0}{4 \pi} \times ( \frac{3( \vec{m_j} \cdot \vec{r_{ij}} ) \vec{r_{ij}}} { | \vec{r_{ij}} |^5 } - \frac{ \vec{m_j} }{ |\vec{r_{ij}}|^3 })$

* 滑动窗口在输入滤波
* 卡尔曼滤波器在输出时进行轨迹的平滑和预测

## Diminishing Magnets

模拟环境生成数据 

SVM分类

(我们应该偏好 1or2 有高recall)

# Hardware Design

* accuracy
* practical range
* low energy consumption and manufacturing cost

## CAMAD

multi-layer -> 2 layer

computer aid vs proposed

PSO

## Hardware Configuration

magnetometers calibration

# Evaluation

implemented optimized LM in C++, then the algorithm is invoked by python.

## Pilot Study 

Using Leap Motion observation as ground truth.

框架变换

## Overhead

diminishing vs ongoing





# 拓展
* 手语翻译
* 手语学习

## 瞎说的
* 需要手势的

* 乐器

* Channels(不同的磁矩大小？)

* 手腕上距离磁铁距离不变为什么要diminish

* 为什么使用PSO？

* 距离越近偶极子的模型越不贴近实际磁场，距离远难以精准测量(线性叠加也要考虑各自磁体之间的影响)

* PCB板 -> 平板设计，难以设计成环

* 八边形环（纯纯的瞎说）