---
layout: post
title:  "Backtracking"
date:   2021-10-16 09:29:20 +0700
categories: post
---

Backtracking is an algorithmic-technique for solving problems recursively by trying to build a solution incrementally, one piece at a time, removing those solutions that fail to satisfy the constraints of the problem at any point of time (by time, here, is referred to the time elapsed till reaching any level of the search tree). 

There are three types of problems in backtracking: 

1. Decision Problem – In this, we search for a feasible solution.
2. Optimization Problem – In this, we search for the best solution.
3. Enumeration Problem – In this, we find all feasible solutions.

Generally, every constraint satisfaction problem which has clear and well-defined constraints on any objective solution, that incrementally builds candidate to the solution and abandons a candidate (“backtracks”) as soon as it determines that the candidate cannot possibly be completed to a valid solution, can be solved by Backtracking.

Given an instance of any computational problem **P** and data **D**  corresponding to the instance, 
all the constraints that need to be satisfied in order to solve the problem are represented by **C**. A backtracking algorithm will then work as follows: 

The Algorithm begins to build up a solution, starting with an empty solution set S. **S = {}**


1. Add to S  the first move that is still left (All possible moves are added to S  one by one). This now creates a new sub-tree s  in the search tree of the algorithm.
2. Check if S+s  satisfies each of the constraints in C. 
    - If Yes, then the sub-tree s  is “eligible” to add more “children”.
    - Else, the entire sub-tree s  is useless, so recurs back to step 1 using argument S.
3. In the event of “eligibility” of the newly formed sub-tree s, recurs back to step 1, using argument S+s.
4. If the check for S+s  returns that it is a solution for the entire data D. Output and terminate the program. 
    - If not, then return that no solution is possible with the current s  and hence discard it.


Difference between Recursion and Backtracking:

In recursion, the function calls itself until it reaches a base case. In backtracking, we use recursion to explore all the possibilities until we get the best result for the problem.

