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
 Given a rod of length ***n*** inches and an array of prices ***p<sub>i</sub>***  for i = 1,2,...n that includes prices of all pieces of size smaller than n. Determine the maximum revenue value ***r<sub>n</sub>*** obtainable by cutting up the rod and selling the pieces. Note that if piece ***p<sub>n</sub>*** for a rod of length n is large enough, an optimal   solution may equire no cutting at all.
 
# Recursive Approach

 In this approach, we decompose the rod. The decomposition consists of the first piece of length i cut of the left hand end, and then the right-hand remainder of length *n - i*. Only the remainder from the right side can be decomposed further.  
 
{% highlight ruby %}
import math

# p = price array
# n = length of a rod that is being analyzed
def cut_rod(p,n):
    # If the lenght of the given rod is 0, no revenue is possible.
    if n == 0:
        return 0
    max_revenue = -math.inf
    for i in range (1,n+1):
        max_revenue = max(max_revenue, p[i] + cut_rod(p, n - i))
    return max_revenue

{% endhighlight %}

 For large values of *n*, this approach would be extremly slow due to many redundant operations. 
 
# Dynammic Programming Approach
 
 **How do we meet the necessary properties for dynamic programming?**
 
 1. Optimal Structure - We can cut the rod in different spots and compare the prices after each cut. Then we can recursively call the same function on a piece obtained after the cut. 
 2. Overlapping Subproblems - In our recursive implementation, we can see that many subproblems are repeating/overlapping.
 

# Top-Down Dynamic Programming Approach

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  
 As we know, this method is similar to the original recursive method, but it includes **memoization**, the process of saving/cashing/remembering already computed values.
 
{% highlight ruby %}
import math

# p = price array
# n = length of a rod that is being analyzed
def cut_rod(p,n):
    # Cache table/array. Fill out the table with minimal values
    cache_table = [-math.inf for i in range(n)]   
    return cut_rod_top_down(prices,n,cache_table)

def cut_rod_top_down(prices, n, cache):
    #If the value is already computed, just return it
    if cache[n] >= 0:
        return cache[n]
    if n == 0:
        max_val = 0
    else:
        max_val = -math.inf
        for i in range (1,n):
            max_val - max(max_value, prices[i] + cut_rod_top_down(prices, n-i, cache))
    cache[n] = max_value
    
    return  max_val

{% endhighlight %}

# Bottom-up Dynamic Programming Approach
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
 In the following piece of code, the for loop with *j* variable represents the length of the rod we plan on cutting. In order to get the best possible price, we must first iterate through all possible smaller sizes of the rod and calculate their maximum prices in order to get the best possible price for the rod of size *n*.
 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  In the for loop with *i* variable, we will find the maximum price for the rod of size *j* by cutting this piece of rod at index *i*. Compare the maximum_value found so far (starts from negative infiniti) with the price of the cut at next index. At the end of the loop, the maximum value will be compared with the given price for the whole rod without cutting since j-i will be equal to 0 in the last iteration of the loop which will result in prices[i] only (left side of the cut).
  
{% highlight ruby %}
import math

# price = price array
# n = length of a rod that is being analyzed
def cut_rod(prices,n):
    # Cache table/array. Fill out the table with minimal values
    cache_table = [0 for i in range(n+1)] 
    cache_table[0] = 0
    
    for j in range(1,n+1):
        max_val = -math.inf
        
        for i in range(j):
            max_val = max(max_val, prices[i] + cache_table[j-i-1] )
            
        cache_table[j] = max_val
        
    return cache_table[n]

{% endhighlight %} 
 
Running time of this approach is &theta(n^2) due to its nesed for loop.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Now, this solution only gives us the maximum price that we can get for slicing or not slicing the rod of length n.  We can modify our function to give us a full solution that consists of not only the maximum price, but also the position where the rod needs to be cut in order to get the maximum value/revenue for the rod of length n.

{% highlight ruby %}
import math

# price = price array
# n = length of a rod that is being analyzed
def cut_rod_plus(prices,n):
    # Cache table/array. Fill out the table with minimal values
    cache_table = [0 for i in range(n+1)] 
    # Array that saves indices of where to cut the rod for the optimal solution
    slice_table = [0 for i in range(n+1)]
    cache_table[0]=0
    
    for j in range(1,n+1):
        max_value = -math.inf
        
        for i in range(j):
            if max_value < prices[i] + cache_table[j-i-1]:
                #Update the maximum value found
                max_value = prices[i] + cache_table[j-i-1]
                
                #Record where the rod was sliced when max_val was found
                slice_table[j] = i+1

        cache_table[j] = max_value
     
    cache_table.pop(0)
    slice_table.pop(0)
    
    return cache_table, slice_table
    
r,s = cut_rod_plus([1,5,8,9,10,17,17,20,24,30],5)

print(r)
print(s)
    
{% endhighlight %} 

Let us see how this would work on an example. We are give the following lists:

{% highlight ruby %}

length *i* |  1   2   3   4   5   6   7   8   9   10
-----------------------------------------------------------
price *p*  |  1   5   8   9  10  17  17  20  24   30

{% endhighlight %}

After running our last function `cut_rod_plus(prices, n)`, we get results such as: 

{% highlight ruby %}

length *i* |  0   1   2   3   4   5   6   7   8   9   10
-----------------------------------------------------------
price *p*  |  0   1   5   8   9  10  17  17  20  24   30
cache_table|  0   1   5   8  10  13  17  18  22  25   30
slice_table|      1   2   3   2   2   6   1   2   3   10

{% endhighlight %}

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
Here we can see that if we had a rod of length 5, we would need to cut the rod at index 2, which leaves us with left side of the rod with length 2 and the right side of length 3. When prices of those 2 sides are combined, the value is 13 (greater than 10, or any other combination), which is the maximum value it could be gotten for selling the rod of length 5.

<!-- https://sites.psu.edu/symbolcodes/codehtml/#math LINK FOR SYMBOLS IN EQUATIONS -->
<!-- h<sub>&theta;</sub>(x) = &theta;<sub>o</sub> x + &theta;<sub>1</sub>x -->
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 The Squid

 
