+++
title = "ReSkin"
date = "2022-11-05T18:46:09+08:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["Machine Learning", "Mobile Computing"]
keywords = ["sensor", ""]
description = "一篇关于使用磁性编织物实现触觉感受器的文章"
showFullContent = false
readingTime = false
hideComments = false
math = true
+++

# Source
[ReSkin](https://reskin.dev)

# Introduction

目前机器人难以实现机械臂灵活操控，很大一部分原因在于没有对于触觉传感的有效解决方案。

## 一些条件

好的触觉传感器应该满足的条件：
* 为稳定的抓取和操控提供共形接触(conformal contact)
* 准确的压力和切向力测量
* 高分辨率力与时间测量
* 大表面积覆盖(作者在这里局的例子是大于$4cm^2$，虽然听起来不大，但是可以满足指尖抓取的要求),和传感器覆盖位置的高空间分辨率。

为了满足一些实用场景下的使用：
* 紧实通用
* 不昂贵
* 寿命长

## 一些其它方案

* 基于视觉的触觉传感器一般沉重，昂贵，反应慢
* 电阻电容传感器需要很多连接，导致很多问题
* 硬传感器，不软😓

## 主要问题
* trade-off: 共形接触和寿命长的材料
* 使用数据驱动的模型难以在不同传感器上泛化，任何皮肤的更换都会要求重新学习模型

## 特点

* ReSkin由磁化材料和磁力计组成
* 利用磁场的扭曲判定接触点和力
* 使用机器学习模型推理
* 可以直接更换皮肤
* 自监督校正

# Background
## 好像很厉害的东西
Resistive
networks patterned onto a knit glove have been used to collect tactile grasping dataset and classify
objects using neural networks.

Capacitive soft skins can be scaled up to larger areas by sampling at different interrogation frequencies to detect position via SVMs with just one interface.

# Design and Fabrication

## Magnetic Elastomer Fabrication

这里面使用的制造方法在于将磁微粒和固化硅橡胶融合在一起，导入模具中进行固化。关于文中提到的2-part polymer确实让我困惑了很久，进行了很久的搜索也不知道这到底是什么。直到我进入这个产品的官网[DragonSkin](https://www.smooth-on.com/products/dragon-skin-10-nv/)。其实从网站上的演示视频可以发现，就是两种橡胶倒在一起时会发生固化，有点类似于AB胶，这种产品常用于制造石膏，蜡，低熔点合金等的模具。

在皮肤的制造材料准备好后，要倒入模具中，并在周围永磁铁的作用下进行固化，这一步的目的可能是让永磁体的磁场诱导磁微粒的磁场统一排列，获得更好的磁场效果。

## Circuit Board

这里有趣的地方在于在这个系统中作者制造了两种电路板，一种就是普通的纯硬质电路板，一种灵巧的有些许柔软度。

对于硬质电路板来说，皮肤是通过螺丝固定的，这一点确实没什么好说的，但是对于更换皮肤的话就会有一点麻烦。而对于灵巧电路板来说，皮肤是由可缝上的魔术扣固定的，更换起来更加方便。（为啥不都用魔术扣😶‍🌫️）

# Experimental Setup

使用Dobot Magician robot进行实验中力的产生。将一个压头绑在机械臂末端，在皮肤上不同位置施加不同的力。

按压的位置是一个$9\times9$网格中的蛇形图案，深度从0.2mm到1.2mm有6种分布，每次迭代共有390次按压。