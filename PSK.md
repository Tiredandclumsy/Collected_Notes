Phase Shift-Keying (PSK) refers to varying the phase of a carrier wave between a number of discrete levels that encode a digital signal, for the purpose of bandpass [[modulation]]. 
This encoding can be done either by each symbol itself, or the difference between consecutive symbols.

# BPSK
Binary PSK refers to the message being encoded by two antipodal phase values - $0 \degree$ and $180 \degree$, or $0$ and $\pi$ radians. The constellation for BPSK is therefore two points - one at $(+A, 0)$ and one at $(-A, 0)$.
## Modulation
A naïve modulator takes the carrier signal, branches it, sens one branch through an inverter, then switches between the rbanches as controlled by the signal. However, this switching requires [[bandpass filtering]] at the carrier frequency, which is practically difficult.
Instead, a linear multiplier can be used on a bipolar version of the signal. If the binary input ranges from $-V$ to $+V$, then it can be pulse shaped as combined with the carrier by a multiplier. 
This is essentially [[ASK#OOK|OOK]], but modulating between $-V$ and $+V$ instead of $0$ and $+V$. 
## Demodulation
There is no non-coherent demodulation of PSK. Instead, the system simply multiplies the incoming signal by a local copy of the carrier, and [[Bandpass filtering|filters]] the result to remove the [[Demodulation#Coherency|sideband]] at twice the carrier frequency. Then a comparitor is used to recover a binary signal.

The [[Error Rate|BER]] of coherent PSK is given by $$P_s = \frac 1 2 \operatorname{erfc}\left( \frac{E_b}{N_0} \right)^{\frac 1 2}$$This is similar to [[ASK#Demodulation#Coherent|coherent ASK]], but has no coefficient of $2$ in the denominator, and so outperforms ASK by $3\text{dB}$. This benefit is similar to the benefit of [[Modulation#Binary signalling|bi-polar vs uni-polar modulation]] at baseband.

# Differential BPSK
There is a possibility with BPSK demodulation that the local carrier will be in anti-phase to the carrier of the transmitter. This only effects PSK, as PSK is the only [[modulation]] scheme that exploits phase. 
This antiphase will cause any bits received to be flipped, such that $0$ is received as $1$ and vice versa. One way to deal with this problem is with a [[training sequence]], but another is differential encoding of PSK.

## Modulation
Modulating a differential PSK signal consists of first using a differential encoder, then passing the binary string to a PSK modulator.
The encoder is an XOR gate, with one input being the binary information, and the other a 1-clock cycle delayed branch of its output. Note here that the binary encoding is bi-polar.
After this stage, the signal is passed through a [[Bandpass filtering|bandpass filter]], then multiplied by the carrier wave.
## Demodulation
### DEPSK
Differentially Encoded PSK is the name given to Differential PSK demodulated by separate detector and demodulator stages.
The demodulator stage multiplies the received signal with a local copy of the carrier, and passes the result through a [[Bandpass filtering|bandpass filter]], then a comparitor to generate a differential binary signal. This is then branched, one branch delayed by 1 clock cycle, and both branches combined by an XOR gate to recover the original signal.
### DPSK
'True' differential PSK is demodulated by combining detection and demodulation stages. This involves taking the received signal, branching it and delaying one branch by 1 clock cycle, then multiplying the two branches together. This has the effect of both bandpass demodulation and differential decoding, as if the two sources are in phase then the result will be a high envelope, and if they are out of phase it will be a low envelope. A bandpass filter then removes the [[Demodulation#Coherency|sideband]] at twice carrier frequency, and a comparitor reverses the original bandpass filtering.

## BER
The [[Error Rate|BER]] of either demodulation system is the same, as they are functionally identical. It is given by $$P_s = \frac 1 2 \operatorname{erfc}\left( \frac{-E_b}{N_0} \right)$$and as such is slightly worse than coherent PSK.