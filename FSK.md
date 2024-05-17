Frequency Shift-Keying (FSK) refers to varying the frequency of a carrier wave between a number of discrete levels that encode a digital signal, for the purpose of bandpass [[modulation]]. 
Mathematically, this means $s(t) = A \cos(\omega(t)t + \theta)$, where $\omega(t)$ is some function of the angular frequency over time that encodes information.

# Binary FSK
Binary FSK refers to using two different frequencies to map to the $0$s and $1$s of a binary signal.
## Modulation
A naïve implementation of a binary FSK modulator would be to switch between two different carrier signals based on the binary message. This is in theory similar to two inverted [[ASK#OOK|OOK]] signals mixed together. However, the sharp high-frequency transitions between frequencies would lead to an infinite bandwidth, and so a different approach must be used.

This practical approach is the use of a voltage-controlled oscillator, or VCO - a component which generates an output signal with a frequency dependent on the input voltage. 
If the binary signal is [[Bandpass filtering|bandpass filtered]] and then passed into a VCO, continuous phase FSK (CPFSK) is achieved.

The [[Signal spectra|spectrum]] of FSK modulation is formed by a superposition of two ASK signals of different frequencies. These two signals peak at their respective frequencies, and have lobes that trail off either side. These tails of high and low frequencies overlap significantly between the two peaks, and so the bandwidth of FSK is influenced heavily by the distance between the peaks.
### MSK
If this distance is a multiple of half the symbol rate then the two spectra are orthogonal, and the peak of each lobe will fall between two lobes of the other spectrum. This leads to minimal interference.
When this property is used, the scheme is referred to as Minimum Shift-Keying (MSK).
### GFSK/GMSK
A Gaussian filter is often used in FSK to minimise lobes either side of the main frequency peaks, since a Gaussian filter has an aggressive attenuation curve. FSK that uses this filter is called Gaussian Frequency Shift-Keying (GFSK), and if it also fulfils the above it is Gaussian Minimum Shift-Keying (GMSK). 
GFSK is used in Bluetooth.

## Demodulation
### Non-coherent
A non-coherent demodulator for BFSK takes the input and splits it into two paths. Each path contains a bandpass filter centred on a frequency, then an [[envelope detector]], then another bandpass filter #incomplete why the second filter?. Then both of these paths are combined by a [[comparitor#Multi-input comparitor|binary comparitor]]. Since one path has the filter centred on the frequency corresponding to a transmitted $0$ bit, and the other a $1$ bit, the theoretical result is a recovered signal. 

The [[Error Rate|BER]] of non-coherent BFSK demodulation is given by $$\frac 1 2 e^{\left(\cfrac{-E_b}{2N_0}\right)}$$
### Coherent
A coherent FSK demodulator requires two local copies - one of each frequency of carrier signal. The signal is split into branches as before, and each branch is mixed with a different local signal, then passed through a low-pass filter to remove the [[Demodulation#Coherency|sideband]] frequency at twice bandpass. Then, the branches are combined with a [[comparitor#Multi-input comparitor|binary comparitor]]. 

The [[Error Rate|BER]] of coherent BFSK demodulation is given by $$\frac 1 2 \operatorname{erfc} \left(\cfrac{-E_b}{2N_0}\right)^\frac 1 2 $$
This is only a $\sim 1 \text{dB}$ improvement over non-coherent demodulation, and so non-coherent FSK demodulators are very common.

## Comparison
A constant envelope means that this modulation scheme is insensitive to amplitude distortion - a common distortion type in communication systems.

FSK tends to achieve slightly worse bandwidth efficiency compared to [[ASK]] and [[PSK]], and has a worse BER than [[PSK]], but a better BER that [[ASK]]. 

# M-ary FSK
M-ary FSK maps every $b$ bits to tone of $2^b$ different frequencies. 
## Modulation
Modulating M-ary FSK is near identical to modulating binary FSK. However, first the binary signal is converted to an M-ary signal, before this result is [[Bandpass filtering|bandpass filtered]], and used to drive an VCO. 
Orthogonality (a property that prevents [[inter-symbol interference]]) can be gained when the frequencies used are multiples of half the [[Rates of communication#Symbol rate|symbol rate]]. Thus the signal can be expressed $$a_m(t) = \cos \left( \left(2 \pi f_c + \frac{2 \pi m f_s}2 \right) t \right) = \cos((2 \pi f_c  + \pi m f_s)t)$$where $m = \{1,2,\dots,M\}$. 
## Demodulation
### Non-coherent
The coherent M-ary FSK demodulator branches the recieved signal into M filters, each centred on one discrete frequency. These are then passed into a [[comparitor#Multi-pass comparitor|multi-pass comparitor]]. The output of this comparitor is finally converted from a M-ary bandpass signal back into a binary signal.
Non-coherent M-ary FSK demodulation will not be discussed further.
## Coherent
Coherent M-ary demodulation branches the signal as before, and multiplies each branch with a local copy of a different carrier signal, where each has the frequency of a symbol in the modulation scheme. These multiplied signals are then filters to remove [[Modulation#Carrier modulation|sidebands]] and passed into a multi-pass comparitor. The output of this comparitor has then recovered the original M-ary signal, which is converted back into binary.
The [[Signal to Noise Ratio|Eb/N0]] requirement for a given [[Error Rate|BER]] 