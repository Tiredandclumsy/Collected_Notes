A random variable is defined by a function $\phi : S \to \mathbb R$. $\phi$ on sample space $S$ defines a random variable.
It is often used in calculations alongside a [[probability measure]] on $S$ to construct a probability functions. 
Given a random variable $X$...
- the probability mass function $P_X(x)$ is defined by $P_X(x) := P(X = x)$
- the cumulative distribution function (CDF) $F_X(x)$ is defined by $F_X(x) := P(X \le x)$

# Discrete vs Continuous
Random variables can be discrete or continuous. Discrete

# Useful values
The median $m$ of $X$ is defined such that $P(X \le m) \ge \frac 1 2$ and $P(X \ge m) \ge \frac 1 2$
The mode $x$ is a (not necessarily unique) value on $X$ such that $P_X(x)$ is maximised
The mean $\mu$ of $X$ is defined as $\mu = E(X) := \sum_{x}P_X(x)$

The variance $\sigma^2$ of $X$ is defined as $\sigma^2 = E(X^2) - \mu^2 = \sum _x[P_X(x)x^2] - \mu^2$
