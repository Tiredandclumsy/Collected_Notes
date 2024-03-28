An op-amp, or operational amplifier, is an integrated circuit used frequently in electronics applications. Theoretically, it is a differential amplifier with a near infinite open-loop gain. 

# Ideal Definition
An op-amp has 2 inputs $V^+$ and $V^-$, and an output $V_{\text{out}}$. $V^+$ is often referred to as the non-inverting input, and $V^-$ the inverting input. $V_{\text{out}}$ is governed by the equation $V_{\text{out}} = A(V^+ - V^-)$ where $A$ is very large, often modelled as infinite. 
A rearrangement of this equation yields the [[virtual short-circuit]].

# Practical Considerations
In practice, an op-amp has a further 2 inputs $V_{S+}$ and $V_{S-}$ which provide power. This means $V_{S-} \le V_{\text{out}} \le V_{S+}$. Further, a small amount of voltage is lost internally when providing power, such that $K \times V_{S-} \le V_{\text{out}} \le K \times V_{S+}$ where $K < 1$ and ranges depending on the op-amp model.

