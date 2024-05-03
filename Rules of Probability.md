1. $P(S) = 1$:  The certain event has probability $1$
2. $P(A) \ge 0$ for any event $A$: All probabilities are non-negative
3. $A \cap B = \emptyset \implies P(A \cup B) = P(A) + P(B)$: The Addition Rule
4. $P(S - A) = P(\bar A) = 1 - P(A)$: The Complement Rule
5. $P(\emptyset)=0$: Probability of the empty set is $0$
6. $A \subseteq B \implies P(A) \le P(B)$: Monotonicity
7. $P(A \cup B) = P(A) + P(B) - P(A \cap B)$

All of these rules can be derived from 3 axioms of probability, known as the Kolmogorov Axioms:
	Let $(S, F, P)$ be a measure space with $P(E)$ being the probability of event $E$ and $P(S) = 1$
1. $\forall E \in F, P(E) \in \mathbb R, P(E) \ge 0$
2. $P(S) = 1$
3. $\forall E = \{E_1, E_2, \dots, E_n\} \text{ s.t. } \forall a,b \in [1,n] E_a \cup E_b = \emptyset, P(\bigcup _{i=1} ^n E_i) = \sum _{i=1} ^n P(E_i)$

# Definitions
The sample space $S$ is the set of all possible outcomes. An outcome is a disjoint and indivisible value representing a possible state the system could occupy. A set of outcomes in $S$ is an event $E \subseteq S$

#discrete-maths