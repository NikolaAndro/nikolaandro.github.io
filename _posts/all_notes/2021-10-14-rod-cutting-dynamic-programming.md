---
layout: post
title:  "Rod Cutting - Dynamic Programming"
date:   2021-10-14 09:29:20 +0700
categories: post
---

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 **Rod cutting** problem uses dynamic programming to solve a problem in deciding where to cut steel rods. 


# Problem:

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Given a rod of length ***n*** inches and an array of prices ***p<sub>i;</sub>*** for i = 1,2,...n that includes prices of all pieces of size smaller than n. Determine the maximum revenue value ***r<sub>n</sub>*** obtainable by cutting up the rod and selling the pieces. Note that if piece ***p<sub>n</sub>*** for a rod of length n is large enough, an optimal   solution may equire no cutting at all.
 
 How do we meet the necessary properties for dynamic programming:
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 1. Optimal Structure - We can cut the rod in different spots and compare the prices after each cut. Then we can recursively call the same function on a piece obtained after the cut. 
 
 Let cutRod(n) be the function that gives us the optimal price for the rod of the length n. The definition of the cutRod would be 
 **cutRod(n) = max(price[i] + cutRod(n - i - 1)) for all *i* in {0,1,2,...n-1}**
 
<!-- https://sites.psu.edu/symbolcodes/codehtml/#math LINK FOR SYMBOLS IN EQUATIONS -->
<!-- h<sub>&theta;</sub>(x) = &theta;<sub>o</sub> x + &theta;<sub>1</sub>x -->
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Nikola Andric

 
