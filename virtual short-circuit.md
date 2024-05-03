# Definition
The virtual short-circuit is an assumption aiding the analysis of networks containing [[op-amp]]s. It states that the voltages at the two inputs of an op-amp are equal. 

# Derivation
$$A(V^+ - V^-) = V_{\text{out}}$$$V^+ - V^-  =\frac{V_{\text{out}}}{A} \simeq 0$$$$V^+ \simeq V^-$$
# Usage
This approximation is not useful when the op-amp does not have a feedback path (specifically negative feedback), since the equation $A(V^+ - V^-) = V_{\text{out}}$ would yield $A \times 0 = V_{\text{out}} = 0$
However, the approximation is useful when finding the gain of [[inverting amplifier]]s and [[non-inverting amplifier]]s.

The virtual short-circuit implies:
- The current flow between inputs is negligible
- The output of an op-amp will settle at the value that minimised the difference between inputs

#linear-circuits