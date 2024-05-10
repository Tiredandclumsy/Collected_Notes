A function $f : A \to B$ is a [[relation]] on $A \times B$ that fulfils 2 criteria:
- $\forall a \in A, \exists b \in B \text{ s.t. } (a,b) \in f$
- $\forall y \ne z \in B, (x,y) \in f \rightarrow (x,z) \notin f$

# Surjections and Injections
The domain $\text{dom}(f)$ of a function $f: A \to B$ is $A$
The codomain of a function $f : A \to B$ is $B$
The range $\text{ran}(f)$ of a function $f : A \to B$ is defined as $\{f(x) : x \in A\}$

A function $f : A \to B$ is surjective, or a surjection, if $\text{ran}(f) = B$, and an injective, or an injection, if $\forall x,y \in A, f(x) = f(y) \rightarrow x = y$

If a function is an injection and a  surjection, it is a [[bijection]].

# Numerical functions
Numerical functions (that is, $\{f \text{ s.t } f :: \mathbb R \to \mathbb R\}$)
have certain intrinsic properties.
## Odd and even functions
Numerical functions can be odd or even:
- $\forall x \in \mathbb R: f(x) = f(-x) \implies$ the function is even
- $\forall x \in \mathbb R: f(x) = -f(-x) \implies$ the function is odd

Every non-constant function $f$ can be decomposed into a sum of an odd and even function: $f(x) = h(x) + g(x)$ where $h(x) = \frac 1 2 \left[ f(x) + f(-x) \right], g(x) = \frac 1 2 \left[ f(x) - f(-x) \right]$

#discrete-maths