## Basic Mapping
<!-- https://apps.dtic.mil/sti/tr/pdf/ADA489598.pdf -->

Let us have a 2D Hilbert space with two complex vectors $a + bi, c + di$.

$$
V = \begin{pmatrix}
a + bi \\
c + di
\end{pmatrix}
= \begin{pmatrix}
r_1 e^{i\phi_1} \\
r_2 e^{i\phi_2}
\end{pmatrix}
$$

To convert this to a point on the Bloch sphere, we first convert it to its polar form and then write it as coefficients of, say, $|0\rangle$ and $|1\rangle$.

$$
|\psi\rangle = r_1 e^{i\phi_1} |0\rangle + r_2 e^{i\phi_2} |1\rangle
$$

We don't care about the exact phase, so we can write $\phi_2$ relative to $\phi_1$ and get rid of $\phi_1$. At the same time, we normalize $r_1$ and $r_2$.

$$
|\psi\rangle = \frac{r_1}{\sqrt{r_1^2 + r_2^2}} |0\rangle + \frac{r_2}{\sqrt{r_1^2 + r_2^2}} e^{i(\phi_2 - \phi_1)} |1\rangle
$$

Normalized $r_1, r_2$ are conveniently angles on a triangle:

$$
|\psi\rangle = \cos(\theta) |0\rangle + e^{i\phi} \sin(\theta) |1\rangle
$$


## Mapping $\mathbb{S}^2$ to the Bloch sphere

### Preliminaries: n-Sphere
Consider a 3-d ball and it's boundary. The boundary is a 2-sphere, denoted by $\mathbb{S}^2$. The 2-sphere is a 2-dimensional manifold embedded in 3-dimensional Euclidean space.

![2-sphere](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7e/Sphere_wireframe_10deg_6r.svg/220px-Sphere_wireframe_10deg_6r.svg.png)

We know we can parametrize this sphere generally as $(x- x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = r^2$, or more generally $\mathbb{S}^2: (x_0 - c_0)^2 + (x_1 - c_1)^2 + (x_2 - c_2)^2 = r^2 \in \mathbb{R}^3$. This is a 2-sphere in 3-d space.

We can go one level up and write $\mathbb{S}^3: \sum_{i=0}^{3} (x_i - c_i)^2 = (x_0 - c_0)^2 + (x_1 - c_1)^2 + (x_2 - c_2)^2 + (x_3 - c_3)^2 = r^2 \in \mathbb{R}^4$. This is a 3-sphere in 4-d space.

### Preliminaries: Quantum States

We we have two vectors say $v,w$ in the Hilbert Space $\mathbb{C}^2$ such that $v = \begin{pmatrix} v_0 \\ v_1 \end{pmatrix}$ and $w = \begin{pmatrix} w_0 \\ w_1 \end{pmatrix}$, such that inner product is defined as $\langle v, w \rangle = v^\dagger w = v_0^* w_0 + v_1^* w_1$.

We define such vectors as quantum states. A pure state as a consequence is when $||v|| = 1$. We tend to write such states with their orthonormal bases $|0\rangle, |1\rangle$ as

$$
|\psi\rangle = \alpha |0\rangle + \beta |1\rangle \because \alpha^2 + \beta^2 = 1
$$


## Mappings

<iframe src="https://q.uiver.app/#q=WzAsMyxbMCwwLCJcXG1hdGhiYntTfcKzIl0sWzMsMiwiXFxtYXRoYmJ7U31eMiJdLFswLDIsIlxcbWF0aGJie0N9UMK5Il0sWzAsMSwiSCJdLFsyLDEsIlMiLDJdLFswLDIsIkUiLDJdXQ==&embed" width="560" height="432" style="border-radius: 8px; border: none;"></iframe>

### $E: \mathbb{S}^3 \rightarrow \mathbb{C}P^1$
We define $\begin{pmatrix}z_1\\ z_2\end{pmatrix} \in \mathbb{S}^3$ also an element of $\mathbb{C}^2$ such that $|z_1|^2 + |z_2|^2 = 1$. Then the image of $\begin{pmatrix}z_1\\ z_2\end{pmatrix}$ in $\mathbb{C}P^1$ under $E$ is $\overline{(z_1/z_2)}$, additionally, since $1/z_2 = \overline{z_2}/|z_2|^2$, and $\overline{\overline{z}} = z$, we write:

$$
E\left( \begin{pmatrix} z_1 \\ z_2 \end{pmatrix} \right) = \overline{z_1}z_2/|z_2|^2
$$,

or equivalently if $z_1 = x_1+iy_1, z_2 = x_2 + iy_2$:

$$
E\left( \begin{pmatrix} x_1 + iy_1 \\ x_2 + iy_2 \end{pmatrix} \right) = \frac{(x_1x_2 + y_1y_2) + i(x_1y_2 - x_2y_1)}{x_2^2 + y_2^2}
$$

Notice, we never get a singularity since $z_1, z_2$ are never simultaneously zero.

### $S: \mathbb{C}P^1 \rightarrow \mathbb{S}^2$
Let $\zeta = a+ib \in \mathbb{C}$, such that $\mathbb{C}$ is the plane $(x, y, 0) \subset \mathbb{R}^3$ (trivially implying that image of $\zeta \in \mathbb{R}^3$ is $(a, b, 0)$). With the north pole as $(0, 0, 1)$, we can now create a stereographic projection from the north pole via a parameterised vector

$$
\vec{V(t)} = (1-t)(0,0,1) + t(a, b, 0), \because t^2a^2 + t^2b^2 + (1-t)^2 = 1
$$

Ignoring trivial solution $t=0$ (north pole itself), we get $t = 1/(1+a^2 + b^2)$, and the image of $\zeta$ on $\mathbb{S}^3$ is $\frac{1}{1+a^2+b^2} (2a,2b,a^2+b^2 -1)$. Conveniently if $\zeta$ is zero we get back the north pole.

### $H: \mathbb{S}^3 \rightarrow \mathbb{S}^3$

Let $w = a+ib$ be the image of $\begin{pmatrix} x_1+iy_1 \\ x_2 + iy_2 \end{pmatrix}$ under $E$, such that $a = \frac{(x_1x_2 + y_1y_2)}{x_2^2 + y_2^2}$ and $b = \frac{(x_1y_2 - x_2y_1)}{x_2^2 + y_2^2}$, such that $a^2+b^2 = \frac{x_1^2+y_1^2}{x_2^2+y_2^2}$.

We can see now $1 + a^2 +b^2 = 1 + \frac{x_1^2+y_1^2}{x_2^2+y_2^2} = \frac{x_2^2 + y_2^2 + x_1^2 + y_1^2}{x_2^2 + y_2^2} = \frac{1}{x_2^2 + y_2^2}$, such that $\begin{pmatrix} x_1+iy_1 \\ x_2 + iy_2 \end{pmatrix} \in \mathbb{S}^3$. Additionally $-1 + a^2 + b^2 = \frac{x_1^2 + y_1^2 - x_2^2 -y_2^2}{x_2^2 + y_2^2}$

Having applied $E$, if we now apply $S$ as seen in the previous section, we get

$$
S(w) = (2(x_1x_2 + y_1y_2), 2(x_1y_2 - x_2y_1), x_1^2 + y_1^2 - x_2^2 - y_2^2)
$$

We can now get therefore a Hopf map

$$
H\left(\begin{pmatrix} x_1+iy_1 \\ x_2 + iy_2 \end{pmatrix}\right) = (2(x_1x_2 + y_1y_2), 2(x_1y_2 - x_2y_1), x_1^2 + y_1^2 - x_2^2 - y_2^2)
$$

Or, using complex notation

$$
H\left(\begin{pmatrix} z_1\\ z_2\end{pmatrix}\right) = (2 Re(\overline{z_1}z_2), 2 Im(\overline{z_1}z_2), |z_1|^2 - |z_2|^2)
$$

We can now complete this by extending this to spherical coordinates, let $|\psi \rangle = \alpha |0\rangle + \beta |1\rangle$, such that $\alpha = r_1 e^{i\phi_1}$ and $\beta = r_2 e^{i\phi_2}$, such that $r_1^2 + r_2^2 = 1$, or it can be remapped to some notation $|\psi\rangle = \cos(\theta) |0\rangle + e^{i\phi} \sin(\theta) |1\rangle$.

We can now write the Hopf map as

$$
\begin{align*}
H\left(\begin{pmatrix} cos(\theta/2) \\ e^{i\phi} \sin(\theta/2) \end{pmatrix}\right) = (
  &2 \cos(\theta/2) \sin(\theta/2) \cos(\phi),\\
  &2 \cos(\theta/2) \sin(\theta/2) \sin(\phi),\\
  &\cos^2(\theta/2) - \sin^2(\theta/2)
)
\end{align*}
$$