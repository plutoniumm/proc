## Lagrangian Method

Let there exist a particle of $m$, at $x$.

A lagrangian is normally defined as $L = T - V$, which here would be applied as

$$L = \frac{1}{2}m (\frac{dx}{dt})^2 - V(x)$$

Let's say this particle moves from some $(x_i, t_i)$ to $(x_f, t_f)$. Then what trajectory would it take? We define the action as

$$S = \int_{t_i}^{t_f} L dt$$

For any PATH connecting $(x_i, t_i)$ to $(x_f, t_f)$, the action is a number describing the path. The Principle of Least Action (PoLA) states that the path taken by the particle is the one that minimizes the action. This is a very powerful principle, and is the basis of the Lagrangian method.

Considering that a small change in a function $df = \frac{df}{dx} dx = f'(x) \epsilon$, for some small purturbation $\epsilon$. Similarly in action since we were looking for a path x(t) that minimizes the action, we now look for a path $x(t) + \epsilon(t)$ that minimizes the action. Here $\epsilon(t)$ is a small function that adds small wiggles to the path.

So HERE

$$
dL = m \frac{dx}{dt} \frac{d\epsilon}{dt} - \frac{dV}{dx} \epsilon
$$

We use IBP to get a new notation for the first term here as

$$
m \frac{dx}{dt} \frac{d\epsilon}{dt} = m \frac{d^2x}{dt^2} \epsilon + \frac{d}{dt} (m \frac{dx}{dt}) \epsilon
$$

So the first term in $dL$ becomes

$$
dL = m \frac{d^2x}{dt^2} \epsilon + \frac{d}{dt} (m \frac{dx}{dt}) \epsilon - \frac{dV}{dx} \epsilon \\
= \epsilon (m \frac{d^2x}{dt^2} + \frac{d}{dt} (m \frac{dx}{dt}) - \frac{dV}{dx})
$$

So now to get the change in the action

$$
dS = \int_{t_i}^{t_f} dL dt = \int_{t_i}^{t_f} \epsilon (m \frac{d^2x}{dt^2} + \frac{d}{dt} (m \frac{dx}{dt}) - \frac{dV}{dx}) dt
$$

We can easily see that since we want $\epsilon$ to VANISH at the end points, the 2nd term in the integrand vanishes. So we are left with

$$
dS = \int_{t_i}^{t_f} \epsilon (m \frac{d^2x}{dt^2} - \frac{dV}{dx}) dt
$$

Where $dS = 0$ for all $\epsilon$ implies that the integrand must vanish. This gives us that the terms should cancel each other out giving us

$$
- \frac{dV}{dx}  = m \frac{d^2x}{dt^2} = \quad \text{or}\\
F = ma
$$


## Applied to Field Theory
In field theory the basic building block is no longer $x(t)$ but some field $\phi(x, t)$ which assigns a number to every point in space and time. The action is now defined as

$$
S = \int_{t_i}^{t_f} dt\ L
$$

The small change here is now that $L$ has infinite degrees of freedom, we require it to be "local" which means that it should be a function of $\phi(x, t)$ and its derivatives at that point. This is the principle of locality.

Or,

$$
L = \int dx\ \mathcal{L}(\phi, \frac{\partial \phi}{\partial x}, \frac{\partial \phi}{\partial t})
$$

where $\mathcal{L}$ is the Lagrangian density. So, now to convert K, V as before

$$
K = \frac{1}{2} m (\frac{dx}{dt})^2 \rightarrow \mathcal{K} = \frac{1}{2c^2} (\frac{\partial \phi}{\partial t})^2
$$

Notice how $c$ is here first to make sure units are correct, 2nd to make sure we're consistent with GTOR. We also don't have a mass here since the field doesn't have a mass. NORMALLY in particle physics we choose $V$ best such that it describes are systems, and that holds true here.

Let's say we want to be consistent with GTOR, so if there exists a terms which is of the form $(\frac{\partial \phi}{\partial t})^2$ there should also exist a term of the form $(\frac{\partial \phi}{\partial x})^2$. This is sometimes called the "Gradient Energy".

Normally there will also be y, z terms but for sake of simplicity we'll ignore them. The rest of the potential energy depends upon the exact system we're looking at. Here we'll consider a simple scalar field theory, so we'll have a potential energy of the form

$$
V = \frac{1}{2} \kappa^2 \phi^2
$$

So the Lagrangian density for this system would be

$$
\mathcal{L} = \frac{1}{2c^2} (\frac{\partial \phi}{\partial t})^2 - \frac{1}{2} (\frac{\partial \phi}{\partial x})^2 - \frac{1}{2} \kappa^2 \phi^2
$$

## Klein-Gordon Equation
The above equation is the Klein-Gordon equation. Notice how very conveniently if the '-' sign in the potential energy was a '+' sign, we'd have the Energy density of the field.

We will now apply principle of least action to this system. We will consider a small perturbation $\epsilon(x, t)$ to the field $\phi(x, t)$ and see how the action changes. We will then require the action to be minimized for all $\epsilon(x, t)$ or, as mentioned before, we require

$$
dS = \int_{t_i}^{t_f} dt\ \int dx\ d\mathcal{L} = 0
$$

We can see

$$
d\mathcal{L} = -\frac{1}{c^2} \frac{\partial\phi}{\partial t} \frac{\partial \epsilon}{\partial t} - \frac{\partial \phi}{\partial x} \frac{\partial \epsilon}{\partial x} - \kappa^2 \phi \epsilon
$$

We can then apply the same IBP trick twice as before to get (leaving out some terms because they vanish after integration over spacetime)

$$
d\mathcal{L} = \epsilon (-\frac{1}{c^2} \frac{\partial^2\phi}{\partial t^2} + \frac{\partial^2 \phi}{\partial x^2} - \kappa^2 \phi)
$$

Putting this in $dS$ we can easily see

$$
\kappa^2 \phi = - \frac{1}{c^2} \frac{\partial^2\phi}{\partial t^2} + \frac{\partial^2 \phi}{\partial x^2}
$$

MOTHER OF GOD.

We can see that, as long as $\omega^2/c^2 - k^2 = \kappa^2$, the plane wave of form $A e^{i(kx - \omega t)}$ is a solution to this equation.

Applying this to quantum theory, we know each wave is a particle, so with $\psi(x, t) \propto e^{i(px - E t)/\hbar}$ as long as m.n$E^2 = p^2 c^2 + m^2 c^4$ such that $m = \hbar \kappa/c$.

## Some other systems
**Spin 1/2**: Dirac Lagrangian

$$
\mathcal{L} = i \sum_\mu \bar{\Psi} \gamma^\mu \frac{\partial \Psi}{\partial x^\mu} - m \bar{\Psi} \Psi
$$

with equation of motion being

$$
i \sum_\mu \gamma^\mu \frac{\partial \Psi}{\partial x^\mu} = m \Psi
$$

**Spin 1**: Maxwell Lagrangian

$$
\mathcal{L} = -\frac{1}{4} \sum_{\mu,\nu} F_{\mu\nu} F^{\mu\nu}
$$

with equation of motion being

$$
\sum_\nu \frac{\partial F^{\mu\nu}}{\partial x^\nu} = 0
$$

**Spin 2**: Einstein-Hilbert Lagrangian

$$
\mathcal{L} = \frac{1}{16\pi G} \sum_{\mu\nu} g^{\mu\nu} R_{\mu\nu}
$$

with equation of motion being

$$
R_{\mu\nu} = 0
$$