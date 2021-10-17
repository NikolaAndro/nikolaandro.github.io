---
layout: post
title:  "Longest Common Subsequence (LCS) - Dynamic Programming"
date:   2021-10-17 09:29:20 +0700
categories: post
---

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
TO DO: explain filling the table and explain how code works

# Problem:

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Given two sequences, find the *length* of longest subsequence present in both of them. A subsequence is a sequence that appears in the same relative order, but not necessarily contiguous. For example, “abc”, “abg”, “bdf”, “aeg”, ‘”acefg”, .. etc are subsequences of “abcdefg”. 
 
 This problem can easily solved recursively. However, that is not good enough. There is a lot overlapping when it comes to long sequences and the runtime is O(n<sup>2</sup>) in the worst case when the sequences have no common characters.
 
{%highlight ruby%}
def lcs(X, Y, m, n):
 
    if m == 0 or n == 0:
        return 0;
    # case when characters from x and y are equal
    elif X[m-1] == Y[n-1]:
        return 1 + lcs(X, Y, m-1, n-1);
    # case when characters from x and y are not equal
    # we have to compare x with y-1 and opposite
    else:
        return max(lcs(X, Y, m, n-1), lcs(X, Y, m-1, n));
 
 
# Driver program to test the above function
X = "GCGCAATG"
Y = "GCCCTAGCG"
print ("Length of LCS is ", lcs(X , Y, len(X), len(Y)))

{%endhighlight%}



 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
 Nikola Andrić

 
