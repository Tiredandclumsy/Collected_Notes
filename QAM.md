Quadrature Amplitude Modulation (QAM) is a binary [[modulation]] scheme that modulates amplitude and phase. 
The system encodes binary data into $M$ different symbols by encoding each half of the binary data to $\sqrt M$ different amplitude levels of an in-phase and quadrature carrier wave.

If $M = 4$, then [[PSK#QPSK|QPSK]] is formed. Thus QAM can be seen as a generalisation of the principles of orthogonality seen in QPSK.
# Modulation
A QAM modulator begins with branching the signal into two branches via a serial to parallel converter, that alternates sending input bits down 1 of 2 outputs. These two branches are the in-phase and quadrature components. Each branch then contains a binary to M-ary baseband converter, which is fed into a [[Bandpass filtering|bandpass filter]]. Finally, each branch is multiplied by a carrier wave, one of which is $90\degree$ out of phase with the other, and the two branches summed before transmission.
The constellation diagram this generates is an $\sqrt M \times \sqrt M$ grid of points, as the in-phase and quadrature components each get modulated to one of $\sqrt M$ levels, and the sum of these two creates a coordinate system for each possible string of $2^M$ bits.
# Demodulation
To demodulate a QAM signal, the received signal is split into two branches. Each is mixed with a local copy of the carrier, but one copy is out of phase by $90 \degree$. This signal is passed through a low-pass filter to remove the sidebands at twice carrier frequency, then a [[comparitor#Multi-level comparitor|multi-level comparitor]] recovers the M-ary (or specifically, $M^{\frac 1 2}$-ary) baseband signals for in-phase and quadrature components. These signals are passed into M-ary to binary converters, and the result combined by a parallel to serial converter, finally recovering the original binary message.

# Comparison
For a given $n$, the $2^n$-ary [[PSK]] has a better [[Error Rate|BER]] than the $4^2$-ary QAM for a given [[Signal to Noise Ratio|SNR]], however since the QAM system gives twice the data rate for the same bandwidth and thus has a radically better bandwidth efficiency, this issue is minor compared to the benefits of QAM.