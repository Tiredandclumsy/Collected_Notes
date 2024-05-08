Communication systems are susceptible to external influence that affects the message being transmitted.

Noise is defined as random signals from natural sources that affects the system. Types include atmospheric noise, caused by electrical processes in the atmosphere affecting antennae, and and thermal noise, caused by thermal agitation of electrons in signal processing circuits. Thermal noise is modelled as Additive White Gaussian Noise (AWGN).

Interference is defined as contamination of a communication message by extraneous sources. These sources can be power lines, machinery, other users of the channel, etc. Interference cannot be modelled as Additive White Gaussian Noise. 

# Additive White Gaussian Noise
AWGN is a model of noise, defining three properties:
- Additive: the noise is added to any other existing noise or interference sources
- White: the noise has uniform power across the frequency spectrum
- Gaussian: the noise exhibits a Gaussian probability distribution for sampled points in time
The Gaussian distribution is given by $$P(X) = \dfrac{1}{\sqrt{2 \pi} \sigma_X} e^{\left( - \dfrac{(x - \mu_X)^2}{2 \sigma _X ^2} \right)}$$where $\mu_X$ is the mean and $\sigma_X$ is the standard deviation.
# Noise Power
The power of thermal noise in a system, in Watts, is given by $N = kTB$, where $k$ is the Boltzmann constant, $T$ is the temperate in Kelvin, and $B$ is the bandwidth in Hertz. $k \approx 1.380649×10^{23} \text{JK}^{-1}$. 
While in theory $T$ and $B$ are variable, there are practical limits to their manipulation. A smaller $T$ requires significant infrastructure to cool the system, and erasure of noise via this coefficient can only be achieved at $0 \text K$, which is practically impossible. Reducing $B$ reduces the data rate, and removal of noise in this manner requires a bandwidth of $0 \text{Hz}$, which prohibits data transfer.
Often noise is converted from $\text{W}$ to be expressed in $\text {dBW}$ or $\text{dBmW}$
Noise power is used most notably in calculating [[Signal to Noise Ratio]]. 

The noise spectral density $N_0$ is the noise power per unit bandwidth $\frac N B$.
# Signal power
Signal power is usually converted to either energy per bit $E_b$ or energy per symbol $E_s$. These are given by the signal power divided by the bit/symbol rate.

#communications