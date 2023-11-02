# Definition
A group $(G, \bullet)$ is defined as a [[set]] $G$ and a [[binary operation]] $\bullet$ that satsfies 4 properties:
1. Closure - $\bullet$ is closed, meaning $x,y \in G \Rightarrow x \bullet y \in G$
2. Associativity - $\bullet$ is associative, meaning $\forall x,y,z \in G , (x \bullet y) \bullet z = x \bullet ( y \bullet z)$
3. Identity - $\exists e \in G \text{ s.t. } \forall x \in G, e \bullet x = x \bullet e = x$
4. Inverse - $\forall x \in G, \exists x^{-1} \in G \text{ s.t. } x \bullet x^{-1} = x^{-1} \bullet x = e$
The group $(G, \bullet)$ is usually referred to as "$G$ under $\bullet$"

# Subsets and supersets of groups
A group $(G, \bullet)$ such that $\bullet$ is [[commutative]] is an Abelian Group. The set of all abelian groups therefore makes up a subset of the set of all groups.

If a set under a binary operation fulfils closure, associativity, and identity it is a monoid. Monoids may or may not fulfil inverse. 
If a set under a binary operation fulfils closure and associativity it is a semi-group.
Semi-groups may or may not fulfil inverse and identity.
The set of all monoids makes up a superset of the set of all groups, and the set of all semi-groups makes up a superset of the set of all monoids.

# Proofs of characteristics
All groups have Uniqueness of Inverse, meaning $\forall x, x^{-1} \in G \text{ s.t. } x \bullet x^{-1} = e, \nexists x^{-1}_2 \text{ s.t. } x \bullet x^{-1}_2 = e$ 
The proof is as follows:
	Suppose $\exists w, z \in G \text{ s.t. } \forall x \in G, w \bullet x = e, z \bullet x = e, w \ne x$
	Henceforth $x \bullet z = e$ (1) and $w \bullet x = e$ (2)
	$w = w \bullet e$ by identity axiom
	$w = w \bullet ( x \bullet z )$ by (1)
	$w = (w \bullet x) \bullet z$ by associativity
	$w = e \bullet z$ by (2)
	$w = z$ by inverse axiom
	$w = z$
	This is a contradiction

All monoids have Uniqueness of Identity, meaning $\exists e \in G \text{ s.t. } \forall x \in G \ e \bullet x = x, \nexists e' \text{ s.t. } \forall x \in G \ e' \bullet x = x \land e \ne e'$
The proof is as follows:
	Suppose $\exists e_1, e_2 \in G \text{ s.t. } \forall x \in G, x \bullet e_1 = e_1 \bullet x = x, x \bullet e_2 = e_2 \bullet x = x, e_1 \ne e_2$
	Henceforth $x \bullet e_1 = e_1 \bullet x = x$ (1) and $x \bullet e_2 = e_2 \bullet x = x$ (2)
	$e_1 \bullet e_2 = e_2$ by (2)
	$e_1 \bullet e_2 = e_1$ by (1)
	$e_1 = e_2$
	This is a contradiction

# Common groups
Certain common groups have standard names.
One such commonly used group is the set of all non-singular $n \times n$ matrices under matrix multiplication, known as the general linear group or $GL(n)$
