The Fourier transform can refer to any one of a set of methods by which a signal can be expressed as a set of coefficients of summed sinusoids of varying frequencies.

The signal generated from the set of coefficients is the original time domain signal transformed into the Fourier domain, and is referred to as the signal's Fourier series.
# Trigonometric Fourier transform
$$f(x) = a_0 + \sum _{n=0} ^\infty a_n \cos \left( \cfrac {2 \pi n x} T \right) + b_n \sin \left( \cfrac{2 \pi n x} T \right)$$
where $n$ is the number of cycles per period. $a_n$ and $b_n$ are the Fourier coefficients.
This transform gives two discrete sets of coefficients, representing the coefficients of integer multiples of the fundamental frequency.

These coefficients are given by $a_n = \cfrac 2 T \int _{-\frac T 2} ^{\frac T 2} f(x) \cos \left( \cfrac{2 \pi n x} T \right) dx$ and $b_n = \cfrac 2 T \int _{-\frac T 2} ^{\frac T 2} f(x) \sin \left( \cfrac{2 \pi n x} T \right) dx$
# Discrete Fourier transform
The discrete Fourier transform is similar to the trigonometric Fourier transform, but expresses the signal instead as a set of complex sinusoids. $$F(u) = \cfrac 1 N \sum_{x=0} ^{N-1} f(x) e^{\tfrac {-j2\pi ux} N} \text{ for } u \in [0,N-1]$$$$f(x) = \cfrac 1 N \sum_{u=0} ^{N-1} F(u) e^{\tfrac {j2\pi ux} N} \text{ for } x \in [0,N-1]$$
$F:\mathbb N \to \mathbb C$, such that the coefficients encode real coefficients of sine and cosine functions. In this way, the expression is equivalent to the trigonometric Fourier transform.
# Continuous Fourier transform
To gain a continuous Fourier domain representation, a continuous Fourier transform must be used. This can be considered the limit of the discrete Fourier transform, as the number of coefficients in any defined interval of frequency multiples approaches infinity.
$$F(u) = \int _{-\infty} ^\infty f(x) e^{-j2 \pi ux}dx$$$$f(x) = \int_{-\infty} ^\infty F(u) e^{j2 \pi ux}du$$
$F:\mathbb R \to \mathbb C$

# Power Spectrum
The complex number generated by the Fourier domain representation $F$ can be simplified for the sake of analysis by investigating the power spectrum $\omega$. This is generated by $\omega = |F(u)|^2$

#data-science