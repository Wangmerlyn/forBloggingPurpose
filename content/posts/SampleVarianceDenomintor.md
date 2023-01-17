+++
title = "为什么样本方差的分母是n-1"
date = "2023-01-17T16:02:52+08:00"
author = "Wang Merlyn"
authorTwitter = "" #do not include @
cover = ""
tags = ["Math", ""]
keywords = ["Probability Theory", ""]
description = "This is the default description"
showFullContent = false
readingTime = false
hideComments = false
math = true
+++

# 方差

## 定义

$$D(X)=E(X-\mu_X)^2$$

## 期望

$$D(X)=E(X^2)-(EX)^2$$

证明：

$$
\begin{aligned}
D(X)&=E(X-\mu_X)^2 \\\
&=E(X^2-2X\mu_X+\mu_X^2) \\\
&=E(X^2)-2\mu_XE(X)+\mu_X^2 \\\
&=E(X^2)-(E(X))^2
\end{aligned}
$$


## 随机变量和的方差

$$D(X+Y)=D(X)+D(Y)+2Cov(X,Y)$$

证明：

$$\begin{aligned}
D(X+Y)&=E(X+Y-(\mu_X+\mu_Y))^2 \\\
	  &=E(X^2+2XY+Y^2-\mu_X^2-\mu_Y^2-2\mu_X\mu_Y) \\\
	  &=E(X^2)-\mu_X^2+E(Y^2)-\mu_Y^2+2E(XY)-2\mu_X\mu_Y\\\
	  &=D(X)+D(Y)-2Cov(X,Y)
\end{aligned}$$

## 采样均值的方差

$$\overline{X} =\frac{1}{n}\sum_i X_i$$

$$\begin{aligned}
D(\overline{X}) &= D(\frac{1}{n}\sum_iX_i) \\\
				&= \sum_i\frac{1}{n^2}D(X) \\\
				&= \frac{1}{n}D(X)
\end{aligned}$$

# 协方差

## 定义

$$
Cov(X,Y) = E((X-\mu_X)(Y-\mu_Y))
$$

## 期望

$$Cov(X,Y) = E(XY)-E(X)E(Y)$$

证明：

$$
\begin{aligned}
Cov(X,Y)&=E(XY)-\mu_YE(X)-\mu_XE(Y)+\mu_X\mu_Y \\\
		&=E(XY)-E(X)E(Y)
\end{aligned}
$$

## 独立随机变量

两个独立随机变量的协方差为0

# 方差的无偏估计

$\frac{\sum_i (x_i-\overline{x})^2}{n-1}$是$\mathbb{D}X$的无偏估计

证明：

$$
\begin{aligned}
E(\sum_i(x_i-\overline{x})^2) &= E(\sum_i(X_i^2)-2\overline{x}\sum_i(X_i)+n\overline{x}^2) \\\
&= E(\sum_i(X_i^2)-2n\overline{x}^2+n\overline{x}^2) \\\
&= nE(X^2)-nE(\overline{X}^2) \\\
&= n(E(X^2)-(EX)^2)-n(E\overline{X}^2-EX^2) \\\
&= nD(X)-D(X) \\\
&= (n-1)D(X)
\end{aligned}
$$


