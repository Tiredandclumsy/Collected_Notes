A communication system is an abstract framework to categorise and reason about different implementations of electronic communication. Any communication system is comprised of 5 sections:
- Message origin - the party that creates the message to be sent. This stage gives an input message
- Transmitter - the stage that encodes the input message into a form capable of being sent along the channel. This stage gives a transmitted signal
- Channel - the stage that carries the message across some distance. This stage gives a received signal
- Receiver - the stage that decodes the received signal into the original form of the input message. This stage gives an output message
- Message destination - the stage that receives and uses the message from the message source.

Generally, the role of a communications engineer is to design a transmitter and receiver pair to transmit a signal across a given channel, working to given constraints.
The transmitter can code, filter, and amplify the signal to be sent down the channel. For passband systems (where the channel permits a finite frequency range not including 0Hz) the transmitter also performs carrier modulation - also known as up-conversion.
The receiver then recovers the original message, usually in a process similar to the inverse of the transmitter (filtering (equalising), decoding). In passband systems, the receiver performs carrier demodulation, also known as down-conversion. Usually, the receiver must also amplify the signal, despite amplification at the transmitter, due to losses in the channel.

Channels usually contribute [[Noise and Interference|noise]] to the signal, cause loss to its power, and only propagate a certain range of frequencies. 

# Baseband / bandpass
If the range of frequencies permitted in the channel ranges from D.C. upwards, the channel is 'baseband', and otherwise it is 'passband' or 'bandpass'.



#communications 