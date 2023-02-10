+++
title = "Regulatory Intensity and Firm-Specific Exposure"
date = "2023-01-18T15:03:49+08:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["Management", "Statistics"]
keywords = ["", ""]
description = "This is the default description"
showFullContent = false
readingTime = false
hideComments = false
math = true
+++

# 工作

使用机器学习方法和一个行政测试集来衡量遵守所有联邦文书规范的法规的成本，然后研究法规负担对关键经济成果的影响。

## 成本

法规的文书工作带来了很大成本

行政法规和因为遵循行政法规而带来的经济负担

# 目录

1. analyze aggregate regulatory burden
2. primary measures of firm-specific reg-
ulatory intensity
3. the economic impact of regulatory intensity

# 背景与数据来源

## Paperwork regulations

Federal regulators收集公共数据。制造企业披露制造原材料，上市公司披露经济状况和商业行动，商业交通公司记录司机的行车时间等。这些数据的收集会造成联邦文书工作的巨大负担。

联邦文书管理由PRA生成和监管

进行信息收集的机构还要提供一个信息收集对于上市公司的负担的估计：Responses,Time and Dollar

# 总计监管强度

将单独的负担综合成一个全面的监管强度指数。

## 计量监管强度

为了计算t时的监管强度，将之前的监管小组转化成panel of agencies，其中每个观察值代表在时刻t由a机构产生的负担。

标准化和winsorize

将时刻t内的所有机构的值相加，构建一个政府时间序列

标准化序列为均值100，得到最终的$RegIn_t$指数，代表为了遵从行政制度在时刻t产生的负担。

关于$RegIn_t$的三个版本：活跃的行政管理，应答数量，遵守制度产生的时长

计算行政管理的数量是透明并且容易重复的，基于假设法规的数量是一个有意义的评价标准。很多研究支持这个简化的假设。

不过并不是所有规章制度都是平等的，有些生来更加复杂和更有负担。

改进：使用官方的估计成本来评价制度。

## 风格化事实

