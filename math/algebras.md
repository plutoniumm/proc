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

### Haar Measure
Anything is a Haar measure on any set $G$, as long as it satisfies the following properties:
- $0 \le \mu(U) \le \infty \forall U \in G$
-  $\mu(xE)=\mu(E) \forall x \in G$ and every measurable $E \in G$.

We can measure the size $m(S)$ of a subset $S$ of $\mathbb{R}$ simply by the integral $m(S) = \int_S 1 dx$. If $S = [a,b]$ is an interval, this gives the length $m(S) = b-a$

> Here we can think of that $dx$ as a measure (technically it's not, but I ignore that here)

If $S = [a,b]$ then $m(S) = b-a$. If $S = [a,b) \cup [c,d]$ then $m(S) = b-a + d-c$, which also means if $S = [a+c, b+c]$ then $m(S) = b-a$. We can see that the measure is translation invariant such that $d(x + c) = d(x)$.

What about a multiplicative group of $\mathbb{R}^+$ such that $m(S) = m(cS)$. Then obviously $\int_S 1 dx$ will not fly. So can use $\int_S \frac{dx}{x}$ which is invariant under multiplication, such that $\frac{d(cx)}{cx} = \frac{dx}{x}$.

And therefore $m([a, b]) = \int_{[a,b]} \frac{dx}{x} = \log \frac{b}{a} = \log \frac{cb}{ca} = \int_{[ca, cb]} \frac{dx}{x} = m([ca, cb])$

Consider a complicated example from group of upper triangular matrices

$$
G=\left\{\left(\begin{array}{cc}\sqrt{y}&\frac{x}{\sqrt y}\\0&\frac1{\sqrt{y}}
\end{array}\right)\mid x,y\in\mathbb{R},y>0\right\}.
$$

then for a 'fixed' element $g(r,s)$ in $G$ we have

$$
(g(r,s)g(x,y))^{-1}d(g(r,s)g(x,y))=g(x,y)^{-1}g(r,s)^{-1}g(r,s)dg(x,y)
=g(x,y)^{-1}dg(x,y),
$$

Therefore the measure for $G$ is $d(g) = \frac{dy * dx}{2y}$ for some group operation $(*)$.

Now one may ask a question of what would a Haar-random unitary matrix look like. We would need a 'haar-random' state such that $|\psi_U\rangle = U|\psi_0\rangle$ where $|\psi_0\rangle$ is some reference state. Note that we wish to construct a MEASURE that is invariant under $U$ and not the state itself.

Or equivalently for some observable $O$, $\int dU \langle \psi_U| O|\psi_U\rangle=\int dU \langle \psi_0|U^\dagger OU|\psi_0\rangle$

As a simple example some unitary in $U(1)$ would just be $U = e^{i\theta}$ where $\theta \in [0, 2\pi]$. We now require a measure $d\mu(U) = d\theta$ that is invariant under $U$ i.e. $d(\theta + \theta_0) = d\theta$. Or more generally $d\mu(UU_0) = d\mu(U)$. In general other than for small values of $N$, 'a' Haar measure is non-trivial to construct.

One can thus construct a Haar random unitary $\in U(2)$ as

$$
U(\phi, \theta, \omega) = \begin{pmatrix}
e^{-i(\phi + \omega)/2} \cos(\theta/2) & -e^{i(\phi - \omega)/2} \sin(\theta/2) \\
e^{-i(\phi - \omega)/2} \sin(\theta/2) & e^{i(\phi + \omega)/2} \cos(\theta/2)
\end{pmatrix}
$$

Such that we sample $\phi, \theta, \omega$ from a Haar measure on $[0, 2\pi] \times [0, \pi] \times [0, 2\pi]$.

Process to an equivalent Haar-random matrix $Q$ in $U(n)$ is as follows:
- Generate a random matrix $Z$ with complex numbers $a+bi$ where $a, b \sim \mathcal{N}(0, 1)$
- Compute the QR decomposition $Z = QR$
- Compute the diagonal matrix $\Lambda = \text{diag}(R_{ii}/|R_{ii}|)$
- Compute $Q' = Q\Lambda$ which will be Haar-random

An example of a NON-haar measure is the Dirac measure $\delta_x(A) = 1$ if $x \in A$ and $0$ otherwise if $x \notin A$. Such that $A$ is a subset of $X$. Note that $\delta_x$ is a measure on $X$ and not only on $A$.

$$
\delta _{x}(A)=1_{A}(x)={\begin{cases}
0, &x \not \in A ;\\
1, &x \in A.
\end{cases}}
$$

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