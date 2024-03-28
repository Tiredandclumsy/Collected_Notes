# Concept
Radix sort is a [[sorting algorithm]] that successively sorts integers by their digits from least to most significant. It uses counting sort on each digit. 
Due to the different [[radix]] values the algorithm can use to represent the values, there are multiple different implementations.

# Characteristics
- Best: $O(d(n + k))$, where $k$ is the radix and $d$ is the number of digits of each element
- Average: $O(d(n + k))$
- Worst: $O(d(n + k))$

- Not in-place
- Stable

# Description
Radix sort uses a stable sorting algorithm to incrementally sort an array by the digits of its elements, staring with the least significant and moving to the most. 
[[Countingsort]] is a common and logical algorithm for the subroutine, since it has an optimal runtime in $O(n + k)$ for $k$ possible elements, and the radix $k$ ensures there are only $k$ possible elements in each subroutine. 

# Full Implementation
Not required

# Runtime analysis
The runtime analysis is obvious, given the subroutine of Countingsort runs in $O(n + k)$ and is performed $d$ times.