[[1 - game idea]] <- back
[[3 - physics engine code]] <- next

---
# constraints
1) game is 2D: x dimension and y dimension


# properties of character particle
character particle will have following properties:
$$
character = (E_{kinetic}, \vec{r(t)}, \vec{v(t)}, m)
$$
- $E_{kinetic}$ is the kinetic energy of the character at time t.
- $\vec{r(t)}$ is the position vector of the character at time t.
- $\vec{v(t)}$ is the velocity vector of the character at time t.
- m is the mass, in kg, of the character.

# mathematics for kinematics
$$
\vec{r(t)} = r_x(t)\hat{i} + r_y(t)\hat{j}
$$
- $r_x(t) = x_0 + v_{x_{0}}t + \frac{1}{2}a_xt^2$
- $r_y(t) = y_0 + v_{y_{0}}t + \frac{1}{2}a_yt^2$

Let $arrow_{right} = 5\frac{m}{s^2}$
- if $arrow_{right}$ pressed for $t$ seconds, $a_x = 5\frac{m}{s^2}$ for $t$ seconds.

Let $arrow_{left}$ = $-arrow_{right}$
- If $arrow_{left}$ pressed for t seconds, $a_x$ = $-5\frac{m}{s^2}$ for t seconds.

When no horizontal arrow is pressed, resistive force, from friction, acts on player decreasing velocity 0 in t time.
- Use stopping time of character.
$friction =$ undefined for now

Let $arrow_{up}$ = $5\frac{m}{s^2}$
- If $arrow_{up}$ pressed for t seconds, $a_{y} = 5\frac{m}{s^2}$ for t seconds.

Let $arrow_{down}$ = -$(arrow_{up} + |g|)$ 
- $g = -9.8\frac{m}{s^2}$
- If $arrow_{down}$ pressed for t seconds, $a_{y} = -(5\frac{m}{s^2}+9.8\frac{m}{s^2})$

If no vertical arrow is pressed, gravity, g, is exerted on player until their vertical velocity is at rest due to landing on a surface with collision enabled.

$$
\vec{v(t)} = \frac{dr_{x}(t)}{dt}\hat{i} + \frac{dr_{y}(t)}{dt}\hat{j}
$$
$$
\vec{v(t)}=\frac{d}{dt}\biggr[x_{0}+v_{x_{0}}t + \frac{1}{2}a_xt^2\biggr]\hat{i} + \frac{d}{dt}\biggr[x_{0}+v_{x_{0}}t + \frac{1}{2}a_xt^2\biggr]
$$
$$
\vec{v(t)}= (v_{x_{0}}+a_{x}t)\hat{i}+(v_{y_{0}}+a_{y}t)\hat{j}
$$

$$
\vec{v(t)}=v_x(t)\hat{i}+v_y(t)\hat{j}
$$
- $v_{x}(t)=v_{x_{0}}+a_{x}t$
- $v_{y}(t)=v_{y_{0}}+a_{y}t$

# mathematics for energy
Recall...
- $E_{kinetic}$ is the current kinetic energy of the character particle at time t.
- m is the mass of the character particle.
- $\vec{v(t)}$ is the velocity vector of the character particle at time t.

$$
E_{kinetic} = \frac{1}{2}m|\vec{v(t)}|
$$

# mathematics for deflection and bouncing
$$
\vec{v(t)}=v_{x}(t)\hat{i}+v_{y}(t)\hat{j}
$$
Based on angle of current velocity, $\vec{v(t)}_{i}$, update $\vec{v(t)}_{i+1}$

$$
\theta = tan^{-1}\biggr(\frac{v_{y}(t)}{v_{x}(t)}\biggr)
$$
- if $v_{x}(t) < 0$ and $v_{y}(t) > 0$, $\vec{v(t)}$ in quadrant 2.
		$\theta_{true} = 180\degree - \theta$
- if $v_{x}(t) < 0$ and $v_{y}(t) < 0$, $\vec{v(t)}$ in quadrant 3.
		$\theta_{true} = \theta - 180\degree$

If character hits a surface perpendicular to it...
- Continue in current direction, cause a bounce.

If character hits a wall, deflect character by 180 degrees.

When a collision occurs, $|\vec{v(t)}|$ decreases.
- $|\vec{v(t)}_{i+1}| < |\vec{v(t)}_{i}| \Rightarrow KE_{i+1} < KE_{i}$

