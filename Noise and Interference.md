Communication systems are susceptible to external influence that affects the message being transmitted.

Noise is defined as random signals from natural sources that affects the system. Types include atmospheric noise, caused by electrical processes in the atmosphere affecting antennae, and and thermal noise, caused by thermal agitation of electrons in signal processing circuits. Thermal noise is modelled as Additive White Gaussian Noise (AWGN).

Interference is defined as contamination of a communication message by extraneous sources. These sources can be power lines, machinery, other users of the channel, etc. Interference cannot be modelled as Additive White Gaussian Noise. 

# Additive White Gaussian Noise
Thermal noise tends to exhibit a Gaussian probabilistic distribution, linking change in signal to probability of such a change. 
$$P(X) = \dfrac{1}{\sqrt{2 \pi} \sigma_x} e^{\left( - \dfrac{(x - \mu_X)^2}{2 \sigma _x ^2} \right)}$$
# Noise Power
The power of thermal noise in a system, in Watts, is given by $N = kTB$, where $k$ is the Boltzmann constant, $T$ is the temperate in Kelvin, and $B$ is the bandwidth in Hertz. $k \approx 1.380649×10^{23} \text{JK}^{-1}$. 
While in theory $T$ and $B$ are variable, there are practical limits to their manipulation. A smaller $T$ requires significant infrastructure to cool the system, and erasure of noise via this coefficient can only be achieved at $0 \text K$, which is practically impossible. Reducing $B$ reduces the data rate, and removal of noise in this manner requires a bandwidth of $0 \text{Hz}$, which prohibits data transfer.
Often noise is converted from $\text{W}$ to be expressed in $\text {dBW}$ or $\text{dBmW}$
Noise power is used most notably in calculating [[Signal to Noise Ratio]]. 

#communications