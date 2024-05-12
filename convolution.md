Convolution describes a binary operation on [[function|functions]] that expresses how each function modifies the other.
Convolution is defined by $$f * g := \int _{-\infty} ^\infty f(t-\tau) g(\tau) d \tau = \int _{-\infty} ^\infty f(\tau) g(t-\tau) d \tau$$It can therefore be noted that convolution is commutative.

# Discrete convolution
Convolving over discrete functions gives the following definition: $$f*g = \sum _{m = -s} ^s f(x-m) h(m))$$for $s \ge 1$, where $s$ is the size of the range of the discrete functions.
Convolution can be conceptualised as reversing the plot of one function, and stepping it through the other, scaling it by the other function's value at each step. The limit of this process as the step length approaches 0 gives the continuous definition above

# 2D discrete convolution
$$f * h = \sum _{m=-s_1} ^{s_1} \sum _{n = s_2} ^{s_2}f(x + m, y+n)h(m,n)$$

# Use in data science
In data science, convolutions are used to remove noise, smooth or sharpen detail, and prepare for [[Feature#Feature extraction|feature extraction]]. 
Usually, data points are convolved with generated weighted functions called filters, kernels, or masks.
The data is discrete, and so the discrete definition is used.

The filter will not be defined for the edges of the data, and so edge values are lost for each convolution. This can be fixed via padding, where the data is extended wither with constant values or copies of the data point.

# Transforms
When applying frequency transforms such as the [[Fourier transform]], convolution becomes multiplication of frequency domain functions.