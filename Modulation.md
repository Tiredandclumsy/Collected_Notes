Modulation refers to varying one or more features of a carrier wave to encode information. 
# Binary signalling
The most simple modulation involves a DC carrier modulated by a binary signal. This can be done in two ways:
- Uni-polar (or on-off): $+V$ encodes a $1$ bit and $0V$ encodes a $0$ bit
- Bi-polar (or polar): $+V$ encodes a $1$ bit and $-V$ encodes a $0$ bit

The [[Error Rate|error rates]] for these two schemes are $P_s = \cfrac 1 2 \operatorname{erfc}\left( \sqrt{\cfrac{E_s}{2N_0}} \right)$ for uni-polar and $P_s  =\cfrac 1 2 \operatorname{erfc} \left( \sqrt{\cfrac{E_s}{N_0}} \right)$ for bi-polar, where $E_s$ is the [[Noise and Interference#Signal power|energy per symbol]] and $N_0$ is the [[Noise and Interference#Noise Power|noise spectral density]].
From this it can be seen that bi-polar schemes offer a lower error rate, as the complimentary error function $\operatorname{erfc}$ is a negative function.
# Carrier modulation
Carrier modulation is any modulation used for the purposes of communication in [[Communication system#Baseband / bandpass|bandpass]] systems, meaning the original message is encoded in a signal that can pass through the channel when the original message cannot. 
This modulation almost always involves modulating a sine wave $A\sin(\omega t + \theta)$ (called the carrier wave), and so there are 3 different properties that can be modulated: amplitude $A$, frequency $f = \cfrac \omega {2\pi}$, and phase $\theta$.
If these properties are modulated by an analogue signal, then amplitude/frequency/phase modulation results. Phase modulation is rare, as it is very similar but less useful than frequency modulation.

However, due to the rise in digital electronics, digital modulation schemes are more popular, and also permit more advanced communication techniques. Digital schemes simply permit the property/properties to vary between discrete levels that are interpreted as strings of bit values. 
Some example digital modulation schemes are:
- [[ASK]]: Modulates amplitude
- [[FSK]]: Modulates frequency
- [[PSK]]: Modulates phase
- [[QAM]]: Modulates amplitude and phase
# M-ary signalling
M-ary signalling refers to any [[modulation]] scheme where the number of symbols used $M$ is greater than 2. Usually $M$ is a power of two, as the symbols can then be easily encoded by and decoded into binary. Thus $M=2^b$ where $b$ is the number of bits per symbol.

Adapting the binary signalling scheme to M-ary leads to a greater bitrate but increases error rate.
The error rate is given by $P_s  =\cfrac {M-1} M \operatorname{erfc} \left(\cfrac 3 {M^2 - 1} \sqrt{\cfrac{E_s}{N_0}} \right)$ assuming a bi-polar scheme (modulating with $M$ discrete voltage levels between $+V$ and $-V$). This shows an increase in bit error rate for a larger alphabet, and also gives the binary bi-polar error rate for $M=2$.

The advantages of M-ary signalling are higher information transfer rates for a given [[Rates of communication#Symbol rate|symbol rate]] and [[bandwidth]], or a reduced bandwidth requirement for a given data rate. Both of these advantages have the effect of improving [[Bandwidth#Bandwidth efficiency|bandwidth efficiency]]. 

#communications 