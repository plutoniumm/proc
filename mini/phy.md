## Equal Temperament
All instruments are just slightly but equally, out of tune.

<iframe src="https://www.youtube-nocookie.com/embed/1Hqm0dYKUx4" title="Why It&#39;s Impossible to Tune a Piano" frameborder="0" allowfullscreen></iframe>

### Pythagorean Tuning and Comma
Pytho says you can tune a system of notes by fifths. So if 2, written as 2/1 (say 440 Hz) and 1/1 (then 220 Hz) exist, a fifth would be 3/2 (330 Hz). This is a perfect fifth.

We can then use a system to of $(3/2)^n$ to create a new system, and everytime we exceed 2 we can divide by 2 to get back into the 1-2 range. This is the Pythagorean tuning system. The problem however is that $(3/2)^12 \approx 2^7$, so we are off by a VERY VERY small factor thus making some notes sound horrendous. This of 129.74 and 128 is the Pythagorean comma.

## The Disease
- Babson creates anti-gravity stones across the country
- Tuft's anti-gravity stone and they end with, "...gravity and how it may be controlled"
- Babson & Baneson (money)
- Babson created Gravity Research Foundation (New Hampshire). He made Glen Martin (pre-cursor to Lockheed Martin) to hire Lois Witten

- Lois Witten created Research Institute for Advanced Study (RIAS) whose alumni include:
  - Solomon Lifschitz
  - Rudolf Kalman
  - Sheldon Glashow
- We almost pretend like this didn't happen.
- In 1973 the Mansfield Amendment was passed which made it ended military funding for Blue Sky research. (Blue Sky research means, do whatever you want we don't care. this is what made america the envy of the world. After Sputnik, they had wanted the best of the best in Academia.)

- In 1965, Ghislane Maxwell's father Robert Maxwell introduced into academia the idea of 'Peer Review' which ultimately created the 'Publish or Perish' culture.
- He realised any complete library of a university will have subscribe to all journals. So he just increased the number of journals and jacked up the prices. And then since we didn't have enough editors, he created the idea of 'Peer Review' which is just a way to get free labour.
- We now use govt money to do research and give it to journals after doing free peer review who then just sell our work back to us.

## Four Vector Potential
A representation for electric scalar potential and magnetic vector potential is a relativistic vector function from which we can derive the EM field.

Let,
$$
B = \nabla \times A\\
\text{and}\\
E = -\nabla \phi - \frac{\partial A}{\partial t}
$$

Let us then define $A_\mu$ as

$$
A_\mu = (A_x, A_y, A_z, i\phi/c)
$$

We know now that we can write Maxwell's equations as

$$
\Box^2 A = -\mu_0 J \text{ and } \Box^2 \phi = -\frac{\rho}{\epsilon_0}\\
\text{such that},
\Box^2 = \nabla^2 - \frac{1}{c^2} \frac{\partial^2}{\partial t^2}
$$

Note: Each $A \rightarrow (A_x, A_y, A_z)$ and therefore each $J \rightarrow (J_x, J_y, J_z)$

We can then convert the scalar into a part of the vector potential as:

$$
\Box^2 \phi * \frac{i}{c} = -\frac{\rho}{\epsilon_0} * \frac{i}{c} \\
= - \frac{ic\rho}{\epsilon_0 c} \\
= -\frac{J_4}{1/\mu_0} \text{ where } J_4 = ic\rho
$$

Therefore, we can write the four vector potential as $\Box^2 A = -\mu_0 J$. We write it this way because the operator $\Box^2$ is a Lorentz invariant operator. This means it is invariant under Lorentz transformations (any linear transformation that preserves the spacetime interval). Additionally $\Box^2 = \Box'^2$.

So we then apply the transformation $A_\mu \rightarrow \partial_{\mu\nu} A_\nu$ to change from one frame to another. Let's now write the four vector potential as:

$$
\begin{pmatrix}
A_1'\\ A_2'\\ A_3'\\ A_4'
\end{pmatrix}
= \begin{pmatrix}
\gamma & 0 & 0 & i\gamma\beta\\
0 & 1 & 0 & 0\\
0 & 0 & 1 & 0\\
-i\gamma\beta & 0 & 0 & \gamma
\end{pmatrix}
\begin{pmatrix}
A_1\\ A_2\\ A_3\\ A_4
\end{pmatrix}
$$

## Aharonov-Bohm Effect
We know mathematically $\nabla \times \nabla \cdot X = 0$ for any vector field $X$. This means that the magnetic field is zero $\nabla \times B = 0$ means we can also write $B = \nabla \times A$ where $A$ is the vector potential.

This implies that in a field where even if the magnetic field is zero, the vector potential is not zero and the phase of the wavefunction is affected by the vector potential. So even as two beams of light approach a solenoid, the phase of the wavefunction is affected by the vector potential.

This general implies that potential is a more fundamental quantity than the field itself since $\text{unique }A \implies \text{unique }B$ but not the other way around.