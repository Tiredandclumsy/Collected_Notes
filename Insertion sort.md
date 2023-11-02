# Concept
Insertion sort is a [[sorting algorithm]] that takes each element in the list from left to right and swaps it with the previous element if the previous element is larger.

# Characteristics
- Best: $O(n)$
- Average: $O(n^2)$
- Worst: $O(n^2)$

- In-place
- Stable

# Description
Insertion sort iterates over the input array from left to right. At each element `A[j]`, it's stored in a register `v`. Then, starting from the element before `A[j]`  and incrementing backwards, a comparison is made. If the next item `A[i + 1]` is larger than `v`, then the current element `A[i]` is written to `A[i+1]`. Once an element smaller than `v` is found, or `i` has reached the beginning of the array, `v` is written to `A[i]`. This has the effect of moving each element towards the start of the list until it 'hits', or is next to, an element smaller than it.

# Full Implementation
``` Pseudocode
INSERTIONSORT(A):
	Require: An array A of n integers
	for j <- 1,...,n-1 do
		v <- A[j]
		i <- j-1
		while i >= 0 and A[i] > v do
			A[i + 1] <- A[i]
			i -= 1
		A[i+1] <- v
```

# Runtime analysis
The runtime is governed by two loops. The first for loop runs in $O(n)$, since it iterates through the array. The second is variable.
Given a sorted list, then the condition `A[i] > v` will always be false, leading to no execution of the second loop and a final runtime in $O(n)$

However, given a worst case scenario, the inner loop would run from `i = j-1` to `i = 0`, and therefore be dependent on `j`. Hence $\sum _{j=1} ^{n-1} j  \cdot O(1) = O(1) \sum _{j=1} ^{n-1} j = O(1) \frac {n(n-1)}{2} = O(1) (n^2 - n) \in O(n^2)$


