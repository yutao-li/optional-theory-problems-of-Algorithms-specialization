1.Prove that the worst-case expected running time of every randomized comparison-based sorting algorithm is <a href="https://www.codecogs.com/eqnedit.php?latex=\Omega&space;(n\log&space;n)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\Omega&space;(n\log&space;n)" title="\Omega (n\log n)" /></a>. (Here the worst-case is over inputs, and the expectation is over the random coin flips made by the algorithm.)

every execution of a randomized comparison-based sorting algorithm will form a path in a comparison-based binary decision tree, and the length of every path, in other words, the height of the tree, is at least <a href="https://www.codecogs.com/eqnedit.php?latex=log_{2}n!" target="_blank"><img src="https://latex.codecogs.com/gif.latex?log_{2}n!" title="log_{2}n!" /></a>(as is shown in the lecture), so the worst-case expected running time is <a href="https://www.codecogs.com/eqnedit.php?latex=\Omega&space;(n\log&space;n)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\Omega&space;(n\log&space;n)" title="\Omega (n\log n)" /></a>

2.Suppose we modify the deterministic linear-time selection algorithm by grouping the elements into groups of 7, rather than groups of 5. (Use the "median-of-medians" as the pivot, as before.) Does the algorithm still run in O(n) time? What if we use groups of 3?

when of 7, it runs in O(n), when of 3, it does not. Easy to figure out following the same way as in the lecture

3.Given an array of n distinct (but unsorted) elements
<a href="https://www.codecogs.com/eqnedit.php?latex=x_{1},x_{1},...,x_{n}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{1},x_{1},...,x_{n}" title="x_{1},x_{1},...,x_{n}" /></a>
with positive weights
<a href="https://www.codecogs.com/eqnedit.php?latex=w_{1},w_{1},...,w_{n}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?w_{1},w_{1},...,w_{n}" title="w_{1},w_{1},...,w_{n}" /></a>
such that 
<a href="https://www.codecogs.com/eqnedit.php?latex=\sum_{i=1}^{n}w_{i}=W" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sum_{i=1}^{n}w_{i}=W" title="\sum_{i=1}^{n}w_{i}=W" /></a>
,a weighted median is an element
<a href="https://www.codecogs.com/eqnedit.php?latex=x_{k}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{k}" title="x_{k}" /></a>
for which the total weight of all elements with value less than
<a href="https://www.codecogs.com/eqnedit.php?latex=x_{k}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?x_{k}" title="x_{k}" /></a>
(i.e., 
<a href="https://www.codecogs.com/eqnedit.php?latex=\sum_{x_{i}<x_{k}}w_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sum_{x_{i}<x_{k}}w_{i}" title="\sum_{x_{i}<x_{k}}w_{i}" /></a>
is at most W/2, and also the total weight of elements with value larger than xk(i.e.,
<a href="https://www.codecogs.com/eqnedit.php?latex=\sum_{x_{i}>x_{k}}w_{i}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\sum_{x_{i}>x_{k}}w_{i}" title="\sum_{x_{i}>x_{k}}w_{i}" /></a>
) is at most W/2. Observe that there are at most two weighted medians. Show how to compute all weighted medians in O(n) worst-case time.

use a modified version of quick select, let variable med=W/2, while partitioning the elements by a pivot, keep track of the sum of weights of left hand side, denoted as W', if W' > med, recurse on the left hand side, else subtract med by W' and recurse on the right hand side.

4.We showed in an optional video lecture that every undirected graph has only polynomially (in the number n of vertices) different minimum cuts. Is this also true for directed graphs? Prove it or give a counterexample.

yes, for any directed graph T,if we add an inverse edge for each edge in T, we will not decrease # of mincut, and we get bi-directed graph, which we can treat as undirected graph T', since T' has only polynomially different minimum cuts, T has no more than that.

5.For a parameter α≥1, an α-minimum cut is one for which the number of crossing edges is at most α times that of a minimum cut. How many α-minimum cuts can an undirected graph have, as a function of α and the number n of vertices? Prove the best upper bound that you can.

see page 6 of https://www.cs.ubc.ca/~nickhar/W13/Scribe/Lecture7Scribe.pdf
