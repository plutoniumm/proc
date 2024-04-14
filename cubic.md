## Cardano's method

Consider cubic equation $ax^3 + bx^2 + cx + d = 0$.

We first divide out the $a$ and make a substitution $x = y - \frac{b}{3a}$ to eliminate the $x^2$ term. This gives us

$$
a y^3 + p y + q = 0 \because \\
p = \frac{3ac - b^2}{3a^2}\text{ and }q = \frac{2b^3 - 9abc + 27a^2d}{27a^3}
$$

We now let $y = u + v$ to eliminate the $y^2$ term. This gives us

$$
u^3 + v^3 + (3uv + p)(u + v) + q = 0
$$

This was done effectively to 'complete the cube' and make the equation look like $(u + v)^3 = u^3 + v^3 + 3uv(u + v)$.

We now let $u^3 + v^3 = -q$ if $3uv + p = 0$. This gives us

$$
u^3 + v^3 = -q\text{ and }3uv = -p
$$

This gives us

$$
u^3 + v^3 = -q\text{ and }u^3v^3 = \frac{p^3}{27}
$$

We now solve for $u^3$ and $v^3$ using the quadratic formula. This gives us

$$
u^3 = \frac{-q}{2} + \sqrt{\frac{q^2}{4} + \frac{p^3}{27}}\text{ and }v^3 = \frac{-q}{2} - \sqrt{\frac{q^2}{4} + \frac{p^3}{27}}
$$

We now solve for $u$ and $v$ using the cubic root. This gives us

$$
u = \sqrt[3]{\frac{-q}{2} + \sqrt{\frac{q^2}{4} + \frac{p^3}{27}}}\text{ and }v = \sqrt[3]{\frac{-q}{2} - \sqrt{\frac{q^2}{4} + \frac{p^3}{27}}}
$$

These can be converted back to $y$ and then to $x$ to get the roots of the cubic equation.

## Ferrari's method

Consider a quartic equation $ax^4 + bx^3 + cx^2 + dx + e = 0$.

As above we first divide out the $a$ and make a substitution $x = y - \frac{b}{4a}$ to eliminate the $x^3$ term. This gives us (depressed quartic)

$$
y^4 + py^2 + qy + r = 0
$$

with
- $p = \frac{8ac - 3b^2}{8a^2}$
- $q = \frac{b^3 - 4abc + 8a^2d}{8a^3}$
- $r = \frac{16a^2b^2 - 64abc + 256a^3e}{256a^4}$

We now expand the square on the LHS and add some terms to get

$$
(y^2 + \frac{p}{2})^2 = -qy -r + \frac{p^2}{4}
$$

We will now add $2y^2 m + pm + m^2$ on both sides to get

$$
(y^2 + \frac{p}{2} + m)^2 = -qy -r + \frac{p^2}{4} + 2y^2 m + pm + m^2
$$

Since the value of $m$ is of our choice, we can choose it such that the RHS becomes a perfect square. This gives us the condition on $m$ such that $D = 0$ for RHS

$$
(-q)^2 - 4(2m)(-r + \frac{p^2}{4} + pm + m^2) = 0 \\
\Rightarrow 8m^3 + 8pm^2 + (2p^2 - 8r)m - q^2 = 0
$$

This is now called a resolvant cubic. We can solve this cubic to get the value of $m$. We can then substitute this value of $m$ back into the equation to get the roots of the quartic equation.

This however now gives us an equation of the form $M^2 = N^2$ since RHS is a perfect square which we will rewrite as $(M - N)(M + N) = 0$. This gives us two equations which we can solve to get the roots of each of its constituent quadratics.

$$
(y^2 + \frac{p}{2} + m + \sqrt{2m}y - \frac{q}{2\sqrt{2m}}) = 0\\
\text{and}\\
(y^2 + \frac{p}{2} + m - \sqrt{2m}y + \frac{q}{2\sqrt{2m}}) = 0
$$
