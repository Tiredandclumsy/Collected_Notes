# Concept
Quicksort is a [[sorting algorithm]] based on [[Mergesort]]. It is thus a [[divide-and-conquer algorithm]]. However it differs from Mergesort in the fact that it is in-place.
The principle of its sorting is the choice of a pivot element. Once a pivot has been chosen, all elements smaller than the pivot are placed to the left of it, and all elements larger are placed to the right. Then the algorithm is called recursively on the two subproblems either side of the pivot.

# Characteristics
- Best: $O(n \log n)$
- Average: $O(n \log n)$
- Worst: $O(n^2)$

- In place
- Not stable

# Description
Mergesort begins by selecting a pivot `A[p]` from the input array. This process is complex and differs based on varying implementations of the algorithm, therefore the implementation described will take the last element as the pivot for simplicity.
Once the pivot has been selected, all elements less than or equal to the pivot are moved to the left of it, and all elements greater are moved to the right. This breaks stability, as the pivot will end up the rightmost element of all the elements with equal value to it. 
Now it can be noted that the pivot is in the correct position. Therefore the procedure need only be called on `A[0 : p - 1]` and `A[p + 1 : n - 1]` , and the array will be sorted with no additional merging required. 

The recursion tree, assuming an optimal pivot that generates equal sub-problems, will have $O(\log n)$ levels. Therefore if a procedure for rearranging around a given pivot can be found that runs in $O(n)$, the algorithm will be able to run optimally in $O(n \log n)$.

A procedure exists for partitioning a sub-array around `A[n-1]`, or the last element, in $O(n)$ time. This facilitates any pivot, as `A[p]` and `A[n-1]` can be swapped in $O(1)$, still yielding $O(n)$.
The procedure is as follows:
- Store the pivot in a register `x`
- Create two reference points `i` and `j`, initialising `i` to $-1$ and `j` to $0$
- Iterate `j` through the list, but at every `A[j] <= x` move `i` forward by $1$ element and swap `A[i]` and `A[j]`
When `j` reaches `j = n-1` the pivot will be placed at `i`, and the partition will be complete. 


Quicksort gains its in-place nature over Mergesort by partitioning the problem is such a way that no additional work is needed to combine the sub-problem solutions.

Despite the worst-case runtime $O(n^2)$, Quicksort is very efficient in practice. It is often used alone, or combined with another algorithm, in most sorting applications.

# Full Implementation
``` Pseudocode
QUICKSORT(A):
	Require: An array A of n integers
	if n = 1 do
		return A
	i <- PARTITION(A)   //note partition here is impure
	A <- QUICKSORT(A[0 : i-1])
	A <- QUICKSORT(A[i+1 : n-1])
	return A

PARTITION(A):
	Require: An array A of n integers
	x <- A[n-1]
	i <- -1
	for j <- 0,...,n-1 do
		if A[j] <= x do
			i += 1
			y <- A[j]
			A[j] <- A[i]
			A[i] <- y   // exchange A[i] and A[j]
	return i
```

# Runtime Analysis
The runtime can be expressed recursively: $T(1) = O(1)$, $T(n) = O(n) + T(n_1) + T(n_2$ where $n_1$ and $n_2$ are the sizes of the resulting sub-problems. Note that $n_1 + n_2 = n-1$

The $O(n)$ terms arises from `PARTITION()` running in $O(n)$. This can be seen via the single loop incrementing `j`, and all other operations running in $O(1)$.

For the worst case, the problem is split entirely unevenly such that $n_1 = n-1$ and $n_2 = 0$.
$T(n) = O(n) + T(n-1)$, $T(n) = Cn + T(n-1)$
$T(n) \le \sum _{i = 1} ^n Ci = C \sum _{i=1} ^n i$
$T(n) = C \frac {n(n+1)}{2} = \frac C 2 (n^2 + n) \in O(n^2)$

The best case involves the problem being split along the median such that $n_1 = \lceil \frac{n-1}2 \rceil$ and $n_2 = \lfloor \frac{n-1}2 \rfloor$. This analysis is more complex.
Described in a recursion tree, it can be noted that at each level the value of $n$ is halved. Therefore, if the level is denoted $\ell$, then $\frac n {2^{\ell - 1}} \le 1$
$\log(n) + 1 \le \ell$, thus tree has $O(\log n)$ levels.
At each level `PARTITION()` is run on both sub-arrays such that it runs in $O(n_1 + n_2) = O(n - 1) = O(n)$
Therefore, with $O(log n)$ levels running in $O(n)$ time, the best case is $O(n \log n)$


# Additional Information
The $O(n \log n)$ runtime is preserved for a wide range of pivots around the median. Additionally, if such an optimal pivot only occurs every $k$ iterations, the algorithm will simply run in $k n \log n$, preserving $O(n \log n)$

There are algorithms for finding the median in $O(n)$ time, and so these could be used to select a pivot while retaining, and indeed ensuring, $O(n \log n)$. However they are computationally intensive and tend not to be efficient in practice. Instead, a random value can be selected by exchanging `A[n-1]` with some value `A[i]`. This also preserves $O(n \log n)$ for reasons related to those above, and is much faster than a median approach for pivot selection, making it ideal for practical implementation.