# Concept
Countingsort is a specific [[sorting algorithm]] that achieves better runtime than the optimal comparison based sorting of $O(n \log n)$. This is because it sorts arrays of elements with values from a known set: $A \in \{a, b, c, \dots\}^n$ where $a < b < c < \dots$ and $|\{a, b, c, \dots\}| = k$.
By counting the number of times each value appears in the array, the values can be written directly into the output array.

# Characteristics
- Best: $O(n + k)$
- Average: $O(n + k)$
- Worst: $O(n + k)$

- Not in-place
- Stable

# Description
Countingsort constructs and fills multiple arrays with data from the input in order to write correct values. 
Firstly, it constructs a $k$ length array `C` and populates it with the frequency of each element in the possible value set. Then it iterates through `B`, replacing each value with the sum of that frequency and its preceding frequencies. This introduces an offset to allow direct writing to indices of the output array. It can also be thought of as writing the frequency of values smaller than or equal to the given value.
The output is to be written in a blank $n-1$ length array `B`. For the final step, `A` is iterated through in reverse, and for each value `x` in `A`, `x` is written in `B` in the position given by `C[x]`. Then after each write, `B[x]` is deprecated by $1$ to make the next identical element written in a new position.

The backwards incrementing in the last step, through both `A` and the decrementing of `B[x]`, ensure stability.

# Implementation
``` Pseudocode
COUNTINGSORT:
	Require: An array A of n integers ranging from 0 to k
	Let B be a new array of length n
	Let C be a new array of length k
	For i <- 0,...,n-1 do
		C[A[i]] += 1
	For i <- 1,...,k do
		C[i] += C[i-1]
	For i <- n-1,...,0 do
		B[C[A[i]] - 1] <- A[i]
		C[A[i]] -= 1
	return B
```

# Runtime Analysis
The first and last loop run in $O(n)$ by inspection, and the second in $O(k)$. Therefore the algorithm runs in $O(n + k)$.  If $k \in O(n)$ then Countingsort runs in $O(n)$.

#algorithms