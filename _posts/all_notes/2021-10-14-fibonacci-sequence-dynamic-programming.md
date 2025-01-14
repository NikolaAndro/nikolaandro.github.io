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
 This approach has an exponential runtime complexity and it is too slow. It repeats the same computations again and again. Since this is a recursive approach, we first cover the base cases and then we make recursive calls. Therefore, when trying to compute F<sub>300</sub> it would take a great amount of time. 
 
{% highlight ruby %}
def fibonacci(n):
    # Check if input is valid
    if type(n) != int:
        raise TypeError("n must be a positive integer!")
    if n < 1:
        raise ValueError("n must be a positive integer!")
	
    # Base cases when n is 0, 1, or 2, the values are 0, 1, and 1.
    if n == 0:
        return 0
    if n <= 2:
        return 1
    # Recursive calls
    return fibonacci(n-1) + fibonacci(n-2)

{% endhighlight %}
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 In order to optimize the recursive case, we can introduce memoization and keep the table of computed values in order to eliminate redundant computations. 
 
# Top-Down Dynamic Programming (recursion + memoization)

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Eliminating redundant computations results in a significant speedup in execution time. 
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 First, we will implent memoization implicitly, and then we will use a built-in python tool that makes memoization trivial.
 
{% highlight ruby %}
 #=> declare the dictionary that will store computed fibonacci values
 fibonacci_cache = {}

 def fibonacci(n):
    # Check if input is valid
    if type(n) != int:
        raise TypeError("n must be a positive integer!")
    if n < 1:
        raise ValueError("n must be a positive integer!")
	
 
    # Check if n is already in the fibonacci cache. If so, return it.
    if n in fibonacci_cache:
        return fibonacci[n]
    # Otherwise, we want to:
    # COMPUTE the value, 
    # STORE IT in cache, and 
    # RETURN it.
    # Base cases when n is 0, 1, or 2, the values are 0, 1, and 1.
    if n == 0:
        value = 0
    if n <= 2:
        value = 1
    elif n > 2:
        value = fibonacci(n-1) + fibonacci(n-2)
	
    # Cache the computed value.
    fibonacci_cache[n] = value
    
    #return it
    return value

{% endhighlight %}
  
 To do this in a more clean way, we can use `lru_cache` module. LRU Cache stands for Least Recently Used Cache. 
 
{% highlight ruby %}
 #=> Import lru_cache from functools module
 from functools import lru_cache
 
 #=> Enter the number of values to cache. Setting it to 1000. By default, python will cache 128 most receantly used values.
 @lru_cache(maxsize = 1000)
 def fibonacci(n):
    # Check if input is valid
    if type(n) != int:
        raise TypeError("n must be a positive integer!")
    if n < 1:
        raise ValueError("n must be a positive integer!")
	
    # Base cases when n is 0, 1, or 2, the values are 0, 1, and 1.
    if n == 0:
        return 0
    if n <= 2:
        return 1
	
    # Recursive calls
    return fibonacci(n-1) + fibonacci(n-2)

{% endhighlight %}
# Bottom-Up Dynammic Programming
 
  
  We are able to do this without using recursion in the bottom-up approach. 
  
{% highlight ruby %}
 def fibonacci(n):
    # Check if input is valid
    if type(n) != int:
        raise TypeError("n must be a positive integer!")
    if n < 1:
        raise ValueError("n must be a positive integer!")
	
    # Base cases when n is 0, 1, or 2, the values are 0, 1, and 1.
    if n == 0:
        return 0
    if n <= 2:
        return 1
	
    # Create a table to keep already calcucated values.
    table = []

    # Insters first 2 trivial values.
    table.append(0)
    table.append(1)
    
    # Calculate the rest of the values using the previously calculated values.
    # Here we go from simpler solutions (bottom) to solving more
    # complex solutions (up).
    for i in range(2, n+1):
        table[i] = table[i-1] + table[i-2]
	
    # Finally return the value that was passed
    return table[n]
{% endhighlight %}  

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 We can see that this problem is solved the fastest using the bottom-up dynamic programming approach. The run-time is linear.
 
<!-- https://sites.psu.edu/symbolcodes/codehtml/#math LINK FOR SYMBOLS IN EQUATIONS -->
<!-- h<sub>&theta;</sub>(x) = &theta;<sub>o</sub> x + &theta;<sub>1</sub>x -->
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 The Squid

 
