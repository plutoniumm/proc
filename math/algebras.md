# Algebras and Topologies

## Defns
- **Homeomorphism**: If you can mould one space into another without tearing or gluing, via dough.

## Measure
A measure is anything that assigns a non-negative real number to the subsets of some set $X$.

Examples:
- **counting measure**: $\mu(A) = |A|$, number of elements in $A$
- **Lebesgue measure**: A translation-invariant measure on $\mathbb{R}^n \because \mu([0,1]) = 1$. For $n=1,2,3$ this coincides with the length, area, and volume of the set. \
$\lambda^*(E) = \inf\{\sum_{i=1}^{\infty} \text{vol}(Q_i) : E \subset \bigcup_{i=1}^{\infty} Q_i\}$, basically the smallest of all possible sums of volumes of boxes that cover $E$.
- **Hausdorff measure**: A generalization of Lebesgue measure that can be used to measure the "size" of fractals. \
For some metric space $(X, \rho)$ on $X$ with measure $\rho$, let $d$ be a diameter such that $d(E) = \sup\{\rho(x,y) : x,y \in E \ne \emptyset\}$ i.e the longest distance b/w any two points in $E$. Then for some subset $S \subset X$, and $\delta >0$, \
$\mathcal{H}^d_{\delta}(S) = \inf\{\sum_{i=1}^{\infty} \text{diam}(U_i)^d : S \subset \bigcup_{i=1}^{\infty} U_i, \text{diam}(U_i) < \delta\}$  i.e the smallest sum of diameters of sets that cover $S$ and have diameter less than $\delta$.

### Outer measure
Let us define a $\sigma$-additive set function as $\mu$ that maps a union of two disjoint sets to numbers i.e. $\mu(A \cup B) = \mu(A) + \mu(B)$ for $A \cap B = \emptyset$, or more generally $\mu(\bigcup_{i=1}^{\infty} A_i) = \sum_{i=1}^{\infty} \mu(A_i)$ for $A_i \cap A_j = \emptyset$ for $i \ne j$.

In order to allow for $\sigma$-additivity, we need to define an outer measure $\mu^*$ that is defined on all subsets of $X$ and satisfies:
- $\mu^*(\emptyset) = 0$
- Countable additivity: for arbitrary sets $A, B_1, B_2, \ldots \in X$ \
if $A \subseteq \bigcup_{i=1}^{\infty} B_i$ then $\mu^*(A) \le \sum_{i=1}^{\infty} \mu^*(B_i)$


## Algebra over $X$
An algebra over a set, moere commonly called a field of sets, is structure of a pair $(X, \mathcal{F})$ where $\mathcal{F}$ is a collection of subsets of $X$ that:

- contains the empty set
- closed under complements
- Any one or more of the following is true
  - closed under binary union i.e $A, B \in \mathcal{F} \implies A \cup B \in \mathcal{F}$
  - closed under binary intersection i.e $A, B \in \mathcal{F} \implies A \cap B \in \mathcal{F}$
  - closed under finite unions
  - closed under finite intersections

An algebra a $\sigma$-algebra if it is closed under countable unions and intersections. Countable may be finite or infinite.


## $\sigma$-algebra
A $\sigma$-algebra is a collection of subsets of $X$ that:
- contains the empty set
- closed under complements
- closed under *countable* unions

Or more formally
Let $\Sigma \subseteq P(X)=2^X$ be a of subset of $X$. Then $\Sigma$ is a $\sigma$-algebra if:
- $X \in \Sigma$
- $\Sigma$ is closed under complements: $A \in \Sigma \implies X \setminus A \in \Sigma$
- $\Sigma$ is closed under countable unions: $A_1, A_2, \ldots \in \Sigma \implies \bigcup_{i=1}^{\infty} A_i \in \Sigma$

Consequently from De-Morgan's laws, $\Sigma$ is also closed under countable intersections.

- Elements of a $\sigma$-algebra are called measurable sets
- $\{X, \emptyset\}$ is the smallest $\sigma$-algebra on $X$

## Limit Point
A limit point $x$ is a point in $S$ such that it can be approximated by points in $S$ that are not equal to $x$. Formally, $x$ is a limit point of $S$ if for every $\epsilon > 0$, there exists a point $y \in S$ such that $0 < |x-y| < \epsilon$

It is not necessary that $x$ is in $S$. This concept of convergence of points is similar to that used in sequences. If no such neighbourhood exits, then $x$ is called an isolated point.

> A space $X$ is discrete if and only if no subset of $X$ has a limit point.

## Closed Set
A set $A$ is closed if it contains all its limit points. Formally, $A$ is closed if every limit point of $A$ is in $A$.

- The union of finitely many closed sets is closed
- The intersection of any number of closed sets is closed
- The empty set and closed set are closed

## Open Set
A set $A$ is open if it contains all its interior points. Formally, $A$ is open if every point in $A$ is an interior point of $A$.

- The intersection of finitely many open sets is open
- The union of any number of open sets is open
- The complement of a closed set is open
- The empty set and the whole set are open

## Clopen Set
Perhaps the greatest piece of terminology in mathematics, a clopen set is a set that is both open and closed. In other words, a set $A$ is clopen if it is both open and closed.

Ex. Empty set and the whole set are clopen.

- A set is clopen iff its boundary is empty

## Topology
A topological space is a space in which closeness can be defined but not necessarily measured.

A topology on a set $X$ is a collection of subsets of $X$ that satisfies the following axioms:
- The empty set and the whole set are in the topology
- The intersection of finitely many sets in the topology is in the topology
- The union of any number of sets in the topology is in the topology

Ex.
- Finite subsets of $Z$ don't form a topology since the union of all finite subsets is infinite and not in the topology