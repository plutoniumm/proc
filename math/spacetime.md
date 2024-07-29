### Lie Bracket
A lie bracket is an operator that assigns to any two vector fields $X$ and $Y$ on a smooth manifold $M$ a new vector field $[X, Y]$ such that the following properties hold:

1. Bilinearity: $[fX + gY, Z] = f[X, Z] + g[Y, Z]$
2. Antisymmetry: $[X, Y] = -[Y, X]$
3. Jacobi Identity: $[X, [Y, Z]] + [Y, [Z, X]] + [Z, [X, Y]] = 0$

It's sometimes written as $\mathcal{L}_X Y$ where $\mathcal{L}_X$ is the Lie derivative along $X$, which is interpreted as the derivative of $Y$ along the flow of $X$.

If a fisherman and float are flowing along a vector field $X$, then if the fisherman moves/turns the fishing rod per the field $Y$, then the Lie bracket $[X, Y]$ is the dragging that the float experiences relative to the water.

### Levi-Civita Connection
Any affine connection is called a Levi-Civita connection if:

1. It is torsion-free: $\nabla_X Y - \nabla_Y X = [X, Y]$ (symmetry condition)
2. It preserves the metric: $\nabla g = 0$ (compatibility condition)

> **Every pseudo-Riemannian manifold $(M, g)$ has a unique Levi-Civita connection $\nabla$**.

The problem with using just the metric tensor is, let's say when converting from cartesian to polar. The metric tensor only tells us how each component scales. It gives us no information about the rotation of the bases in the tangent space. The connection gives us this information.

So our transformation metric tensor would be $g_{r\theta} = [1, 0; 0, r^2]$ and the connection would be $\Delta_r e_\theta = \Delta_\theta e_r$ for some basis vectors $e_r$ and $e_\theta$. So everytime we move along the $r$ direction, we have to rotate the basis vectors by $\Delta_\theta$.

So for 2 basis vectors $e_r, e_\theta$, and two co-ordinate directions in which they can be transported, we need 4 derivatives to describe the change EACH of which have 2 components.

$$
\frac{\partial e_r}{\partial r} = \langle \Gamma^r_{rr}, \Gamma^\theta_{rr}\rangle \\
\frac{\partial e_r}{\partial \theta} = \langle \Gamma^r_{r\theta}, \Gamma^\theta_{r\theta}\rangle \\
\frac{\partial e_\theta}{\partial r} = \langle \Gamma^r_{\theta r}, \Gamma^\theta_{\theta r}\rangle \\
\frac{\partial e_\theta}{\partial \theta} = \langle \Gamma^r_{\theta\theta}, \Gamma^\theta_{\theta\theta}\rangle
$$

These 8 components are the Christoffel symbols.