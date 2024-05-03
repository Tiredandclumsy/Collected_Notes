The lowest common multiple of two numbers $x$ and $y$  is the smallest integer $m$ such that $m | x$ and $m | y$, where $a | b \leftrightarrow \frac a b \in \mathbb Z$

# Euclid's Algorithm
The LCM can be computed via Euclid's Algorithm, given two values $x$ and $y$:
Compute $r_1$ as the remainder of $x \div y$
Compute $r_2$ as the remainder of $y \div r_1$
Compute $r_n$ as the remainder of $r_{n-2} \div r_{n-1}$ until $r_i = 0$ is found
The LCM is given by $r_{i-1}$

#mathematics