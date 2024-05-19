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

# QPSK
A cosine and a sine wave of the same phase and frequency are orthogonal. Therefore, two BPSK signals, one modulated on a cosine wave and the other on a sine wave, will not cause any interference between each other. This 4-ary PSK modulation is called quadrature PSK or QPSK.
## Modulation
The modulator for QPSK first passes the binary signal through a 2-bit serial to parallel converter. This system outputs two branches, sending consecutive bits down alternating branches. These branches then undergo standard BPSK modulation - a [[Bandpass filtering|bandpass filter]] and a mixer, but one mixer is $90\degree$ out of phase to the other. The two branches are summed, and the result transmitted.
The constellation diagram for QPSK has 4 points, one in each quadrant, all of equal magnitude and lying on $45\degree$ diagonals. This is because the 4 possible bits lead to either a $1$ or $-1$ component of sine or cosine, leading to the points $(1,1),(1,-1),(-1,1)(-1,-1)$.
## Demodulation
To demodulate QPSK, the received signal is split into 2 branches. Each branch is multiplied by the local copy of the carrier, but one branch copy is first delayed so it is $90 \degree$ out of phase. Then demodulation continues as per BPSK with a low-pass filter and a comparitor, before both branches are combined in a parallel to serial converter, that takes each simultaneous pair of bits and outputs them one after another on a single channel.

The maths of this demodulation is as follows: suppose some pair of bits $I,Q \in \{0,1\}$ is transmitted, with $I$ being in-phase (cosine) and $Q$ being quadrature (sine).  The transmitted signal is therefore $IA\cos(\omega_c t) + QA\sin(\omega_ct)$.
In-phase, the demodulation first gives $$IA\cos^2(\omega_c t) + QA\sin(\omega_c t)\cos(\omega_ct)$$$$IA\left(\frac 1 2 \cos(2 \omega_c t) + \frac 1 2 \right) + QA \left(\frac 1 2 sin(2 \omega_c)\right)$$by the double angle formulae
$$\frac {IA} 2 + \frac {IA} 2 \cos(2 \omega_c t) + \frac {QA} 2 \sin(2 \omega_ct)$$When this is passed through the low-pass filter, only $\frac {IA} 2$ remains - a scalar multiple of the in-phase signal.
For quadrature the maths is similar: $$IA\cos(\omega_c t) \sin(\omega_c t) + QA\sin^2(\omega_ct)$$$$IA \left(\frac 1 2 \sin(\omega_ct)\right) + QA \left( \frac 1 2 - \frac 1 2 \cos(2 \omega_c t) \right)$$by the double angle formulae$$\frac{QA} 2 - \frac {QA} 2 \cos(2 \omega_c t) + \frac{IA}2 \sin(\omega_c t)$$When this result is filters as before, only $\frac{QA}2$ remains, which is a scalar multiple of the quadrature signal.

The [[Error Rate|BER]] is the same as BPSK and polar baseband:$$P_s = \frac 1 2 \operatorname{erfc} \left( \sqrt{\frac{E_b}{N_0}} \right)$$As such, QPSK allows a communications engineer to double the [[Rates of communication#Data rate|data rate]] of the PSK system without sacrificing BER degradation.

# M-ary PSK
M-ary PSk is rare for $M>4$, and so the modulation and demodulation will not be discussed here.
The constellation diagram M-ary PSK generates is $M$ points spaced evenly on the edge of a unit circle. 
Beyond QPSK the BER will suffer from the increase in data rate. The BER is given by $$P_s=\operatorname{erfc}\left( \frac{E_s}{N_0}\sin \left(\frac \pi M \right) \right)$$