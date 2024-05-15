The Shannon-Hartley theorem relates the channel capacity of a [[communication system]] to the [[Signal to Noise Ratio|SNR]], assuming all the noise is in the form of [[Noise and Interference#Additive White Gaussian Noise|AWGN]]. $$C = B \log_2 \left(1+ \frac S N \right)$$where $C$ is the channel capacity (the largest possible [[Rates of communication#Data rate|data rate]]), $B$ is the [[bandwidth]], and $\cfrac S N$ is the SNR of the system.

It is important to note that while AWGN is never the only form of noise and interference, it is very commonly the dominant form.

# Other forms
The equation is universal, and can be rearranged into multiple useful forms:
- $C = B \log_{2}\left(1 + \cfrac{S}{N}\right)$
- $\cfrac C B = \log_{2} \left(1 + \cfrac S N\right)$
- $C = B \log_{2} \left(1 + \cfrac{E_{b}C}{N_{0}B}\right)$
- $\cfrac C B = \log_{2} \left(1 + \cfrac{E_{b}C}{N_{0}B} \right)$
- $\cfrac C B = \log_{2} \left(1 + \cfrac{\frac{E_{b}}{N_{0}}}{\frac{C}{B}}\right)$

# Shannon curve
The Shannon-Hartley equation can be plotted in two ways.

The plot of $\log_{10}\left( \cfrac{E_b}{N_0} \right)$ against $\log_2\left( \cfrac C B \right)$ (SNR per bit in decibels against a log plot of maximum bandwidth efficiency) gives an increasing curve through the origin. Any [[communication system]] plotted on this graph has x-axis of $\log_2\left( \cfrac {f_b}B \right)$, as this represents the practical bandwidth efficiency. This curve represents that boundary between error-prone and error-free systems as on the right or left of the curve respectively. Here error free means $f_d < C$.
The further right a system is on the plot, the more bandwidth efficient it is, and the further left it is the more power efficient. 

If the axis are flipped such that the curve is $\log_2\left( \cfrac C B \right)$ against $\log_{10}\left( \cfrac{E_b}{N_0} \right)$, then a clear asymptote can be seen as the curve approaches 0 bandwidth efficiency. This point is at $-1.6 \text{dB}$ of $\cfrac {E_b}{N_0}$, meaning any system lover than this SNR cannot achieve error-free communication.

