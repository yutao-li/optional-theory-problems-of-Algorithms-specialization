1.You are given as input an unsorted array of n distinct numbers, where n is a power of 2. Give an algorithm that identifies the second-largest number in the array, and that uses at most
<a href="https://www.codecogs.com/eqnedit.php?latex=n&plus;\log_{2}n-2" target="_blank"><img src="https://latex.codecogs.com/gif.latex?n&plus;\log_{2}n-2" title="n+\log_{2}n-2" /></a>

https://stackoverflow.com/questions/9889679/find-second-largest-number-in-array-at-most-nlog%E2%82%82n%E2%88%922-comparisons/24429765

2.You are a given a unimodal array of n distinct elements, meaning that its entries are in increasing order up until its maximum element, after which its elements are in decreasing order. Give an algorithm to compute the maximum element that runs in O(log n) time.

binary search, determine the next interval by comparing current element with adjacent ones.

3.You are given a sorted (from smallest to largest) array A of n distinct integers which can be positive, negative, or zero. You want to decide whether or not there is an index i such that A[i] = i. Design the fastest algorithm that you can for solving this problem.

binary search, if A[i]<i, search left interval, else search right interval
