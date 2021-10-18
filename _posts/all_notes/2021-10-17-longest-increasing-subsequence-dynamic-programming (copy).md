---
layout: post
title:  "Longest Increasing Subsequence (LIS) - Dynamic Programming"
date:   2021-10-17 09:29:20 +0700
categories: post
---

# Problem:

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Find the length of the longest subsequence of a given sequence such that all elements of the subsequence are sorted in increasing order. For example, the length of LIS for 10, 22,9, 33, 21, 50, 41, 60, 80 is 6 and LIS is 10, 22, 33, 50, 60, 80.

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 We can go about this problem in multiple ways, but here I will use the LCS as a tool for solving this problem. 
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 First, since we are given a list of numbers, we will create another list that is created by sorting the given list. This new list can be used in LCS together with the original list to find the length of the longest increasing subsequence.
 
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Nikola Andrić

 
