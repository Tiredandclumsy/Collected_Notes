# Concept
A heap is a tree where no children have a larger value than their parent node. Heapsort is a [[sorting algorithm]] that uses this data structure to continually extract the largest value from the data.

# Characteristics
- $O(n \log n)$
- In place
- Not stable - the swapping of top and bottom elements breaks stability

# Description
Heapsort consists of 2 key procedures - `build()` and `Heapify()`. `Heapify()` takes a node and its two children, and performs any value swaps necessary to ensure the given subtree is a heap. `build()` uses `Heapify()` as a subroutine to ensure an input tree is a heap.

It should be noted that the notion of a tree and heap does not require additional memory, as the data is still physically stored in a register array. The notion of a tree is simply applied to values in the array. This is done with the idea that the first element is the root, the next 2 constitute the next layer, and so forth. Therefore the left and right children of node $i$ are nodes $2i$ and $2i + 1$, and the parent of node $i$ is node $\lfloor \frac i 2 \rfloor$.

Once the data is stored in a heap, the root node (largest value, now stored at $i=0$) can be swapped with the last node. Without the swap the heap would be split into 2 subtrees by the root's removal. However, this swap means the tree is no longer a heap, and must be reconstructed with `build()` before the next element is removed.

Then the heap is treated as being 1 element smaller, as this removes the newly moved largest element from the heap. The process is repeated until the heap only stored the single smallest element, at which point the array is sorted.

# Full Implementation
``` Pseudocode
Heapify():
Require An array of integers A of length n

```

#incomplete

# Runtime analysis
#incomplete 


#algorithms