# Manifolds and Lie Groups

## Manifolds
A manifold is a topological space that locally resembles (homeomorphic) Euclidean space. Where, locally homeomorphic $\implies$ every point has a neighborhood homeomorphic to an open subset of the Euclidean space $R^n, \forall n \in \mathbb{N}$.

A manifold is differentiable if it is locally a vector space. Some good examples are: $R^n$, the sphere $S^n$, the spacetime, some mesh from say CFD software, Lie groups, etc.

## Chart
A chart $(U, \phi)$ on $M$ consists of an open subset $U$ of $M$, and a homeomorphism $\phi$ from $U$ to an open subset of some Euclidean space $R^n$

## Dual Space
If $V$ is a vector space on Field $F$, then the dual space $V^*$ is the set of all linear maps from $V$ to $F$. The dual space is also a vector space on $F$.


## Bundles and Tangents
### Fiber Bundle
Imagine a circle with a line growing out vertically from each point on it. The circle it the base space, the lines are the fibers, and the whole structure is a fiber bundle therefore creating a new Total Space which is a cylinder.

We can also take the same circle and make fibers grow out to come and meet back on the other side (each fiber itself being a circle). Here we made a total space that is a torus.

Now imagine a line where we made the fibers grow out to meet back on the other side. circular strip. BUT, if we were to give each fiber a little twist before joining them back, we would get a Mobius strip.

### Vector Bundle
Consider a topological space $X$ and a total space $E$ such that there exists a continuous surjection $\pi: E \to X$, such that $\forall x \in X$, the fiber $\pi^{-1}(x)$ is a vector space. Then $E$ is a vector bundle over $X$.

### Tangent Space
The tangent space $T_pM$ at a point $p$ on a manifold $M$ is the vector space of all derivations at $p$. For a sphere then, at some point $p$, the tangent space is the plane tangent to the sphere at $p$.

The motivation for a tangent space is such. Since differentiation only relies on the behaviour of a function around a point, there are no issues caused by the fact that the manifold is only locally Euclidean. So since on an arbitrary manifold, absolute 'coordinates' may be inherently meaningless, like say a sphere, we can still define a tangent space at each point.

This tangent space makes 'directional movement' on the manifold possible by defining tangent space as a set of all possible directions at a point and the derivative of a function at that point as the rate of change of the function in that direction.

### Tangent Bundle
The tangent bundle $TM$ of a manifold $M$ is the disjoint union of the tangent spaces $T_pM$ at each point $p$ in $M$. The tangent bundle itself reconstructs the manifold

### Cotangent Bundle
The cotangent bundle $T^*M$ of a manifold $M$ is the disjoint union of the cotangent spaces $T^*_pM$ at each point $p$ in $M$. The cotangent bundle is the dual space of the tangent bundle.

### Hopf Fibration
If we have a 2-sphere $S^2$ such that $x^2 + y^2 + z^2 = 1$, and we write that in polar as $x = \sin(\theta)\cos(\phi)$, $y = \sin(\theta)\sin(\phi)$, $z = \cos(\theta)$, then we can define the $F(\alpha) = (X_0, X_1, X_2, X_3) \in \mathbb{R}^4$ as

$$
X_0 = \cos(\frac{\alpha + \phi}{2})\sin(\theta/2) \\
X_1 = \sin(\frac{\alpha + \phi}{2})\sin(\theta/2) \\
X_2 = \cos(\frac{\alpha - \phi}{2})\cos(\theta/2) \\
X_3 = \sin(\frac{\alpha - \phi}{2})\cos(\theta/2)
$$

where $\alpha$ is a parameter in the 4d space which sweeps out the 2-sphere. This is the Hopf Fibration.

### Metric Tensor
For the pythogoras thm $ds^2 = dx^2 + dy^2$, we can write this as $ds^2 = g_{ij}dx^idx^j$ where $g_{ij}$ is the metric tensor. The metric tensor is a symmetric positive definite tensor field that defines the inner product of the tangent space at each point on the manifold.

For a euclidean space, the metric tensor is the identity matrix. Which when put together gives us $ds^2 = 1dx.dx + 0dx.dy + 0dy.dx + 1dy.dy = dx^2 + dy^2$. Or on the surface of a sphere the metrix tensor is $ds^2 = 1R^2d\theta^2 + R^2\cos^2(\theta).d\phi^2 + 0d\theta.d\phi + 0d\phi.d\theta$.

For an arbitrary manifold, the metric tensor is a matrix that varies from point to point. An example of this in use are the Christoffel symbols where we write the symbol as a function of the change in the metric tensor.

### Pseudo-Riemannian Manifold
A pseudo-Riemannian manifold is a manifold with a metric tensor may not be positive definite. This is useful in general relativity where the metric tensor is used to describe the curvature of spacetime.

### Reimannian Metric
When we make the tangent space $T_pM$ for a given manifold $M$, it may not come equipped with it's own metric, making it difficult to define the length of a vector. A Riemannian metric is a smooth assignment of an inner product to each tangent space that varies smoothly from point to point.

### Covariant Derivative
The covariant derivative measures how one tensor field changes in the direction of a vector field while also taking the curvature of the underlying space into account. In coordinates, this means that we compute the directional derivative as in flat space but we now also have extra terms (i.e. the Christoffel symbols) that tell us how the basis vectors change. More precisely

for some vector $v$ on metric $g$, let's say we were to change the coordinates to some new system $X$ (from $x$), then how do we get the new vector, $V = v \frac{dX}{dx}$. But this is incorrect since $V$ cannot vary. So we add an extra term to the derivative to create a new covariant derivative

$$
\nabla_v = \frac{d}{dX} + G^{-1} \frac{dG}{dX}
$$

Where we can see $\nabla_v G = 0$ since now the derivative accounts for the variation of the metric itself too. More generally we write

$$
\nabla_a v^b = \partial_a v^b + \Gamma^b_{ac}v^c
$$

By virtue of the fact that the correction factor is a log derivative, we can linearize even multiplicative changes in the metric tensor.


## Connections
A connection generalises the idea of 'transporting' local geometric structures along some manifold.

### Affine Connection
On a surface of a ball let's say, it's the idea of moving the tangent space PARALLEL to the ball's surface. So a plate touching the ball at a point, and then moving it parallel to the surface