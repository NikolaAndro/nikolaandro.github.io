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
 We can tell if a greedy algorithm can solve certain problem by demonstrating that the problem has the above 3 properties.
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 What is interesting is that both DP and greedy strategies propose *optimal substructure* and we might be tempted to develop a DP solution when greedy solution is enough or opposite. For that reason, we need to see the differences between DP and greedy solutions. 
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 We know that in *0-1 Knapsack Problem* we need to fill out the bag with items while maximizing its weight capacity and value of the items in the knapsack. In the case of *Fractional Knapsack Problem* we have the same goal, but we are allowed to take fractions/pieces of the items.
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Although the problems are similar, we can solve the fractional knkapsack problem using greedy approach, but cannot solve 0-1 knapssack problem using the same approach.  When solving the fractional prooblem, we can easily compute the most valuable fraction of each object per weight (ex. the most money per pound) and choose that item until we exhaust it or until we fill out the bag. If the item is exhausted, we take the next most valuable item and keep filling the bag, and so on. 
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 To see that the greedy approach is not working on  0-1 knapsack problem , we can show that if we take the most valuable item first, and keep filling the bag, we may be left over with a certain capability of the bag (ex. 20 more lbs until reaching full capacity) that does not allow us to select any other item becuase all other items weigh more than 20lbs.
 
 Application of greedy algorithms can be seen in the [*activity selection problem*](https://nikolaandro.github.io/activity-selection-problem/).
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Nikola Andrić
 
 

 
