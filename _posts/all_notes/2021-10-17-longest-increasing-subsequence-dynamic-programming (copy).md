---
layout: post
title:  "Longest Increasing Subsequence (LIS) - Dynamic Programming"
date:   2021-10-17 09:29:20 +0700
categories: post
---
 **Pre-req: [longest common subsequence (LCS)](https://nikolaandro.github.io/longest-common-subsequence-dynamic-programming/)
 
# Problem:

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Find the length of the longest subsequence of a given sequence such that all elements of the subsequence are sorted in increasing order. For example, the length of LIS for 10, 22,9, 33, 21, 50, 41, 60, 80 is 6 and LIS is 10, 22, 33, 50, 60, 80.

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 We can go about this problem in multiple ways, but here I will use the LCS as a tool for solving this problem. 
 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 First, since we are given a list of numbers, we will create another list that is created by sorting the given list. This new list can be used in LCS together with the original list to find the length of the longest increasing subsequence.
 
 {%highlight ruby%}
def lis(a):
    n=len(a)
    # Creating the sorted list
    b=sorted(list(set(a)))
    m=len(b)
     
     
    # Creating table table for storing the answers of sub problems
    table=[[-1 for i in range(m+1)] for j in range(n+1)]
     
    # Finding Longest common Subsequence of the two arrays
    for i in range(n+1):
             
        for j in range(m+1):
            if i==0 or j==0:
                table[i][j]=0
            elif a[i-1]==b[j-1]:
                table[i][j]=1+table[i-1][j-1]
            else:
                table[i][j]=max(table[i-1][j],table[i][j-1])
    
    # Following code is used to print LCS
    index = table[m][n]
  
    # Create a character array to store the lcs string
    lcs = [""] * (index+1)
    lcs[index] = ""
  
    # Start from the right-most-bottom-most corner and
    # one by one store characters in lcs[]
    i = m
    j = n
    while i > 0 and j > 0:
  
        # If current character in X[] and Y are same, then
        # current character is part of LCS
        if a[i-1] == b[j-1]:
            lcs[index-1] = a[i-1]
            i-=1
            j-=1
            index-=1
  
        # If not same, then find the larger of two and
        # go in the direction of larger value
        elif table[i-1][j] > table[i][j-1]:
            i-=1
        else:
            j-=1
        print("current position is: ", i,",",j)
    print (lcs)
    
    return table[-1][-1]
     
# Driver program to test above function
arr = [10, 22, 9, 33, 21, 50, 41, 60]
print("Length of LIS is ", lis(arr))

{%endhighlight%}

 From this code we can see that 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Nikola Andrić

 
