---
layout: post
title:  "Formal Description of Dynamic Programming (DP)"
date:   2021-10-16 09:29:20 +0700
categories: post
---

# Formal Description​


s<sub>i</sub> - denotes the state of the system at i<sup>th</sup> time, for all i = 1, 2, ..., n (state transitions).

x<sub>i</sub> - denotes the *decision* made at i<sup>th</sup> time for all i = 1, 2, ..., n.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
![formal representation](../../assets/posts_images/formal_dp_0.png)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*Figure 1*

In other words, for all i = 1,2,...,n-1, the state transitions are denoted as:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
![formal representation](../../assets/posts_images/formal_dp_1.png)

Let the cost of the changing state from s<sub>i</sub> to s<sub>i=1</sub> be denoted as g<sub>i</sub>(s<sub>i</sub>,x<sub>i</sub>)

Then the total cost is given as:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
![formal representation](../../assets/posts_images/formal_dp_2.png)


# Design Methodology for DP

Four step method:

1.  Characterize the Bellman equation for the problem.
2.  Recursively find the optimal solution and itscorresponding value for each tail problem.
3.  Compute the value of an optimal solution in a bottom-upfashion.
4.  Construct an optimal solution from computedinformation.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Nikola Andrić
