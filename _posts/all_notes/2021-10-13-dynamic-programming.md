---
layout: post
title:  "Dynamic Programming"
date:   2021-10-13 09:29:20 +0700
categories: post
---

****Note In Progress****

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
**Dynamic programming** solves problems by combining the solutions to subproblems. It can be
similar to divide-and-conquer method, where problem is partitioned into disjoint subproblems,
subproblems are recursively solved and then combined to find the solution of the original problem.
However, dynamic programming applies when the subproblems overlap - that is, when
subproblems share subsubproblems. In this context, a divide-and-conquer algorithm does more
work than necessary, repeatedly solving the common subsubproblems. A dynamic-programming
algorithm solves each subsubproblem just once and then saves its answer in a table, thereby
avoiding the work of recomputing the answer every time it solves each subsubproblems.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Dynamic Programming is used to solve optimization problems. These type of problems can have many possible optimal solutions. Hence, the goal of dynamic programming is to find one optimal solution. 


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
In order to know when to look for a dynamic-programming solution to a problem, we need to recognize if our problem has **optimal substructure** and **overlapping subproblems**. 

# Optimal Substructure

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
A problem demonstrates an `optimal substructure` if an optimal solution to the problem, within itself, contains optimal solutions to subproblems. Hence, when we recognize such a structure, we can be sure that we can apply dynamic programming.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
The optimal solution in dynamic programming is built from the optimal solutions of the subproblems.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
When discovering optimal solution of a problem, we will follow the pattern:
  - Show that a solution to the problem consists of making a decision/choice, such as cutting a rod, that leaves one or more subproblems to be solved using the same method.
  - Suppose that for this problem, we were given the first decision that leads to an optimal solution.
  - Given this choice, we need to determine which subproblems arise.
  - Show that solutions to the subproblems used to solve the original problem are also optimal by using a `cut and paste technique`. In this technique, we assume that some piece of the optimal solution S* is not an optimal solution to a smaller subproblem. Then we need to show that replacing that piece with the optimal
solution to the smaller subproblem improves the supposedly optimal solution S*. Therefore, that S* must include an optimal solution to a smaller subproblem.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Dynamic Programming very frequently uses optimal substructure in a `bottom-up approach`. This means that we first determine optimal solutions to subproblems and then using those optimal solutions, we find the optimal solution of the "upper level" problem. 

# Overlapping Subproblems

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;


# Memoization

Some of the problems that can be solved using the dynamic programming:
  - Rod Cutting
  - Matrix-Chain Multiplication
  - Longest Common Subsequence
  - Coin Changing Problem
  - Knapsack Problem
  - Graph Problems


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Nikola Andric
