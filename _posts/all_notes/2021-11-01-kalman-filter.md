---
layout: post
title:  "Kalman Filter"
date:   2021-11-01 09:29:20 +0700
categories: post
---



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
***The Kalman Filter*** is one of the most important and common estimation algorithms. The Kalman Filter produces estimates of 
hidden variables based on inaccurate and uncertain measurements. Also, the Kalman Filter provides a prediction of the future
system state based on past estimations.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
The filter is named after ***Rudolf E. Kálmán*** (May 19, 1930 – July 2, 2016). In 1960, Kálmán published his famous paper describing 
a **recursive solution to the discrete-data linear filtering problem**.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Its first use was on the Apollo missions to the moon, and since then it has been used in an enormous variety of domains. Today the Kalman filter is used in Tracking Targets (Radar), location and navigation systems, control systems, computer graphics
and much more.

# Why Kalman filters?

Imagine we are making a self-driving car and we are trying to localize its position in an environment. The sensors of the car can detect cars, pedestrians, and cyclists. Knowing the location of these objects can help the car make judgements, preventing collisions. But on top of knowing the location of the objects, the car needs to predict their future locations so that it can plan what to do ahead of time. For example, if it were to detect a child running towards the road, it should expect the child not to stop. The Kalman filter can help with this problem, as it is used to assist in tracking and estimation of the state of a system.
The car has sensors that determines the position of objects, as well as a model that predicts their future positions. In the real world, predictive models and sensors aren’t perfect. There is always some uncertainty. For example, the weather can affect the incoming sensory data, so the car can’t completely trust the information. ***With Kalman filters, we can mitigate the uncertainty by combining the information we do have with a distribution that we feel more confident in.***

[Examples](https://github.com/NikolaAndro/Kalman_Filters)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
The Squid
