# Definition
Input: A natural number $n$ representing the unit length of a pole, a function $p : N \to Z$ representing the price of each pole length
The pole can be cut into unit-multiple lengths
A pole of length $i$ can be sold for a price $p(i)$
Output: The maximum possible revenue a pole of length $n$ can be cut and sold for

# Notation
A pole of length $n$ cut into $i$ pieces of length $k_j$ for $j = 1 \to i$ is expressed $n = k_1 + k_2 + \dots + k_i$
The optimal revenue for a pole of length $n$ is expressed $r_n$

# Analysis
A naive algorithm must run in $O(2^n)$ given there are $n-1$ positions to cut a pole of length $n$ at, and so $2^{n-1}$ possibilities for cutting such a pole. Although many of these possibilities are identical (note $3 = 1 + 2$ and $3 = 2 + 1$ give the same revenue) the number of unique cuttings is still exponential.

However, the problem exhibits [[optimal substructure]]. Assuming there exists some optimal cutting $n = K_1 + K_2 + K_3 + \dots + K_i$, it must be the case that $n - K_1 = K_2 + K_3 + \dots + K_n$ is also optimal, since if it weren't, the truly optimal cutting could be found and substituted into the solution to $n$, proving $n = K_1 + K_2 + K_3 + \dots + K_i$ was non-optimal.
Therefore, an initial recursive framing to the problem can be found, whereby $r_n = \max _{i = 1 \to n} \{p_i + r_{n-i}\}$, considering $r_0 = p_0 = 0$.

#algorithms