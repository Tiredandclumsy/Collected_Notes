Amplitude Shift-Keying (ASK) refers to varying the amplitude of a carrier wave between a number of discrete levels that encode a digital signal, for the purpose of bandpass [[modulation]]. 

# OOK
On-off keying (also known as binary ASK) refers to a binary signal mapping $0 \to 0V$ and $1 \to +V$ being mixed with a carrier wave.
The resulting [[constellation diagram]] has a point at the origin $(0,0)$, and one at $(V, 0)$. 

## Modulation
An intuitive modulator for OOK would be a carrier wave output via a switch, the switch being controlled by the binary signal. However, this creates a square-shaped envelope which has an infinite frequency [[Signal spectra|spectrum]], and so [[bandpass filtering]] must be applied. Since the carrier wave is already such high-frequency, a filter that passes the carrier but attenuates higher frequencies is very difficult to achieve. 
Instead, a bandpass filter can be applied to the binary signal, and the result mixed with the carrier. This has the same effect, but with a significantly simpler practical implementation.

## Demodulation
### Non-coherent
A non-coherent OOK demodulator is as simple as an [[envelope detector]] fed into a [[comparitor]]. The envelope generator reverses the mixing with the carrier signal, and the comparitor reverses the bandpass filtering.

The [[Error Rate|BER]] of non-coherent OOK is given by $$P_\epsilon = \frac 1 2 \operatorname{erfc}\left( \sqrt{\cfrac{E_b}{2N_0}} \right) + \frac 1 2 e^{\left(\cfrac{-E_b}{4N_0}\right)}$$
### Coherent
Mixing the incoming signal with the local copy creates the two [[Demodulation#Coherency|sideband]] copies of the signal - one at baseband and one at twice the carrier frequency. Bandpass filtering then removes the high frequency signal, and a comparitor is used to reverse the original bandpass filtering, recovering the original signal.

The [[Error Rate|BER]] of coherent OOK is given by $$P_\epsilon = \frac 1 2 \operatorname{erfc}\left( \sqrt{\cfrac{E_b}{2N_0}} \right)$$