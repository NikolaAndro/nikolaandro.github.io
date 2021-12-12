---
layout: post
title:  "Quicksort Algorithm"
date:   2021-10-10 09:29:20 +0700
categories: post
---

**QuickSort** is a Divide and Conquer algorithm. It picks an element as pivot and partitions the given array around the picked pivot. 
There are many different versions of quickSort that pick pivot in different ways. 

1. Always pick first element as pivot.
2. Always pick last element as pivot
3. Pick a random element as pivot.
4. Pick median as pivot.

The main part of the algorithm is the partition() where the pivot x is being placed in a sorted spot in the array. That is being done in a way that all element that are
less than x are put on hte left side of x and other elements on the right side of x. This should be done in linear time.

{%highlight ruby%}

quickSort(arr[], low, high)
{
    if (low < high)
    {
        pivot = partition(arr, low, high);

        quickSort(arr, low, pivot - 1);  // Before pi
        quickSort(arr, pivot + 1, high); // After pi
    }
}


# This Function handles sorting part of quick sort
# start and end points to first and last element of
# an array respectively
def partition(start, end, array):
      
    # Initializing pivot's index to start
    pivot_index = start 
    pivot = array[pivot_index]
      
    # This loop runs till start pointer crosses 
    # end pointer, and when it does we swap the
    # pivot with element on end pointer
    while start < end:
          
        # Increment the start pointer till it finds an 
        # element greater than  pivot 
        while start < len(array) and array[start] <= pivot:
            start += 1
              
        # Decrement the end pointer till it finds an 
        # element less than pivot
        while array[end] > pivot:
            end -= 1
          
        # If start and end have not crossed each other, 
        # swap the numbers on start and end
        if(start < end):
            array[start], array[end] = array[end], array[start]
      
    # Swap pivot element with element on end pointer.
    # This puts pivot on its correct sorted place.
    array[end], array[pivot_index] = array[pivot_index], array[end]
     
    # Returning end pointer to divide the array into 2
    return end
    
{%endhighlight%}
