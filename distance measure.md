A distance measure $D$ on an $n$ dimensional vector space $M$ is a metric (type of [[function]]) $D : M \times M \to \mathbb R$ which fulfils 4 properties:
- Non-negativity: $\forall a,b \in \mathbb R ^n : D(a,b) \ge 0$
- Reflexivity: $\forall a,b \in \mathbb R^n : D(a,b) = 0 \iff a=b$
- Symmetry: $\forall a,b \in \mathbb R^n: D(a,b) = D(b,a)$
- Triangular inequality: $\forall a,b,c \in \mathbb R^n: D(a,b) \le d(a,c) + D(c,b)$
Distance measures more generally can be defined on any kind of data, such as sequences of symbols.
# P-norm distances
Normal distance, also known as Minkowski distance, is the generalisation of distances to a discrete ordered set. The $p$-norm distance $L_p$, for any $p \in \mathbb N$ is defined $$\left ( \sum _{i=1} ^n |x_i - y_i|^p \right )^{\tfrac 1 p}$$
## Taxicab distance
The Taxicab distance, also known as the Manhattan distance, returns the sum of the differences between the points in each dimension.
$$D(x,y) = \sum _{i=1} ^n |x_i - y_i|$$
It is the $1$-norm distance $L_1$
## Euclidean distance
The Euclidean distance, or normal distance, returns the square root of the sum of the squares of the differences between the points in each dimension.
$$D(x,y) = \sqrt{\sum _{i=1} ^n |x_i - y_i |^2}$$
It can be expressed in vector form: 
$$D(x,y) = \Vert x - y \Vert = \sqrt{(x-y)^T(x-y)}$$
It is the $2$-norm distance $L_2$
## Chebyshev distance
The Chebyshev distance, also known as the chessboard distance, takes the greatest of the distances of the points along each dimension.
$$D(x,y) = \max _i (|x_i - y_i|)$$
Alternatively, it can be expressed $$\lim_{p \to \infty} \left(\sum _{i=1} ^n |x_i - y_i|^p \right)^{\tfrac 1 p}$$
It is the $\infty$-norm distance $L_\infty$

# Dynamic Time Warping
Since Minkowski distances are sensitive to translations and scalings, a new distance measure was created  by Berndt and Clifford in 1994 to define distance between time-sampled data such as audio and spatial movement tracking.

For two series $X = (x_1, x_2, \dots, x_n)$ and $Y = (y_1, y_2, \dots, y_n)$, dynamic time warping is defined as $$\operatorname{DTW} (X,Y) = D(x_1,y_1) + \min\{\operatorname{DTW}(X, \operatorname{REST}(Y)), \operatorname{DTW}(\operatorname{REST}(X), Y), \operatorname{DTW}(\operatorname{REST}(X), \operatorname{REST}(Y))\}$$where $\operatorname{REST}(A) = (a_2, \dots, a_n)$ and $D(x,y)$ is a distance function between real values, usually $|x-y|$

DTW can be thought of as generating a distance matrix between all pairs of points in the two sequences, and finding the minimum path through this matrix.

# Cosine distance
Cosine distance (inverse of cosine similarity) is defined as one subtract the cosine of the angle between the vectors represented by the two points.
$\operatorname{similarity}(A,B) = \cos(\theta) = \cfrac{A \cdot B}{\Vert A \Vert \Vert B \Vert}$
$\operatorname{distance}(A,B) = 1 - \operatorname{similarity}(A,B) = 1 - \cos(\theta) = 1 - \cfrac{A \cdot B}{\Vert A \Vert \Vert B \Vert}$

# Mahalanobis distance
The Mahalanobis distance is a measure between a data vector and a set of data, or more specifically two vectors with regard to a specific data set covariance. 
$$\operatorname{mahalanobis}(a,b) = (a-b)^T \Sigma ^{-1}(a-b)$$ where $\operatorname{cov}(X,Y) = \Sigma = \cfrac 1 {N-1} \sum_{i=1} ^N (x_i - \bar x)(y_i - \bar y)$

# Symbolic distances
Distance can be defined on words, binary sequences, DNA sequences, and more. These all define distance measures between strings of symbols from a pre-defined alphabet.
## Hamming distance
Hamming distance defines a distance between any two strings of equal length.
It is defined as the number of substitutions required to change one string into the other, or the number of positions with different symbols between the two strings.
For binary strings, Hamming distance is equal to $L_1$. 
It is used in coding theory and error correction.
## Edit distance
Edit distance defines a distance between any two strings of any length. It describes three permitted operations, and counts the minimum number of operations required to transform one string into the other. The three operations are insertion, deletion, and substitution. 
It is used in spelling correction and DNA string comparison.


#data-science
