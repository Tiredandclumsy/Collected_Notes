# Concept
Mergesort is a [[sorting algorithm]] employing recursion.
If both halves of an array are sorted, then the array can be sorted in $O(n)$ by simply storing each sorted half in arrays `B` and `C`, then traversing both, The smaller of the two elements inspected is written to `A`, then the position in the array from which the smaller value originates is incremented by 1. 
Performing this recursively creates a sorting algorithm known as Mergesort.

# Characteristics
- Best: $O(n \log n)$
- Average: $O(n \log n)$
- Worst: $O(n \log n)$
- Not in-place
- Stable

# Description
Mergesort is a [[divide-and-conquer algorithm]]. It recursively calls itself on the two halves of the array, and then merges the two halves before returning the result. The merge stages performs the sorting of the algorithm. 

Merge takes as array as input, splits it into its ordered halves, and iterates through both halves. After each step it compares the element of each array, adding the smaller of the two to `A`. Then it increments its position in the array containing the written element, 

# Full Implementation
``` Pseudocode
MERGESORT(A):
	Require array A of n integers
	A[0 : floor(n/2)] <- MERGESORT(A[0 : floor(n / 2)])
	A[floor(n / 2) + 1 : n] <- MERGSESORT(A[floor(n / 2) : n])
	A <- MERGE(A[0 : floor(n / 2)], A[floor(n / 2) + 1 : n])
	return A

MERGE(A):
	Require array A of n integers
	B <- A[0 : floor(n / 2)]
	C <- A[floor(n / 2) + 1 : n]
	k, i, j = 0
	while (i < floor(n / 2)) and (j < floor(n / 2) + 1) do
		if B[i] <= C[j] do
			A[k] = B[i]
			i += 1
		else do
			A[k] = C[j]
			j += 1
		k += 1
	return A
```

# Runtime analysis
The runtime can be split into two steps - the depth of recursion, and the runtime of `MERGE()` at each call.

The recursion tree is of depth $\log(n)$, or more specifically $\log(2 \lceil \frac n 2 \rceil)$, and thus is in $O(\log n)$
At each step, `MERGE()` runs in $O(n)$. This is because it iterates through both halves of the array, and thus iterates through each element of the input array. It must perform as many writes to `A` as elements in the input, and so the number of writes is also $O(n)$ leading to $O(n)$ overall.
Since `MERGE()` is performed $O(\log n)$times and runs in $O(n)$, Mergesort has a runtime $O(n \log n)$. In fact, this runtime does not change based on any properties of the input array, as no worst-case assumptions were made in the above reasoning. Therefore Mergessort runs in $\Theta (n \log n)$
