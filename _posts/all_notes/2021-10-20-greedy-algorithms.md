---
layout: post
title:  "Greedy Algorithms"
date:   2021-10-20 09:29:20 +0700
categories: post
---
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Unlike dynamic programming algorithms that looka at all possible solutions and "look in hte future moves", **greedy algorithms** always make a choice that is the best at the given moment. 
 They do not care about what situation is going to be like after that move has been made. That is where the name *greedy algorithms* come from.
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 However, greedy algorithms do not always give the optimal solution to the problem, only sometimes.
 
 How do we design greedy algorithms?
 
 1. Cast (cookey cutter shape) the optimization problelm in one in which we make a choice and  are left with one subprobelm to solve.
 2. Prove that htere is always an optimal solution to the original problem that makes the greedy choice, so the greedy choice is always safe.
 3. Demonstrate optimal substructure by showing that if we made the greedy choice, what remains is a subproblem with the property such that if 
 we combine an optimal solution with the subproblem of the greedy choice we made, we arrive at an optimal solution to the original problem.
  
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Nikola Andrić
 
 

 
