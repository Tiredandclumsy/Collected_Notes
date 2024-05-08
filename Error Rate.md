Bit or Symbol Error Rate emerged from the probability of an arbitrary bit or symbol being decoded in error. These probabilities are denoted $P_b$ and $P_s$. The limit of the ratio of errors to total bits/symbols transmitted as time approaches infinity is the Bit of Symbol Error Rate (BER/SER).

The error rate is dependent on
- Energy of the signal at the receiver (not transmitter)
- Energy of the noise
- Distribution of noise and interference
- Modulation scheme

Bit Error Rate is commonly a more useful metric. In binary [[modulation]] schemes BER is equal to SER intuitively. However, for M-ary modulation schemes the rates differ based on encoding.
To reduce BER for a given SER, Gray coding can be employed. This allows adjacent symbols to encode bit strings that differ by only 1 bit. Since errors are most likely to change a symbol into an adjacent one (e.g. read an amplitude level as 1 level too high) this reduces the average BER. Gray coding causes $P_b \approx \frac{P_b}{b}$ where $b$ is the number of bits per symbol. This probability of bit error is the theoretical minimum.

Plotting BER against [[Signal to Noise Ratio|SNR]] gives a [[BER vs SNR curve]].


#communications