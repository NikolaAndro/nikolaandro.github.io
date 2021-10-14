---
layout: post
title:  "Fibonacci Sequence - Dynamic Programming"
date:   2021-10-14 09:29:20 +0700
categories: post
---

# Fibonacci Sequence

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 **Fibonacci Sequence:** *F<sub>n</sub> = F<sub>(n-1)</sub> + F<sub>(n-2)</sub>*


 In this note, we will solve this problem using: 
 
	- recursion only
	- top-down dynamic programming (a.k.a. recursion + memoization)
	- bottom-up dynammic programming 
	
# Recursion only:

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 This approach has an exponential runtime complexity and it is too slow. It repeats the same computations again and again. Since this is a recursive approach, we first cover the base cases and then we make recursive calls.
 
{% highlight ruby %}
def fibonacci(n):
    #=> Base cases when n is 0, 1, or 2, the values are 0, 1, and 1.
    if n == 0:
        return 0
    if n <= 2:
        return 1
    #=> Recursive calls
    return fibonacci(n-1) + fibonacci(n-2)

{% endhighlight %}
 
 
 
# Top-Down Dynamic Programming 

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 In order to optimize the recursive case, we can introduce memoization and keep the table of computed values in order to eliminate redundant computations.
 
# Bottom-Up Dynammic Programming
 
<!-- https://sites.psu.edu/symbolcodes/codehtml/#math LINK FOR SYMBOLS IN EQUATIONS -->
<!-- h<sub>&theta;</sub>(x) = &theta;<sub>o</sub> x + &theta;<sub>1</sub>x -->
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Nikola Andric

 
