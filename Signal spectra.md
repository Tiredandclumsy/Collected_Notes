A [[modulation]] scheme generates a [[signal]] intended to exist in a certain frequency range. The plot of frequencies, similar to a [[Fourier transform|Fourier series]] representation, shows the actual frequency spread of the signal.

# Simple sinusoidal modulation
The simplest example is [[Modulation#Carrier modulation|amplitude modulation]] between two sinusoids. This is done by passing two sine waves into a mixer, and can be expressed mathematically as $\cos(\omega_c t) \cos(\omega _m t)$, where $\omega_c$ is the angular frequency of the carrier wave, and $\omega_m$ the angular frequency of the 'message wave'. $$\cos(\omega_c t) \cos(\omega _m t) = \frac 1 2 \cos((\omega_c - \omega_m)t) + \frac 1 2 \cos((\omega_c + \omega_m)t)$$From this identity if can be seen that the signal spectrum of simple sinusoidal amplitude modulation consists of 2 0.5 height peaks, at $\omega_c - \omega_m$ and $\omega_c + \omega_m$. These frequencies are referred to as 'sidebands'. 

A square wave has a spectrum nominally extending to infinity, as it is made up of an infinite number of base sinusoids. 
When this is modulated with a carrier wave the individual sinuosids are modulated as above and combined due to superposition. With each being copied and placed at the difference and sum of its frequency compared to the carrier, the result is a spectrum that is moved to then reflected in the carrier frequency. 

Therefore, sinusoidal carrier modulation can be shown to double the bandwidth of any baseband signal. 

#communications