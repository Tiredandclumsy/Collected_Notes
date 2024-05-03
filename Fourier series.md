The Fourier Series can refer to any one of a set of methods by which a signal can be expressed as a set of coefficients of summed sinusoids of varying frequencies.

The signal generated from the set of coefficients is the signal transformed into the Fourier domain.

# Trigonometric Fourier Series
$$f(x) = a_0 + \sum _{n=0} ^\infty a_n \cos \left( \cfrac {2 \pi n x} T \right) + b_n \sin \left( \cfrac{2 \pi n x} T \right)$$
where $n$ is the number of cycles per period. $a_n$ and $b_n$ are the Fourier coefficients.

These coefficients are given by $a_n = \cfrac 2 T \int _{-\frac T 2} ^{\frac T 2} f(x) \cos \left( \cfrac{2 \pi n x} T \right) dx$ and $b_n = \cfrac 2 T \int _{-\frac T 2} ^{\frac T 2} f(x) \sin \left( \cfrac{2 \pi n x} T \right) dx$
