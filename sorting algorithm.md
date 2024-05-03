A sorting algorithm is any algorithm that takes as input an array of complete [[relation#Order relation|order]]-able elements, and outputs an equal length array containing all such elements in ascending order.

# Characteristics
A sorting algorithm can be in-place or stable. 

In-place algorithms require an additional number of registers in $O(1)$ to sort an input of length $n$.
Stable algorithms ensure that any two equal-valued elements retain the same relative order in the output array as they had in the input array.

# Comparison-based sorting
Most sorting algorithms determine the order of elements by successively comparing pairs of elements in an array, without any other information being gathered. This is called comparison based sorting.
This is notable because it does not rely on inspecting the absolute value of any elements. All information is a boolean value of `A[i] <= A[j]`

Sorting an array is equivalent to finding a permutation $\pi$ such that $A[\pi^{-1}(1) \le A[\pi ^{-1}(2) \le \dots]]$
A permutation is a [[bijection]] from $A$ to $A$: $\pi : [n] \to [n]$

Let $\Pi$ be the set of all permutations of $[n]$. $|\Pi| = n!$, since there are $n$ choices for the first element $\pi(A[0])$, $n-1$ choices for the second, and so forth. 

It can be noted that any comparison either halves the possible sample space of permutations, or does nothing to it, as for every comparison that yields true there must exist a permutation where the two compared elements are reversed, and the comparison yields false.
Therefore every comparison-based sorting algorithm can be represented in a binary tree. Each node is a comparison, and each leaf is a solution. There are $|\Pi| = n!$ possible leaves.

A binary tree of height $h$ has no more than $2^h$ leaves. 
$2 ^h \le n!$, $h \le \log(n!)$
Stirling's approximation states that $n! \ge \left(\frac n e \right) ^n$
$h \le \log \left(\left ( \frac n e \right ) ^n \right)$
$h \le n \log \left ( \frac n e \right )$
$h \in O(n \log n)$
Since $h$ is the number of comparisons in a given path to a solution, $h$ is equal to the number of comparisons required to sort any given array. A comparison-based sorting algorithm therefore runs in $\Omega( n \log n)$

#algorithms