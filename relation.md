A relation is a subset of the Cartesian product of a set, $R \subseteq A \times A$, or of two sets, $A \times B$. As such it consists of ordered pairs of objects. If $(x,y) \in R$ then it is said that $R$ holds for $x,y$

For example, $<$ is an [[relation#Order relation|order relation]] on $\mathbb N$, equal to $\{(x,y) : x,y \in \mathbb N , x < y\}$

# Notation
A relation $R$ is commonly expressed where $R(x,y)$ means $(x,y) \in R$.
A relation $R \subseteq A \times A$ is referred to as a relation on $A$
A relation $R \subseteq A \times B$ is referred to as a relation on $A \times B$

# Equivalence relation
An equivalence relation represents a metric by which elements of a set may be evaluated as equivalent or not. For a relation $R$ on $A$ to be an equivalence relation it must fulfil 3 criteria:
- Reflexivity: $\forall x \in A, R(x,x)$
- Transitivity: $\forall x,y,z \in A, R(x,y) \land R(y,z) \rightarrow R(x,z)$
- Symmetry: $\forall x,y \in A, R(x,y) \leftrightarrow R(y,x)$

# Order relation
An order relation represents a metric by which elements of a set may be placed in order compared to one another. For a relation $R$ on $A$ to be an order relation it must fulfil 3 criteria:
- Reflexivity: $\forall x \in A, R(x,x)$
- Transitivity: $\forall x,y,z \in A, R(x,y) \land R(y,z) \rightarrow R(x,z)$
- Anti-symmetry: $\forall x,y \in A, R(x,y) \land R(y,x) \rightarrow x = y$
An ordering $R$ on $A$ is complete if $\forall x,y \in A, R(x,y) \lor R(y,x)$, and if not it is partial. Most ordering are partial orderings.

# Hasse Diagrams
A Hasse Diagram is a visualisation of a relation where every element in the set is represented, and $R(x,y)$ holding is represented as a line from $x$ to $y$. However, no reflexive relations are shown, and neither are any relations that can be inferred from transitivity. The direction of each relation between elements is upwards, and no arrowheads or other means of expressing direction are used.

# Maximal and minimal elements
A minimal element $b \in A$ of $(A, R)$ is such that $\forall x \in A, R(b,x) \to x = b$
A maximal element $b \in A$ of $(A, R)$ is such that $\forall x \in A, R(x,b) \to x = b$

An upper bound $u$ of ($A, R$) is such that $\forall x \in A, R(u, x)$
A least upper bound of $A$ $\text{sup} A$ is such that for all upper bounds $u$ in $A$, $\text{sup} A \le u$
A lower bound $u$ of ($A, R$) is such that $\forall x \in A, R(x, u)$
A greatest lower bound of $A$ $\text{inf} A$ is such that for all lower bounds $l$ in $A$, $\text{inf} A \ge l$

It can be noted that bounds must be related to all elements in the set, but maximal and minimal elements do not.

