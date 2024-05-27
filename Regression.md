Regression refers to one of a number of processes for estimating the relationship between two or more variables.

In general, regression takes a set of data points $W = (x_1,y_1), (x_2,y_2), \dots , (x_N,y_N)$ and a loss function $\mathcal L : \mathbb R ^2 \to \mathbb R$, and attempts to generate a function $\hat y : \mathbb R \to \mathbb R$ of a pre-specified form that minimises the loss function over all points.

# Common loss functions
In two dimensions, the naive loss function would be $\mathcal L = \sum _i |\hat y (x_i) - y_i|$, meaning the sum of the distance between the actual data value and predicted value for each known value of $x$. This however poses the issue of manipulation - when the process of regression is undertaken with this function it becomes impossible to solve the final equations without resorting to numerical methods. This is due to the absolute value function being on-differentiable
This issue is fixed by instead using the squared function, and defining the loss function as the sum of the squared distances: $$\mathcal L = \sum _i (\hat y (x_i) - y_i)^2$$
# Regression of constant predictor
The simplest function to use as a predictor is a constant function $\hat y (x) = w_1$. Substituted into the loss function: $\mathcal L (w_1) = \sum _i (\hat y (x_i) - y_i)^2 = \sum _i (w_1 - y_i)^2$
The minimum of this loss function can be calculated as the point at which $\cfrac {d \mathcal L} {dw_1} = 0$
$0 = \cfrac d {dw_1} \left( \sum _{i=1} ^N (w_1 - y_i)^2 \right)$
$0 = \sum _{i=1} ^N \cfrac d {dw_1} (w_1- y_i)^2 = \sum _{i=1} ^N \cfrac d {dw_1} (w_1 ^2 - 2w_1 y_i + y_i ^2)$
$0 = \sum _{i=1} ^N (2w_1 -2y_i)$
$0 = \sum _{i=1} ^N (w_1 - y_1) = \sum _{i=1} ^N w_1 - \sum _{i=1} ^N y_i$
$0 = Nw_1 - \sum _{i=1} ^N y_i$
$w_1 = \cfrac 1 N \sum _{i=1} ^N y_i$, which gives the mean

# Regression of slope predictor
If a slope predictor (a line with a with a 0 y-intercept) is used: $\hat y (x_i) = w_2 x_i$, $\mathcal L(w_2) = \sum_i (\hat y(x_i) - y_i)^2 = \sum _i (w_2 x_i - y_i)^2$
$\cfrac{d \mathcal L}{d w_2} = 0$
$0 = \cfrac d {dw_2} \left( \sum _{i=1} ^N (x_iw_2 - y_i) ^2 \right)$
$0 = \sum _{i=1} ^N \cfrac d {dw_2} (w_2 x_i - y_i)^2 = \sum _{i=1} ^N \cfrac d {dw_2} (x_i ^2 w_2 ^2 - 2 x_i w_2 y_i + y_i^2)$
$0 = \sum _{i=1} ^N (2 w_2 x_i ^2 - 2x_i y_i)$
$0 = \sum _{i=1} ^N (w_2 x_i ^2 - x_i y_i) = \sum _{i=1} ^N (w_2 x_i ^2) - \sum _{i=1} ^N (x_i y_i)$
$0 = w_2 \sum _{i=1} ^N x_i ^2 - \sum _{i=1} ^N (x_i y_i)$
$w_2 = \cfrac{\sum _{i=1} ^N y_i x_i}{\sum _{i=1} ^N x_i ^2}$

# Regression of straight line predictor
If a straight line $\hat y(x_i) = w_1 + w_2 x_i$ is used, the derivation is similar, if more complex, to above.
The equation yields the following expression if differentiated with regard to $w_2$:
$$w_2 = \cfrac{\cfrac 1 N \sum _{i=1} ^N x_i y_i - \left( \cfrac 1 N \sum _{i=1} ^N x_i \right) \left( \cfrac 1 N \sum _{i=1} ^N y_i\right)}{\cfrac 1 N \sum_{i=1}^N x_i ^2 - \left( \cfrac 1 N \sum _{i=1} ^N x_i \right)^2}$$
This can be expressed more succinctly as $w_2 = \cfrac{\overline{xy} - \overline x \ \overline y}{\overline{x^2} - \overline x ^2}$
Once this has been derived, the process can be repeated differentiating over $w_1$ to yield $w_1 = \cfrac 1 N \sum_{i=1} ^N (y_i - w_2 x_i)$

# Multi-variable representation
To perform regression on multiple variables, the data first has to be expressed in a form conducive to regression technique.
This is usually done via each data point's independent variables being a row in a matrix of all the data. Then, the dependent value is stored in a $N$-length column vector. For example, given $N$ data points of $D$ dimensions: $$\mathbf X = \begin{pmatrix} X_{11} & X_{12} & \dots & X_{1D} \\ X_{21} & X_{22} & \dots & X_{2D} \\ \vdots & \vdots & \ddots & \vdots \\ X_{N1} & X_{N2} & \dots & X_{ND} \end{pmatrix}, \mathbf y = \begin{pmatrix} y_1 \\ y_2 \\ \vdots \\ y_N\end{pmatrix} $$
Each data point then exists as a row vector: $\mathbf x_i = \begin{pmatrix} X_{i1} & X_{i2} & \dots & X_{iD} \end{pmatrix}$
# Linear multivariable regression
The most common prediction function is a weighted sum of dimensions, equivalent to a multi dimensional plane. This manifests as a row vector of weights $\mathbf w = \begin{pmatrix} w_1 & w_2 & \dots & w_D \end{pmatrix}$, with the prediction function expressed $$\hat y (x_i) = \mathbf x_i ^T \mathbf w = \sum _{j=1} ^D X_{ij} w_j$$
From this, the optimal weights can be derived. This derivation does not need to be known. The result is as follows: $$\mathbf w ^* = \left(\mathbf X ^T \mathbf X \right)^{-1} \mathbf X ^T \mathbf y$$
# Non-linear regression
This linear approach can be altered to allow regression with non linear predictors. These predictors take a single input, and are expressed as a sum of simple functions with coefficients to be calculated. This sum representation particularly aids polynomial predictors.
$\hat y (x) = f_1(x) + f_2(x) + \dots + f_D(x)$. 
This then constructs the input vector $\mathbf x ^T (x) = \begin{pmatrix} f_1(x) & f_2(x) &\dots & f_D(x) \end{pmatrix}$ and a large regression matrix can be constructed: $$\mathbf X = \begin{pmatrix} f_1(x_1) & f_2(x_1) & \dots & f_D (x_1) \\ f_1(x_2) & f_2(x_2) & \dots & f_D(x_2) \\ \vdots & \vdots & \ddots & \vdots \\ f_1(x_N) & f_2(x_N) & \dots & f_D(x_N) \end{pmatrix}, \mathbf y = \begin{pmatrix} y_1 \\ y_2 \\ \vdots \\ y_N\end{pmatrix} $$
The equation to be solved is then $\hat y (x) = \mathbf x^T(x) \mathbf w = w_1 f_1 (x) + w_2 f_2(x) + \dots + w_D f_D(x)$. Once the functions have been chosen and substituted into $\mathbf X$, the whole set of matrices can be substituted into the optimal weight equation. $$\mathbf w ^* = \left( \mathbf X^T \times \mathbf X \right) ^{-1} \mathbf X^T \mathbf y$$This is essentially like treating individual functions on a single dimension as multiple dimensions of a single data point.
# Regularisation
Complex functions in the previous case can lead to overfitting or chaotic behaviour, for example if large coefficients are used for higher order polynomials. This can be minimised by penalising large weights, done via an additional term in the loss function which minimises the sum of the square of the weights: $$\mathcal L (\mathbf w) = \sum _{i=1} ^N \left (y_i - \mathbf w ^T \mathbf x(x_i) \right)^2 + \lambda \sum _{i=1} ^D w_i ^2$$
This leads to a new optimal weight function. $$\mathbf w ^* = \left( \mathbf X ^T \mathbf X + \lambda \mathbf I \right) ^{-1} \mathbf X ^T \mathbf y$$
#data-science 