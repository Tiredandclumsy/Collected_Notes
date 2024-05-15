Demodulation is the reverse process to [[modulation]] - where a message is recovered after being encoded by one or more properties of a wave and passed down a channel in a [[communication system]]. 

Carrier demodulation refers to any technique used to recover a message that has been [[Modulation#Carrier modulation|carrier modulated]] to be transmitted in a [[Communication system#Baseband / bandpass|bandpass]] system.
# Coherency
Carrier demodulation techniques can be categorised as either coherent or non-coherent. 
A coherent demodulation technique involves use of a local copy of the carrier wave, and as such requires prior knowledge of the carrier wave's unmodulated frequency. A non-coherent demodulation technique requires no such local copy, and works regardless of the frequency of the carrier wave.
A non-coherent system is usually cheaper and less complex, but also suffers from reduced performance.

The simplest non-coherent demodulator is an [[envelope detector]]. This functions intuitively. However, a simple coherent demodulator is more complicated.

The coherent demodulator consists of the local copy and input passing through a mixer, then a [[bandpass filtering|low-pass filter]].  The signal after the mixer is the product of the incoming signal and local copy: $$A(t) \cos(\omega_c t) \cos(\omega_ct + \theta) = \frac 1 2 A(t) \cos(\theta) + \frac 1 2 A(t) \cos(2 \omega_c t + \theta)$$where $A(t)$ is the original message. Therefore, the result of the mixer is a copy of the baseband message multiplied by a constant $\cos(\theta)$ term, and a copy of the bandpass signal at twice the carrier frequency. The low-pass filter removes this second term, leaving only the baseband message.
The $\cos(\theta)$ term raises some problems. Measures must be taken to ensure that the local copy of the carrier wave is in-phase with the received signal, or else $|\theta| >> 0$, and so $|\cos \theta| << 1$, and the signal will be heavily attenuated by demodulation. 
One technique to do this is a phase-lock loop, which is a circuit to match the phase of the local oscillator to the incoming signal.
If the local copy is a different frequency to the true carrier signal, then $\theta$ will be a function of time, and this term cannot be removed. 