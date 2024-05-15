# Symbol rate
The symbol rate of a [[Communication system]] refers to the rate of change of symbol states on a channel. Put simply, it is the number of symbols transmitted per unit time.
Symbol rate is usually measured in symbols per second, also called Baud, and is denoted $f_s$. 

The reciprocal of the symbol rate is the symbol period $T_s$

The symbol rate is limited by the [[bandwidth]]. In [[Communication system#Baseband / bandpass|baseband]] systems $f_s = 2B$ meaning the maximum symbol rate for a gives system is twice the bandwidth of the channel.
In bandpass systems, due to the doubling of bandwidth as a result of [[Signal spectra#Simple sinusoidal modulation|sinusoidal modulation]], the factor of two cancels and disappears, meaning the maximum symbol rate is equal to the bandwidth, and the minimum bandwidth is equal to the symbol rate.
These are theoretical limits, and are very rarely achieved in practice.
# Data rate
The data rate (or information transfer rate) is defined as the number of bits transmitted per unit time.
It is usually measured in bits per second, and is denoted $f_d$.

Data rate is given from symbol rate: $f_d = f_s \times \log_2 M$ where $M$ is the number of symbols used in the communications system.
Therefore if two symbols are used ([[Modulation#Binary signalling|binary]] systems), symbol and bit rates are intuitively equal, but in [[Modulation#M-ary signalling|M-ary]] systems one symbol transmits more than one bit.

It should be noted that, according to the equation, there is no maximum data rate achievable for a given channel. Increasing $M$ in the system always leads to a higher data rate. However, a larger $M$ makes the system more sensitive to [[noise and interference]]. 