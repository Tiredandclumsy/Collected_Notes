Maximum likelihood estimation (MLE) is a method of estimating the parameters of a probability distribution based on a data set.

Assuming some distribution $P(x_i|\theta)$ parameterised by $\theta$, the goal is to find the value of $\theta$ which maximises the likelihood of the observed data set occurring. The probability of any data set occurring is equal to the product of the probabilities of its data points, and so MLE seeks, in theory, to maximise $$P(x_1, \dots, x_N | \theta) = \prod _{i=1} ^N P(x_i|\theta)$$
# Log-likelihood
However, since large products can suffer from numerical over/underflow and are difficult to perform calculus on, the log-likelihood is taken instead: $$\mathcal L (\theta) = \log P(x_1, \dots, x_N | \theta) = \sum _{i=1} ^N \log p(x_i | \theta)$$This gives the same result as the standard likelihood, as $\log$ is an increasing function, and so the $x$ value giving maximum $f(x)$ also gives maximum $\log f(x)$.
# Biased coin example
One of the simplest parameterised distributions $P(x|\theta)$ is a biased coin. Here $\theta$, or $p$, represents the probability of the coin landing on heads. Heads values are interpreted as numerical $1$, and tails as $0$. Therefore, $P(x=1|p) = p , P(x=0|\theta) = 1-p$. Intuitively $P(x=1|p) + P(x=0|p) = 1$.

For the sake of generalisation, this formula can be written as $$P(x|p) = p^x(1-p)^{1-x}$$which for this binary case is equivalent to the initial statement.
 
Substituting this distribution into the log-likelihood expression gives $$\mathcal L(p) = \sum _{i=1} ^N \log\left(p^{x_i}(1-p)^{1-x_i}\right)$$Log laws permit the decomposition of the product into a sum $$\mathcal L(p) = \sum _{i=1} ^N \left(\log(p^{x_i}) +  \log\left((1-p)^{1-x_i}\right)\right)$$and the powers into products $$\mathcal L(p) = \sum _{i=1} ^N \left( x_i \log p + (1-x_i)\log(1-p) \right)$$This sum can then be split to apply to each term separately. This allows the removal of the $p$ terms from the sum, as they are independent of $i$. $$\mathcal L(p) = \left( \sum _{i=1} ^N x_i \right) \log p + \left( \sum_{i=1} ^N (1-x_i) \right) \log(1-p)$$Finally, the second sum can be simplified $$\mathcal L(p) = \left( \sum _{i=1} ^N x_i \right) \log p + \left( N - \sum _{i=1} ^N x_i \right) \log(1-p)$$
To find the maximum likelihood, the value of $p$ giving $\cfrac {d \mathcal L}{dp}=0$ can be computed, as follows. $$\cfrac {d\mathcal L}{dp} = \left( \sum _{i=1} ^N x_i \right) \cfrac {d\log p}{dp} + \left( N - \sum _{i=1} ^N x_i \right) \frac {d\log(1-p)}{dp} = 0$$The sums are independent of $p$ and so remain unchanged by the differentiation. 
It is a standard result that $\cfrac {d\log p }{dp} = \cfrac 1 p$, however the other derivative can be computed via the chain rule, where $u=1-p, y=\log(1-p) = \log(u), \cfrac{d \log(1-p)}{dp} = \cfrac 1 {1-p}$
Substituting these derivatives into the full equation yields $$\cfrac {d\mathcal L}{dp} = \left( \sum _{i=1} ^N x_i \right) \cfrac 1 p + \left( N - \sum _{i=1} ^N x_i \right) \cfrac 1 {1-p} = 0$$Multiply by $p(1-p)$ to remove denominators $$0 = \left( \sum _{i=1} ^N x_i \right) (1-p) + \left( N - \sum _{i=1} ^N x_i \right) p$$separate terms $$0 = \left( \sum _{i=1} ^N x_i \right) - \left( \sum _{i=1} ^N x_i \right)p - Np + \left( \sum _{i=1} ^N x_i \right)p = \left( \sum _{i=1} ^N x_i \right) - Np$$Add $Np$ to both sides and divide by $N$, finally yielding $$p = \cfrac 1 N \sum _{i=1} ^N x_i$$This shows the maximum likelihood predictor of a biased coin is the mean of the observed data set.

# Maximum likelihood classification
Given a dataset $\mathbf X$ of $N$ inputs $\mathbf x_1, \dots, \mathbf x_N$,  (where each $\mathbf x_k$ is a vector of continuous features) and a set of binary labels for the data points $Y = y_1, \dots, y_N$, it is useful to form a strategy for labelling new data points - some function $f: \mathbb R^N \to \{0,1\}$. 
An obvious candidate is a weighted sum of features passed into the heaviside step function - meaning if the sum is less that $0$ the label is $0$, and if it is greater the label is $1$. Formally: $$f_\mathbf w(\mathbf x) = \Theta(\mathbf w ^T \mathbf x)$$ where $\mathbf w$ is the vector of weights, and $\Theta(x) = \begin{cases} 0 & \text{if } x < 0 \\ 1 & \text{otherwise} \end{cases}$
Then $\mathbf w$ can be tweaked until $\forall i f_\mathbf w (\mathbf x_i) \approx y_i$. To formalise this loss, the loss function $\sum _{i=1} ^N \operatorname{XOR}(y_i, f_\mathbf w(\mathbf x_i))$ can be used, since the XOR function returns 1 when there is a difference between the two inputs.

The issue with this approach is that the number of wrong classifications will always be an integer, and so the plot of error for varying $\mathbf w$ will have a gradient of 0 at every point. This means calculus techniques, even gradient descent, cannot be used. 
To solve this, the model must be fitted with some continuous notion of error to facilitate a differentiable loss.
This continuous error can be gained by the model giving a probability, rather than a best-guess - a value of $P(y=1|\mathbf x)$. Therefore, a new function $p : \mathbb R ^N \to [0,1]$ must be formed, which requires a continuous replacement for the heaviside step function.
This function is the sigmoid: $\sigma (x) = \cfrac 1 {1 + e^{-x}}, \sigma : \mathbb R \to [0,1]$$P(y_i = 1 | \mathbf x_i) = \sigma(\mathbf w^T \mathbf x_i), P(y_i = 0 | \mathbf x_i) = 1- \sigma(\mathbf w^T \mathbf x_i)$
This system can be converted into a best-guess predictor by taking whichever class is most likely (has a probability over $0.5$):
$f_\mathbf w (\mathbf x_i) = \begin{cases} 1 & \text{if } P(y_i = 1|\mathbf x_i) > 0.5 \\ 0 & \text{otherwise} \end{cases}$

The sigmoid function has the property of being greater than $0.5$ for input values greater than $0$ and vice versa: $\sigma(0) = \cfrac 1 {1+e^0} = \cfrac 1 {1+1} = \cfrac 1 2$
Since $P(y_i = 1|\mathbf x_i) = \sigma(\mathbf w^T \mathbf x_i)$ the above $f_\mathbf w$ is equivalent to $$f_\mathbf w (\mathbf x_i) = \begin{cases} 1 & \text{if } \mathbf w^T x_i > 0.5 \\ 0 & \text{otherwise} \end{cases}$$

# Gaussian maximum likelihood
The Gaussian distribution takes two parameters , a mean $m$ and variance $v$$$P(x|m,v) = \cfrac 1 {\sqrt{2 \pi}}\left( e^{\left( -\frac 1 {2v} (x-m)^2 \right)} \right)$$Using the log-likelihood $$\log P(x|m,v) = \log \left( \cfrac 1 {\sqrt{2 \pi}}e^{ -\frac 1 {2v} (x-m)^2}\right)$$$$\log P(x|m,v) = \log \cfrac 1 {\sqrt{2 \pi}} + \log \cfrac 1 {\sqrt v} + \log\left( e^{-\frac 1 {2v} (x-m)^2} \right)$$Via log laws $$\log P(x|m,v) = -\cfrac 1 2 \log(2 \pi) - \cfrac 1 2 \log v - \cfrac 1 {2v}(x-m)^2$$$$\log P(x|m,v) = -\cfrac 1 2 \left(\log(2 \pi) + \log v + \cfrac 1 v(x-m)^2\right)$$
The maximum of this two-parameter function must lie where both $\cfrac {\partial \mathcal L(m,v)}{\partial m} = 0$ and $\cfrac {\partial \mathcal L(m,v)}{\partial v} = 0$
$$\mathcal L(m,v) = \sum _{i=1} ^N \log P(x_i | m,v)$$

#data-science