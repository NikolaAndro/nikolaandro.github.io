---
layout: post
title:  "Amortized Analysis of Algorithms"
date:   2021-10-27 09:29:20 +0700
categories: post
---

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
In the **amortized analysis**, we average the time required to perform a sequence of operations over the number of operations performed. The difference between amortized and avereage-case analysis is that amortized  analysis does not involve probability, but it guarantees the *average performance of each operation in the worst case.*


There are 3 different approaches to amortized analysis:

      1. Agregate Method - Determine total cost T(n) for a sequence of 
      n operations and calculate the amortized cost per operation 
      as T(n)/n.
      
      2. Accounting Method - Assign cost to each operation, 
      overcharging some operations and undercharging some 
      operations. The idea is that early overcharged 
      operations prepay for later undercharged operations. 
      
      3. Potential Method - A potential energy is associated to 
      the data structure,rather than individual credit to operations. 
      
# Amortized Bounds:

Assign the amortized cost for each operation such that you ""preserve the sum."" In other words,

SUM(amortized cost of the operations) >= SUM(actual cost of the operatinos)

The sum of amortized costs should always be bigger because we want the upper bound on the actual cost. This is useful because in some algorithms such as Dijksra's algorithm, we do not care about the shortest path at time t, but only about the shortest path when the algorithm is completly finished. Hence, in this case we care only about sum of the costs, not individual operations cost.  


      
# Agregate Method

The agregate method represents the **amortized cost** as the average cost per operation T(n)/n. Even though different operations may exist, they will all be assigned the same amortized cost by this method (accounting and potential method assign different amortized costs to different operations). This is why this method is the most intuitive, but also recognized as the weakest method to perform the amortization.

**CLRS Chapter 17**

*Problem 17.1-1*

If the stach operations included a MULTIPUSH operation, which pushes k items onto stack, would the O(1) bound on the amortized cost of the stack operations continue to hold?

Answer: No. What if there was MULTIPUSH(k) and then MULTIPOP(k) operations. They both have O(k) execution time. Hence the amortized time by agregate method would be 2 * O(k) / 2 = O(k), which is not O(k).

      
# Accounting Method

Let us define a bank:

  - allow an operation to store credit in the bank account (bank account >= 0).
  - allow an operation to take coins out of the bank topay for execution time using the credit that is stored in the bank.
  - balance must be >= 0.

Let's say an insertion function in the tree costs O(lgn) and deletion takes O(lgn).

So, we would pay the bank 1 coin worth O(lgn) per each insertion.

When we delete an element, we use the money from the bank to cover the deletion, which gives us amortization. 

Amortized cost = actual cost + deposits - withdrawals 

In other words, we assign different charges to different operations. Some operations are charged more or less than the actual cost of the operation. *The amount we charge the operation is called **amortized cost***. When operation's amortized cost exceeds the actual cost of operation, we assigh that difference to specific objects in the data structure as ***credits***. The same credit can help pay for later operations when the amortized cost is smaller than the actual cost of the operation. Different operations may have different amortized costs, which is different from the agregate method.

Example:

Let stack have the following methods and their **actual costs**:
- push 1
- pop 1
- multipop min(k,s), where s is the stack size and k is # of elements being popped.

Their amortized costs:
- push 2,
- pop 0,
- multipop 0

Our goal is to demonstrate that we can pay for any sequence of stack operations using their amortized costs. 



# Potential Method


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Nikola Andrić
