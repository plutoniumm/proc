## Affine Transform

An affine transformation is a linear mapping method that preserves points, straight lines, and planes. Sets of parallel lines remain parallel after an affine transformation. From the below image we can see that in an affine transformation $Ax + b$ on $x$.

![Affine manipulation](https://i.imgur.com/stV4DUq.png)


$$
X \rightarrow
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
X
+
\begin{bmatrix}
e \\
f
\end{bmatrix}
$$


Then
- $a$ represents horizontal scaling
- $b$ represents horizontal skewing
- $c$ represents vertical skewing
- $d$ represents vertical scaling
- $e$ represents horizontal translation
- $f$ represents vertical translation

Rotations are technically done as a combination of sheering. So if we sheer'd -0.38 in $b$ and 0.38 in $c$ we would get a net rotation which is just slightly larger than the original image (so we scale down by a bit). That just works out to be the rotation matrix.

$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix} =
\begin{bmatrix}
cos(\theta) & -sin(\theta) \\
sin(\theta) & cos(\theta)
\end{bmatrix}
$$

While these are all 2D in practice it is more common to write Affine transforms in $n+1$D, so we tend to write the rotation matrix as

$$
\begin{bmatrix}
cos(\theta) & -sin(\theta) & 0 \\
sin(\theta) & cos(\theta) & 0 \\
0 & 0 & 1
\end{bmatrix}
$$

Where as before the first to terms $0,0$ are in fact sheers in Z which we just ignore.

## Million Dollar Problems (in simple terms)
### P vs NP
**Barebones**:
There are two kinds of problems:
- P: Problems that can be solved in polynomial time
- NP: Problems that can be CHECKED in polynomial time (but not necessarily solved in polynomial time)

The question is: Are these two classes the same? That is, can problems that can be checked in polynomial time also be solved in polynomial time?

**Slighly more detail**:
- P: Problems that can be solved in polynomial time
- NP-Complete: Problems that are at least as hard as the hardest problems in NP
- BPP: Problems that can be solved in polynomial time with a small probability of error via randomization
- BQP: Problems that can be solved in polynomial time with a quantum computer
- NP: Problems that can be checked in polynomial time
- NP-Hard: Problems that are at least as hard as the hardest problems in NP
- PCP: Problems that can be checked in polynomial time with a small probability of error

### Riemann Hypothesis
We define a sum on integers as

$$
\zeta(s) = \sum_{n=1}^{\infty} \frac{1}{n^s} \because s \in \mathbb{C}
$$

This function zeros out on many points in the complex plane. The Riemann Hypothesis states that all non-trivial zeros of the Riemann zeta function have a real part of 1/2 i.e of form $s = 1/2 + it$ where $t \in \mathbb{R}$.

### Poincare Conjecture [SOLVED]

A sphere is defined as a set of points equidistant from a center point in some n-dimensions. The Poincare Conjecture states that a 3D sphere is the only 3D shape with no holes (every other object can be deformed into a sphere).

### Navier–Stokes existence and smoothness

The fluid dynamics equations are a set of equations that describe the flow of fluids.

$$
\rho \frac{Du}{Dt} = -\nabla p + \nabla \cdot \tau + f
$$

or in simple words

$$
\text{Inertia} = \text{Pressure} + \text{Viscous forces} + \text{External forces}
$$

The Navier-Stokes existence and smoothness problem is to prove that solutions to the Navier-Stokes equations exist and are smooth in 3D.

### Birch and Swinnerton-Dyer Conjecture

### Hodge Conjecture

### Yang–Mills existence and mass gap
Mass Gap: A mass gap is the difference in energy between the ground state and the first excited state in a quantum field theory. This is generally considered to be 'a particle' in the theory.

---