A problem with the optimal substructure property is one where any optimal solution to such a problem is either unitary or contains within it an optimal solution to a different form of the same problem.

For example, one such problem is the [[pole cutting algorithm]]. Given a pole $n = k_1 + k_2 + k_3 + \dots + k_i$, it must be the case that $n - k_1 = k_2 + k_3 + \dots + k_n$. If this was not the case, then an optimal solution to $n-k_1$ could be substituted into the previous solution to $n$, creating a better revenue and proving the previous solution to $n$ was not optimal.

#algorithms