+++
title = "Finexus"
date = "2022-11-19T21:59:36+08:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["Machine Learning", "Mobile Computing"]
keywords = ["", ""]
description = "This is the default description"
showFullContent = false
readingTime = false
hideComments = false
math = true
+++

# Introduction

* CV based: occlusion issues(遮挡问题), limited to the view of the camera
* IMU: low-cost and occlusion-free; require frequent calibrations
* strain gauge: strain gauge may shift

# Related Work

## Computer Vision-Based Approaches

* infrared camera(红外摄像头)
* depth camera

## On-Body Sensing

* EMG
* electric field

## Indirect Sensing
* 2.4 GHz
* Doppler-shifted signals

These techniques usually require accurate sensor calibration to obtain sufficient signal-to-noise ratios (SNR). They also rely on signal reflections from the human body and hence suffer from occlusion issues.

## Magnetic Field Sensing

* Razer Hydra(MF+IMU): 需要产生3维磁场，导致很笨重
* Polhemus 使用磁场梯度，导致必须在静止状态下使用

还有一些其它的设备，但是这些技术要么需要使用较大的传感器阵列，要么只能支持2D定位。

